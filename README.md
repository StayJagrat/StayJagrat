:root {
    --bg-base: #020617;
    --bg-panel: rgba(15, 23, 42, 0.6);
    --border-color: rgba(56, 189, 248, 0.15);
    --text-main: #F8FAFC;
    --text-muted: #94A3B8;
    
    --neon-cyan: #06B6D4;
    --neon-pink: #EC4899;
    --neon-purple: #8B5CF6;
    
    --glass-blur: blur(16px);
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Outfit', sans-serif;
    background-color: var(--bg-base);
    color: var(--text-main);
    overflow: hidden; /* Dashboard is a fixed full-screen app */
}

/* Ambient animated background */
.glow-bg {
    position: fixed;
    width: 100vw;
    height: 100vh;
    z-index: -1;
    background: 
        radial-gradient(circle at 15% 50%, rgba(6, 182, 212, 0.08) 0%, transparent 40%),
        radial-gradient(circle at 85% 30%, rgba(236, 72, 153, 0.08) 0%, transparent 40%);
    animation: pulse-bg 8s ease-in-out infinite alternate;
}

@keyframes pulse-bg {
    0% { transform: scale(1); opacity: 0.8; }
    100% { transform: scale(1.1); opacity: 1; }
}

/* App Layout */
.dashboard-layout {
    display: flex;
    height: 100vh;
    width: 100vw;
}

/* Sidebar */
.sidebar {
    width: 260px;
    background: var(--bg-panel);
    border-right: 1px solid var(--border-color);
    backdrop-filter: var(--glass-blur);
    -webkit-backdrop-filter: var(--glass-blur);
    display: flex;
    flex-direction: column;
    padding: 1.5rem;
    z-index: 10;
}

.brand {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 3rem;
}

.brand-icon {
    width: 32px;
    height: 32px;
    background: linear-gradient(135deg, var(--neon-cyan), var(--neon-purple));
    border-radius: 8px;
    box-shadow: 0 0 15px rgba(6, 182, 212, 0.5);
    position: relative;
}

.brand-icon::after {
    content: '';
    position: absolute;
    inset: 4px;
    background: var(--bg-base);
    border-radius: 4px;
}

.brand h2 {
    font-weight: 700;
    letter-spacing: 1px;
    text-transform: uppercase;
    background: linear-gradient(to right, #fff, var(--neon-cyan));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.side-nav {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    flex: 1;
}

.nav-item {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 0.8rem 1rem;
    color: var(--text-muted);
    text-decoration: none;
    border-radius: 8px;
    transition: all 0.3s ease;
    font-weight: 500;
    position: relative;
    overflow: hidden;
}

.nav-item:hover {
    color: var(--text-main);
    background: rgba(255,255,255,0.03);
}

.nav-item.active {
    color: var(--neon-cyan);
    background: rgba(6, 182, 212, 0.1);
    border: 1px solid rgba(6, 182, 212, 0.2);
}

.nav-item.active::before {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    height: 100%;
    width: 3px;
    background: var(--neon-cyan);
    box-shadow: 0 0 10px var(--neon-cyan);
}

.sidebar-footer {
    padding-top: 1.5rem;
    border-top: 1px solid var(--border-color);
}

.user-profile {
    display: flex;
    align-items: center;
    gap: 12px;
}

.avatar {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    background: url('https://ui-avatars.com/api/?name=Admin&background=0D8ABC&color=fff') center/cover;
    border: 2px solid var(--neon-cyan);
    box-shadow: 0 0 10px rgba(6, 182, 212, 0.3);
}

.user-info h4 { font-size: 0.9rem; }
.user-info p { font-size: 0.75rem; color: var(--neon-pink); }

/* Main Content */
.main-content {
    flex: 1;
    display: flex;
    flex-direction: column;
    padding: 1.5rem 2rem;
    overflow-y: auto;
}

.top-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 2rem;
}

.search-bar {
    background: var(--bg-panel);
    border: 1px solid var(--border-color);
    border-radius: 100px;
    padding: 0.6rem 1.5rem;
    display: flex;
    align-items: center;
    gap: 10px;
    width: 300px;
    backdrop-filter: var(--glass-blur);
    transition: box-shadow 0.3s ease;
}

.search-bar:focus-within {
    box-shadow: 0 0 15px rgba(6, 182, 212, 0.2);
    border-color: var(--neon-cyan);
}

.search-bar input {
    background: none;
    border: none;
    color: var(--text-main);
    outline: none;
    width: 100%;
    font-family: inherit;
}

.header-actions {
    display: flex;
    align-items: center;
    gap: 1rem;
}

.icon-btn {
    background: var(--bg-panel);
    border: 1px solid var(--border-color);
    color: var(--text-main);
    width: 40px;
    height: 40px;
    border-radius: 50%;
    cursor: pointer;
    position: relative;
    transition: all 0.3s;
}

.icon-btn:hover {
    background: rgba(255,255,255,0.05);
}

.badge {
    position: absolute;
    top: -2px; right: -2px;
    width: 10px; height: 10px;
    background: var(--neon-pink);
    border-radius: 50%;
    box-shadow: 0 0 10px var(--neon-pink);
}

