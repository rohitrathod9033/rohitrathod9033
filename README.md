<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rohit Rathod - Full-Stack Developer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;800&family=Fira+Code:wght@400;700&display=swap" rel="stylesheet">
  <style>
    /* ------------------------------------- */
    /* GLOBAL STYLES & VARIABLES (LIGHT THEME) */
    /* ------------------------------------- */
    :root {
      --primary-color: #007bff;
      --secondary-color: #6c757d;
      --text-color: #212529;
      --bg-dark: #ffffff;
      --bg-light: #f8f9fa;
      --accent-color: #dc3545;
      --glow-color: #dee2e6;
      --font-family-body: 'Poppins', sans-serif;
      --font-family-code: 'Fira Code', monospace;
    }

    body {
      margin: 0;
      font-family: var(--font-family-body);
      color: var(--text-color);
      background-color: var(--bg-dark);
      overflow-x: hidden;
      line-height: 1.6;
    }

    /* Scrollbar styling for a futuristic look */
    ::-webkit-scrollbar {
      width: 8px;
    }
    ::-webkit-scrollbar-track {
      background: var(--bg-light);
    }
    ::-webkit-scrollbar-thumb {
      background: var(--primary-color);
      border-radius: 4px;
    }

    .container {
      max-width: 1200px;
      margin: auto;
      padding: 0 20px;
    }

    h1, h2, h3 {
      font-weight: 800;
      color: var(--text-color);
      text-transform: uppercase;
      letter-spacing: 2px;
      text-shadow: none; /* Removed for a cleaner look */
    }

    section {
      padding: 80px 0;
      position: relative;
      z-index: 2;
    }

    /* ------------------------------------- */
    /* HERO SECTION (CANVAS + TYPING EFFECT) */
    /* ------------------------------------- */
    .hero {
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      position: relative;
      overflow: hidden;
      background-color: var(--bg-dark);
    }

    #hero-canvas {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
    }

    .hero-content {
      position: relative;
      z-index: 2;
    }

    .hero-content h1 {
      font-size: clamp(2rem, 8vw, 4rem);
      margin: 0;
      opacity: 0;
      animation: fadeIn 1s forwards 0.5s ease-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(-20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    .typing-container {
      position: relative;
      height: 60px;
      display: flex;
      align-items: center;
    }
    
    #typing-text {
      font-family: var(--font-family-code);
      font-size: clamp(1rem, 2.5vw, 1.8rem);
      color: var(--primary-color);
      font-weight: 700;
      white-space: nowrap;
      overflow: hidden;
      border-right: 2px solid rgba(0, 123, 255, 0.75);
      animation: blink-caret 1s step-end infinite;
    }

    @keyframes blink-caret {
      from, to { border-color: transparent }
      50% { border-color: var(--primary-color) }
    }

    .profile-badges {
      margin-top: 20px;
      display: flex;
      justify-content: center;
      gap: 15px;
      flex-wrap: wrap;
    }

    /* ------------------------------------- */
    /* SCROLL-TRIGGERED ANIMATIONS */
    /* ------------------------------------- */
    .fade-in-up {
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94), transform 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    }

    .fade-in-up.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* ------------------------------------- */
    /* ABOUT ME SECTION */
    /* ------------------------------------- */
    .about-me {
      background-color: var(--bg-light);
    }

    .about-me h2 {
      text-align: center;
      margin-bottom: 40px;
      font-size: clamp(1.8rem, 4vw, 3rem);
    }
    
    .about-me ul {
      list-style-type: '�';
      padding-left: 20px;
      font-size: 1.1rem;
      max-width: 800px;
      margin: auto;
    }
    .about-me ul li {
      margin-bottom: 15px;
    }
    .about-me ul li::marker {
      color: var(--primary-color);
    }
    .about-me ul li strong {
      color: var(--text-color);
    }
    .about-me ul li a {
      color: var(--primary-color);
      text-decoration: none;
      transition: color 0.3s ease;
    }
    .about-me ul li a:hover {
      color: var(--accent-color);
    }
    
    /* ------------------------------------- */
    /* TECH STACK (ANIMATED ICONS) */
    /* ------------------------------------- */
    .tech-stack {
      text-align: center;
    }
    .tech-stack h2 {
      margin-bottom: 40px;
      font-size: clamp(1.8rem, 4vw, 3rem);
    }
    .tech-grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 30px;
    }
    .tech-item {
      width: 100px;
      height: 100px;
      background: var(--bg-dark);
      border: 1px solid var(--glow-color);
      border-radius: 12px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      cursor: pointer;
    }
    .tech-item:hover {
      transform: translateY(-5px) scale(1.05);
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
    }
    .tech-item img {
      width: 60px;
      height: 60px;
      object-fit: contain;
    }
    .tech-item span {
      margin-top: 10px;
      font-weight: 600;
      text-transform: uppercase;
      font-size: 0.8rem;
    }

    /* ------------------------------------- */
    /* GITHUB STATS & FOOTER */
    /* ------------------------------------- */
    .stats-section {
      background-color: var(--bg-light);
      text-align: center;
    }
    .stats-section:nth-of-type(odd) {
      background-color: var(--bg-dark);
    }
    .stats-grid {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 20px;
      margin-top: 40px;
    }
    .stats-grid img {
      max-width: 100%;
      height: auto;
      filter: drop-shadow(0 4px 8px rgba(0,0,0,0.1));
    }
    
    .snake-animation {
      margin-top: 60px;
    }

    .footer {
      background-color: var(--bg-light);
      text-align: center;
      padding-top: 40px;
      border-top: 1px solid var(--glow-color);
    }
    .footer p {
      color: var(--secondary-color);
    }
  </style>
