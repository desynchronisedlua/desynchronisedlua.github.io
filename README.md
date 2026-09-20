<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Desync's Portfolio</title>
  <meta name="description" content="Roblox scripter with 7+ years experience. 50M+ visits contributed.">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #050b14;
      --panel: #081321;
      --panel-hover: #0b1a2d;
      --text: #f4f7fb;
      --muted: #9aa9bd;
      --border: rgba(22, 104, 217, 0.35);
      --accent: #1687ff;
      --accent-2: #7c5cfc;
      --radius: 16px;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      font-family: 'Inter', system-ui, sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.6;
      min-height: 100vh;
    }

    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background: 
        radial-gradient(ellipse 80% 50% at 50% -20%, rgba(22, 135, 255, 0.12), transparent),
        radial-gradient(ellipse 60% 40% at 90% 100%, rgba(124, 92, 252, 0.08), transparent);
      pointer-events: none;
      z-index: -1;
    }

    .site-header {
      position: sticky;
      top: 0;
      z-index: 100;
      background: rgba(5, 11, 20, 0.85);
      backdrop-filter: blur(14px);
      border-bottom: 1px solid var(--border);
    }

    .header-inner {
      max-width: 1200px;
      margin: 0 auto;
      padding: 1rem 1.5rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .brand {
      font-weight: 700;
      font-size: 1.3rem;
      text-decoration: none;
      letter-spacing: -0.02em;
    }

    .brand .white { color: #ffffff; }
    .brand .purple { color: var(--accent-2); }

    .nav { display: flex; gap: 1.75rem; }

    .nav-link {
      color: var(--muted);
      text-decoration: none;
      font-weight: 500;
      font-size: 0.95rem;
      transition: color 0.2s;
      position: relative;
    }

    .nav-link:hover { color: var(--text); }

    .nav-link.active {
      color: var(--accent);
    }

    .nav-link.active::after {
      content: '';
      position: absolute;
      bottom: -6px;
      left: 0;
      right: 0;
      height: 2px;
      background: var(--accent);
      border-radius: 2px;
    }

    .page-shell {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 1.5rem;
    }

    section { padding: 3.5rem 0; }

    .home-hero {
      display: grid;
      grid-template-columns: 1fr auto;
      gap: 3rem;
      align-items: center;
      padding-top: 3.5rem;
      padding-bottom: 2rem;
    }

    .page-title {
      font-size: clamp(2.6rem, 5vw, 3.8rem);
      font-weight: 800;
      letter-spacing: -0.03em;
      line-height: 1.1;
      margin-bottom: 0.75rem;
    }

    .page-title .white { color: #ffffff; }
    .page-title .purple { color: var(--accent-2); }

    .page-description {
      color: var(--muted);
      font-size: 1.15rem;
      margin-bottom: 2rem;
      max-width: 480px;
    }

    .action-row {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .button {
      display: inline-flex;
      align-items: center;
      gap: 0.55rem;
      padding: 0.85rem 1.5rem;
      border-radius: 12px;
      font-weight: 600;
      font-size: 0.95rem;
      text-decoration: none;
      transition: all 0.2s;
      border: none;
      cursor: pointer;
    }

    .button-primary {
      background: var(--accent);
      color: white;
      box-shadow: 0 0 24px rgba(22, 135, 255, 0.35);
    }

    .button-primary:hover {
      background: #0f76e6;
      transform: translateY(-2px);
    }

    .button-secondary {
      background: transparent;
      color: var(--text);
      border: 1px solid var(--border);
    }

    .button-secondary:hover {
      background: var(--panel);
      border-color: var(--accent);
    }

    .button-icon { width: 18px; height: 18px; }

    .home-profile {
      width: 220px;
      height: 220px;
      border-radius: 50%;
      overflow: hidden;
      border: 3px solid var(--accent-2);
      box-shadow: 0 0 40px rgba(124, 92, 252, 0.35);
      background: #0d1525;
    }

    .home-profile img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .home-stats-strip {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 1rem;
      margin-top: 2.5rem;
    }

    .stat-card {
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1.4rem 1.2rem;
      display: flex;
      align-items: center;
      gap: 1rem;
      transition: all 0.2s;
    }

    .stat-card:hover {
      background: var(--panel-hover);
      border-color: var(--accent);
      transform: translateY(-3px);
    }

    .stat-icon {
      width: 28px;
      height: 28px;
      flex-shrink: 0;
      color: var(--accent);
    }

    .stat-icon img {
      width: 28px;
      height: 28px;
      object-fit: contain;
    }

    .stat-value {
      font-size: 1.35rem;
      font-weight: 700;
      line-height: 1.2;
    }

    .stat-label {
      font-size: 0.82rem;
      color: var(--muted);
    }

    .connect-section { padding-top: 1rem; padding-bottom: 4rem; }

    .connect-title {
      text-align: center;
      font-size: 1.7rem;
      font-weight: 700;
      margin-bottom: 1.75rem;
    }

    .social-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 1rem;
      max-width: 520px;
      margin: 0 auto;
    }

    .social-card {
      display: flex;
      align-items: center;
      gap: 0.9rem;
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: 14px;
      padding: 1.1rem 1.3rem;
      color: var(--text);
      text-decoration: none;
      transition: all 0.2s;
    }

    .social-card:hover {
      background: var(--panel-hover);
      border-color: var(--accent);
      transform: translateY(-2px);
    }

    .social-icon {
      width: 24px;
      height: 24px;
      flex-shrink: 0;
    }

    .social-icon img {
      width: 24px;
      height: 24px;
      object-fit: contain;
    }

    .social-label { font-weight: 600; font-size: 0.95rem; }

    .social-sublabel {
      display: block;
      font-size: 0.78rem;
      color: var(--muted);
      margin-top: 1px;
    }

    .section-title {
      font-size: 2.4rem;
      font-weight: 800;
      letter-spacing: -0.03em;
      text-align: center;
      margin-bottom: 0.5rem;
    }

    .section-subtitle {
      color: var(--muted);
      text-align: center;
      margin-bottom: 2.75rem;
      font-size: 1.1rem;
      max-width: 640px;
      margin-left: auto;
      margin-right: auto;
    }

    .about-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.4rem;
      margin-bottom: 3rem;
    }

    .about-card {
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1.8rem;
      transition: all 0.2s;
    }

    .about-card:hover {
      border-color: var(--accent);
      transform: translateY(-3px);
    }

    .about-icon {
      width: 36px;
      height: 36px;
      margin-bottom: 1.1rem;
      color: var(--accent);
    }

    .about-icon svg { width: 100%; height: 100%; }

    .about-card h3 {
      font-size: 1.15rem;
      margin-bottom: 0.7rem;
    }

    .about-card p, .about-card ul {
      color: var(--muted);
      font-size: 0.95rem;
    }

    .about-card ul { list-style: none; }

    .about-card li {
      margin-bottom: 0.4rem;
      padding-left: 1.1rem;
      position: relative;
    }

    .about-card li::before {
      content: "•";
      position: absolute;
      left: 0;
      color: var(--accent);
    }

    .games-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 1.25rem;
      margin-bottom: 3.5rem;
    }

    .game-card {
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1.2rem;
      transition: all 0.2s;
      text-decoration: none;
      color: inherit;
      display: block;
      position: relative;
      overflow: hidden;
    }

    .game-card:hover {
      border-color: var(--accent);
      transform: translateY(-4px);
      background: var(--panel-hover);
    }

    .game-thumb {
      position: relative;
      border-radius: 12px;
      overflow: hidden;
      margin-bottom: 12px;
      aspect-ratio: 1;
      background: #0d1525;
    }

    .game-thumb img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
      transition: transform 0.3s;
    }

    .game-card:hover .game-thumb img {
      transform: scale(1.05);
    }

    .game-overlay {
      position: absolute;
      inset: 0;
      background: rgba(5, 11, 20, 0.85);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      gap: 0.55rem;
      opacity: 0;
      transition: opacity 0.25s;
      padding: 1rem;
      text-align: center;
    }

    .game-card:hover .game-overlay {
      opacity: 1;
    }

    .game-stat {
      font-size: 0.88rem;
      color: var(--text);
      line-height: 1.3;
    }

    .game-stat strong {
      color: var(--accent);
      font-weight: 700;
      display: block;
      font-size: 0.78rem;
      text-transform: uppercase;
      letter-spacing: 0.03em;
      margin-bottom: 1px;
    }

    .game-card h3 {
      font-size: 1.05rem;
      margin: 0;
    }

    .note {
      background: rgba(22, 135, 255, 0.08);
      border: 1px solid rgba(22, 135, 255, 0.25);
      border-radius: 12px;
      padding: 1rem 1.25rem;
      margin-bottom: 2.5rem;
      font-size: 0.95rem;
      color: var(--muted);
    }

    .groups-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
      gap: 1rem;
    }

    .group-card {
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: 14px;
      padding: 1.2rem 1.4rem;
      display: flex;
      align-items: center;
      gap: 0.9rem;
      text-decoration: none;
      color: inherit;
      transition: all 0.2s;
    }

    .group-card:hover {
      border-color: var(--accent);
      background: var(--panel-hover);
      transform: translateY(-2px);
    }

    .group-icon {
      width: 42px;
      height: 42px;
      flex-shrink: 0;
      border-radius: 10px;
      overflow: hidden;
    }

    .group-icon img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .page { display: none; }
    .page.active { display: block; }

    footer {
      text-align: center;
      padding: 1.75rem;
      color: var(--muted);
      font-size: 0.85rem;
      border-top: 1px solid var(--border);
    }

    @media (max-width: 900px) {
      .home-hero {
        grid-template-columns: 1fr;
        text-align: center;
      }
      .page-description { margin-left: auto; margin-right: auto; }
      .action-row { justify-content: center; }
      .home-profile { margin: 0 auto; width: 180px; height: 180px; }
      .home-stats-strip { grid-template-columns: repeat(2, 1fr); }
      .about-grid { grid-template-columns: 1fr; }
    }

    @media (max-width: 500px) {
      .home-stats-strip { grid-template-columns: 1fr; }
      .social-grid { grid-template-columns: 1fr; }
      .nav { gap: 1.2rem; }
    }
  </style>
