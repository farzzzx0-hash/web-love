<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Surprise Romantis untuk Pasangan</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #fdbb2d);
            min-height: 100vh;
            color: #fff;
            overflow-x: hidden;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        /* Intro Kartun Styles */
        #introSection {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #ff6b6b, #ff8e8e);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            transition: opacity 1s ease;
        }
        
        .intro-content {
            text-align: center;
            padding: 20px;
        }
        
        .couple-characters {
            display: flex;
            justify-content: center;
            align-items: flex-end;
            margin-bottom: 30px;
            gap: 50px;
        }
        
        .character {
            width: 120px;
            height: 200px;
            position: relative;
            animation: float 3s ease-in-out infinite;
        }
        
        .boy {
            animation-delay: 0s;
        }
        
        .girl {
            animation-delay: 0.5s;
        }
        
        .character-body {
            width: 80px;
            height: 120px;
            background: #4a90e2;
            border-radius: 40px 40px 0 0;
            position: absolute;
            bottom: 0;
            left: 20px;
        }
        
        .girl .character-body {
            background: #ff6b9d;
        }
        
        .character-head {
            width: 60px;
            height: 60px;
            background: #ffd1a4;
            border-radius: 50%;
            position: absolute;
            top: -30px;
            left: 10px;
        }
        
        .character-heart {
            position: absolute;
            top: -50px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 30px;
            color: #ff4d6d;
            animation: heartbeat 1.2s infinite;
        }
        
        .intro-text {
            font-size: 2.5rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            opacity: 0;
            animation: fadeInText 2s forwards;
        }
        
        .intro-subtext {
            font-size: 1.2rem;
            margin-bottom: 30px;
            opacity: 0;
            animation: fadeInText 2s 0.5s forwards;
        }
        
        .start-btn {
            background: rgba(255, 255, 255, 0.2);
            border: 2px solid white;
            color: white;
            padding: 15px 40px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1.2rem;
            transition: all 0.3s;
            backdrop-filter: blur(5px);
            opacity: 0;
            animation: fadeInText 2s 1s forwards;
        }
        
        .start-btn:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: scale(1.05);
        }
        
        /* Main Content Styles */
        .main-content {
            display: none;
        }
        
        .header {
            text-align: center;
            padding: 40px 20px;
            opacity: 0;
            animation: fadeIn 2s forwards;
        }
        
        h1 {
            font-size: 3rem;
            margin-bottom: 15px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }
        
        .subtitle {
            font-size: 1.3rem;
            opacity: 0.9;
        }
        
        /* Section untuk foto pasangan */
        .photo-section {
            text-align: center;
            margin: 40px 0;
            opacity: 0;
            animation: slideUp 1.5s 0.5s forwards;
        }
        
        .photo-frame {
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 15px 35px rgba(0,0,0,0.3);
            max-width: 500px;
            margin: 0 auto;
            position: relative;
            background: rgba(255, 255, 255, 0.1);
            padding: 20px;
        }
        
        .couple-placeholder {
            width: 100%;
            height: 300px;
            background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: white;
            border-radius: 10px;
        }
        
        .couple-placeholder i {
            font-size: 80px;
            margin-bottom: 20px;
        }
        
        .upload-btn {
            background: rgba(255, 255, 255, 0.2);
            border: none;
            color: white;
            padding: 10px 20px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1rem;
            margin-top: 15px;
            transition: all 0.3s;
        }
        
        .upload-btn:hover {
            background: rgba(255, 255, 255, 0.3);
        }
        
        #couplePhoto {
            width: 100%;
            border-radius: 10px;
            display: none;
        }
        
        .video-section {
            margin: 40px 0;
            text-align: center;
            opacity: 0;
            animation: slideUp 1.5s 0.5s forwards;
        }
        
        .video-container {
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 15px 35px rgba(0,0,0,0.3);
            max-width: 800px;
            margin: 0 auto;
            position: relative;
        }
        
        #animationCanvas {
            width: 100%;
            height: 450px;
            display: block;
            background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
        }
        
        .video-controls {
            margin-top: 20px;
            display: flex;
            justify-content: center;
            gap: 15px;
        }
        
        .control-btn {
            background: rgba(255, 255, 255, 0.2);
            border: none;
            color: white;
            padding: 12px 25px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1rem;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: all 0.3s;
            backdrop-filter: blur(5px);
        }
        
        .control-btn:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-3px);
        }
        
        .messages-section {
            margin: 80px 0;
            opacity: 0;
            animation: fadeIn 2s 1.5s forwards;
        }
        
        .message-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 40px;
            margin: 30px 0;
            box-shadow: 0 8px 32px rgba(0,0,0,0.1);
            border: 1px solid rgba(255,255,255,0.1);
            text-align: left;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.5s;
        }
        
        .message-card.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        .message-card h3 {
            font-size: 1.6rem;
            margin-bottom: 20px;
            color: #ffd700;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .message-card p {
            font-size: 1.2rem;
            line-height: 1.7;
            margin-bottom: 15px;
        }
        
        .heart {
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: #ff4d6d;
            transform: rotate(45deg);
            opacity: 0.7;
            pointer-events: none;
        }
        
        .heart:before, .heart:after {
            content: '';
            width: 20px;
            height: 20px;
            background-color: #ff4d6d;
            border-radius: 50%;
            position: absolute;
        }
        
        .heart:before {
            top: -10px;
            left: 0;
        }
        
        .heart:after {
            top: 0;
            left: -10px;
        }
        
        .floating-hearts {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .footer {
            margin-top: 50px;
            text-align: center;
            font-size: 1rem;
            opacity: 0.8;
            padding: 20px;
        }
        
        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @keyframes fadeInText {
            from { 
                opacity: 0;
                transform: translateY(20px);
            }
            to { 
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes slideUp {
            from { 
                opacity: 0;
                transform: translateY(50px);
            }
            to { 
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }
        
        @keyframes heartbeat {
            0%, 100% {
                transform: translateX(-50%) scale(1);
            }
            50% {
                transform: translateX(-50%) scale(1.2);
            }
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.2rem;
            }
            
            .intro-text {
                font-size: 2rem;
            }
            
            .couple-characters {
                gap: 30px;
            }
            
            .character {
                width: 80px;
                height: 150px;
            }
            
            .character-body {
                width: 60px;
                height: 90px;
            }
            
            .character-head {
                width: 45px;
                height: 45px;
                top: -22px;
                left: 7px;
            }
            
            .message-card {
                padding: 25px;
            }
            
            #animationCanvas {
                height: 350px;
            }
            
            .couple-placeholder {
                height: 250px;
            }
        }
        
        @media (max-width: 480px) {
            h1 {
                font-size: 1.8rem;
            }
            
            .intro-text {
                font-size: 1.6rem;
            }
            
            .subtitle {
                font-size: 1.1rem;
            }
            
            .couple-characters {
                gap: 20px;
            }
            
            .character {
                width: 60px;
                height: 120px;
            }
            
            .character-body {
                width: 45px;
                height: 70px;
                left: 7px;
            }
            
            .character-head {
                width: 35px;
                height: 35px;
                top: -17px;
                left: 5px;
            }
            
            #animationCanvas {
                height: 250px;
            }
            
            .message-card {
                padding: 20px;
            }
            
            .message-card p {
                font-size: 1.1rem;
            }
            
            .couple-placeholder {
                height: 200px;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
</head>
<body>
    <!-- Intro Kartun Section -->
    <section id="introSection">
        <div class="intro-content">
            <div class="couple-characters">
                <div class="character boy">
                    <div class="character-head"></div>
                    <div class="character-body"></div>
                    <div class="character-heart">❤️</div>
                </div>
                <div class="character girl">
                    <div class="character-head"></div>
                    <div class="character-body"></div>
                    <div class="character-heart">❤️</div>
                </div>
            </div>
            <h2 class="intro-text">Cerita Kita</h2>
            <p class="intro-subtext">Sebuah perjalanan indah penuh cinta dan kebahagiaan</p>
            <button class="start-btn" id="startBtn">Mulai Kejutan</button>
        </div>
    </section>
    
    <!-- Main Content -->
    <div class="main-content" id="mainContent">
        <div class="floating-hearts" id="hearts-container"></div>
        
        <div class="container">
            <div class="header">
                <h1>Untukmu, Sayangku</h1>
                <p class="subtitle">Sebuah kejutan kecil dari hatiku</p>
            </div>
            
            <!-- Section untuk foto pasangan -->
            <div class="photo-section">
                <div class="photo-frame">
                    <div class="couple-placeholder" id="photoPlaceholder">
                        <i class="fas fa-heart"></i>
                        <p>Foto kita berdua</p>
                        <button class="upload-btn" id="uploadBtn">Unggah Foto Kita</button>
                    </div>
                    <img id="couplePhoto" alt="Foto kita berdua">
                </div>
                <input type="file" id="photoInput" accept="image/*" style="display: none;">
            </div>
            
            <div class="video-section">
                <div class="video-container">
                    <canvas id="animationCanvas"></canvas>
                </div>
                <div class="video-controls">
                    <button class="control-btn" id="playBtn">
                        <i class="fas fa-play"></i> Putar Animasi
                    </button>
                    <button class="control-btn" id="pauseBtn">
                        <i class="fas fa-pause"></i> Jeda
                    </button>
                    <button class="control-btn" id="heartBtn">
                        <i class="fas fa-heart"></i> Hati Spesial
                    </button>
                </div>
            </div>
            
            <div class="messages-section" id="messagesSection">
                <div class="message-card">
                    <h3><i class="fas fa-heart"></i> Tentang Kita</h3>
                    <p>Setiap momen bersamamu terasa spesial. Dari hal-hal kecil seperti berbagi cerita di penghujung hari, hingga petualangan yang kita lakukan bersama.</p>
                    <p>Aku bersyukur bisa berbagi hidup dengan seseorang yang memahami dan menerimaku apa adanya.</p>
                </div>
                
                <div class="message-card">
                    <h3><i class="fas fa-star"></i> Hal yang Kusuka</h3>
                    <p>Aku menyukai caramu melihat dunia, tawamu yang menular, dan caramu membuatku merasa berarti.</p>
                    <p>Kebiasaan kecilmu, cara kamu peduli pada orang lain, dan caramu menghadapi tantangan - semuanya membuatku semakin mengagumimu.</p>
                </div>
                
                <div class="message-card">
                    <h3><i class="fas fa-hand-holding-heart"></i> Terima Kasih</h3>
                    <p>Terima kasih telah menjadi pendamping yang sabar, teman yang setia, dan cinta dalam hidupku.</p>
                    <p>Terima kasih untuk semua dukungan, pengertian, dan kebahagiaan yang kamu bawa ke dalam hidupku.</p>
                </div>
                
                <div class="message-card">
                    <h3><i class="fas fa-infinity"></i> Masa Depan Kita</h3>
                    <p>Aku berharap bisa terus membangun kehidupan yang penuh makna bersamamu.</p>
                    <p>Menghadapi tantangan bersama, merayakan keberhasilan, dan menciptakan kenangan indah yang akan kita kenang selamanya.</p>
                </div>
            </div>
            
            <div class="footer">
                <p>Dibuat dengan ❤️ khusus untukmu - Hari ini dan selamanya</p>
            </div>
        </div>
    </div>

    <script>
        // Intro Kartun Functionality
        const introSection = document.getElementById('introSection');
        const mainContent = document.getElementById('mainContent');
        const startBtn = document.getElementById('startBtn');
        
        startBtn.addEventListener('click', function() {
            // Fade out intro
            introSection.style.opacity = '0';
            
            // Show main content after intro fades out
            setTimeout(function() {
                introSection.style.display = 'none';
                mainContent.style.display = 'block';
                
                // Initialize main content animations
                createFloatingHearts();
                init();
                isPlaying = true;
                animate();
            }, 1000);
        });
        
        // Fungsi untuk mengunggah foto
        const uploadBtn = document.getElementById('uploadBtn');
        const photoInput = document.getElementById('photoInput');
        const couplePhoto = document.getElementById('couplePhoto');
        const photoPlaceholder = document.getElementById('photoPlaceholder');
        
        uploadBtn.addEventListener('click', function() {
            photoInput.click();
        });
        
        photoInput.addEventListener('change', function(e) {
            if (e.target.files && e.target.files[0]) {
                const reader = new FileReader();
                
                reader.onload = function(e) {
                    couplePhoto.src = e.target.result;
                    couplePhoto.style.display = 'block';
                    photoPlaceholder.style.display = 'none';
                }
                
                reader.readAsDataURL(e.target.files[0]);
            }
        });
        
        // Membuat hati yang melayang di latar belakang
        function createFloatingHearts() {
            const container = document.getElementById('hearts-container');
            const heartCount = 15;
            
            for (let i = 0; i < heartCount; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                
                // Posisi acak
                const left = Math.random() * 100;
                const top = Math.random() * 100;
                const delay = Math.random() * 5;
                const duration = 5 + Math.random() * 5;
                const size = 10 + Math.random() * 20;
                
                heart.style.left = `${left}%`;
                heart.style.top = `${top}%`;
                heart.style.animation = `float ${duration}s ${delay}s infinite ease-in-out`;
                heart.style.width = `${size}px`;
                hea# web-love
