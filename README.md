document.addEventListener('DOMContentLoaded', () => {
    // Simulate real-time data updates
    const statValues = document.querySelectorAll('.stat-value');
    const computeVal = statValues[0];
    const latencyVal = statValues[1];

    setInterval(() => {
        // Randomly fluctuate compute power between 90.0 and 98.0
        const randomCompute = (90 + Math.random() * 8).toFixed(1);
        computeVal.innerHTML = `${randomCompute} <span class="unit">TFLOPS</span>`;

        // Randomly fluctuate latency between 10.0 and 15.0
        const randomLatency = (10 + Math.random() * 5).toFixed(1);
        latencyVal.innerHTML = `${randomLatency} <span class="unit">ms</span>`;
    }, 3000);

    // Controls toggle
    const chartControls = document.querySelectorAll('.controls button');
    chartControls.forEach(btn => {
        btn.addEventListener('click', (e) => {
            chartControls.forEach(b => b.classList.remove('active'));
            e.target.classList.add('active');
            
            // Retrigger the chart animation
            const chartLine = document.querySelector('.chart-line');
            const chartArea = document.querySelector('.chart-area');
            
            chartLine.style.animation = 'none';
            chartArea.style.animation = 'none';
            
            // Force reflow
            void chartLine.offsetWidth;
            
            chartLine.style.animation = 'draw-line 1.5s ease-out forwards';
            chartArea.style.animation = 'fade-area 1.5s ease-out forwards 0.3s';
        });
    });

    // Sidebar navigation logic (purely visual for demo)
    const navItems = document.querySelectorAll('.nav-item');
    navItems.forEach(item => {
        item.addEventListener('click', (e) => {
            e.preventDefault();
            navItems.forEach(nav => nav.classList.remove('active'));
            item.classList.add('active');
        });
    });
});
