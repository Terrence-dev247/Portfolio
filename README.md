<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Tebogo Poohe — Data Science & Cybersecurity</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=Inter:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet" />
  <style>
    /* ── TOKENS ─────────────────────────────────────────── */
    :root {
      --navy:    #0D1B2A;
      --navy2:   #1A2E42;
      --teal:    #00B4A6;
      --teal-d:  #008F84;
      --amber:   #F4A926;
      --off:     #F2F4F7;
      --text:    #1C2B3A;
      --muted:   #637587;
      --border:  #DDE3EA;
      --white:   #FFFFFF;
      --display: 'Syne', sans-serif;
      --body:    'Inter', sans-serif;
      --mono:    'JetBrains Mono', monospace;
      --radius:  10px;
      --shadow:  0 4px 24px rgba(13,27,42,0.08);
    }

    /* ── RESET ──────────────────────────────────────────── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body {
      font-family: var(--body);
      color: var(--text);
      background: var(--white);
      line-height: 1.65;
      -webkit-font-smoothing: antialiased;
    }
    a { color: inherit; text-decoration: none; }
    img { max-width: 100%; display: block; }

    /* ── NAV ────────────────────────────────────────────── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 5%;
      height: 64px;
      background: rgba(13,27,42,0.92);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(255,255,255,0.06);
    }
    .nav-logo {
      font-family: var(--display);
      font-weight: 800; font-size: 17px;
      color: var(--white);
      letter-spacing: -0.3px;
    }
    .nav-logo span { color: var(--teal); }
    .nav-links { display: flex; gap: 32px; list-style: none; }
    .nav-links a {
      font-size: 13px; font-weight: 500; color: rgba(255,255,255,0.7);
      letter-spacing: 0.04em; text-transform: uppercase;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--teal); }

    /* ── HERO ───────────────────────────────────────────── */
    .hero {
      min-height: 100vh;
      background: var(--navy);
      display: flex; align-items: center;
      padding: 100px 5% 60px;
      position: relative;
      overflow: hidden;
    }
    /* Signature element: animated data-grid background */
    .hero::before {
      content: '';
      position: absolute; inset: 0;
      background-image:
        linear-gradient(rgba(0,180,166,0.06) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,180,166,0.06) 1px, transparent 1px);
      background-size: 48px 48px;
      animation: gridMove 20s linear infinite;
    }
    @keyframes gridMove {
      from { background-position: 0 0; }
      to   { background-position: 48px 48px; }
    }
    .hero-inner {
      position: relative; z-index: 1;
      max-width: 1100px; margin: 0 auto; width: 100%;
      display: grid; grid-template-columns: 1fr auto;
      align-items: center; gap: 60px;
    }
    .hero-eyebrow {
      font-family: var(--mono);
      font-size: 13px; color: var(--teal);
      margin-bottom: 20px;
      display: flex; align-items: center; gap: 10px;
    }
    .hero-eyebrow::before {
      content: '';
      display: block; width: 32px; height: 1px;
      background: var(--teal);
    }
    .hero h1 {
      font-family: var(--display);
      font-size: clamp(2.8rem, 6vw, 5rem);
      font-weight: 800; line-height: 1.05;
      color: var(--white);
      letter-spacing: -1.5px;
      margin-bottom: 24px;
    }
    .hero h1 em {
      font-style: normal;
      color: var(--teal);
    }
    .hero-sub {
      font-size: 17px; color: rgba(255,255,255,0.6);
      max-width: 520px; line-height: 1.7;
      margin-bottom: 36px;
    }
    .hero-actions { display: flex; gap: 14px; flex-wrap: wrap; }
    .btn {
      display: inline-flex; align-items: center; gap: 8px;
      padding: 13px 26px;
      border-radius: var(--radius);
      font-size: 14px; font-weight: 600;
      cursor: pointer; transition: all 0.2s;
      border: none;
    }
    .btn-primary {
      background: var(--teal);
      color: var(--navy);
    }
    .btn-primary:hover { background: var(--teal-d); transform: translateY(-1px); }
    .btn-ghost {
      background: transparent;
      border: 1.5px solid rgba(255,255,255,0.2);
      color: rgba(255,255,255,0.8);
    }
    .btn-ghost:hover { border-color: var(--teal); color: var(--teal); }

    .hero-photo-wrap {
      display: flex; flex-direction: column;
      align-items: center; gap: 14px; flex-shrink: 0;
    }
    .hero-photo {
      width: 260px; height: 260px;
      border-radius: 50%;
      border: 3px solid var(--teal);
      object-fit: cover;
      object-position: center top;
      box-shadow: 0 0 0 10px rgba(0,180,166,0.12), 0 20px 60px rgba(0,0,0,0.4);
    }
    .hero-photo-name {
      font-family: var(--display);
      font-size: 15px; font-weight: 700;
      color: rgba(255,255,255,0.9);
      letter-spacing: 0.4px;
      text-align: center;
    }
    .hero-photo-title {
      font-family: var(--mono);
      font-size: 11px; color: var(--teal);
      text-align: center; margin-top: -8px;
      letter-spacing: 0.06em;
    }

    /* ── STAT BAR ───────────────────────────────────────── */
    .stat-bar {
      background: var(--navy2);
      border-top: 1px solid rgba(255,255,255,0.06);
      border-bottom: 1px solid rgba(255,255,255,0.06);
      padding: 28px 5%;
    }
    .stat-bar-inner {
      max-width: 1100px; margin: 0 auto;
      display: flex; gap: 0;
    }
    .stat {
      flex: 1; text-align: center;
      border-right: 1px solid rgba(255,255,255,0.08);
      padding: 8px 0;
    }
    .stat:last-child { border-right: none; }
    .stat-num {
      font-family: var(--display);
      font-size: 2rem; font-weight: 800;
      color: var(--teal); line-height: 1;
    }
    .stat-label {
      font-size: 12px; color: rgba(255,255,255,0.45);
      margin-top: 6px; letter-spacing: 0.04em;
      text-transform: uppercase;
    }

    /* ── SECTIONS ───────────────────────────────────────── */
    .section {
      padding: 96px 5%;
    }
    .section-alt { background: var(--off); }
    .section-dark { background: var(--navy); }
    .container { max-width: 1100px; margin: 0 auto; }
    .section-tag {
      font-family: var(--mono);
      font-size: 11px; font-weight: 500;
      color: var(--teal); letter-spacing: 0.1em;
      text-transform: uppercase;
      margin-bottom: 12px;
      display: flex; align-items: center; gap: 10px;
    }
    .section-tag::before {
      content: '';
      display: block; width: 24px; height: 1px;
      background: var(--teal);
    }
    .section-title {
      font-family: var(--display);
      font-size: clamp(1.8rem, 3.5vw, 2.6rem);
      font-weight: 800; letter-spacing: -0.5px;
      color: var(--text); line-height: 1.15;
      margin-bottom: 48px;
    }
    .section-dark .section-title { color: var(--white); }

    /* ── ABOUT ──────────────────────────────────────────── */
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 64px; align-items: start;
    }
    .about-text p {
      font-size: 16px; color: var(--muted);
      line-height: 1.8; margin-bottom: 16px;
    }
    .about-text p strong { color: var(--text); }
    .track-chips { display: flex; gap: 10px; flex-wrap: wrap; margin-top: 28px; }
    .chip {
      display: inline-flex; align-items: center; gap: 6px;
      padding: 7px 14px; border-radius: 20px;
      font-size: 13px; font-weight: 500;
      background: rgba(0,180,166,0.1);
      color: var(--teal-d);
      border: 1px solid rgba(0,180,166,0.2);
    }
    .about-edu {}
    .edu-card {
      background: var(--white);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 20px 22px;
      margin-bottom: 14px;
      position: relative;
      border-left: 3px solid var(--teal);
    }
    .edu-school { font-weight: 600; font-size: 15px; color: var(--text); }
    .edu-degree { font-size: 13px; color: var(--muted); margin-top: 4px; }
    .edu-year {
      position: absolute; top: 20px; right: 20px;
      font-family: var(--mono); font-size: 12px;
      color: var(--teal);
    }
    .edu-modules {
      margin-top: 10px; font-size: 12px; color: var(--muted);
      line-height: 1.6;
    }

    /* ── SKILLS ─────────────────────────────────────────── */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 20px;
    }
    .skill-card {
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: var(--radius);
      padding: 24px;
    }
    .skill-icon {
      width: 40px; height: 40px;
      border-radius: 8px;
      background: rgba(0,180,166,0.15);
      display: flex; align-items: center; justify-content: center;
      font-size: 20px; margin-bottom: 14px;
    }
    .skill-title {
      font-family: var(--display);
      font-size: 15px; font-weight: 700;
      color: var(--white); margin-bottom: 10px;
    }
    .skill-list {
      list-style: none;
      font-size: 13px; color: rgba(255,255,255,0.5);
      line-height: 2;
    }
    .skill-list li::before {
      content: '→ '; color: var(--teal); font-weight: 600;
    }

    /* ── PROJECTS ───────────────────────────────────────── */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 24px;
    }
    .project-card {
      background: var(--white);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      overflow: hidden;
      transition: box-shadow 0.25s, transform 0.25s;
    }
    .project-card:hover {
      box-shadow: var(--shadow);
      transform: translateY(-3px);
    }
    .project-card.featured {
      grid-column: span 2;
      display: grid; grid-template-columns: 1fr 1fr;
    }
    .project-banner {
      background: var(--navy);
      padding: 32px;
      display: flex; flex-direction: column; justify-content: space-between;
    }
    .project-card.featured .project-banner {
      border-radius: 0;
    }
    .project-banner-label {
      font-family: var(--mono);
      font-size: 11px; color: var(--teal);
      letter-spacing: 0.08em; text-transform: uppercase;
    }
    .project-banner h3 {
      font-family: var(--display);
      font-size: 20px; font-weight: 800;
      color: var(--white); margin: 12px 0 8px;
      line-height: 1.2;
    }
    .project-banner p {
      font-size: 13px; color: rgba(255,255,255,0.55);
      line-height: 1.7;
    }
    .project-body { padding: 24px 28px; }
    .project-card:not(.featured) .project-body { padding: 24px; }
    .project-card:not(.featured) .project-banner {
      min-height: 140px; border-radius: 0;
    }
    .project-card:not(.featured) .project-banner h3 { font-size: 17px; }
    .tag-row { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 14px; }
    .tag {
      font-family: var(--mono);
      font-size: 11px; padding: 4px 10px;
      border-radius: 4px;
      background: rgba(0,180,166,0.1);
      color: var(--teal-d);
      border: 1px solid rgba(0,180,166,0.2);
    }
    .project-highlights {
      margin-top: 14px; list-style: none;
      font-size: 13px; color: var(--muted);
      line-height: 1.9;
    }
    .project-highlights li::before {
      content: '✓ ';
      color: var(--teal); font-weight: 700;
    }
    .project-links {
      display: flex; gap: 10px; margin-top: 20px;
    }
    .project-link {
      font-size: 12px; font-weight: 600;
      color: var(--teal-d);
      padding: 7px 14px; border-radius: 6px;
      border: 1px solid rgba(0,180,166,0.3);
      transition: all 0.2s;
      display: flex; align-items: center; gap: 5px;
    }
    .project-link:hover {
      background: var(--teal); color: var(--navy);
      border-color: var(--teal);
    }

    /* ── CERTS ──────────────────────────────────────────── */
    .cert-groups {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 28px;
    }
    .cert-group {
      background: var(--white);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      overflow: hidden;
    }
    .cert-group-header {
      padding: 16px 20px;
      background: var(--navy);
      display: flex; align-items: center; gap: 10px;
    }
    .cert-group-icon { font-size: 18px; }
    .cert-group-title {
      font-family: var(--display);
      font-size: 14px; font-weight: 700;
      color: var(--white);
    }
    .cert-group-count {
      margin-left: auto;
      font-family: var(--mono); font-size: 11px;
      color: var(--teal); background: rgba(0,180,166,0.15);
      padding: 3px 8px; border-radius: 10px;
    }
    .cert-items { padding: 6px 0; }
    .cert-item {
      display: flex; align-items: center; gap: 10px;
      padding: 10px 20px;
      border-bottom: 1px solid var(--border);
      transition: background 0.15s;
    }
    .cert-item:last-child { border-bottom: none; }
    .cert-item:hover { background: var(--off); }
    .cert-dot {
      width: 6px; height: 6px; border-radius: 50%;
      background: var(--teal); flex-shrink: 0;
    }
    .cert-name { font-size: 13px; font-weight: 500; color: var(--text); }
    .cert-issuer { font-size: 11px; color: var(--muted); }
    .cert-year {
      margin-left: auto;
      font-family: var(--mono); font-size: 11px;
      color: var(--teal);
    }

    /* ── CONTACT ────────────────────────────────────────── */
    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 48px; align-items: center;
    }
    .contact-text .section-title { margin-bottom: 20px; }
    .contact-text p {
      font-size: 16px; color: rgba(255,255,255,0.55);
      line-height: 1.8; margin-bottom: 32px;
    }
    .contact-links { display: flex; flex-direction: column; gap: 14px; }
    .contact-link {
      display: flex; align-items: center; gap: 14px;
      padding: 16px 20px;
      border-radius: var(--radius);
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      transition: all 0.2s; color: var(--white);
    }
    .contact-link:hover {
      border-color: var(--teal);
      background: rgba(0,180,166,0.08);
    }
    .contact-link-icon {
      width: 38px; height: 38px; border-radius: 8px;
      background: rgba(0,180,166,0.15);
      display: flex; align-items: center; justify-content: center;
      font-size: 18px; flex-shrink: 0;
    }
    .contact-link-label {
      font-size: 11px; color: rgba(255,255,255,0.4);
      text-transform: uppercase; letter-spacing: 0.06em;
    }
    .contact-link-val {
      font-size: 14px; font-weight: 500;
      color: rgba(255,255,255,0.85);
    }

    /* ── FOOTER ─────────────────────────────────────────── */
    footer {
      background: var(--navy);
      border-top: 1px solid rgba(255,255,255,0.06);
      padding: 28px 5%;
      text-align: center;
      font-size: 13px; color: rgba(255,255,255,0.3);
    }
    footer a { color: var(--teal); }

    /* ── RESPONSIVE ─────────────────────────────────────── */
    @media (max-width: 768px) {
      .hero-inner {
        grid-template-columns: 1fr;
        text-align: center;
      }
      .hero-photo-wrap {
        order: -1;
        margin: 0 auto;
      }
      .hero-photo { width: 180px; height: 180px; }
      .hero-eyebrow { justify-content: center; }
      .hero-actions { justify-content: center; }
      .hero-sub { margin: 0 auto 36px; }
      .about-grid { grid-template-columns: 1fr; }
      .project-card.featured {
        grid-column: span 1;
        display: block;
      }
      .contact-grid { grid-template-columns: 1fr; }
      .nav-links { display: none; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <div class="nav-logo">Tebogo Terrence <span>Poohe</span></div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#certs">Certifications</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-inner">
      <div class="hero-text">
        <div class="hero-eyebrow">BSc IT · Richfield Graduate Institute of Technology · Pretoria</div>
        <h1>Data Science<br />&amp; <em>Cyber</em>security<br />Student.</h1>
        <p class="hero-sub">
          I build machine learning systems, RAG pipelines, and security-aware applications.
          Based in Pretoria — graduating 2026.
        </p>
        <div class="hero-actions">
          <a href="#projects" class="btn btn-primary">View Projects →</a>
          <a href="#contact" class="btn btn-ghost">Get in Touch</a>
        </div>
      </div>
      <div class="hero-photo-wrap">
        <img
          src="nna.jpg"
          alt="Tebogo Terrence Poohe"
          class="hero-photo"
        />
        <div class="hero-photo-name">Tebogo Terrence Poohe</div>
        <div class="hero-photo-title">BSc IT · Pretoria, South Africa</div>
      </div>
    </div>
  </section>

  <!-- STAT BAR -->
  <div class="stat-bar">
    <div class="stat-bar-inner">
      <div class="stat">
        <div class="stat-num">15</div>
        <div class="stat-label">Verified Badges</div>
      </div>
      <div class="stat">
        <div class="stat-num">3</div>
        <div class="stat-label">NQF Levels</div>
      </div>
      <div class="stat">
        <div class="stat-num">4</div>
        <div class="stat-label">ML Models Built</div>
      </div>
      <div class="stat">
        <div class="stat-num">2026</div>
        <div class="stat-label">Graduating</div>
      </div>
    </div>
  </div>

  <!-- ABOUT -->
  <section class="section" id="about">
    <div class="container">
      <div class="section-tag">Who I Am</div>
      <div class="about-grid">
        <div class="about-text">
          <div class="section-title">Building at the intersection of data and security.</div>
          <p>
            I'm a final-year BSc IT student at Richfield Graduate Institute of Technology,
            specialising in <strong>Emerging Technology</strong> with a focus on Data Science and
            Cybersecurity. My academic work combines machine learning pipelines, RAG systems,
            and network security fundamentals. Based in <strong>Pretoria, South Africa</strong>.
          </p>
          <p>
            I've completed the full <strong>Cisco Junior Cybersecurity Analyst Career Path</strong>,
            AWS Cloud Architecting training, and IBM SkillsBuild programmes — all while maintaining
            consistent academic performance across three NQF levels.
          </p>
          <p>
            I'm actively looking for <strong>graduate roles, internships, or bursary opportunities</strong>
            in data science, cybersecurity, or cloud — where I can turn academic work into
            real-world impact.
          </p>
          <div class="track-chips">
            <span class="chip">📊 Data Science</span>
            <span class="chip">🔐 Cybersecurity</span>
            <span class="chip">☁️ Cloud Computing</span>
            <span class="chip">🤖 Machine Learning</span>
          </div>
        </div>
        <div class="about-edu">
          <div class="edu-card">
            <div class="edu-school">Richfield Graduate Institute of Technology</div>
            <div class="edu-degree">BSc Information Technology — Emerging Technology · Pretoria</div>
            <div class="edu-year">2024–2026</div>
            <div class="edu-modules">
              Key modules: Machine Learning 700 · Cyber Security 700 · AI 700 ·
              Cloud Computing 600 · Big Data &amp; IoT 600 · Data Manipulation &amp;
              Visualisation 600 · Statistics for Data Science 600
            </div>
          </div>
          <div class="edu-card">
            <div class="edu-school">Mmoledi Secondary School</div>
            <div class="edu-degree">NSC — Admission to Bachelor's Degree</div>
            <div class="edu-year">2019–2023</div>
          </div>
          <a href="academic_transcript20250804-33-3fzf6w.pdf" class="btn btn-primary" style="margin-top:18px; display:inline-flex;">
            📄 Download Academic Transcript
          </a>
        </div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section class="section section-dark" id="skills">
    <div class="container">
      <div class="section-tag" style="color:var(--teal)">What I Work With</div>
      <div class="section-title">Technical Skills</div>
      <div class="skills-grid">
        <div class="skill-card">
          <div class="skill-icon">📊</div>
          <div class="skill-title">Data & Machine Learning</div>
          <ul class="skill-list">
            <li>Python (pandas, NumPy, scikit-learn)</li>
            <li>matplotlib, seaborn, Plotly</li>
            <li>SQL, Excel, Tableau</li>
            <li>Jupyter Notebooks, Streamlit</li>
          </ul>
        </div>
        <div class="skill-card">
          <div class="skill-icon">🔐</div>
          <div class="skill-title">Cybersecurity</div>
          <ul class="skill-list">
            <li>Network vulnerability assessment</li>
            <li>Endpoint &amp; network defense</li>
            <li>Threat management &amp; response</li>
            <li>Cisco Packet Tracer, cryptography</li>
          </ul>
        </div>
        <div class="skill-card">
          <div class="skill-icon">☁️</div>
          <div class="skill-title">Cloud & Emerging Tech</div>
          <ul class="skill-list">
            <li>AWS Cloud Architecting</li>
            <li>AI, Blockchain, IoT concepts</li>
            <li>Cloud security fundamentals</li>
            <li>IBM SkillsBuild technologies</li>
          </ul>
        </div>
        <div class="skill-card">
          <div class="skill-icon">🛠️</div>
          <div class="skill-title">Tools & Development</div>
          <ul class="skill-list">
            <li>Git, GitHub, Linux</li>
            <li>VS Code, PyCharm</li>
            <li>HTML, CSS, JavaScript</li>
            <li>FAISS, RAG pipelines, LLMs</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section class="section section-alt" id="projects">
    <div class="container">
      <div class="section-tag">What I've Built</div>
      <div class="section-title">Academic Projects</div>
      <div class="projects-grid">

        <!-- FEATURED: Road Accidents Dashboard -->
        <div class="project-card featured">
          <div class="project-banner" style="background: linear-gradient(135deg, #0D1B2A 0%, #1A3A5C 100%);">
            <div>
              <div class="project-banner-label">⭐ Featured Project · ML700</div>
              <h3>SA Road Accidents<br/>ML Safety Dashboard</h3>
              <p>
                An interactive dashboard combining ensemble machine learning with a
                Q-learning RL agent for adaptive road safety intervention recommendations.
              </p>
            </div>
            <div class="tag-row">
              <span class="tag">Python</span>
              <span class="tag">scikit-learn</span>
              <span class="tag">Streamlit</span>
              <span class="tag">Q-Learning</span>
              <span class="tag">Plotly</span>
            </div>
          </div>
          <div class="project-body">
            <ul class="project-highlights">
              <li>Random Forest, Gradient Boosting &amp; Soft-Voting Ensemble (83% accuracy)</li>
              <li>Q-learning agent with 9-state MDP across 5,000 training episodes</li>
              <li>Live prediction tool: input accident details → severity + intervention</li>
              <li>Interactive EDA with 6 Plotly charts and sidebar filters</li>
              <li>POPIA-compliant responsible AI framework</li>
            </ul>
            <div class="project-links">
              <a href="https://github.com/terrence-dev247" class="project-link" target="_blank">
                ⬡ GitHub Repo
              </a>
            </div>
          </div>
        </div>

        <!-- RAG Pipeline -->
        <div class="project-card">
          <div class="project-banner" style="background: linear-gradient(135deg, #0D2B1A 0%, #0D3B2A 100%);">
            <div class="project-banner-label">ML700 · NLP</div>
            <h3>Parliamentary Hansard RAG Pipeline</h3>
            <p>Semantic search system over SA Parliamentary transcripts using LLMs and vector retrieval.</p>
            <div class="tag-row">
              <span class="tag">FAISS</span>
              <span class="tag">TF-IDF</span>
              <span class="tag">LSA</span>
              <span class="tag">BPE</span>
              <span class="tag">Python</span>
            </div>
          </div>
          <div class="project-body">
            <ul class="project-highlights">
              <li>BPE tokenisation + TF-IDF &amp; LSA embeddings</li>
              <li>FAISS-indexed vector store for semantic search</li>
              <li>Sentiment classification pipeline</li>
              <li>POPIA-compliant responsible AI framework</li>
            </ul>
            <div class="project-links">
              <a href="https://github.com/terrence-dev247" class="project-link" target="_blank">⬡ GitHub</a>
            </div>
          </div>
        </div>

        <!-- Phishing Classifier -->
        <div class="project-card">
          <div class="project-banner" style="background: linear-gradient(135deg, #1A0D2B 0%, #2A0D3B 100%);">
            <div class="project-banner-label">Cybersecurity + ML</div>
            <h3>Phishing Email Classifier</h3>
            <p>Machine learning model to detect phishing emails — bridging data science and cybersecurity.</p>
            <div class="tag-row">
              <span class="tag">Python</span>
              <span class="tag">NLP</span>
              <span class="tag">scikit-learn</span>
            </div>
          </div>
          <div class="project-body">
            <ul class="project-highlights">
              <li>NLP feature extraction on email text</li>
              <li>Classification across multiple ML algorithms</li>
              <li>Applied to real-world cybersecurity threat detection</li>
            </ul>
            <div class="project-links">
              <a href="https://github.com/terrence-dev247" class="project-link" target="_blank">⬡ GitHub</a>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- CERTS -->
  <section class="section" id="certs">
    <div class="container">
      <div class="section-tag">Credentials</div>
      <div class="section-title">Certifications & Badges</div>
      <div class="cert-groups">

        <div class="cert-group">
          <div class="cert-group-header">
            <div class="cert-group-icon">🔐</div>
            <div class="cert-group-title">Cybersecurity</div>
            <div class="cert-group-count">7</div>
          </div>
          <div class="cert-items">
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">Junior Cybersecurity Analyst Career Path</div><div class="cert-issuer">Cisco Networking Academy</div></div><div class="cert-year">2024</div></div>
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">Cyber Threat Management</div><div class="cert-issuer">Cisco Networking Academy</div></div><div class="cert-year">2024</div></div>
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">Network Defense</div><div class="cert-issuer">Cisco Networking Academy</div></div><div class="cert-year">2024</div></div>
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">Endpoint Security</div><div class="cert-issuer">Cisco Networking Academy</div></div><div class="cert-year">2024</div></div>
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">Introduction to Cybersecurity</div><div class="cert-issuer">Cisco Networking Academy</div></div><div class="cert-year">2024</div></div>
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">Cybersecurity Fundamentals</div><div class="cert-issuer">IBM SkillsBuild</div></div><div class="cert-year">2024</div></div>
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">Intro to Threat Landscape 2.0</div><div class="cert-issuer">Fortinet</div></div><div class="cert-year">2024</div></div>
          </div>
        </div>

        <div class="cert-group">
          <div class="cert-group-header">
            <div class="cert-group-icon">📊</div>
            <div class="cert-group-title">Data, Cloud & Emerging Tech</div>
            <div class="cert-group-count">4</div>
          </div>
          <div class="cert-items">
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">Data Analytics Essentials</div><div class="cert-issuer">Cisco Networking Academy</div></div><div class="cert-year">2025</div></div>
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">Introduction to Data Science</div><div class="cert-issuer">Cisco Networking Academy</div></div><div class="cert-year">2025</div></div>
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">AWS Academy — Cloud Architecting</div><div class="cert-issuer">Amazon Web Services</div></div><div class="cert-year">2024</div></div>
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">Explore Emerging Tech</div><div class="cert-issuer">IBM SkillsBuild</div></div><div class="cert-year">2024</div></div>
          </div>
        </div>

        <div class="cert-group">
          <div class="cert-group-header">
            <div class="cert-group-icon">🌐</div>
            <div class="cert-group-title">Networking & Development</div>
            <div class="cert-group-count">4</div>
          </div>
          <div class="cert-items">
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">Networking Basics</div><div class="cert-issuer">Cisco Networking Academy</div></div><div class="cert-year">2024</div></div>
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">Networking Devices & Initial Config</div><div class="cert-issuer">Cisco Networking Academy</div></div><div class="cert-year">2024</div></div>
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">Operating Systems Basics</div><div class="cert-issuer">Cisco Networking Academy</div></div><div class="cert-year">2024</div></div>
            <div class="cert-item"><div class="cert-dot"></div><div><div class="cert-name">JavaScript Essentials 1</div><div class="cert-issuer">Cisco / OpenEDG</div></div><div class="cert-year">2024</div></div>
          </div>
        </div>

      </div>
      <div style="margin-top: 28px; text-align:center;">
        <a href="https://www.credly.com/users/tebogo-poohe" target="_blank" class="btn btn-primary">
          🏅 View All Verified Badges on Credly
        </a>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section class="section section-dark" id="contact">
    <div class="container">
      <div class="contact-grid">
        <div class="contact-text">
          <div class="section-tag" style="color:var(--teal)">Get In Touch</div>
          <div class="section-title">Open to opportunities.</div>
          <p>
            I'm actively looking for graduate roles, internships, and bursary opportunities
            in data science, cybersecurity, or cloud computing. Let's connect.
          </p>
          <a href="mailto:terrencepoohe@gmail.com" class="btn btn-primary">Send me an Email →</a>
        </div>
        <div class="contact-links">
          <a href="mailto:terrencepoohe@gmail.com" class="contact-link">
            <div class="contact-link-icon">✉️</div>
            <div>
              <div class="contact-link-label">Email</div>
              <div class="contact-link-val">terrencepoohe@gmail.com</div>
            </div>
          </a>
          <a href="https://www.linkedin.com/in/tebogo-poohe" target="_blank" class="contact-link">
            <div class="contact-link-icon">💼</div>
            <div>
              <div class="contact-link-label">LinkedIn</div>
              <div class="contact-link-val">linkedin.com/in/tebogo-poohe</div>
            </div>
          </a>
          <a href="https://github.com/terrence-dev247" target="_blank" class="contact-link">
            <div class="contact-link-icon">⬡</div>
            <div>
              <div class="contact-link-label">GitHub</div>
              <div class="contact-link-val">github.com/terrence-dev247</div>
            </div>
          </a>
          <a href="https://www.credly.com/users/tebogo-poohe" target="_blank" class="contact-link">
            <div class="contact-link-icon">🏅</div>
            <div>
              <div class="contact-link-label">Credly Badges</div>
              <div class="contact-link-val">credly.com/users/tebogo-poohe</div>
            </div>
          </a>
          <a href="tel:+27673314015" class="contact-link">
            <div class="contact-link-icon">📞</div>
            <div>
              <div class="contact-link-label">Phone</div>
              <div class="contact-link-val">+27 67 331 4015</div>
            </div>
          </a>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <p>Designed &amp; built by Tebogo Terrence Poohe · Pretoria, South Africa ·
      <a href="https://github.com/terrence-dev247" target="_blank">GitHub</a>
    </p>
  </footer>

</body>
</html>
