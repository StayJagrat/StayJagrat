<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Futuristic Dashboard | V-Core Analytics</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="glow-bg"></div>

    <div class="dashboard-layout">
        <!-- Sidebar -->
        <aside class="sidebar">
            <div class="brand">
                <div class="brand-icon"></div>
                <h2>V-Core</h2>
            </div>
            <nav class="side-nav">
                <a href="#" class="nav-item active">
                    <span class="icon">📊</span> Overview
                </a>
                <a href="#" class="nav-item">
                    <span class="icon">⚡</span> Performance
                </a>
                <a href="#" class="nav-item">
                    <span class="icon">🌌</span> Network Map
                </a>
                <a href="#" class="nav-item">
                    <span class="icon">🛡️</span> Security
                </a>
                <a href="#" class="nav-item">
                    <span class="icon">⚙️</span> Settings
                </a>
            </nav>
            <div class="sidebar-footer">
                <div class="user-profile">
                    <div class="avatar"></div>
                    <div class="user-info">
                        <h4>Admin 01</h4>
                        <p>System Online</p>
                    </div>
                </div>
            </div>
        </aside>

        <!-- Main Content -->
        <main class="main-content">
            <header class="top-header">
                <div class="search-bar">
                    <span class="search-icon">🔍</span>
                    <input type="text" placeholder="Query system data...">
                </div>
                <div class="header-actions">
                    <button class="icon-btn" data-tooltip="Notifications">🔔<span class="badge"></span></button>
                    <button class="btn-glow">Run Diagnostics</button>
                </div>
            </header>

            <div class="dashboard-grid">
                <!-- Status Card 1 -->
                <div class="card stat-card pulse-hover">
                    <div class="card-header">
                        <h3>Compute Power</h3>
                        <span class="trend up">+14%</span>
                    </div>
                    <div class="stat-value">94.2 <span class="unit">TFLOPS</span></div>
                    <div class="progress-container">
                        <div class="progress-bar cyan-glow" style="width: 85%"></div>
                    </div>
                </div>

                <!-- Status Card 2 -->
                <div class="card stat-card pulse-hover">
                    <div class="card-header">
                        <h3>Network Latency</h3>
                        <span class="trend down">-5ms</span>
                    </div>
                    <div class="stat-value">12.4 <span class="unit">ms</span></div>
                    <div class="progress-container">
                        <div class="progress-bar pink-glow" style="width: 15%"></div>
                    </div>
                </div>

                <!-- Status Card 3 -->
                <div class="card stat-card pulse-hover">
                    <div class="card-header">
                        <h3>Active Nodes</h3>
                        <span class="trend up">+8</span>
                    </div>
                    <div class="stat-value">1,024 <span class="unit">nodes</span></div>
                    <div class="progress-container">
                        <div class="progress-bar purple-glow" style="width: 100%"></div>
                    </div>
                </div>

                <!-- Large Chart Area -->
                <div class="card large-card span-2">
                    <div class="card-header">
                        <h3>Neural Throughput Overview</h3>
                        <div class="controls">
                            <button class="active">1H</button>
                            <button>24H</button>
                            <button>7D</button>
                        </div>
                    </div>
                    <div class="chart-container">
                        <!-- CSS-only animated chart mock -->
                        <div class="line-chart">
                            <svg viewBox="0 0 500 150" preserveAspectRatio="none">
                                <defs>
                                    <linearGradient id="cyanGrad" x1="0" y1="0" x2="0" y2="1">
                                        <stop offset="0%" stop-color="rgba(6, 182, 212, 0.5)" />
                                        <stop offset="100%" stop-color="rgba(6, 182, 212, 0)" />
                                    </linearGradient>
                                </defs>
                                <path class="chart-area" d="M0,150 L0,80 Q25,120 50,60 T100,70 T150,30 T200,90 T250,50 T300,100 T350,20 T400,60 T450,10 L500,40 L500,150 Z" fill="url(#cyanGrad)"></path>
                                <path class="chart-line" d="M0,80 Q25,120 50,60 T100,70 T150,30 T200,90 T250,50 T300,100 T350,20 T400,60 T450,10 L500,40" fill="none" stroke="#06B6D4" stroke-width="3"></path>
                            </svg>
                        </div>
                    </div>
                </div>

                <!-- Activity Feed -->
                <div class="card feed-card">
                    <div class="card-header">
                        <h3>System Logs</h3>
                    </div>
                    <div class="log-list">
                        <div class="log-item">
                            <div class="log-dot cyan"></div>
                            <div class="log-content">
                                <p>Cluster alpha scaled up</p>
                                <span>2 mins ago</span>
                            </div>
                        </div>
                        <div class="log-item">
                            <div class="log-dot pink"></div>
                            <div class="log-content">
                                <p>Firewall protocol updated</p>
                                <span>15 mins ago</span>
                            </div>
                        </div>
                        <div class="log-item">
                            <div class="log-dot purple"></div>
                            <div class="log-content">
                                <p>Anomaly detected in sector 4</p>
                                <span>1 hour ago</span>
                            </div>
                        </div>
                        <div class="log-item">
                            <div class="log-dot cyan"></div>
                            <div class="log-content">
                                <p>Backup completed successfully</p>
                                <span>2 hours ago</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </main>
    </div>

    <script src="script.js"></script>
</body>
</html>