</head>
<body>

  <header class="site-header">
    <div class="header-inner">
      <a class="brand" href="#" data-page="home">
        <span class="white">Desync's</span> <span class="purple">Portfolio</span>
      </a>
      <nav class="nav">
        <a class="nav-link active" href="#" data-page="home">Home</a>
        <a class="nav-link" href="#" data-page="about">About</a>
        <a class="nav-link" href="#" data-page="work">Services</a>
      </nav>
    </div>
  </header>

  <!-- HOME -->
  <div id="home" class="page active">
    <section>
      <div class="page-shell home-hero">
        <div class="home-copy">
          <div class="page-title">
            <span class="white">Desync's</span> <span class="purple">Portfolio</span>
          </div>
          <p class="page-description">Roblox scripter with 7+ years of experience building game systems that have contributed to 50M+ visits.</p>
          <div class="action-row">
            <a class="button button-primary" href="#" data-page="work">
              <span>VIEW WORK</span>
              <span class="button-icon">
                <svg viewBox="0 0 24 24" fill="none"><path d="M14 4h6v6M20 4l-9 9" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/><path d="M20 13v5a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h5" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/></svg>
              </span>
            </a>
            <a class="button button-secondary" href="https://discord.gg/pwSUxwcUvW" target="_blank">CONTACT</a>
          </div>
        </div>

        <div class="home-profile">
          <img src="https://i.ibb.co/hFg2r7DQ/Untitled624-20230921193221.png" alt="Desync">
        </div>
      </div>

      <div class="page-shell">
        <div class="home-stats-strip">
          <article class="stat-card">
            <span class="stat-icon">
              <svg viewBox="0 0 24 24" fill="none"><path d="M8 11a3 3 0 1 0 0-6 3 3 0 0 0 0 6Zm8-1a2.5 2.5 0 1 0 0-5 2.5 2.5 0 0 0 0 5ZM3 19v-1.5A4.5 4.5 0 0 1 7.5 13h1A4.5 4.5 0 0 1 13 17.5V19H3Zm10.6 0v-1.2c0-1.3-.4-2.5-1.1-3.5.6-.3 1.3-.5 2-.5h.8a3.7 3.7 0 0 1 3.7 3.7V19h-5.4Z" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/></svg>
            </span>
            <div>
              <div class="stat-value">50M+</div>
              <div class="stat-label">Visits Contributed</div>
            </div>
          </article>

          <article class="stat-card">
            <span class="stat-icon">
              <svg viewBox="0 0 24 24" fill="none"><path d="M4 17l5-5 3 3 7-8" stroke="currentColor" stroke-width="1.9" stroke-linecap="round" stroke-linejoin="round"/><path d="M15 7h4v4" stroke="currentColor" stroke-width="1.9" stroke-linecap="round" stroke-linejoin="round"/></svg>
            </span>
            <div>
              <div class="stat-value">6,393</div>
              <div class="stat-label">Peak CCU</div>
            </div>
          </article>

          <article class="stat-card">
            <span class="stat-icon">
              <img src="https://en.help.roblox.com/hc/article_attachments/7997146649876" alt="Verified">
            </span>
            <div>
              <div class="stat-value">Verified</div>
              <div class="stat-label">Roblox Developer</div>
            </div>
          </article>

          <article class="stat-card">
            <span class="stat-icon">
              <svg viewBox="0 0 24 24" fill="none"><path d="m8 6-5 6 5 6M16 6l5 6-5 6M14 4l-4 16" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"/></svg>
            </span>
            <div>
              <div class="stat-value">7+ Years</div>
              <div class="stat-label">Scripting Experience</div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section class="connect-section">
      <div class="page-shell">
        <h2 class="connect-title">Let's Connect</h2>
        <div class="social-grid">
          <a class="social-card" href="https://www.roblox.com/users/10266090264/profile" target="_blank">
            <span class="social-icon"><img src="https://www.roblox.com/favicon.ico" alt="Roblox"></span>
            <span class="social-label">Roblox</span>
          </a>
          <a class="social-card" href="https://discord.gg/pwSUxwcUvW" target="_blank">
            <span class="social-icon">
              <svg viewBox="0 0 24 24" fill="currentColor"><path d="M18.9 5.4a16.4 16.4 0 0 0-4-1.2l-.5 1a14.6 14.6 0 0 0-4.8 0l-.5-1a16.7 16.7 0 0 0-4 1.2C2.6 9 1.9 12.5 2.2 16a16.8 16.8 0 0 0 5 2.5l1.2-1.6a10.7 10.7 0 0 1-1.8-.9l.4-.3a11.7 11.7 0 0 0 10 0l.5.3c-.6.4-1.2.7-1.9.9l1.2 1.6a16.8 16.8 0 0 0 5-2.5c.4-4.1-.7-7.6-2.9-10.6ZM8.4 14.2c-1 0-1.8-.9-1.8-2s.8-2 1.8-2 1.8.9 1.8 2-.8 2-1.8 2Zm7.2 0c-1 0-1.8-.9-1.8-2s.8-2 1.8-2 1.8.9 1.8 2-.8 2-1.8 2Z"/></svg>
            </span>
            <span class="social-label">Discord</span>
          </a>
          <a class="social-card" href="https://x.com/DesyncWasHere" target="_blank">
            <span class="social-icon"><img src="https://x.com/favicon.ico" alt="X"></span>
            <span class="social-label">X / Twitter</span>
          </a>
          <a class="social-card" href="mailto:desyncportfolio@gmail.com">
            <span class="social-icon"><img src="https://ssl.gstatic.com/ui/v1/icons/mail/rfr/gmail.ico" alt="Email"></span>
            <span>
              <span class="social-label">Email</span>
              <small class="social-sublabel">desyncportfolio@gmail.com</small>
            </span>
          </a>
        </div>
      </div>
    </section>
  </div>

  <!-- ABOUT -->
  <div id="about" class="page">
    <section>
      <div class="page-shell">
        <h2 class="section-title">About Me</h2>
        <p class="section-subtitle">I'm a Roblox scripter with 7+ years of experience. I focus on building solid game systems and gameplay logic — not pretty UI.</p>

        <div class="about-grid">
          <div class="about-card">
            <div class="about-icon">
              <svg viewBox="0 0 24 24" fill="none"><circle cx="12" cy="8" r="3" stroke="currentColor" stroke-width="1.7"/><path d="M5.5 20v-1.5A6.5 6.5 0 0 1 12 12a6.5 6.5 0 0 1 6.5 6.5V20h-13Z" stroke="currentColor" stroke-width="1.7" stroke-linejoin="round"/></svg>
            </div>
            <h3>Who I Am</h3>
            <p>Roblox developer who has contributed to games that reached 50M+ total visits and a peak of 6,393 concurrent players. I write the systems that make games actually work.</p>
          </div>

          <div class="about-card">
            <div class="about-icon">
              <svg viewBox="0 0 24 24" fill="none"><path d="m8 6-5 6 5 6M16 6l5 6-5 6M14 4l-4 16" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"/></svg>
            </div>
            <h3>What I Do</h3>
            <ul>
              <li>Game Systems & Logic</li>
              <li>Scripting (Luau)</li>
              <li>Gameplay Features</li>
              <li>Backend Systems</li>
            </ul>
          </div>

          <div class="about-card">
            <div class="about-icon">
              <svg viewBox="0 0 24 24" fill="none"><circle cx="12" cy="12" r="8" stroke="currentColor" stroke-width="1.5"/><circle cx="12" cy="12" r="4.5" stroke="currentColor" stroke-width="1.5"/><circle cx="12" cy="12" r="1.5" fill="currentColor"/></svg>
            </div>
            <h3>What I Focus On</h3>
            <ul>
              <li>Clean, working code</li>
              <li>Performance</li>
              <li>Reliable systems</li>
              <li>Gameplay that functions</li>
            </ul>
          </div>
        </div>

        <h2 class="connect-title">Let's Connect</h2>
        <div class="social-grid">
          <a class="social-card" href="https://www.roblox.com/users/10266090264/profile" target="_blank">
            <span class="social-icon"><img src="https://www.roblox.com/favicon.ico" alt="Roblox"></span>
            <span class="social-label">Roblox</span>
          </a>
          <a class="social-card" href="https://discord.gg/pwSUxwcUvW" target="_blank">
            <span class="social-icon">
              <svg viewBox="0 0 24 24" fill="currentColor"><path d="M18.9 5.4a16.4 16.4 0 0 0-4-1.2l-.5 1a14.6 14.6 0 0 0-4.8 0l-.5-1a16.7 16.7 0 0 0-4 1.2C2.6 9 1.9 12.5 2.2 16a16.8 16.8 0 0 0 5 2.5l1.2-1.6a10.7 10.7 0 0 1-1.8-.9l.4-.3a11.7 11.7 0 0 0 10 0l.5.3c-.6.4-1.2.7-1.9.9l1.2 1.6a16.8 16.8 0 0 0 5-2.5c.4-4.1-.7-7.6-2.9-10.6ZM8.4 14.2c-1 0-1.8-.9-1.8-2s.8-2 1.8-2 1.8.9 1.8 2-.8 2-1.8 2Zm7.2 0c-1 0-1.8-.9-1.8-2s.8-2 1.8-2 1.8.9 1.8 2-.8 2-1.8 2Z"/></svg>
            </span>
            <span class="social-label">Discord</span>
          </a>
          <a class="social-card" href="https://x.com/DesyncWasHere" target="_blank">
            <span class="social-icon"><img src="https://x.com/favicon.ico" alt="X"></span>
            <span class="social-label">X / Twitter</span>
          </a>
          <a class="social-card" href="mailto:desyncportfolio@gmail.com">
            <span class="social-icon"><img src="https://ssl.gstatic.com/ui/v1/icons/mail/rfr/gmail.ico" alt="Email"></span>
            <span>
              <span class="social-label">Email</span>
              <small class="social-sublabel">desyncportfolio@gmail.com</small>
            </span>
          </a>
        </div>
      </div>
    </section>
  </div>

  <!-- SERVICES -->
  <div id="work" class="page">
    <section>
      <div class="page-shell">
        <h2 class="section-title">Services</h2>
        <p class="section-subtitle">Games I've worked on and groups I've contributed to / own.</p>

        <div class="note">
          Some of these games may no longer be active. They still show real systems that had to be coded.<br>
          Stats update live from Roblox.
        </div>

        <h3 style="font-size: 1.4rem; margin-bottom: 1.25rem; font-weight: 700;">Games</h3>
        <div class="games-grid" id="games-grid">
          <p style="color:var(--muted)">Loading live stats...</p>
        </div>

        <h3 style="font-size: 1.4rem; margin: 3rem 0 1.25rem; font-weight: 700;">Groups</h3>
        <div class="groups-grid" id="groups-grid">
          <p style="color:var(--muted)">Loading groups...</p>
        </div>

        <div style="margin-top: 3.5rem;">
          <h2 class="connect-title">Let's Connect</h2>
          <div class="social-grid">
            <a class="social-card" href="https://www.roblox.com/users/10266090264/profile" target="_blank">
              <span class="social-icon"><img src="https://www.roblox.com/favicon.ico" alt="Roblox"></span>
              <span class="social-label">Roblox</span>
            </a>
            <a class="social-card" href="https://discord.gg/pwSUxwcUvW" target="_blank">
              <span class="social-icon">
                <svg viewBox="0 0 24 24" fill="currentColor"><path d="M18.9 5.4a16.4 16.4 0 0 0-4-1.2l-.5 1a14.6 14.6 0 0 0-4.8 0l-.5-1a16.7 16.7 0 0 0-4 1.2C2.6 9 1.9 12.5 2.2 16a16.8 16.8 0 0 0 5 2.5l1.2-1.6a10.7 10.7 0 0 1-1.8-.9l.4-.3a11.7 11.7 0 0 0 10 0l.5.3c-.6.4-1.2.7-1.9.9l1.2 1.6a16.8 16.8 0 0 0 5-2.5c.4-4.1-.7-7.6-2.9-10.6ZM8.4 14.2c-1 0-1.8-.9-1.8-2s.8-2 1.8-2 1.8.9 1.8 2-.8 2-1.8 2Zm7.2 0c-1 0-1.8-.9-1.8-2s.8-2 1.8-2 1.8.9 1.8 2-.8 2-1.8 2Z"/></svg>
              </span>
              <span class="social-label">Discord</span>
            </a>
            <a class="social-card" href="https://x.com/DesyncWasHere" target="_blank">
              <span class="social-icon"><img src="https://x.com/favicon.ico" alt="X"></span>
              <span class="social-label">X / Twitter</span>
            </a>
            <a class="social-card" href="mailto:desyncportfolio@gmail.com">
              <span class="social-icon"><img src="https://ssl.gstatic.com/ui/v1/icons/mail/rfr/gmail.ico" alt="Email"></span>
              <span>
                <span class="social-label">Email</span>
                <small class="social-sublabel">desyncportfolio@gmail.com</small>
              </span>
            </a>
          </div>
        </div>
      </div>
    </section>
  </div>

  <footer>© 2026 Desync — Roblox Scripter</footer>

 <script>
  // ========== Page Navigation ==========
  const pages = document.querySelectorAll('.page');
  const navLinks = document.querySelectorAll('.nav-link');

  function showPage(id) {
    pages.forEach(p => p.classList.remove('active'));
    navLinks.forEach(l => l.classList.remove('active'));
    document.getElementById(id)?.classList.add('active');
    document.querySelector(`.nav-link[data-page="${id}"]`)?.classList.add('active');
    window.scrollTo(0, 0);
  }

  document.querySelectorAll('[data-page]').forEach(el => {
    el.addEventListener('click', e => {
      e.preventDefault();
      showPage(el.dataset.page);
    });
  });

  // ========== Sound System ==========
  const audioCtx = new (window.AudioContext || window.webkitAudioContext)();

  function playTone(freq, type, duration, volume = 0.08) {
    if (audioCtx.state === 'suspended') audioCtx.resume();
    const osc = audioCtx.createOscillator();
    const gain = audioCtx.createGain();
    osc.type = type;
    osc.frequency.setValueAtTime(freq, audioCtx.currentTime);
    gain.gain.setValueAtTime(volume, audioCtx.currentTime);
    gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + duration);
    osc.connect(gain);
    gain.connect(audioCtx.destination);
    osc.start();
    osc.stop(audioCtx.currentTime + duration);
  }

  function playHover() { playTone(620, 'sine', 0.07, 0.045); }
  function playClick() {
    playTone(880, 'sine', 0.09, 0.07);
    setTimeout(() => playTone(520, 'sine', 0.06, 0.04), 40);
  }

  // ========== Live Data (with CORS proxy) ==========
  const PROXY = 'https://corsproxy.io/?';

  const GAMES = [
    { placeId: 112999934412261, name: "Greedy Fish Stealer", thumb: "https://tr.rbxcdn.com/180DAY-81abe9aaf1445d2b6c6be8d2b006f04b/512/512/Image/Png/noFilter" },
    { placeId: 140667013973477, name: "+1 Jump to Dunk", thumb: "https://tr.rbxcdn.com/180DAY-e0af60f93da27b48d0390aee9029ed2a/512/512/Image/Png/noFilter" },
    { placeId: 108253049921435, name: "+1 Aura Blast", thumb: "https://tr.rbxcdn.com/180DAY-b46558d627465af7d1c8bec2cd5bca5d/512/512/Image/Png/noFilter" },
    { placeId: 85732503427910, name: "+1 Fart Speed Escape", thumb: "https://tr.rbxcdn.com/180DAY-9adf3f6175cd2d8ec26903ad22358fe2/512/512/Image/Png/noFilter" },
    { placeId: 79987593686042, name: "Mine For Brainrots", thumb: "https://tr.rbxcdn.com/180DAY-29ee762356aaaab1fcfe3a385b80b84f/512/512/Image/Png/noFilter" },
    { placeId: 73118428536704, name: "+1 Speed Wheelchair Tsunami Escape", thumb: "https://tr.rbxcdn.com/180DAY-9374ebe5deea15a633c013753f8f6d2a/512/512/Image/Png/noFilter" },
    { placeId: 82770013738133, name: "+1 Car Speed Tape Escape", thumb: "https://tr.rbxcdn.com/180DAY-8bee46c218d9f03689010e4be99e6842/512/512/Image/Png/noFilter" }
  ];

  const GROUPS = [
    { id: 646311695, name: "Made 2 Play", icon: "https://tr.rbxcdn.com/180DAY-e7806d34164aeaa53cddbae31a59be47/150/150/Image/Png/noFilter" },
    { id: 703038082, name: "#Catalyst Games", icon: "https://tr.rbxcdn.com/180DAY-63d1f467d5447bf20dc829bd2303b205/150/150/Image/Png/noFilter" },
    { id: 783325502, name: "Lunar's Big Games", icon: "https://tr.rbxcdn.com/180DAY-c9571eff76b218a47aeab6239a1b1db5/150/150/Image/Png/noFilter" },
    { id: 366483296, name: "jump to dunk", icon: "https://tr.rbxcdn.com/180DAY-1a3b033988403d33ed29abec6f7ff343/150/150/Image/Png/noFilter" },
    { id: 460583975, name: "Form & Play", icon: "https://tr.rbxcdn.com/180DAY-a471bf3c256fde41813483519f1d649d/150/150/Image/Png/noFilter" }
  ];

  function formatNumber(n) {
    if (n >= 1_000_000) return (n / 1_000_000).toFixed(2).replace(/\.00$/, '') + 'M';
    if (n >= 1_000) return (n / 1_000).toFixed(1).replace(/\.0$/, '') + 'K';
    return n.toString();
  }

  async function fetchJSON(url) {
    const res = await fetch(PROXY + encodeURIComponent(url));
    if (!res.ok) throw new Error('Network error');
    return res.json();
  }

  async function loadGames() {
    const grid = document.getElementById('games-grid');

    const cards = await Promise.all(GAMES.map(async (game) => {
      try {
        // Get universe ID
        const uniData = await fetchJSON(`https://apis.roblox.com/universes/v1/places/${game.placeId}/universe`);
        const universeId = uniData.universeId;

        // Get stats
        const statsData = await fetchJSON(`https://games.roblox.com/v1/games?universeIds=${universeId}`);
        const stats = statsData.data?.[0] || {};

        const visits = formatNumber(stats.visits || 0);
        const favs = formatNumber(stats.favoritedCount || 0);
        const playing = stats.playing ?? 0;

        return `
          <a class="game-card" href="https://www.roblox.com/games/${game.placeId}" target="_blank">
            <div class="game-thumb">
              <img src="${game.thumb}" alt="${game.name}">
              <div class="game-overlay">
                <div class="game-stat"><strong>Visits</strong>${visits}</div>
                <div class="game-stat"><strong>Favourites</strong>${favs}</div>
                <div class="game-stat"><strong>Playing</strong>${playing}</div>
              </div>
            </div>
            <div style="display:flex; justify-content:space-between; align-items:center;">
              <h3>${game.name}</h3>
              <span class="button-icon">
                <svg viewBox="0 0 24 24" fill="none" width="18" height="18"><path d="M14 4h6v6M20 4l-9 9" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"></path><path d="M20 13v5a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h5" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"></path></svg>
              </span>
            </div>
          </a>
        `;
      } catch (err) {
        console.warn('Failed to load', game.name, err);
        return `
          <a class="game-card" href="https://www.roblox.com/games/${game.placeId}" target="_blank">
            <div class="game-thumb">
              <img src="${game.thumb}" alt="${game.name}">
              <div class="game-overlay">
                <div class="game-stat"><strong>Visits</strong>—</div>
                <div class="game-stat"><strong>Favourites</strong>—</div>
                <div class="game-stat"><strong>Playing</strong>—</div>
              </div>
            </div>
            <div style="display:flex; justify-content:space-between; align-items:center;">
              <h3>${game.name}</h3>
              <span class="button-icon">
                <svg viewBox="0 0 24 24" fill="none" width="18" height="18"><path d="M14 4h6v6M20 4l-9 9" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"></path><path d="M20 13v5a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h5" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"></path></svg>
              </span>
            </div>
          </a>
        `;
      }
    }));

    grid.innerHTML = cards.join('');

    grid.querySelectorAll('.game-card').forEach(el => {
      el.addEventListener('mouseenter', playHover);
      el.addEventListener('click', playClick);
    });
  }

  async function loadGroups() {
    const grid = document.getElementById('groups-grid');

    const cards = await Promise.all(GROUPS.map(async (group) => {
      try {
        const data = await fetchJSON(`https://groups.roblox.com/v1/groups/${group.id}`);
        const members = formatNumber(data.memberCount || 0);

        return `
          <a class="group-card" href="https://www.roblox.com/communities/${group.id}" target="_blank">
            <span class="group-icon">
              <img src="${group.icon}" alt="${group.name}">
            </span>
            <div style="flex:1;">
              <div style="font-weight: 600;">${group.name}</div>
              <div style="font-size: 0.85rem; color: var(--muted);">${members} members</div>
            </div>
            <span class="button-icon">
              <svg viewBox="0 0 24 24" fill="none" width="18" height="18"><path d="M14 4h6v6M20 4l-9 9" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"></path><path d="M20 13v5a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h5" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"></path></svg>
            </span>
          </a>
        `;
      } catch {
        return `
          <a class="group-card" href="https://www.roblox.com/communities/${group.id}" target="_blank">
            <span class="group-icon">
              <img src="${group.icon}" alt="${group.name}">
            </span>
            <div style="flex:1;">
              <div style="font-weight: 600;">${group.name}</div>
              <div style="font-size: 0.85rem; color: var(--muted);">— members</div>
            </div>
            <span class="button-icon">
              <svg viewBox="0 0 24 24" fill="none" width="18" height="18"><path d="M14 4h6v6M20 4l-9 9" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"></path><path d="M20 13v5a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h5" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"></path></svg>
            </span>
          </a>
        `;
      }
    }));

    grid.innerHTML = cards.join('');

    grid.querySelectorAll('.group-card').forEach(el => {
      el.addEventListener('mouseenter', playHover);
      el.addEventListener('click', playClick);
    });
  }

  // Init
  document.addEventListener('DOMContentLoaded', () => {
    document.querySelectorAll('a, button, .nav-link, .button, .social-card, .stat-card, [data-page]').forEach(el => {
      el.addEventListener('mouseenter', playHover);
      el.addEventListener('click', playClick);
    });

    loadGames();
    loadGroups();
  });
</script>
</body>
</html>