</head>
<body>

  <!-- HERO SECTION with waving emoji, typing effect, and profile badges -->
  <header class="hero">
    <canvas id="hero-canvas"></canvas>
    <div class="hero-content">
      <h1>
        <img src="https://raw.githubusercontent.com/rohitrathod9033/rohitrathod9033/output/wave.gif" alt="wave" width="34px" />
        Hi, I'm Rohit Rathod
      </h1>
      <div class="typing-container">
        <span id="typing-text"></span>
      </div>
      <div class="profile-badges">
        <img src="https://komarev.com/ghpvc/?username=rohitrathod9033&label=Profile+views&color=0e75b6&style=flat" alt="profile views" />
        <img src="https://img.shields.io/github/followers/rohitrathod9033?label=Followers&style=social" alt="followers" />
        <img src="https://img.shields.io/github/stars/rohitrathod9033?label=Stars&style=social" alt="stars" />
      </div>
    </div>
  </header>

  <!-- ABOUT ME SECTION -->
  <section class="about-me">
    <div class="container fade-in-up">
      <h2>🚀 About Me</h2>
      <ul>
        <li>🔭 Currently working on **E-Learning Portal**</li>
        <li>🌟 Built: <a href="https://astrotalk-clone.netlify.app/">Astrotalk Clone</a></li>
        <li>💬 Ask me about **MERN Stack**</li>
        <li>📫 Reach me: **rohitrathod60371@gmail.com**</li>
        <li>⚡ Fun fact: *I think I'm funny 😄*</li>
      </ul>
    </div>
  </section>

  <!-- TECH STACK SECTION (Custom Animated Icons) -->
  <section class="tech-stack">
    <div class="container fade-in-up">
      <h2>🛠 Tech Stack</h2>
      <div class="tech-grid">
        <div class="tech-item">
          <img src="https://img.icons8.com/color/48/000000/javascript--v1.png" alt="JavaScript">
          <span>JavaScript</span>
        </div>
        <div class="tech-item">
          <img src="https://img.icons8.com/color/48/000000/react-native.png" alt="React">
          <span>React</span>
        </div>
        <div class="tech-item">
          <img src="https://img.icons8.com/color/48/000000/nodejs.png" alt="Node.js">
          <span>Node.js</span>
        </div>
        <div class="tech-item">
          <img src="https://img.icons8.com/color/48/000000/express.png" alt="Express">
          <span>Express</span>
        </div>
        <div class="tech-item">
          <img src="https://img.icons8.com/color/48/000000/mongodb.png" alt="MongoDB">
          <span>MongoDB</span>
        </div>
        <div class="tech-item">
          <img src="https://img.icons8.com/color/48/000000/tailwindcss.png" alt="Tailwind">
          <span>Tailwind</span>
        </div>
        <div class="tech-item">
          <img src="https://img.icons8.com/color/48/000000/amazon-web-services.png" alt="AWS">
          <span>AWS</span>
        </div>
        <div class="tech-item">
          <img src="https://img.icons8.com/color/48/000000/docker.png" alt="Docker">
          <span>Docker</span>
        </div>
        <div class="tech-item">
          <img src="https://img.icons8.com/color/48/000000/git.png" alt="Git">
          <span>Git</span>
        </div>
      </div>
    </div>
  </section>

  <!-- GITHUB STATS SECTION -->
  <section class="stats-section">
    <div class="container fade-in-up">
      <h2>📊 GitHub Stats</h2>
      <div class="stats-grid">
        <img src="https://github-readme-stats.vercel.app/api?username=rohitrathod9033&show_icons=true&theme=default&hide_border=true" height="160" alt="github-stats"/>
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=rohitrathod9033&layout=compact&theme=default&hide_border=true" height="160" alt="top-langs"/>
      </div>
    </div>
  </section>

  <!-- STREAK & TROPHIES SECTION -->
  <section class="stats-section">
    <div class="container fade-in-up">
      <h2>🔥 Streak & Trophies</h2>
      <div class="stats-grid">
        <img src="https://github-readme-streak-stats.herokuapp.com?user=rohitrathod9033&theme=default&hide_border=true" alt="streak" />
        <img src="https://github-profile-trophy.vercel.app/?username=rohitrathod9033&theme=default&no-frame=true" alt="trophies" />
      </div>
    </div>
  </section>

  <!-- SNAKE ANIMATION -->
  <section class="stats-section snake-animation">
    <div class="container fade-in-up">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake-dark.svg" />
        <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake.svg" />
        <img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake.svg" />
      </picture>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <p>Thanks for visiting — let’s build something awesome! 🚀</p>
  </footer>

  <script>
    // -------------------------------------
    // JAVASCRIPT FOR DYNAMIC EFFECTS
    // -------------------------------------
    document.addEventListener('DOMContentLoaded', () => {

      // --- Typing Effect for Hero Section ---
      const typingTextElement = document.getElementById('typing-text');
      const phrases = [
        "Full-Stack JavaScript Developer",
        "MERN Stack | MongoDB Express React Node",
        "Building E-Learning Portal",
        "Open to Collaborations"
      ];
      let phraseIndex = 0;
      let charIndex = 0;
      let isDeleting = false;
      const typingSpeed = 70;
      const deletingSpeed = 40;
      const pauseBetweenPhrases = 1200;

      function type() {
        const currentPhrase = phrases[phraseIndex];
        let displayText = currentPhrase.substring(0, charIndex);

        typingTextElement.textContent = displayText;

        if (!isDeleting) {
          if (charIndex < currentPhrase.length) {
            charIndex++;
            setTimeout(type, typingSpeed);
          } else {
            isDeleting = true;
            setTimeout(type, pauseBetweenPhrases);
          }
        } else {
          if (charIndex > 0) {
            charIndex--;
            setTimeout(type, deletingSpeed);
          } else {
            isDeleting = false;
            phraseIndex = (phraseIndex + 1) % phrases.length;
            setTimeout(type, 500);
          }
        }
      }
      type();

      // --- Particle Background on Canvas ---
      const canvas = document.getElementById('hero-canvas');
      const ctx = canvas.getContext('2d');
      let particles = [];
      let mouse = { x: null, y: null };
      
      const resizeCanvas = () => {
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
      }
      resizeCanvas();
      window.addEventListener('resize', resizeCanvas);

      canvas.addEventListener('mousemove', (e) => {
        mouse.x = e.x;
        mouse.y = e.y;
      });

      canvas.addEventListener('mouseleave', () => {
        mouse.x = null;
        mouse.y = null;
      });

      class Particle {
        constructor(x, y, size, color, speedX, speedY) {
          this.x = x;
          this.y = y;
          this.size = size;
          this.color = color;
          this.speedX = speedX;
          this.speedY = speedY;
        }
        update() {
          this.x += this.speedX;
          this.y += this.speedY;
          if (this.size > 0.2) this.size -= 0.1;
        }
        draw() {
          ctx.fillStyle = this.color;
          ctx.beginPath();
          ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
          ctx.fill();
        }
      }

      function createParticles() {
        for (let i = 0; i < 100; i++) {
          particles.push(new Particle(
            Math.random() * canvas.width,
            Math.random() * canvas.height,
            Math.random() * 2 + 0.5,
            'rgba(0, 0, 0, 0.1)',
            (Math.random() - 0.5) * 0.2,
            (Math.random() - 0.5) * 0.2
          ));
        }
      }

      function handleParticles() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        for (let i = 0; i < particles.length; i++) {
          let p = particles[i];
          p.update();
          p.draw();
          if (p.size <= 0.2) {
            particles.splice(i, 1);
            particles.push(new Particle(
              Math.random() * canvas.width,
              Math.random() * canvas.height,
              Math.random() * 2 + 0.5,
              'rgba(0, 0, 0, 0.1)',
              (Math.random() - 0.5) * 0.2,
              (Math.random() - 0.5) * 0.2
            ));
            i--;
          }
        }
      }

      function animate() {
        handleParticles();
        requestAnimationFrame(animate);
      }
      createParticles();
      animate();
      
      // --- Scroll-Triggered Animations ---
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('visible');
          } else {
            // Optional: to animate out when scrolling back up
            // entry.target.classList.remove('visible');
          }
        });
      }, {
        threshold: 0.1
      });

      document.querySelectorAll('.fade-in-up').forEach(element => {
        observer.observe(element);
      });
      
    });
  </script>

</body>
</html>
�
