<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Riccardo Stella</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Archivo:ital,wght@0,400;0,500;0,700;1,400&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #080808;
      --fg: #f0ede6;
      --dim: #333;
      --mid: #777;
      --sans: 'Archivo', sans-serif;
      --display: 'Bebas Neue', sans-serif;
    }

    html { font-size: 16px; }

    body {
      background: var(--bg);
      color: var(--fg);
      font-family: var(--sans);
      min-height: 100vh;
      overflow-x: hidden;
    }

    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='1'/%3E%3C/svg%3E");
      opacity: 0.03;
      pointer-events: none;
      z-index: 100;
    }

    .container {
      max-width: 1100px;
      margin: 0 auto;
      padding: 0 2.5rem;
    }

    /* NAV */
    nav {
      padding: 2rem 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid var(--dim);
      animation: fadeIn 0.6s ease both;
    }

    .nav-logo {
      font-family: var(--display);
      font-size: 1.1rem;
      letter-spacing: 0.12em;
      color: var(--fg);
    }

    .nav-links {
      display: flex;
      gap: 2.5rem;
      list-style: none;
    }

    .nav-links a {
      font-size: 0.68rem;
      font-weight: 500;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--mid);
      text-decoration: none;
      transition: color 0.2s;
    }

    .nav-links a:hover { color: var(--fg); }

    /* HERO */
    .hero {
      padding: 5rem 0 4rem;
      border-bottom: 1px solid var(--dim);
    }

    .hero-tag {
      font-size: 0.65rem;
      font-weight: 500;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--mid);
      margin-bottom: 2rem;
      display: flex;
      align-items: center;
      gap: 0.75rem;
      animation: fadeIn 0.5s 0.1s ease both;
    }

    .hero-tag::before {
      content: '';
      display: block;
      width: 2rem;
      height: 1px;
      background: var(--mid);
    }

    .hero-name {
      font-family: var(--display);
      font-size: clamp(5.5rem, 17vw, 14rem);
      line-height: 0.87;
      letter-spacing: 0.01em;
      animation: slideUp 0.9s 0.15s cubic-bezier(0.16, 1, 0.3, 1) both;
    }

    .hero-name .outline {
      display: block;
      color: transparent;
      -webkit-text-stroke: 1.5px var(--fg);
    }

    .hero-bottom {
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
      margin-top: 3rem;
      animation: fadeIn 0.6s 0.45s ease both;
    }

    .hero-bio {
      font-size: clamp(0.9rem, 1.5vw, 1.1rem);
      line-height: 1.7;
      color: var(--mid);
      max-width: 420px;
    }

    .hero-bio strong {
      color: var(--fg);
      font-weight: 500;
    }

    .hero-status {
      text-align: right;
      font-size: 0.62rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      line-height: 2.2;
      color: var(--mid);
    }

    .status-dot {
      display: inline-block;
      width: 5px;
      height: 5px;
      background: #4cff91;
      border-radius: 50%;
      margin-right: 0.5rem;
      vertical-align: middle;
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.2; }
    }

    /* WORK */
    .work {
      padding: 4rem 0;
      border-bottom: 1px solid var(--dim);
      animation: fadeIn 0.6s 0.55s ease both;
    }

    .section-header {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      margin-bottom: 2rem;
    }

    .section-title {
      font-size: 0.62rem;
      font-weight: 500;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--mid);
    }

    .section-count {
      font-size: 0.6rem;
      color: var(--dim);
      letter-spacing: 0.08em;
    }

    .work-list { list-style: none; }

    .work-item {
      display: grid;
      grid-template-columns: 3rem 1fr auto;
      align-items: center;
      gap: 1.5rem;
      padding: 1.6rem 0;
      border-top: 1px solid var(--dim);
      text-decoration: none;
      color: inherit;
      transition: background 0.2s, padding 0.2s, margin 0.2s;
    }

    .work-item:last-child { border-bottom: 1px solid var(--dim); }

    .work-item:hover {
      background: rgba(240,237,230,0.04);
      padding-left: 1rem;
      padding-right: 1rem;
      margin: 0 -1rem;
    }

    .work-item:hover .work-title { letter-spacing: 0.04em; }
    .work-item:hover .work-arrow { transform: translate(4px, -4px); color: var(--fg); }

    .work-num {
      font-family: var(--display);
      font-size: 0.72rem;
      color: var(--dim);
      letter-spacing: 0.05em;
    }

    .work-title {
      font-family: var(--display);
      font-size: clamp(1.8rem, 3.8vw, 2.8rem);
      letter-spacing: 0.02em;
      line-height: 1;
      transition: letter-spacing 0.3s;
    }

    .work-desc {
      display: block;
      font-size: 0.7rem;
      color: var(--mid);
      margin-top: 0.3rem;
      letter-spacing: 0.03em;
    }

    .work-arrow {
      font-size: 1.3rem;
      color: var(--mid);
      transition: transform 0.25s, color 0.25s;
    }

    /* FOOTER */
    footer {
      padding: 2.5rem 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
      animation: fadeIn 0.6s 0.65s ease both;
    }

    .footer-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

    .footer-links a {
      font-size: 0.65rem;
      font-weight: 500;
      letter-spacing: 0.14em;
      text-transform: uppercase;
      color: var(--mid);
      text-decoration: none;
      position: relative;
      transition: color 0.2s;
    }

    .footer-links a::after {
      content: '';
      position: absolute;
      bottom: -2px;
      left: 0;
      width: 0;
      height: 1px;
      background: var(--fg);
      transition: width 0.25s;
    }

    .footer-links a:hover { color: var(--fg); }
    .footer-links a:hover::after { width: 100%; }

    .footer-copy {
      font-size: 0.6rem;
      color: var(--dim);
      letter-spacing: 0.1em;
    }

    /* ANIMATIONS */
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @keyframes slideUp {
      from { opacity: 0; transform: translateY(50px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* MOBILE */
    @media (max-width: 600px) {
      .container { padding: 0 1.25rem; }
      .hero-bottom { flex-direction: column; gap: 2rem; align-items: flex-start; }
      .hero-status { text-align: left; }
      .work-item { grid-template-columns: 2rem 1fr auto; gap: 1rem; }
      footer { flex-direction: column; align-items: flex-start; gap: 1.5rem; }
      .nav-links { gap: 1.5rem; }
    }
  </style>
</head>
<body>
  <div class="container">

    <nav>
      <span class="nav-logo">RS</span>
      <ul class="nav-links">
        <li><a href="#">Work</a></li>
        <li><a href="#">About</a></li>
        <li><a href="mailto:hello@example.com">Contact</a></li>
      </ul>
    </nav>

    <section class="hero">
      <p class="hero-tag">Your Title Here</p>
      <h1 class="hero-name">
        Riccardo<span class="outline">Stella</span>
      </h1>
      <div class="hero-bottom">
        <p class="hero-bio">
          <strong>A short, bold sentence about who you are.</strong>
          A second sentence with more texture — your approach, your craft, what makes your work different.
        </p>
        <div class="hero-status">
          <span class="status-dot"></span>Available for work<br>
          Based in City, Country<br>
          Open to remote
        </div>
      </div>
    </section>

    <section class="work">
      <div class="section-header">
        <span class="section-title">Selected Work</span>
        <span class="section-count">03 projects</span>
      </div>
      <ul class="work-list">
        <li>
          <a class="work-item" href="#">
            <span class="work-num">01</span>
            <span>
              <span class="work-title">Project One</span>
              <span class="work-desc">One-line description of what this project is or does</span>
            </span>
            <span class="work-arrow">↗</span>
          </a>
        </li>
        <li>
          <a class="work-item" href="#">
            <span class="work-num">02</span>
            <span>
              <span class="work-title">Project Two</span>
              <span class="work-desc">One-line description of what this project is or does</span>
            </span>
            <span class="work-arrow">↗</span>
          </a>
        </li>
        <li>
          <a class="work-item" href="#">
            <span class="work-num">03</span>
            <span>
              <span class="work-title">Project Three</span>
              <span class="work-desc">One-line description of what this project is or does</span>
            </span>
            <span class="work-arrow">↗</span>
          </a>
        </li>
      </ul>
    </section>

    <footer>
      <ul class="footer-links">
        <li><a href="https://github.com/pastanerd" target="_blank">GitHub</a></li>
        <li><a href="mailto:hello@example.com">Email</a></li>
        <li><a href="#">LinkedIn</a></li>
        <li><a href="#">Twitter</a></li>
      </ul>
      <span class="footer-copy">© Riccardo Stella 2026</span>
    </footer>

  </div>
</body>
</html>
