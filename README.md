<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Jamshid Zayniyev · Frontend Engineer Portfolio</title>
  <!-- Google Fonts (optional but modern) -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
  <!-- Font Awesome 6 (free CDN for clean icons, just in case, but keeping original icon structure) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #f9fafc;
      font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', Roboto, Helvetica, sans-serif;
      color: #1e293b;
      line-height: 1.5;
      padding: 2rem 1.5rem;
    }

    .container {
      max-width: 1280px;
      margin: 0 auto;
      background: white;
      border-radius: 2rem;
      box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.08);
      padding: 2rem 2rem 2.5rem 2rem;
      transition: all 0.2s;
    }

    /* headings */
    h1, h2, h3 {
      font-weight: 700;
      letter-spacing: -0.02em;
    }

    h1 {
      font-size: 2.5rem;
      background: linear-gradient(135deg, #0f172a, #2563eb);
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
      margin-bottom: 0.5rem;
    }

    h3 {
      color: #334155;
      font-weight: 500;
      margin-bottom: 1rem;
    }

    /* profile view badge row */
    .profile-row {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      margin-top: 0.5rem;
      margin-bottom: 1.5rem;
    }

    /* right image (floated originally, but we use flex for responsiveness) */
    .hero-section {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      gap: 2rem;
      margin: 1.5rem 0 2rem 0;
      align-items: center;
    }

    .hero-text {
      flex: 2;
      min-width: 220px;
    }

    .hero-image {
      flex: 1;
      text-align: center;
      min-width: 200px;
    }

    .hero-image img {
      max-width: 100%;
      width: 360px;
      border-radius: 28px;
      box-shadow: 0 25px 40px -12px rgba(0, 0, 0, 0.2);
      transition: transform 0.2s ease;
    }

    .hero-image img:hover {
      transform: scale(1.02);
    }

    /* section styling */
    .section {
      margin: 2.5rem 0 2rem 0;
    }

    .section-title {
      font-size: 1.8rem;
      font-weight: 700;
      border-left: 5px solid #2563eb;
      padding-left: 1rem;
      margin-bottom: 1.6rem;
      color: #0f172a;
    }

    /* ========== HORIZONTAL TECH STACK ROW ========== */
    /* TECH STACK: yonma-yon, wrap, gap, centered */
    .tech-grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 2rem;
      row-gap: 2rem;
      align-items: center;
      background: #f8fafc;
      padding: 2rem 1rem;
      border-radius: 2rem;
      margin-top: 0.5rem;
    }

    .tech-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      background: white;
      width: 90px;
      padding: 0.9rem 0.5rem;
      border-radius: 1.2rem;
      box-shadow: 0 5px 12px rgba(0, 0, 0, 0.03);
      transition: all 0.2s;
      border: 1px solid #eef2ff;
    }

    .tech-item:hover {
      transform: translateY(-5px);
      border-color: #bfdbfe;
      box-shadow: 0 12px 20px -12px rgba(37, 99, 235, 0.2);
    }

    .tech-item img {
      width: 48px;
      height: 48px;
      object-fit: contain;
      margin-bottom: 0.5rem;
    }

    .tech-item span {
      font-size: 0.75rem;
      font-weight: 500;
      color: #1e293b;
      letter-spacing: -0.2px;
    }

    /* ========== SOCIAL CONNECT : yonma-yon, inline-flex ========== */
    .social-links-horizontal {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      align-items: center;
      justify-content: flex-start;
      background: #ffffff;
      padding: 0.75rem 0 1rem 0;
    }

    .social-icon {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: #f1f5f9;
      padding: 0.6rem 1.4rem;
      border-radius: 60px;
      transition: all 0.2s;
      text-decoration: none;
      color: #1e293b;
      font-weight: 500;
      border: 1px solid #e2e8f0;
    }

    .social-icon img {
      width: 28px;
      height: 28px;
      transition: transform 0.1s;
    }

    /* fallback for img if they use original social icons */
    .social-icon i {
      font-size: 1.8rem;
      color: #0f172a;
    }

    .social-icon:hover {
      background: #2563eb;
      border-color: #2563eb;
      color: white;
      transform: translateY(-3px);
    }

    .social-icon:hover i,
    .social-icon:hover span {
      color: white;
    }

    .social-icon span {
      font-size: 0.95rem;
      font-weight: 500;
    }

    /* for the linkedin original svg override, but we keep both styles */
    .social-icon .custom-icon {
      width: 28px;
      height: 28px;
      filter: none;
    }

    /* Stats sections (inline but not breaking tech/social) */
    .stats-wrapper {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      justify-content: space-between;
      margin-top: 1.5rem;
    }

    .stats-card {
      background: #f8fafc;
      border-radius: 1.5rem;
      padding: 1rem;
      flex: 1;
      min-width: 240px;
      text-align: center;
      box-shadow: 0 2px 5px rgba(0,0,0,0.02);
    }

    .stats-card img {
      max-width: 100%;
      height: auto;
      border-radius: 12px;
    }

    hr {
      margin: 1.5rem 0;
      border: none;
      border-top: 2px dotted #e2e8f0;
    }

    .focus-list {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      list-style: none;
      margin: 1rem 0;
    }

    .focus-list li {
      background: #eef2ff;
      padding: 0.4rem 1rem;
      border-radius: 30px;
      font-size: 0.85rem;
      font-weight: 500;
      color: #1e40af;
    }

    .current-goal {
      background: linear-gradient(115deg, #f1f5f9, #ffffff);
      padding: 1.2rem 1.5rem;
      border-radius: 1.5rem;
      border-left: 4px solid #2563eb;
      font-weight: 500;
    }

    @media (max-width: 780px) {
      .container {
        padding: 1.5rem;
      }
      .tech-item {
        width: 75px;
      }
      .tech-item img {
        width: 40px;
        height: 40px;
      }
      .social-icon {
        padding: 0.4rem 1rem;
      }
      .hero-section {
        flex-direction: column;
      }
      h1 {
        font-size: 2rem;
      }
    }
  </style>
</head>
<body>
<div class="container">
  
  <!-- Header: Hi I'm Jamshid -->
  <h1 align="center">Hi 👋, I'm Jamshid Zayniyev</h1>
  <h3 align="center">Frontend Engineer | React.js • Next.js • TypeScript • Scalable Web Applications</h3>
  <p align="center" style="max-width: 700px; margin: 0.5rem auto 0 auto; color: #475569;">
    Building high-performance, scalable, and user-focused digital products with modern frontend architecture.
  </p>

  <!-- Profile views row (left side) + optional but keep style -->
  <div class="profile-row">
    <p align="left">
      <img src="https://komarev.com/ghpvc/?username=jamshid-zayniyev&label=Profile%20Views&color=0e75b6&style=flat" alt="jamshid-zayniyev" />
    </p>
  </div>

  <!-- Hero: text + image right (but we use modern flex, image stays right side visually) -->
  <div class="hero-section">
    <div class="hero-text">
      <h2 style="font-size: 1.6rem; margin-bottom: 0.5rem;">🚀 About Me</h2>
      <ul style="list-style-type: none; margin-top: 0.5rem;">
        <li>💼 Frontend Engineer with 5+ years of experience building production-ready applications</li>
        <li>🔭 Currently working at <strong>ATS</strong></li>
        <li>⚡ Specialized in <strong>React.js, Next.js, TypeScript, Frontend Architecture</strong></li>
        <li>🌱 Currently exploring <strong>React Native</strong> and advanced backend systems with <strong>Node.js</strong></li>
        <li>🧠 Strong focus on performance optimization, scalable UI systems, and clean code architecture</li>
        <li>💬 Ask me about <strong>React, TypeScript, Next.js, Node.js, Frontend System Design</strong></li>
        <li>🌍 Open to international remote opportunities in the <strong>USA</strong> and <strong>Europe</strong></li>
        <li>📫 Reach me at: <strong>jamshidzayniev10@gmail.com</strong></li>
        <li>⚡ Fun fact: <strong>I believe good code should be simple, scalable, and slightly funny</strong></li>
      </ul>
    </div>
    <div class="hero-image">
      <img alt="Coding" src="https://user-images.githubusercontent.com/69011963/137184767-79a13ec7-1bb3-4341-a6da-3a149c9c159a.gif" />
    </div>
  </div>

  <!-- 🛠 Tech Stack section: yonma-yon chiqsin (horizontal, wrap) -->
  <div class="section">
    <h2 class="section-title">🛠 Tech Stack</h2>
    <div class="tech-grid">
      <!-- React -->
      <div class="tech-item">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg" alt="react" />
        <span>React</span>
      </div>
      <!-- Next.js -->
      <div class="tech-item">
        <img src="https://cdn.worldvectorlogo.com/logos/nextjs-2.svg" alt="nextjs" style="background: #0f172a; padding: 4px; border-radius: 12px;" />
        <span>Next.js</span>
      </div>
      <!-- TypeScript -->
      <div class="tech-item">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" alt="typescript" />
        <span>TypeScript</span>
      </div>
      <!-- JavaScript -->
      <div class="tech-item">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="javascript" />
        <span>JavaScript</span>
      </div>
      <!-- Redux -->
      <div class="tech-item">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/redux/redux-original.svg" alt="redux" />
        <span>Redux</span>
      </div>
      <!-- TailwindCSS -->
      <div class="tech-item">
        <img src="https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg" alt="tailwind" />
        <span>Tailwind</span>
      </div>
      <!-- Sass -->
      <div class="tech-item">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/sass/sass-original.svg" alt="sass" />
        <span>Sass</span>
      </div>
      <!-- Node.js -->
      <div class="tech-item">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="nodejs" />
        <span>Node.js</span>
      </div>
      <!-- MongoDB -->
      <div class="tech-item">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="mongodb" />
        <span>MongoDB</span>
      </div>
      <!-- Git -->
      <div class="tech-item">
        <img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="git" />
        <span>Git</span>
      </div>
      <!-- Figma -->
      <div class="tech-item">
        <img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt="figma" />
        <span>Figma</span>
      </div>
    </div>
  </div>

  <!-- 🌐 Connect With Me: yonma-yon chiqsin , original iconlar bilan-->
  <div class="section">
    <h2 class="section-title">🌐 Connect With Me</h2>
    <div class="social-links-horizontal">
      <!-- LinkedIn: using original icons from linkedin alt but we make sure images appear inline -->
      <a href="https://linkedin.com/in/jamshid-zayniev-091b66266" target="_blank" class="social-icon">
        <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="linkedin" width="28" height="28" style="filter: none;" />
        <span>LinkedIn</span>
      </a>
      <!-- Facebook -->
      <a href="https://fb.com/zayniyev" target="_blank" class="social-icon">
        <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/facebook.svg" alt="facebook" width="28" height="28" />
        <span>Facebook</span>
      </a>
      <!-- Instagram -->
      <a href="https://instagram.com/jamzayn10" target="_blank" class="social-icon">
        <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/instagram.svg" alt="instagram" width="28" height="28" />
        <span>Instagram</span>
      </a>
      <!-- optional additional consistency: maybe add custom mail? but we keep original three exactly as requested -->
    </div>
  </div>

  <!-- 📈 GitHub Analytics: three cards inline with flex wrap -->
  <div class="section">
    <h2 class="section-title">📈 GitHub Analytics</h2>
    <div class="stats-wrapper">
      <div class="stats-card">
        <img src="https://github-readme-stats.vercel.app/api/top-langs?username=jamshid-zayniyev&show_icons=true&locale=en&layout=compact" alt="top-langs" style="max-width: 100%;" />
      </div>
      <div class="stats-card">
        <img src="https://github-readme-stats.vercel.app/api?username=jamshid-zayniyev&show_icons=true&locale=en" alt="stats" />
      </div>
      <div class="stats-card">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=jamshid-zayniyev" alt="streak" />
      </div>
    </div>
  </div>

  <!-- 🎯 Professional Focus (horizontal style list) -->
  <div class="section">
    <h2 class="section-title">🎯 Professional Focus</h2>
    <ul class="focus-list">
      <li>Scalable Frontend Architecture</li>
      <li>Enterprise-Level Web Applications</li>
      <li>Performance Optimization</li>
      <li>Clean Code & Maintainability</li>
      <li>UI/UX Driven Development</li>
      <li>SEO Optimization</li>
      <li>Responsive and Accessible Design</li>
      <li>Full Product Ownership</li>
    </ul>
  </div>

  <!-- 📌 Current Goal -->
  <div class="section">
    <h2 class="section-title">📌 Current Goal</h2>
    <div class="current-goal">
      Building impactful products, leading frontend systems, and contributing to global remote teams with engineering excellence.
    </div>
  </div>

  <hr />
  <p align="center" style="color: #5b6e8c; font-size: 0.8rem; margin-top: 0.5rem;">
    ⚡ Jamshid Zayniyev — React • Next.js • TypeScript Architect
  </p>
</div>
</body>
</html>
