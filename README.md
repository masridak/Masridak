
    
    :root {
      --bg-color: #000032;
      --star-count: 200;
    }

    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      background-color: var(--bg-color);
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
      font-family: 'Space Mono', monospace;
    }

    /* Efek bintang di latar belakang */
    .stars {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
    }

    .star {
      position: absolute;
      background: white;
      border-radius: 50%;
      animation: twinkle 5s infinite;
    }

    @keyframes twinkle {
      0%, 100% { opacity: 0.2; }
      50% { opacity: 1; }
    }

    /* Generate stars dynamically */
    <script>
      document.addEventListener('DOMContentLoaded', function() {
        const starsContainer = document.querySelector('.stars');
        for (let i = 0; i < var(--star-count); i++) {
          const star = document.createElement('div');
          star.classList.add('star');
          
          // Random position
          const x = Math.random() * 100;
          const y = Math.random() * 100;
          
          // Random size between 1-3px
          const size = Math.random() * 2 + 1;
          
          // Random animation delay
          const delay = Math.random() * 5;
          
          star.style.left = `${x}%`;
          star.style.top = `${y}%`;
          star.style.width = `${size}px`;
          star.style.height = `${size}px`;
          star.style.animationDelay = `${delay}s`;
          
          starsContainer.appendChild(star);
        }
      });
    </script>

    .galaxy {
      position: relative;
      width: 1500px;
      height: 1000px;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .sun {
      position: absolute;
      width: 160px;
      height: 160px;
      border-radius: 50%;
      background: radial-gradient(circle at 30% 30%, 
        #ffde00 0%, 
        #ff8c00 30%, 
        #ff4500 70%, 
        #ff0000 100%);
      box-shadow: 0 0 80px #ff8c00, 
                  0 0 160px #ff4500;
      animation: rotateSun 30s linear infinite;
      z-index: 1;
    }

    /* Orbit styles */
    .orbit {
      position: absolute;
      border-radius: 50%;
      border: 1px solid rgba(255, 255, 255, 0.05);
      transform-origin: center;
    }

    /* Planet container */
    .planet {
      position: absolute;
      border-radius: 50%;
      animation-timing-function: linear;
      animation-iteration-count: infinite;
      transform-origin: center;
    }

    /* Specific planet orbits */
    #mercury-orbit {
      width: 200px;
      height: 200px;
      animation: rotateOrbit 8.8s linear infinite;
    }

    #venus-orbit {
      width: 300px;
      height: 300px;
      animation: rotateOrbit 22.6s linear infinite;
    }

    #earth-orbit {
      width: 400px;
      height: 400px;
      animation: rotateOrbit 36.5s linear infinite;
    }

    #mars-orbit {
      width: 550px;
      height: 550px;
      animation: rotateOrbit 68.7s linear infinite;
    }

    #jupiter-orbit {
      width: 750px;
      height: 750px;
      animation: rotateOrbit 432.9s linear infinite;
    }

    #saturn-orbit {
      width: 950px;
      height: 950px;
      animation: rotateOrbit 1075.6s linear infinite;
    }

    #uranus-orbit {
      width: 1100px;
      height: 1100px;
      animation: rotateOrbit 3068.7s linear infinite;
    }

    #neptune-orbit {
      width: 1300px;
      height: 1300px;
      animation: rotateOrbit 6014.2s linear infinite;
    }

    /* Planet styles */
    #mercury {
      width: 15px;
      height: 15px;
      background: radial-gradient(circle at 30% 30%, 
        #c0c0c0 0%, 
        #a0a0a0 50%, 
        #808080 100%);
      top: -7.5px;
      animation: rotatePlanet 58.6s linear infinite;
    }

    #venus {
      width: 30px;
      height: 30px;
      background: radial-gradient(circle at 30% 30%, 
        #e6b17e 0%, 
        #d4a06a 50%, 
        #b88a4e 100%);
      top: -15px;
      animation: rotatePlanet 243s linear infinite reverse;
    }

    #earth {
      width: 32px;
      height: 32px;
      background: radial-gradient(circle at 30% 30%, 
        #1faaf1 0%, 
        #06599c 50%, 
        #033158 100%);
      box-shadow: inset 0 0 20px rgba(255, 255, 255, 0.2);
      top: -16px;
      animation: rotatePlanet 24h linear infinite;
    }

    #earth::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      border-radius: 50%;
      background: url('https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/7206ff37-5005-46d1-a589-b8027ffb4872.png') center center;
      opacity: 0.3;
      mix-blend-mode: overlay;
      animation: rotateClouds 48h linear infinite;
    }

    #mars {
      width: 25px;
      height: 25px;
      background: radial-gradient(circle at 30% 30%, 
        #c1440e 0%, 
        #9a3a0b 50%, 
        #722c06 100%);
      top: -12.5px;
      animation: rotatePlanet 24.6s linear infinite;
    }

    #jupiter {
      width: 90px;
      height: 90px;
      background: radial-gradient(circle at 30% 30%, 
        #e39c68 0%, 
        #d18c52 30%, 
        #a56a35 70%, 
        #8b572a 100%);
      box-shadow: inset 0 0 30px rgba(0, 0, 0, 0.2);
      top: -45px;
      animation: rotatePlanet 9.9s linear infinite;
    }

    /* Jupiter's great red spot */
    #jupiter::after {
      content: '';
      position: absolute;
      top: 30%;
      right: 20%;
      width: 25%;
      height: 15%;
      background: #c13c28;
      border-radius: 50% 50% 50% 50% / 60% 60% 40% 40%;
    }

    #saturn {
      width: 75px;
      height: 75px;
      background: radial-gradient(circle at 30% 30%, 
        #e3d9b0 0%, 
        #d4c999 50%, 
        #b7ac75 100%);
      box-shadow: inset 0 0 20px rgba(0, 0, 0, 0.3);
      top: -37.5px;
      animation: rotatePlanet 10.2s linear infinite;
    }

    /* Saturn's rings */
    #saturn::before {
      content: '';
      position: absolute;
      width: 150px;
      height: 15px;
      background: linear-gradient(90deg, 
        rgba(210, 187, 133, 0.8) 0%, 
        rgba(173, 154, 102, 0.9) 50%, 
        rgba(210, 187, 133, 0.8) 100%);
      border-radius: 50%;
      transform: rotateX(65deg);
      top: 50%;
      left: 50%;
      margin-left: -75px;
      margin-top: -7.5px;
      z-index: -1;
    }

    #uranus {
      width: 40px;
      height: 40px;
      background: radial-gradient(circle at 30% 30%, 
        #b0e3e3 0%, 
        #8cc9c9 50%, 
        #5eaaaa 100%);
      top: -20px;
      animation: rotatePlanet 17.2s linear infinite reverse;
    }

    /* Uranus' rings */
    #uranus::before {
      content: '';
      position: absolute;
      width: 80px;
      height: 8px;
      background: linear-gradient(90deg, 
        rgba(138, 205, 205, 0.6) 0%, 
        rgba(102, 168, 168, 0.7) 50%, 
        rgba(138, 205, 205, 0.6) 100%);
      border-radius: 50%;
      transform: rotateX(70deg);
      top: 50%;
      left: 50%;
      margin-left: -40px;
      margin-top: -4px;
      z-index: -1;
    }

    #neptune {
      width: 38px;
      height: 38px;
      background: radial-gradient(circle at 30% 30%, 
        #4b70dd 0%, 
        #3a5ab5 50%, 
        #29448d 100%);
      top: -19px;
      animation: rotatePlanet 16.1s linear infinite;
    }

    /* Moon orbit for Earth */
    #moon-orbit {
      position: absolute;
      width: 70px;
      height: 70px;
      border-radius: 50%;
      border: 1px solid rgba(255, 255, 255, 0.05);
      top: -16px;
      left: -16px;
      animation: rotateMoonOrbit 2.7s linear infinite;
    }

    #moon {
      position: absolute;
      width: 8px;
      height: 8px;
      background: radial-gradient(circle at 30% 30%, 
        #d8d8d8 0%, 
        #b0b0b0 50%, 
        #888 100%);
      top: 50%;
      left: -4px;
      animation: rotatePlanet 27.3s linear infinite;
    }

    /* Animations */
    @keyframes rotateSun {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    @keyframes rotateOrbit {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    @keyframes rotatePlanet {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    @keyframes rotateMoonOrbit {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    @keyframes rotateClouds {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    @keyframes twinkle {
      0%, 100% { opacity: 0.2; }
      50% { opacity: 1; }
    }

    /* Controls and info panel */
    .controls {
      position: fixed;
      bottom: 20px;
      left: 0;
      width: 100%;
      display: flex;
      justify-content: center;
      gap: 20px;
      z-index: 100;
    }

    button {
      padding: 10px 20px;
      background: rgba(255, 255, 255, 0.1);
      color: white;
      border: 1px solid rgba(255, 255, 255, 0.2);
      border-radius: 5px;
      cursor: pointer;
      transition: all 0.3s ease;
      font-family: 'Space Mono', monospace;
    }

    button:hover {
      background: rgba(255, 255, 255, 0.2);
    }

    .info-panel {
      position: fixed;
      top: 20px;
      left: 20px;
      color: white;
      background: rgba(0, 0, 0, 0.5);
      padding: 15px;
      border-radius: 10px;
      max-width: 300px;
      z-index: 100;
    }

    /* Zoom control */
    .zoom-controls {
      position: fixed;
      top: 20px;
      right: 20px;
      display: flex;
      flex-direction: column;
      gap: 10px;
      z-index: 100;
    }

    .planet-info {
      position: fixed;
      bottom: 80px;
      left: 0;
      width: 100%;
      display: flex;
      justify-content: center;
      z-index: 100;
    }

    .planet-info-box {
      background: rgba(0, 0, 0, 0.7);
      color: white;
      padding: 10px 20px;
      border-radius: 5px;
      max-width: 80%;
      text-align: center;
    }

    /* Responsive design */
    @media (max-width: 1200px) {
      .galaxy {
        transform: scale(0.8);
      }
    }

    @media (max-width: 992px) {
      .galaxy {
        transform: scale(0.6);
      }
    }

    @media (max-width: 768px) {
      .galaxy {
        transform: scale(0.4);
      }
      
      .info-panel {
        max-width: 200px;
        font-size: 0.8rem;
      }
    }
  </style>
</head>
<body>
  <!-- Bintang latar belakang -->
  <div class="stars"></div>

  <div class="galaxy">
    <div class="sun"></div>
    
    <!-- Mercury -->
    <div class="orbit" id="mercury-orbit">
      <div class="planet" id="mercury"></div>
    </div>
    
    <!-- Venus -->
    <div class="orbit" id="venus-orbit">
      <div class="planet" id="venus"></div>
    </div>
    
    <!-- Earth with Moon -->
    <div class="orbit" id="earth-orbit">
      <div class="planet" id="earth"></div>
      <div class="orbit" id="moon-orbit">
        <div class="planet" id="moon"></div>
      </div>
    </div>
    
    <!-- Mars -->
    <div class="orbit" id="mars-orbit">
      <div class="planet" id="mars"></div>
    </div>
    
    <!-- Jupiter -->
    <div class="orbit" id="jupiter-orbit">
      <div class="planet" id="jupiter"></div>
    </div>
    
    <!-- Saturn -->
    <div class="orbit" id="saturn-orbit">
      <div class="planet" id="saturn"></div>
    </div>
    
    <!-- Uranus -->
    <div class="orbit" id="uranus-orbit">
      <div class="planet" id="uranus"></div>
    </div>
    
    <!-- Neptune -->
    <div class="orbit" id="neptune-orbit">
      <div class="planet" id="neptune"></div>
    </div>
  </div>
  
  <div class="info-panel">
    <h2>Sistem Tata Surya Lengkap</h2>
    <p>Simulasi semua planet dalam tata surya kita dengan:</p>
    <ul>
      <li>8 planet dengan karakteristik unik</li>
      <li>Rotasi yang akurat</li>
      <li>Revolusi mengelilingi Matahari</li>
      <li>Fitur khusus seperti cincin Saturnus</li>
    </ul>
  </div>
  
  <div class="zoom-controls">
    <button id="zoomIn">Perbesar</button>
    <button id="zoomOut">Perkecil</button>
    <button id="resetZoom">Reset</button>
  </div>
  
  <div class="controls">
    <button id="pauseBtn">Jeda</button>
    <button id="speedBtn">Kecepatan 2x</button>
  </div>

  <div class="planet-info">
    <div class="planet-info-box" id="current-planet-info">
      Arahkan kursor ke planet untuk melihat informasi
    </div>
  </div>
  
  <script>
    document.addEventListener('DOMContentLoaded', function() {
      const galaxy = document.querySelector('.galaxy');
      const planets = document.querySelectorAll('.planet, .sun');
      const pauseBtn = document.getElementById('pauseBtn');
      const speedBtn = document.getElementById('speedBtn');
      const zoomInBtn = document.getElementById('zoomIn');
      const zoomOutBtn = document.getElementById('zoomOut');
      const resetZoomBtn = document.getElementById('resetZoom');
      const planetInfo = document.getElementById('current-planet-info');
      
      let isPaused = false;
      let isFast = false;
      let currentScale = 1;
      const scaleStep = 0.2;
      const maxScale = 2;
      const minScale = 0.5;
      
      // Generate stars
      const starsContainer = document.querySelector('.stars');
      const starCount = 300;
      
      for (let i = 0; i < starCount; i++) {
        const star = document.createElement('div');
        star.classList.add('star');
        
        const x = Math.random() * 100;
        const y = Math.random() * 100;
        const size = Math.random() * 2 + 1;
        const delay = Math.random() * 5;
        
        star.style.left = `${x}%`;
        star.style.top = `${y}%`;
        star.style.width = `${size}px`;
        star.style.height = `${size}px`;
        star.style.animationDelay = `${delay}s`;
        
        starsContainer.appendChild(star);
      }
      
      // Planet data for info display
      const planetData = {
        'sun': {
          name: 'Matahari',
          desc: 'Bintang pusat tata surya kita. Suhu permukaan ~5,500°C',
          type: 'Bintang'
        },
        'mercury': {
          name: 'Merkurius',
          desc: 'Planet terkecil dan terdekat dari Matahari. Tidak memiliki bulan.',
          type: 'Planet Kebumian'
        },
        'venus': {
          name: 'Venus',
          desc: 'Planet terpanas dengan atmosfer tebal CO₂. Rotasi sangat lambat.',
          type: 'Planet Kebumian'
        },
        'earth': {
          name: 'Bumi',
          desc: 'Planet kita dengan air cair dan kehidupan. Memiliki 1 bulan.',
          type: 'Planet Kebumian'
        },
        'mars': {
          name: 'Mars',
          desc: 'Planet merah dengan gunung tertinggi di tata surya. Memiliki 2 bulan kecil.',
          type: 'Planet Kebumian'
        },
        'jupiter': {
          name: 'Jupiter',
          desc: 'Planet terbesar dengan 79 bulan. Memiliki Bintik Merah Raksasa.',
          type: 'Planet Raksasa Gas'
        },
        'saturn': {
          name: 'Saturnus',
          desc: 'Dikenal dengan cincinnya yang spektakuler. Memiliki 82 bulan.',
          type: 'Planet Raksasa Gas'
        },
        'uranus': {
          name: 'Uranus',
          desc: 'Planet raksasa es dengan rotasi miring. Memiliki 27 bulan.',
          type: 'Planet Raksasa Es'
        },
        'neptune': {
          name: 'Neptunus',
          desc: 'Planet terjauh dengan angin terkuat. Memiliki 14 bulan.',
          type: 'Planet Raksasa Es'
        },
        'moon': {
          name: 'Bulan',
          desc: 'Satelit alam Bumi. Periode orbit ~27.3 hari.',
          type: 'Satelit Alam'
        }
      };
      
      // Pause/resume animation
      pauseBtn.addEventListener('click', function() {
        isPaused = !isPaused;
        
        const animatedElements = document.querySelectorAll('[class*="orbit"], .planet, .sun');
        
        if (isPaused) {
          animatedElements.forEach(el => {
            el.style.animationPlayState = 'paused';
          });
          pauseBtn.textContent = 'Lanjutkan';
        } else {
          animatedElements.forEach(el => {
            el.style.animationPlayState = 'running';
          });
          pauseBtn.textContent = 'Jeda';
        }
      });
      
      // Speed control
      speedBtn.addEventListener('click', function() {
        isFast = !isFast;
        
        const animatedElements = document.querySelectorAll('[class*="orbit"], .planet, .sun');
        
        if (isFast) {
          animatedElements.forEach(el => {
            el.style.animationDuration = getHalfDuration(el.style.animationDuration);
          });
          speedBtn.textContent = 'Kecepatan Normal';
        } else {
          animatedElements.forEach(el => {
            el.style.animationDuration = getDoubleDuration(el.style.animationDuration);
          });
          speedBtn.textContent = 'Kecepatan 2x';
        }
      });
      
      // Zoom controls
      zoomInBtn.addEventListener('click', function() {
        if (currentScale < maxScale) {
          currentScale += scaleStep;
          galaxy.style.transform = `scale(${currentScale})`;
        }
      });
      
      zoomOutBtn.addEventListener('click', function() {
        if (currentScale > minScale) {
          currentScale -= scaleStep;
          galaxy.style.transform = `scale(${currentScale})`;
        }
      });
      
      resetZoomBtn.addEventListener('click', function() {
        currentScale = 1;
        galaxy.style.transform = `scale(${currentScale})`;
      });
      
      // Planet hover info
      planets.forEach(planet => {
        planet.addEventListener('mouseover', function() {
          const planetId = planet.id;
          if (planetData[planetId]) {
            planetInfo.innerHTML = `
              <h3>${planetData[planetId].name}</h3>
              <p><em>${planetData[planetId].type}</em></p>
              <p>${planetData[planetId].desc}</p>
            `;
          }
        });
        
        planet.addEventListener('mouseout', function() {
          planetInfo.textContent = 'Arahkan kursor ke planet untuk melihat informasi';
        });
      });
      
      // Helper functions
      function getHalfDuration(duration) {
        if (!duration) return '';
        const num = parseFloat(duration);
        const unit = duration.match(/[a-zA-Z]+/)[0];
        return (num / 2) + unit;
      }
      
      function getDoubleDuration(duration) {
        if (!duration) return '';
        const num = parseFloat(duration);
        const unit = duration.match(/[a-zA-Z]+/)[0];
        return (num * 2) + unit;
      }
    });
  </script>
</body>
</html>

