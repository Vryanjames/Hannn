<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Everything 🌹</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;1,400&family=Dancing+Script:wght@400;700&family=Cormorant+Garamond:ital,wght@0,300;0,400;1,400&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            overflow: hidden;
            background: linear-gradient(135deg, #1a0a0f 0%, #2d1b24 50%, #1a0a0f 100%);
            font-family: 'Cormorant Garamond', serif;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* Ambient particles */
        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(255, 215, 0, 0.6);
            border-radius: 50%;
            pointer-events: none;
            animation: float 20s infinite linear;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) translateX(0) scale(0);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) translateX(100px) scale(1);
                opacity: 0;
            }
        }

        /* Main Container */
        .container {
            position: relative;
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
        }

        /* Title */
        .title {
            position: absolute;
            top: 5%;
            font-family: 'Dancing Script', cursive;
            font-size: 3.5rem;
            color: #ffd700;
            text-shadow: 0 0 30px rgba(255, 215, 0, 0.5);
            opacity: 0;
            animation: fadeInDown 2s ease forwards;
            z-index: 10;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Bouquet Container */
        .bouquet-wrapper {
            position: relative;
            width: 500px;
            height: 600px;
            cursor: pointer;
            transition: transform 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
            filter: drop-shadow(0 30px 60px rgba(0, 0, 0, 0.5));
            z-index: 20;
        }

        .bouquet-wrapper:hover {
            transform: scale(1.05) translateY(-10px);
        }

        .bouquet-wrapper:active {
            transform: scale(0.98);
        }

        /* Large Central Rose */
        .rose-container {
            position: absolute;
            top: 50px;
            left: 50%;
            transform: translateX(-50%);
            width: 200px;
            height: 200px;
            z-index: 10;
        }

        .rose {
            position: relative;
            width: 100%;
            height: 100%;
            animation: breathe 4s ease-in-out infinite;
        }

        @keyframes breathe {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        /* Rose petals using CSS */
        .rose-petals {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
        }

        .petal {
            position: absolute;
            background: linear-gradient(135deg, #ff1744 0%, #d50000 50%, #b71c1c 100%);
            border-radius: 50% 50% 50% 0;
            transform-origin: bottom left;
            box-shadow: inset -2px -2px 8px rgba(0,0,0,0.3), 0 4px 8px rgba(0,0,0,0.2);
            transition: all 0.3s ease;
        }

        .petal:nth-child(1) {
            width: 100px;
            height: 100px;
            top: 50px;
            left: 50px;
            transform: rotate(0deg);
            background: linear-gradient(135deg, #ff5252 0%, #d50000 100%);
            z-index: 5;
        }

        .petal:nth-child(2) {
            width: 90px;
            height: 90px;
            top: 45px;
            left: 60px;
            transform: rotate(72deg);
            background: linear-gradient(135deg, #ff1744 0%, #c62828 100%);
            z-index: 4;
        }

        .petal:nth-child(3) {
            width: 85px;
            height: 85px;
            top: 55px;
            left: 45px;
            transform: rotate(144deg);
            background: linear-gradient(135deg, #f44336 0%, #b71c1c 100%);
            z-index: 3;
        }

        .petal:nth-child(4) {
            width: 80px;
            height: 80px;
            top: 60px;
            left: 55px;
            transform: rotate(216deg);
            background: linear-gradient(135deg, #e53935 0%, #c62828 100%);
            z-index: 2;
        }

        .petal:nth-child(5) {
            width: 75px;
            height: 75px;
            top: 50px;
            left: 65px;
            transform: rotate(288deg);
            background: linear-gradient(135deg, #d32f2f 0%, #b71c1c 100%);
            z-index: 1;
        }

        /* Inner petals */
        .inner-petal {
            position: absolute;
            background: linear-gradient(135deg, #ff8a80 0%, #ff1744 100%);
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            box-shadow: inset 0 0 20px rgba(0,0,0,0.2);
        }

        .inner-petal:nth-child(6) { width: 50px; height: 50px; z-index: 6; }
        .inner-petal:nth-child(7) { width: 35px; height: 35px; z-index: 7; background: linear-gradient(135deg, #ffab91 0%, #ff8a80 100%); }
        .inner-petal:nth-child(8) { 
            width: 20px; 
            height: 20px; 
            z-index: 8; 
            background: radial-gradient(circle, #ffd700 0%, #ff8f00 100%);
            box-shadow: 0 0 20px rgba(255, 215, 0, 0.8);
        }

        /* Surrounding Flowers */
        .flower-side {
            position: absolute;
            width: 120px;
            height: 120px;
            animation: sway 3s ease-in-out infinite;
        }

        .flower-side.left {
            top: 150px;
            left: 50px;
            animation-delay: 0.5s;
            transform: rotate(-15deg) scale(0.9);
        }

        .flower-side.right {
            top: 140px;
            right: 50px;
            animation-delay: 1s;
            transform: rotate(15deg) scale(0.85);
        }

        .flower-side.back-left {
            top: 80px;
            left: 100px;
            animation-delay: 1.5s;
            transform: rotate(-25deg) scale(0.7);
            opacity: 0.9;
        }

        .flower-side.back-right {
            top: 90px;
            right: 90px;
            animation-delay: 0.3s;
            transform: rotate(20deg) scale(0.75);
            opacity: 0.9;
        }

        @keyframes sway {
            0%, 100% { transform: rotate(var(--r, 0deg)) translateX(0); }
            50% { transform: rotate(var(--r, 0deg)) translateX(5px); }
        }

        /* Simple flower design */
        .simple-flower {
            position: relative;
            width: 100%;
            height: 100%;
        }

        .sf-petal {
            position: absolute;
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, #ff69b4 0%, #c71585 100%);
            border-radius: 50% 50% 50% 0;
            top: 40px;
            left: 40px;
            transform-origin: bottom left;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }

        .sf-petal:nth-child(1) { transform: rotate(0deg) translateX(20px); }
        .sf-petal:nth-child(2) { transform: rotate(72deg) translateX(20px); background: linear-gradient(135deg, #ff1493 0%, #c71585 100%); }
        .sf-petal:nth-child(3) { transform: rotate(144deg) translateX(20px); background: linear-gradient(135deg, #db7093 0%, #c71585 100%); }
        .sf-petal:nth-child(4) { transform: rotate(216deg) translateX(20px); background: linear-gradient(135deg, #ff69b4 0%, #ff1493 100%); }
        .sf-petal:nth-child(5) { transform: rotate(288deg) translateX(20px); background: linear-gradient(135deg, #ffb6c1 0%, #ff69b4 100%); }

        .sf-center {
            position: absolute;
            width: 25px;
            height: 25px;
            background: radial-gradient(circle, #ffd700 0%, #ff8c00 100%);
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 10;
            box-shadow: 0 0 10px rgba(255, 215, 0, 0.6);
        }

        /* Stems */
        .stem {
            position: absolute;
            width: 4px;
            height: 200px;
            background: linear-gradient(to bottom, #2e7d32 0%, #1b5e20 100%);
            bottom: -180px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
            z-index: 1;
        }

        .stem.left { transform: translateX(-50%) rotate(-20deg); height: 180px; }
        .stem.right { transform: translateX(-50%) rotate(20deg); height: 170px; }
        .stem.back { height: 220px; opacity: 0.8; }

        /* Leaves */
        .leaf {
            position: absolute;
            width: 40px;
            height: 20px;
            background: linear-gradient(135deg, #4caf50 0%, #2e7d32 100%);
            border-radius: 0 50% 0 50%;
            bottom: -100px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }

        .leaf.l1 { left: 30%; transform: rotate(-30deg); bottom: -120px; }
        .leaf.l2 { right: 30%; transform: scaleX(-1) rotate(-30deg); bottom: -140px; }
        .leaf.l3 { left: 25%; transform: rotate(-40deg); bottom: -80px; }

        /* Wrapper/Bouquet holder */
        .wrapper {
            position: absolute;
            bottom: -50px;
            left: 50%;
            transform: translateX(-50%);
            width: 180px;
            height: 120px;
            background: linear-gradient(135deg, #8d6e63 0%, #5d4037 100%);
            clip-path: polygon(15% 0%, 85% 0%, 100% 100%, 0% 100%);
            z-index: 5;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        .wrapper::before {
            content: '';
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 30px;
            height: 100%;
            background: linear-gradient(to bottom, rgba(255,255,255,0.2), transparent);
        }

        /* Ribbon */
        .ribbon {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 40px;
            z-index: 6;
        }

        .ribbon::before {
            content: '🎀';
            font-size: 3rem;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            filter: drop-shadow(0 2px 4px rgba(0,0,0,0.3));
        }

        /* Sparkles around bouquet */
        .sparkle {
            position: absolute;
            color: #ffd700;
            font-size: 1.5rem;
            animation: twinkle 2s infinite;
            pointer-events: none;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0; transform: scale(0); }
            50% { opacity: 1; transform: scale(1); }
        }

        /* Hint text */
        .hint {
            position: absolute;
            bottom: 10%;
            font-family: 'Cormorant Garamond', serif;
            font-size: 1.3rem;
            color: rgba(255, 215, 0, 0.8);
            letter-spacing: 2px;
            animation: pulse 2s infinite;
            text-transform: uppercase;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.5; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.05); }
        }

        /* Message Overlay */
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(20px);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.8s ease;
            z-index: 1000;
            padding: 20px;
        }

        .overlay.active {
            opacity: 1;
            pointer-events: all;
        }

        .message-card {
            background: linear-gradient(135deg, #fff8e1 0%, #ffecb3 100%);
            padding: 60px;
            border-radius: 30px;
            max-width: 700px;
            text-align: center;
            position: relative;
            transform: scale(0.8) translateY(50px);
            transition: transform 0.8s cubic-bezier(0.34, 1.56, 0.64, 1);
            border: 3px solid rgba(255, 215, 0, 0.5);
            box-shadow: 0 40px 80px rgba(0,0,0,0.4), inset 0 0 60px rgba(255,215,0,0.1);
        }

        .overlay.active .message-card {
            transform: scale(1) translateY(0);
        }

        .message-text {
            font-family: 'Dancing Script', cursive;
            font-size: 2.8rem;
            color: #5d4037;
            line-height: 1.5;
            margin-bottom: 30px;
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 1s ease forwards 0.5s;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .message-icon {
            font-size: 4rem;
            margin-bottom: 20px;
            opacity: 0;
            animation: fadeIn 1s ease forwards 0.3s;
        }

        @keyframes fadeIn {
            to { opacity: 1; }
        }

        .signature {
            font-family: 'Playfair Display', serif;
            font-size: 1.3rem;
            color: #d4a017;
            font-style: italic;
            opacity: 0;
            animation: fadeIn 1s ease forwards 1.2s;
            margin-top: 20px;
        }

        .hearts-divider {
            font-size: 2rem;
            color: #ff1744;
            letter-spacing: 15px;
            margin: 20px 0;
            opacity: 0;
            animation: fadeIn 1s ease forwards 0.8s;
        }

        .close-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            width: 50px;
            height: 50px;
            border: none;
            background: rgba(255, 23, 68, 0.1);
            border-radius: 50%;
            cursor: pointer;
            font-size: 1.8rem;
            color: #ff1744;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: serif;
        }

        .close-btn:hover {
            background: rgba(255, 23, 68, 0.2);
            transform: rotate(90deg) scale(1.1);
        }

        /* Corner decorations */
        .corner {
            position: absolute;
            width: 80px;
            height: 80px;
            border: 3px solid rgba(212, 160, 23, 0.3);
            border-radius: 50%;
        }

        .corner.top-left {
            top: -40px;
            left: -40px;
            border-right: none;
            border-bottom: none;
        }

        .corner.bottom-right {
            bottom: -40px;
            right: -40px;
            border-left: none;
            border-top: none;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .title { font-size: 2.5rem; top: 3%; }
            .bouquet-wrapper { width: 350px; height: 450px; }
            .rose-container { width: 150px; height: 150px; top: 40px; }
            .petal:nth-child(1) { width: 75px; height: 75px; top: 37px; left: 37px; }
            .petal:nth-child(2) { width: 67px; height: 67px; top: 33px; left: 45px; }
            .petal:nth-child(3) { width: 63px; height: 63px; top: 41px; left: 33px; }
            .petal:nth-child(4) { width: 60px; height: 60px; top: 45px; left: 41px; }
            .petal:nth-child(5) { width: 56px; height: 56px; top: 37px; left: 48px; }
            .flower-side { width: 90px; height: 90px; }
            .flower-side.left { left: 30px; top: 120px; }
            .flower-side.right { right: 30px; top: 110px; }
            .message-card { padding: 40px 30px; }
            .message-text { font-size: 2rem; }
        }
    </style>
</head>
<body>

    <!-- Ambient Particles -->
    <div id="particles"></div>

    <!-- Main Container -->
    <div class="container">
        
        <!-- Title -->
        <h1 class="title">For My Love</h1>

        <!-- Bouquet -->
        <div class="bouquet-wrapper" onclick="openMessage(event)">
            
            <!-- Back flowers -->
            <div class="flower-side back-left">
                <div class="simple-flower">
                    <div class="sf-petal"></div>
                    <div class="sf-petal"></div>
                    <div class="sf-petal"></div>
                    <div class="sf-petal"></div>
                    <div class="sf-petal"></div>
                    <div class="sf-center"></div>
                </div>
                <div class="stem back" style="transform: translateX(-50%) rotate(-30deg);"></div>
            </div>

            <div class="flower-side back-right">
                <div class="simple-flower">
                    <div class="sf-petal" style="background: linear-gradient(135deg, #dda0dd 0%, #da70d6 100%);"></div>
                    <div class="sf-petal" style="background: linear-gradient(135deg, #ba55d3 0%, #9932cc 100%);"></div>
                    <div class="sf-petal" style="background: linear-gradient(135deg, #dda0dd 0%, #ba55d3 100%);"></div>
                    <div class="sf-petal" style="background: linear-gradient(135deg, #da70d6 0%, #ba55d3 100%);"></div>
                    <div class="sf-petal" style="background: linear-gradient(135deg, #ee82ee 0%, #da70d6 100%);"></div>
                    <div class="sf-center"></div>
                </div>
                <div class="stem back" style="transform: translateX(-50%) rotate(25deg);"></div>
            </div>

            <!-- Side flowers -->
            <div class="flower-side left">
                <div class="simple-flower">
                    <div class="sf-petal" style="background: linear-gradient(135deg, #ffb6c1 0%, #ff69b4 100%);"></div>
                    <div class="sf-petal" style="background: linear-gradient(135deg, #ff69b4 0%, #ff1493 100%);"></div>
                    <div class="sf-petal" style="background: linear-gradient(135deg, #ffc0cb 0%, #ff69b4 100%);"></div>
                    <div class="sf-petal" style="background: linear-gradient(135deg, #ff1493 0%, #c71585 100%);"></div>
                    <div class="sf-petal" style="background: linear-gradient(135deg, #db7093 0%, #ff69b4 100%);"></div>
                    <div class="sf-center"></div>
                </div>
                <div class="stem left"></div>
                <div class="leaf l3" style="left: 40%; bottom: -90px;"></div>
            </div>

            <div class="flower-side right">
                <div class="simple-flower">
                    <div class="sf-petal" style="background: linear-gradient(135deg, #ff6347 0%, #dc143c 100%);"></div>
                    <div class="sf-petal" style="background: linear-gradient(135deg, #ff4500 0%, #b22222 100%);"></div>
                    <div class="sf-petal" style="background: linear-gradient(135deg, #fa8072 0%, #dc143c 100%);"></div>
                    <div class="sf-petal" style="background: linear-gradient(135deg, #e9967a 0%, #cd5c5c 100%);"></div>
                    <div class="sf-petal" style="background: linear-gradient(135deg, #ffa07a 0%, #dc143c 100%);"></div>
                    <div class="sf-center"></div>
                </div>
                <div class="stem right"></div>
                <div class="leaf l3" style="right: 40%; left: auto; bottom: -100px; transform: scaleX(-1) rotate(-40deg);"></div>
            </div>

            <!-- Main Rose -->
            <div class="rose-container">
                <div class="rose">
                    <div class="rose-petals">
                        <div class="petal"></div>
                        <div class="petal"></div>
                        <div class="petal"></div>
                        <div class="petal"></div>
                        <div class="petal"></div>
                        <div class="inner-petal"></div>
                        <div class="inner-petal"></div>
                        <div class="inner-petal"></div>
                    </div>
                </div>
                <div class="stem" style="height: 250px; bottom: -220px; z-index: 1;"></div>
                <div class="leaf l1"></div>
                <div class="leaf l2"></div>
            </div>

            <!-- Wrapper -->
            <div class="wrapper"></div>
            <div class="ribbon"></div>

            <!-- Sparkles -->
            <div class="sparkle" style="top: 20px; left: 50px; animation-delay: 0s;">✨</div>
            <div class="sparkle" style="top: 80px; right: 60px; animation-delay: 0.5s;">✨</div>
            <div class="sparkle" style="top: 150px; left: 30px; animation-delay: 1s;">✨</div>
            <div class="sparkle" style="top: 100px; right: 40px; animation-delay: 1.5s;">✨</div>
            <div class="sparkle" style="bottom: 100px; left: 80px; animation-delay: 0.3s;">✨</div>
            <div class="sparkle" style="bottom: 150px; right: 80px; animation-delay: 0.8s;">✨</div>

        </div>

        <!-- Hint -->
        <div class="hint">Click the rose to open your message</div>

    </div>

    <!-- Message Overlay -->
    <div class="overlay" id="overlay" onclick="closeMessage(event)">
        <div class="message-card" onclick="event.stopPropagation()">
            <button class="close-btn" onclick="closeMessage(event)">×</button>
            <div class="corner top-left"></div>
            <div class="corner bottom-right"></div>
            
            <div class="message-icon">🌹</div>
            
            <p class="message-text">
                You are not just a girl, you're my girl, my home, my heart and my safest place. You're my everything
            </p>
            
            <div class="hearts-divider">❦ ❦ ❦</div>
            
            <p class="signature">Forever Yours</p>
        </div>
    </div>

    <script>
        // Create ambient particles
        function createParticles() {
            const container = document.getElementById('particles');
            for (let i = 0; i < 30; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDuration = (Math.random() * 15 + 15) + 's';
                particle.style.animationDelay = Math.random() * 20 + 's';
                container.appendChild(particle);
            }
        }

        // Burst effect when clicking
        function createBurst(x, y) {
            const colors = ['#ffd700', '#ff1744', '#ff69b4', '#ff1493', '#ffb6c1'];
            for (let i = 0; i < 30; i++) {
                const particle = document.createElement('div');
                particle.style.position = 'absolute';
                particle.style.width = '8px';
                particle.style.height = '8px';
                particle.style.background = colors[Math.floor(Math.random() * colors.length)];
                particle.style.borderRadius = '50%';
                particle.style.left = x + 'px';
                particle.style.top = y + 'px';
                particle.style.pointerEvents = 'none';
                particle.style.zIndex = '9999';
                
                const angle = (Math.PI * 2 * i) / 30;
                const velocity = 100 + Math.random() * 150;
                const tx = Math.cos(angle) * velocity;
                const ty = Math.sin(angle) * velocity;
                
                particle.animate([
                    { transform: 'translate(0, 0) scale(1)', opacity: 1 },
                    { transform: `translate(${tx}px, ${ty}px) scale(0)`, opacity: 0 }
                ], {
                    duration: 1000,
                    easing: 'cubic-bezier(0, .9, .57, 1)'
                }).onfinish = () => particle.remove();
                
                document.body.appendChild(particle);
            }
        }

        // Open message
        function openMessage(event) {
            const overlay = document.getElementById('overlay');
            const rect = event.currentTarget.getBoundingClientRect();
            const centerX = rect.left + rect.width / 2;
            const centerY = rect.top + rect.height / 2;
            
            createBurst(centerX, centerY);
            overlay.classList.add('active');
            
            // Additional celebration bursts
            setTimeout(() => createBurst(window.innerWidth / 2, window.innerHeight / 2), 500);
            setTimeout(() => createBurst(window.innerWidth / 3, window.innerHeight / 3), 800);
            setTimeout(() => createBurst(window.innerWidth * 2/3, window.innerHeight * 2/3), 1100);
        }

        // Close message
        function closeMessage(event) {
            event.stopPropagation();
            document.getElementById('overlay').classList.remove('active');
        }

        // Initialize
        createParticles();

        // Add mouse movement parallax
        document.addEventListener('mousemove', (e) => {
            const x = (window.innerWidth - e.pageX) / 50;
            const y = (window.innerHeight - e.pageY) / 50;
            
            const roses = document.querySelectorAll('.rose-container, .flower-side');
            roses.forEach((rose, index) => {
                const speed = (index + 1) * 0.3;
                rose.style.transform = `translateX(calc(-50% + ${x * speed}px)) translateY(${y * speed}px)`;
            });
        });
    </script>
</body>
</html>
