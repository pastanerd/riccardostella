<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Riccardo Stella</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300&family=DM+Mono:wght@300;400&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --black: #0d0d0d;
      --white: #f5f4f0;
      --grey: #999;
      --rule: #d8d6d0;
      --mono: 'DM Mono', monospace;
      --serif: 'Cormorant Garamond', serif;
    }

    html { font-size: 16px; }

    body {
      background: var(--white);
      color: var(--black);
      font-family: var(--mono);
      font-weight: 300;
      min-height: 100vh;
      padding: 3rem 2rem;
      max-width: 860px;
      margin: 0 auto;
    }

    /* ── HEADER ── */
    header {
      display: grid;
      grid-template-columns: 1fr auto;
      align-items: end;
      padding-bottom: 1.25rem;
      border-bottom: 1px solid var(--black);
      margin-bottom: 3.5rem;
      animation: fadeUp 0.7s ease both;
    }

    .name {
      font-family: var(--serif);
      font-size: clamp(2.8rem, 6vw, 5rem);
      font-weight: 300;
      line-height: 0.95;
      letter-spacing: -0.01em;
    }

    .name em {
      font-style: italic;
      font-weight: 300;
    }

    .header-meta {
      text-align: right;
      font-size: 0.65rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--grey);
      line-height: 1.8;
      padding-bottom: 0.25rem;
    }

    /* ── SECTION LABEL ── */
    .label {
      font-size: 0.6rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--grey);
      margin-bottom: 1rem;
    }

    /* ── BIO ── */
    .bio {
      margin-bottom: 4rem;
      animation: fadeUp 0.7s 0.15s ease both;
    }

    .bio p {
      font-family: var(--serif);
      font-size: clamp(1.35rem, 2.8vw, 1.75rem);
      font-weight: 300;
      line-height: 1.5;
      max-width: 600px;
      color: var(--black);
    }

    .bio p span {
      color: var(--grey);
    }

    /* ── WORK ── */
    .work {
      margin-bottom: 4rem;
      animation: fadeUp 0.7s 0.3s ease both;
    }

    .work-list {
      list-style: none;
    }

    .work-list li {
      display: grid;
      grid-template-columns: 1.5rem 1fr auto;
      align-items: baseline;
      gap: 1rem;
      padding: 1rem 0;
      border-bottom: 1px solid var(--rule);
      transition: opacity 0.2s;
    }

    .work-list li:first-child {
      border-top: 1px solid var(--rule);
    }

    .work-list li:hover { opacity: 0.6; }

    .work-num {
      font-size: 0.6rem;
      color: var(--grey);
      letter-spacing: 0.08em;
    }

    .work-title {
      font-family: var(--serif);
      font-size: 1.2rem;
      font-weight: 400;
    }

    .work-desc {
      font-size: 0.7rem;
      color: var(--grey);
      letter-spacing: 0.04em;
      display: block;
      margin-top: 0.2rem;
    }

    .work-link {
      font-size: 0.6rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--grey);
      text-decoration: none;
      border-bottom: 1px solid var(--rule);
      padding-bottom: 1px;
      transition: color 0.2s, border-color 0.2s;
      white-space: nowrap;
    }

    .work-link:hover {
      color: var(--black);
      border-color: var(--black);
    }

    /* ── FOOTER / LINKS ── */
    footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding-top: 1.5rem;
      border-top: 1px solid var(--black);
      animation: fadeUp 0.7s 0.45s ease both;
    }

    .links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

    .links a {
      font-size: 0.65rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--black);
      text-decoration: none;
      border-bottom: 1px solid transparent;
      padding-bottom: 1px;
      transition: border-color 0.2s;
    }

    .links a:hover { border-color: var(--black); }

    .footer-year {
      font-size: 0.6rem;
      color: var(--grey);
      letter-spacing: 0.1em;
    }

    /* ── ANIMATION ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(16px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ── MOBILE ── */
    @media (max-width: 540px) {
      body { padding: 2rem 1.25rem; }

      header {
        grid-template-columns: 1fr;
        gap: 0.75rem;
        align-items: start;
      }

      .header-meta { text-align: left; }

      .work-list li {
        grid-template-columns: 1.2rem 1fr;
      }

      .work-link { display: none; }

      footer { flex-direction: column; align-items: flex-start; gap: 1rem; }
    }
  </style>
</head>
<body>

  <header>
    <h1 class="name">Riccardo<br><em>Stella</em></h1>
    <div class="header-meta">
      Your Title Here<br>
      Based in City, Country<br>
      Available for work
    </div>
  </header>

  <section class="bio">
    <p class="label">About</p>
    <p>
      A short, thoughtful sentence about who you are and what you do.
      <span>A second sentence that adds texture — your approach, your interests, what drives your work.</span>
    </p>
  </section>

  <section class="work">
    <p class="label">Selected Work</p>
    <ul class="work-list">
      <li>
        <span class="work-num">01</span>
        <span>
          <span class="work-title">Project One</span>
          <span class="work-desc">One-line description of what this project is or does</span>
        </span>
        <a href="#" class="work-link">View →</a>
      </li>
      <li>
        <span class="work-num">02</span>
        <span>
          <span class="work-title">Project Two</span>
          <span class="work-desc">One-line description of what this project is or does</span>
        </span>
        <a href="#" class="work-link">View →</a>
      </li>
      <li>
        <span class="work-num">03</span>
        <span>
          <span class="work-title">Project Three</span>
          <span class="work-desc">One-line description of what this project is or does</span>
        </span>
        <a href="#" class="work-link">View →</a>
      </li>
    </ul>
  </section>

  <footer>
    <ul class="links">
      <li><a href="https://github.com/pastanerd" target="_blank">GitHub</a></li>
      <li><a href="mailto:hello@example.com">Email</a></li>
      <li><a href="#">LinkedIn</a></li>
      <li><a href="#">Twitter</a></li>
    </ul>
    <span class="footer-year">© 2026</span>
  </footer>

</body>
</html>
