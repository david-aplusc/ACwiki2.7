<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>A+C Animation Studios Wiki</title>

  <!-- Google Fonts - Fredoka for a rounded, plasticine feel -->
  <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@300..700&display=swap" rel="stylesheet">
  <!-- Bootstrap + Font-Awesome -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

  <style>
    :root {
      /* Plasticine Clay Palette */
      --clay-red: #E74C3C;
      --clay-blue: #3498DB;
      --clay-yellow: #F1C40F;
      --clay-green: #27AE60;
      --clay-orange: #E67E22;
      --clay-purple: #9B59B6;
      --clay-white: #FDFEFE;
      --clay-base: #ECF0F1;
      
      --text-dark: #2C3E50;
      --text-medium: #7F8C8D;
      
      --clay-shadow: 8px 8px 16px rgba(0,0,0,0.1), -8px -8px 16px rgba(255,255,255,0.7);
      --clay-shadow-inset: inset 4px 4px 8px rgba(0,0,0,0.1), inset -4px -4px 8px rgba(255,255,255,0.7);
      --clay-radius: 20px;
      --clay-transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    }

    body {
      font-family: 'Fredoka', sans-serif;
      background-color: #f0f2f5;
      background-image: radial-gradient(#d1d9e6 1px, transparent 1px);
      background-size: 20px 20px;
      color: var(--text-dark);
      padding-top: 120px;
      min-height: 100vh;
    }

    /* HEADER */
    .wiki-header {
      position: fixed;
      top: 20px; left: 20px; right: 20px;
      height: 80px;
      display: flex;
      align-items: center;
      justify-content: center;
      background: var(--clay-white);
      border-radius: var(--clay-radius);
      box-shadow: var(--clay-shadow);
      z-index: 1050;
      border: 4px solid var(--clay-white);
    }
    .logo-center {
      display: flex;
      align-items: center;
      gap: 1rem;
    }
    .studio-logo-svg { height: 45px; filter: drop-shadow(0 2px 4px rgba(0,0,0,.1)); }
    .studio-text h1 { font-size: 1.8rem; font-weight: 600; margin: 0; letter-spacing: -0.5px; }
    .studio-text .plus { color: var(--clay-red); font-weight: 700; }

    /* NAV */
    .nav-container {
      position: fixed;
      top: 120px; left: 20px; right: 20px;
      z-index: 1040;
    }
    .nav-sections { 
      display: flex; 
      justify-content: center; 
      gap: 1.5rem; 
      padding: 1rem;
      background: rgba(255,255,255,0.5);
      backdrop-filter: blur(10px);
      border-radius: var(--clay-radius);
      box-shadow: var(--clay-shadow-inset);
    }
    .nav-section { position: relative; }
    .nav-section-title {
      font-weight: 600; cursor: pointer; padding: 0.8rem 1.5rem;
      color: var(--text-dark);
      background: var(--clay-white);
      border-radius: 15px;
      box-shadow: var(--clay-shadow);
      transition: var(--clay-transition);
      border: 2px solid transparent;
      user-select: none;
    }
    .nav-section-title:hover {
      transform: scale(1.05) translateY(-2px);
      box-shadow: 10px 10px 20px rgba(0,0,0,0.15);
    }
    .nav-section-title::after { content: '▼'; margin-left: .6rem; font-size: .7rem; transition: transform 0.3s; }
    .nav-section.open .nav-section-title::after { transform: rotate(180deg); }
    
    .nav-items { 
      display: none; 
      position: absolute;
      top: calc(100% + 10px);
      left: 0;
      min-width: 200px;
      background: var(--clay-white);
      border-radius: 15px;
      box-shadow: 15px 15px 30px rgba(0,0,0,0.2);
      padding: 1rem;
      flex-direction: column;
      z-index: 1100;
      animation: popIn 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    }
    @keyframes popIn {
      from { transform: scale(0.8) translateY(-10px); opacity: 0; }
      to { transform: scale(1) translateY(0); opacity: 1; }
    }
    .nav-items.show { display: flex; }
    .nav-items li { list-style: none; }
    .nav-link {
      color: var(--text-medium); 
      text-decoration: none; 
      padding: 0.6rem 1rem;
      display: block;
      transition: var(--clay-transition);
      border-radius: 10px;
      margin-bottom: 5px;
    }
    .nav-link:hover { 
      background: var(--clay-base);
      color: var(--clay-blue);
      transform: translateX(5px);
    }
    .nav-link.active { 
      background: var(--clay-blue);
      color: white;
      font-weight: 600;
    }

    /* MAIN */
    .main-content { max-width: 1000px; margin: 180px auto 100px; padding: 0 20px; }
    .wiki-section { display: none; animation: slideUp 0.5s ease-out; }
    .wiki-section.active { display: block; }
    @keyframes slideUp { 
      from { opacity: 0; transform: translateY(40px) scale(0.95); } 
      to { opacity: 1; transform: translateY(0) scale(1); } 
    }

    /* CLAY CARDS */
    .clay-card {
      position: relative;
      padding: 3rem;
      margin-bottom: 3rem;
      border-radius: 40px 25px 35px 30px; /* Irregular corners */
      z-index: 1;
    }

    /* The actual clay body with texture */
    .clay-card::after {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0; bottom: 0;
      background: var(--clay-white);
      border-radius: inherit;
      box-shadow: var(--clay-shadow);
      border: 8px solid var(--clay-white);
      filter: url(#clay-texture);
      z-index: -1;
    }
    
    /* Simulate thumbprints/imperfections */
    .clay-card::before {
      content: '';
      position: absolute;
      top: -20px; right: -20px;
      width: 80px; height: 80px;
      background: rgba(0,0,0,0.03);
      border-radius: 50%;
      filter: blur(15px);
      box-shadow: inset 2px 2px 5px rgba(0,0,0,0.1);
      z-index: 0;
    }
    
    .clay-card h2 {
      font-weight: 700;
      font-size: 2.8rem;
      margin-bottom: 2rem;
      color: var(--clay-red);
      text-shadow: 3px 3px 0px rgba(0,0,0,0.05);
      border-bottom: 8px solid var(--clay-yellow);
      display: inline-block;
      border-radius: 12px;
      padding-bottom: 5px;
      transform: rotate(-1deg); /* Slight rotation for stop-motion feel */
    }

    /* IFRAME */
    .doc-embed {
      width: 100%; height: 700px; border: 8px solid var(--clay-base);
      border-radius: 20px;
      box-shadow: inset 5px 5px 15px rgba(0,0,0,0.1);
      background: white;
    }

    /* VIDEO */
    .video-container {
      position: relative;
      padding-bottom: 56.25%;
      height: 0;
      overflow: hidden;
      background: #000;
      border-radius: 20px;
      margin-top: 1.5rem;
      border: 8px solid var(--clay-base);
      box-shadow: var(--clay-shadow);
    }
    .video-container iframe {
      position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0;
    }

    /* FOOTER */
    footer {
      text-align: center;
      padding: 4rem 2rem;
      color: var(--text-medium);
      font-size: 0.9rem;
    }

    /* RESPONSIVE */
    @media (max-width: 768px) {
      body { padding-top: 100px; }
      .nav-sections { flex-wrap: wrap; }
      .main-content { margin-top: 250px; }
      .clay-card { padding: 1.5rem; }
      .clay-card h2 { font-size: 1.8rem; }
    }
  </style>
</head>

<body>
  <!-- HEADER -->
  <header class="wiki-header">
    <div class="logo-center">
      <img src="https://aplusc.tv/wp-content/themes/a%2Bc-studios/assets/images/a+c-studios-logo-b.svg"
           alt="A+C Studios Logo" class="studio-logo-svg">
      <div class="studio-text">
        <h1>A<span class="plus">+</span>C Internal Wiki</h1>
      </div>
    </div>
  </header>

  <nav class="nav-container">
    <div class="nav-sections">
      <div class="nav-section">
        <div class="nav-section-title" onclick="toggleDropdown(this)">Rulebook</div>
        <ul class="nav-items">
          <li><a class="nav-link" href="#" onclick="showSection('house-docs', this)">House Docs</a></li>
          <li><a class="nav-link" href="#" onclick="showSection('health-safety', this)">Handbook</a></li>
          <li><a class="nav-link" href="#" onclick="showSection('working-with-minors', this)">Working with Minors</a></li>
          <li><a class="nav-link" href="#" onclick="showSection('ai-policy', this)">AI Policy</a></li>
        </ul>
      </div>
      <div class="nav-section">
        <div class="nav-section-title" onclick="toggleDropdown(this)">Production</div>
        <ul class="nav-items">
          <li><a class="nav-link" href="#" onclick="showSection('post-production', this)">Post-Production</a></li>
          <li><a class="nav-link" href="#" onclick="showSection('client-delivery', this)">Client Delivery</a></li>
        </ul>
      </div>
      <div class="nav-section">
        <div class="nav-section-title" onclick="toggleDropdown(this)">Finance</div>
        <ul class="nav-items">
          <li><a class="nav-link" href="#" onclick="showSection('invoicing-guide', this)">Invoicing</a></li>
        </ul>
      </div>
      <div class="nav-section">
        <div class="nav-section-title" onclick="toggleDropdown(this)">Knowledge</div>
        <ul class="nav-items">
          <li><a class="nav-link" href="#" onclick="showSection('brand-guidelines', this)">Brand</a></li>
          <li><a class="nav-link" href="#" onclick="showSection('company-history', this)">History</a></li>
          <li><a class="nav-link" href="#" onclick="showSection('locations-parking', this)">Locations & Parking</a></li>
          <li><a class="nav-link" href="#" onclick="showSection('welcome-video', this)">Welcome Video</a></li>
        </ul>
      </div>
    </div>
  </nav>

  <main class="main-content">
    <div class="wiki-section active" id="dashboard">
      <div class="clay-card">
        <h2>Welcome</h2>
        <p>Select a section from the navigation above to find studio information, policies, and production guides.</p>
        <div style="margin-top: 2rem; text-align: center;">
             <i class="fas fa-hand-holding-heart" style="font-size: 5rem; color: var(--clay-yellow); opacity: 0.3;"></i>
        </div>
      </div>
    </div>

    <!-- Rulebook Sections -->
    <div class="wiki-section" id="house-docs">
      <div class="clay-card">
        <h2>House Docs</h2>
        <iframe class="doc-embed" src="https://docs.google.com/document/d/e/2PACX-1vRMUd_6OdG-7c2Tz8hglkq3uPiCdbzfkUzyVaG5kxR1nptyu8EEIDv8FBoEJaz1gvo0CZsd3NA5uhoa/pub"></iframe>
      </div>
    </div>

    <div class="wiki-section" id="health-safety">
      <div class="clay-card">
        <h2>A+C Handbook</h2>
        <iframe class="doc-embed" src="https://docs.google.com/document/d/e/2PACX-1vSAF1Qr2I7LedCKv5Vg0Xn_tKJONlbhYTRtdUxRyKDz2ut9aaf3Dz8UQj3IOjMbEHP8LHHALTUAQaEA/pub"></iframe>
      </div>
    </div>

    <div class="wiki-section" id="working-with-minors">
      <div class="clay-card">
        <h2>Working with Minors</h2>
        <iframe class="doc-embed" src="https://docs.google.com/document/d/e/2PACX-1vT7KUJuEaddwspB2RberkAWF42LVCb42Bo1QdUy2_j5LXx0hECGJJPyEckSMVlcYKBmtvPHHxWCoExt/pub"></iframe>
      </div>
    </div>

    <div class="wiki-section" id="ai-policy">
      <div class="clay-card">
        <h2>AI Policy</h2>
        <iframe class="doc-embed" src="https://docs.google.com/document/d/e/2PACX-1vQmLneAb6gQuLNaCW-QCPdbFo5WTk6_fnFg1E6OB_8Kx0izmdlu4CK8DYUfBINIXY1HAlQrL-4BE34g/pub?embedded=true"></iframe>
      </div>
    </div>

    <!-- Production Sections -->
    <div class="wiki-section" id="post-production">
      <div class="clay-card">
        <h2>Post-Production SOPs</h2>
        <iframe class="doc-embed" src="https://docs.google.com/document/d/e/2PACX-1vScItu_Eugc1vNvc3WnVlFgzvpVYpu_eUGXUUkEs9tY7osqzpvu8hV8rKBKXjnDIu-Zfiw6sO85FglQ/pub?embedded=true"></iframe>
      </div>
    </div>

    <div class="wiki-section" id="client-delivery">
      <div class="clay-card">
        <h2>Client Delivery</h2>
        <iframe class="doc-embed" src="https://docs.google.com/document/d/e/2PACX-1vScItu_Eugc1vNvc3WnVlFgzvpVYpu_eUGXUUkEs9tY7osqzpvu8hV8rKBKXjnDIu-Zfiw6sO85FglQ/pub?embedded=true"></iframe>
      </div>
    </div>

    <!-- Finance Sections -->
    <div class="wiki-section" id="invoicing-guide">
      <div class="clay-card">
        <h2>Invoicing Guide</h2>
        <iframe class="doc-embed" src="https://docs.google.com/document/d/e/2PACX-1vRJ1c6F3XwD1C-T7rG53sGclHK5W95MRS4xd474O3rsRZAeOayXeKvce8JFJiHgEe_t_lchOJrL9jZr/pub"></iframe>
      </div>
    </div>

    <!-- Knowledge Sections -->
    <div class="wiki-section" id="brand-guidelines">
      <div class="clay-card">
        <h2>Brand Guidelines</h2>
        <iframe class="doc-embed" src="https://docs.google.com/presentation/d/e/2PACX-1vSmzBbAQ-zijbnh8U48r5Oz4y76MMs8c9aD3iNCBjRuDBmKIIBtOsdLQzVGNOiJHPpLPCip2wW11CiT/pubembed?start=false&loop=false&delayms=10000" frameborder="0" allowfullscreen="true"></iframe>
      </div>
    </div>

    <div class="wiki-section" id="company-history">
      <div class="clay-card">
        <h2>Company History</h2>
        <iframe class="doc-embed" src="https://docs.google.com/document/d/e/2PACX-1vScItu_Eugc1vNvc3WnVlFgzvpVYpu_eUGXUUkEs9tY7osqzpvu8hV8rKBKXjnDIu-Zfiw6sO85FglQ/pub?embedded=true"></iframe>
      </div>
    </div>

    <div class="wiki-section" id="locations-parking">
      <div class="clay-card">
        <h2>Locations & Parking</h2>
        <p>Our studio location and parking information.</p>
        <div class="video-container" style="padding-bottom: 75%;"> <!-- Adjusted for map aspect ratio -->
          <iframe src="https://www.google.com/maps/d/u/0/embed?mid=1XhlgT9sbjp2_2_wMQ5eIpQdPvFE5CVM&ehbc=2E312F" width="640" height="480"></iframe>
        </div>
        <div style="margin-top: 2rem;">
            <iframe class="doc-embed" src="https://docs.google.com/document/d/e/2PACX-1vTNnLPDw8yp-k2SbAlC1WZBWcoK5x-CjyZhVAEiwriLGlunq-b6b9GsXX7-qBN_Ccm05pz_dQ1p6SUJ/pub"></iframe>
        </div>
      </div>
    </div>

    <div class="wiki-section" id="welcome-video">
      <div class="clay-card">
        <h2>Welcome Video</h2>
        <p>Here is a short introduction to our studio.</p>
        <div class="video-container">
          <iframe 
            src="https://www.youtube.com/embed/9s-K_wQsFE4?si=sA7VJCZXhQTdGr7H" 
            title="YouTube video player" 
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
            allowfullscreen
            loading="lazy">
          </iframe>
        </div>
      </div>
    </div>
  </main>

  <footer>
    <p>Internal use only - Built by David Baker & Antigravity</p>
  </footer>

  <!-- SVG Filter for Clay Texture -->
  <svg style="position: absolute; width: 0; height: 0;">
    <filter id="clay-texture">
      <feTurbulence type="fractalNoise" baseFrequency="0.04" numOctaves="3" result="noise" />
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="3" />
    </filter>
  </svg>

  <script>
    function toggleDropdown(element) {
      const navSection = element.parentElement;
      const items = element.nextElementSibling;
      const allSections = document.querySelectorAll('.nav-section');
      
      allSections.forEach(section => {
        if (section !== navSection) {
          section.classList.remove('open');
          section.querySelector('.nav-items').classList.remove('show');
        }
      });
      
      navSection.classList.toggle('open');
      items.classList.toggle('show');
    }

    function showSection(id, element) {
      // Hide all sections
      document.querySelectorAll('.wiki-section').forEach(s => s.classList.remove('active'));
      // Remove active from all links
      document.querySelectorAll('.nav-link').forEach(l => l.classList.remove('active'));
      
      // Show target section
      const target = document.getElementById(id);
      if (target) {
        target.classList.add('active');
        window.scrollTo({ top: 0, behavior: 'smooth' });
      }
      
      // Mark link as active
      if (element) {
        element.classList.add('active');
      }
      
      // Close dropdowns
      document.querySelectorAll('.nav-items').forEach(i => i.classList.remove('show'));
      document.querySelectorAll('.nav-section').forEach(s => s.classList.remove('open'));
    }

    // Close dropdowns on outside click
    window.onclick = function(event) {
      if (!event.target.matches('.nav-section-title')) {
        document.querySelectorAll('.nav-items').forEach(i => i.classList.remove('show'));
        document.querySelectorAll('.nav-section').forEach(s => s.classList.remove('open'));
      }
    }
  </script>
</body>
</html>