.btn-glow {
    background: transparent;
    color: var(--neon-cyan);
    border: 1px solid var(--neon-cyan);
    padding: 0.6rem 1.5rem;
    border-radius: 8px;
    font-weight: 600;
    cursor: pointer;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-size: 0.8rem;
    transition: all 0.3s ease;
    box-shadow: inset 0 0 10px rgba(6, 182, 212, 0.1), 0 0 10px rgba(6, 182, 212, 0.1);
}

.btn-glow:hover {
    background: rgba(6, 182, 212, 0.1);
    box-shadow: inset 0 0 15px rgba(6, 182, 212, 0.3), 0 0 15px rgba(6, 182, 212, 0.3);
    text-shadow: 0 0 5px var(--neon-cyan);
}

/* Dashboard Grid (Bento Box) */
.dashboard-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: auto auto;
    gap: 1.5rem;
}

.card {
    background: var(--bg-panel);
    border: 1px solid var(--border-color);
    border-radius: 16px;
    padding: 1.5rem;
    backdrop-filter: var(--glass-blur);
    -webkit-backdrop-filter: var(--glass-blur);
    transition: transform 0.3s ease, border-color 0.3s ease;
}

.pulse-hover:hover {
    transform: translateY(-5px);
    border-color: rgba(255,255,255,0.1);
}

.card-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
}

.card-header h3 {
    font-size: 1rem;
    font-weight: 500;
    color: var(--text-muted);
}

.trend {
    font-size: 0.8rem;
    font-weight: 600;
    padding: 2px 8px;
    border-radius: 100px;
}
.trend.up { background: rgba(16, 185, 129, 0.1); color: #10B981; }
.trend.down { background: rgba(236, 72, 153, 0.1); color: var(--neon-pink); }

.stat-value {
    font-size: 2.5rem;
    font-weight: 700;
    margin-bottom: 1rem;
}
.unit { font-size: 1rem; color: var(--text-muted); font-weight: 400; }

.progress-container {
    height: 6px;
    background: rgba(255,255,255,0.05);
    border-radius: 100px;
    overflow: hidden;
}

.progress-bar {
    height: 100%;
    border-radius: 100px;
    animation: fill-bar 1.5s ease-out forwards;
    transform-origin: left;
}

@keyframes fill-bar {
    from { transform: scaleX(0); }
    to { transform: scaleX(1); }
}

.cyan-glow { background: var(--neon-cyan); box-shadow: 0 0 10px var(--neon-cyan); }
.pink-glow { background: var(--neon-pink); box-shadow: 0 0 10px var(--neon-pink); }
.purple-glow { background: var(--neon-purple); box-shadow: 0 0 10px var(--neon-purple); }

/* Large Chart Card */
.large-card.span-2 {
    grid-column: span 2;
}

.controls button {
    background: none;
    border: 1px solid var(--border-color);
    color: var(--text-muted);
    padding: 4px 12px;
    border-radius: 4px;
    cursor: pointer;
    font-size: 0.8rem;
    transition: all 0.2s;
}
.controls button.active {
    background: rgba(6, 182, 212, 0.2);
    color: var(--neon-cyan);
    border-color: var(--neon-cyan);
}

.chart-container {
    height: 250px;
    width: 100%;
    margin-top: 1rem;
    position: relative;
}

.line-chart svg {
    width: 100%;
    height: 100%;
    overflow: visible;
}

.chart-line {
    stroke-dasharray: 1000;
    stroke-dashoffset: 1000;
    animation: draw-line 2s ease-out forwards;
}

@keyframes draw-line {
    to { stroke-dashoffset: 0; }
}

.chart-area {
    opacity: 0;
    animation: fade-area 2s ease-out forwards 0.5s;
}

@keyframes fade-area {
    to { opacity: 1; }
}

/* Feed Card */
.feed-card {
    display: flex;
    flex-direction: column;
}

.log-list {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    overflow-y: auto;
    flex: 1;
}

.log-item {
    display: flex;
    gap: 12px;
    align-items: flex-start;
}

.log-dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    margin-top: 5px;
    flex-shrink: 0;
}
.log-dot.cyan { background: var(--neon-cyan); box-shadow: 0 0 8px var(--neon-cyan); }
.log-dot.pink { background: var(--neon-pink); box-shadow: 0 0 8px var(--neon-pink); }
.log-dot.purple { background: var(--neon-purple); box-shadow: 0 0 8px var(--neon-purple); }

.log-content p {
    font-size: 0.9rem;
    color: var(--text-main);
    margin-bottom: 2px;
}

.log-content span {
    font-size: 0.75rem;
    color: var(--text-muted);
}

/* Scrollbar styling for a polished look */
::-webkit-scrollbar {
    width: 6px;
}
::-webkit-scrollbar-track {
    background: transparent;
}
::-webkit-scrollbar-thumb {
    background: rgba(255, 255, 255, 0.1);
    border-radius: 10px;
}
::-webkit-scrollbar-thumb:hover {
    background: rgba(255, 255, 255, 0.2);
}
