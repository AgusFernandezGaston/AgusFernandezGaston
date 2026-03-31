<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Agustín Fernández Gastón — Data Analyst & Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:ital,wght@0,300;0,400;0,500;1,300&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --border: #1e1e2e;
    --accent: #7fff6e;
    --accent2: #5bc8ff;
    --text: #e8e8f0;
    --muted: #6b6b80;
    --card: #13131c;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Mono', monospace;
    font-size: 14px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(127,255,110,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(127,255,110,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 0 24px;
    position: relative;
    z-index: 1;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
    background: rgba(10,10,15,0.85);
  }

  nav .container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 52px;
  }

  .nav-logo {
    color: var(--accent);
    font-weight: 500;
    font-size: 13px;
    letter-spacing: 0.05em;
    text-decoration: none;
  }

  .nav-links {
    display: flex;
    gap: 28px;
    list-style: none;
  }

  .nav-links a {
    color: var(--muted);
    text-decoration: none;
    font-size: 12px;
    letter-spacing: 0.08em;
    transition: color 0.2s;
  }

  .nav-links a:hover { color: var(--accent); }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding-top: 52px;
  }

  .hero-inner {
    padding: 80px 0 60px;
  }

  .hero-tag {
    display: inline-block;
    font-size: 11px;
    letter-spacing: 0.15em;
    color: var(--accent);
    border: 1px solid rgba(127,255,110,0.3);
    padding: 4px 12px;
    border-radius: 2px;
    margin-bottom: 28px;
    text-transform: uppercase;
  }

  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(42px, 8vw, 76px);
    font-weight: 800;
    line-height: 1.0;
    letter-spacing: -0.03em;
    margin-bottom: 8px;
  }

  h1 .name-line {
    display: block;
  }

  h1 .accent-word {
    color: var(--accent);
  }

  .hero-subtitle {
    font-size: 15px;
    color: var(--muted);
    margin: 24px 0 40px;
    max-width: 520px;
    line-height: 1.8;
  }

  .hero-subtitle span {
    color: var(--accent2);
  }

  .hero-cta {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 11px 24px;
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    letter-spacing: 0.08em;
    text-decoration: none;
    border-radius: 3px;
    transition: all 0.2s;
    cursor: pointer;
    border: none;
  }

  .btn-primary {
    background: var(--accent);
    color: #0a0a0f;
    font-weight: 500;
  }

  .btn-primary:hover {
    background: #6be860;
    transform: translateY(-1px);
  }

  .btn-outline {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--border);
  }

  .btn-outline:hover {
    border-color: var(--accent);
    color: var(--accent);
  }

  /* STACK BAR */
  .stack-bar {
    margin-top: 64px;
    padding: 20px 0;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    display: flex;
    gap: 32px;
    flex-wrap: wrap;
    align-items: center;
  }

  .stack-label {
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    white-space: nowrap;
  }

  .stack-tags {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
  }

  .tag {
    font-size: 11px;
    color: var(--accent2);
    background: rgba(91,200,255,0.07);
    border: 1px solid rgba(91,200,255,0.15);
    padding: 3px 10px;
    border-radius: 2px;
  }

  /* SECTIONS */
  section {
    padding: 80px 0;
  }

  .section-header {
    margin-bottom: 48px;
  }

  .section-num {
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 0.15em;
    display: block;
    margin-bottom: 8px;
  }

  h2 {
    font-family: 'Syne', sans-serif;
    font-size: 36px;
    font-weight: 700;
    letter-spacing: -0.02em;
  }

  /* PROJECTS */
  .projects-grid {
    display: grid;
    gap: 16px;
  }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 28px 32px;
    text-decoration: none;
    color: inherit;
    display: block;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 3px;
    height: 100%;
    background: var(--accent);
    transform: scaleY(0);
    transform-origin: bottom;
    transition: transform 0.25s;
  }

  .project-card:hover {
    border-color: rgba(127,255,110,0.25);
    transform: translateX(4px);
  }

  .project-card:hover::before {
    transform: scaleY(1);
  }

  .project-top {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 16px;
    margin-bottom: 12px;
  }

  .project-title {
    font-family: 'Syne', sans-serif;
    font-size: 18px;
    font-weight: 600;
    color: var(--text);
  }

  .project-arrow {
    color: var(--muted);
    font-size: 18px;
    transition: color 0.2s, transform 0.2s;
    flex-shrink: 0;
  }

  .project-card:hover .project-arrow {
    color: var(--accent);
    transform: translate(3px, -3px);
  }

  .project-desc {
    color: var(--muted);
    font-size: 13px;
    line-height: 1.7;
    margin-bottom: 16px;
  }

  .project-tech {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .tech-tag {
    font-size: 10px;
    letter-spacing: 0.1em;
    color: var(--muted);
    border: 1px solid var(--border);
    padding: 2px 8px;
    border-radius: 2px;
    text-transform: uppercase;
  }

  /* ABOUT */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 40px;
    align-items: start;
  }

  @media (max-width: 600px) {
    .about-grid { grid-template-columns: 1fr; }
  }

  .about-text p {
    color: var(--muted);
    font-size: 13px;
    line-height: 1.9;
    margin-bottom: 16px;
  }

  .about-text p strong {
    color: var(--text);
    font-weight: 500;
  }

  .skills-list {
    display: grid;
    gap: 8px;
  }

  .skill-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 14px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 3px;
    font-size: 12px;
  }

  .skill-name { color: var(--text); }
  .skill-level { color: var(--accent); font-size: 10px; letter-spacing: 0.1em; }

  /* CONTACT */
  .contact-box {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 48px;
    text-align: center;
  }

  .contact-box h3 {
    font-family: 'Syne', sans-serif;
    font-size: 28px;
    font-weight: 700;
    margin-bottom: 12px;
  }

  .contact-box p {
    color: var(--muted);
    font-size: 13px;
    margin-bottom: 32px;
    max-width: 400px;
    margin-left: auto;
    margin-right: auto;
  }

  .contact-links {
    display: flex;
    gap: 12px;
    justify-content: center;
    flex-wrap: wrap;
  }

  /* FOOTER */
  footer {
    border-top: 1px solid var(--border);
    padding: 24px 0;
    text-align: center;
  }

  footer p {
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.08em;
  }

  footer span { color: var(--accent); }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .hero-inner > * {
    animation: fadeUp 0.6s ease both;
  }

  .hero-inner > *:nth-child(1) { animation-delay: 0.1s; }
  .hero-inner > *:nth-child(2) { animation-delay: 0.2s; }
  .hero-inner > *:nth-child(3) { animation-delay: 0.3s; }
  .hero-inner > *:nth-child(4) { animation-delay: 0.4s; }
  .hero-inner > *:nth-child(5) { animation-delay: 0.5s; }

  /* Cursor blink */
  .cursor {
    display: inline-block;
    width: 3px;
    height: 0.85em;
    background: var(--accent);
    margin-left: 4px;
    vertical-align: middle;
    animation: blink 1s step-end infinite;
  }

  @keyframes blink {
    50% { opacity: 0; }
  }
</style>
</head>
<body>

<nav>
  <div class="container">
    <a class="nav-logo" href="#">AFG.dev</a>
    <ul class="nav-links">
      <li><a href="#projects">projects</a></li>
      <li><a href="#about">about</a></li>
      <li><a href="#contact">contact</a></li>
    </ul>
  </div>
</nav>

<section class="hero">
  <div class="container">
    <div class="hero-inner">
      <span class="hero-tag">available for freelance</span>
      <h1>
        <span class="name-line">Agustín</span>
        <span class="name-line"><span class="accent-word">Fernández</span></span>
        <span class="name-line">Gastón<span class="cursor"></span></span>
      </h1>
      <p class="hero-subtitle">
        Data Analyst & Scientist with a background in <span>Electronic Engineering</span>.<br>
        I turn raw data into decisions — and ideas into websites.
      </p>
      <div class="hero-cta">
        <a href="#projects" class="btn btn-primary">View my work →</a>
        <a href="https://www.linkedin.com/in/fern%C3%A1ndez-gast%C3%B3n-agust%C3%ADn-2571182aa/" target="_blank" class="btn btn-outline">LinkedIn</a>
        <a href="https://github.com/AgusFernandezGaston" target="_blank" class="btn btn-outline">GitHub</a>
      </div>

      <div class="stack-bar">
        <span class="stack-label">Stack</span>
        <div class="stack-tags">
          <span class="tag">R</span>
          <span class="tag">Python</span>
          <span class="tag">Power BI</span>
          <span class="tag">DAX</span>
          <span class="tag">ggplot2</span>
          <span class="tag">Framer</span>
          <span class="tag">HTML/CSS</span>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="projects">
  <div class="container">
    <div class="section-header">
      <span class="section-num">// 01</span>
      <h2>Projects</h2>
    </div>

    <div class="projects-grid">

      <a class="project-card" href="https://github.com/AgusFernandezGaston" target="_blank">
        <div class="project-top">
          <span class="project-title">Depression Risk Analysis — Argentine Students</span>
          <span class="project-arrow">↗</span>
        </div>
        <p class="project-desc">
          Statistical analysis of risk behaviors (alcohol, tobacco, drugs, physical inactivity) and depression probability across 56,981 secondary school students. Full pipeline: VBA data cleaning, EDA, chi-square testing, Cramér's V, and ggplot2 visualizations.
        </p>
        <div class="project-tech">
          <span class="tech-tag">R</span>
          <span class="tech-tag">ggplot2</span>
          <span class="tech-tag">Statistics</span>
          <span class="tech-tag">EMSE 2018</span>
          <span class="tech-tag">VBA</span>
        </div>
      </a>

      <a class="project-card" href="#" target="_blank">
        <div class="project-top">
          <span class="project-title">Sales Performance Dashboard</span>
          <span class="project-arrow">↗</span>
        </div>
        <p class="project-desc">
          Interactive Power BI dashboard with dimensional star schema model (Calendar, Customers, Brands, Products). KPI cards, combo charts, treemap, year-over-year comparison 2016 vs 2017, slicers, and Q&A natural language visual.
        </p>
        <div class="project-tech">
          <span class="tech-tag">Power BI</span>
          <span class="tech-tag">DAX</span>
          <span class="tech-tag">Star Schema</span>
          <span class="tech-tag">Data Modeling</span>
        </div>
      </a>

      <a class="project-card" href="https://github.com/AgusFernandezGaston/workshop-brilliance" target="_blank">
        <div class="project-top">
          <span class="project-title">Workshop Brilliance</span>
          <span class="project-arrow">↗</span>
        </div>
        <p class="project-desc">
          Web development project showcasing front-end skills and modern design implementation.
        </p>
        <div class="project-tech">
          <span class="tech-tag">Web Dev</span>
          <span class="tech-tag">HTML/CSS</span>
          <span class="tech-tag">JavaScript</span>
        </div>
      </a>

      <a class="project-card" href="https://aviat.framer.website/" target="_blank">
        <div class="project-top">
          <span class="project-title">Aviat Medical Clinic — Website</span>
          <span class="project-arrow">↗</span>
        </div>
        <p class="project-desc">
          Clean, modern website for a medical clinic. WhatsApp-integrated appointment booking, Google Maps embed, mobile-first responsive design. Real client, live production site.
        </p>
        <div class="project-tech">
          <span class="tech-tag">Framer</span>
          <span class="tech-tag">UX Design</span>
          <span class="tech-tag">Web</span>
          <span class="tech-tag">Client Work</span>
        </div>
      </a>

    </div>
  </div>
</section>

<section id="about">
  <div class="container">
    <div class="section-header">
      <span class="section-num">// 02</span>
      <h2>About</h2>
    </div>

    <div class="about-grid">
      <div class="about-text">
        <p>
          I'm a <strong>Data Scientist</strong> graduated from the Data Science Diploma at Mundos E (Córdoba, Argentina), currently finishing my degree in <strong>Electronic Engineering</strong>.
        </p>
        <p>
          I work with <strong>R, Python, and Power BI</strong> to analyze data, build statistical models, and create dashboards that help people make better decisions.
        </p>
        <p>
          On the side, I build websites for businesses using Framer, and I repair electronics. I'm based in <strong>La Rioja, Argentina</strong> and open to remote freelance work from anywhere.
        </p>
        <p>
          I'm looking to grow in data analytics and business intelligence, building toward a fully remote career that fits my life.
        </p>
      </div>

      <div class="skills-list">
        <div class="skill-row">
          <span class="skill-name">R / ggplot2 / tidyverse</span>
          <span class="skill-level">Advanced</span>
        </div>
        <div class="skill-row">
          <span class="skill-name">Power BI / DAX</span>
          <span class="skill-level">Advanced</span>
        </div>
        <div class="skill-row">
          <span class="skill-name">Statistical Modeling</span>
          <span class="skill-level">Advanced</span>
        </div>
        <div class="skill-row">
          <span class="skill-name">Python / pandas</span>
          <span class="skill-level">Intermediate</span>
        </div>
        <div class="skill-row">
          <span class="skill-name">Excel / VBA</span>
          <span class="skill-level">Intermediate</span>
        </div>
        <div class="skill-row">
          <span class="skill-name">Web Dev / Framer</span>
          <span class="skill-level">Intermediate</span>
        </div>
        <div class="skill-row">
          <span class="skill-name">Electronic Engineering</span>
          <span class="skill-level">In progress</span>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="container">
    <div class="section-header">
      <span class="section-num">// 03</span>
      <h2>Contact</h2>
    </div>
    <div class="contact-box">
      <h3>Let's work together</h3>
      <p>Open to freelance projects in data analysis, Power BI dashboards, and web development. Remote-friendly.</p>
      <div class="contact-links">
        <a href="https://www.linkedin.com/in/fern%C3%A1ndez-gast%C3%B3n-agust%C3%ADn-2571182aa/" target="_blank" class="btn btn-primary">LinkedIn →</a>
        <a href="https://github.com/AgusFernandezGaston" target="_blank" class="btn btn-outline">GitHub</a>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="container">
    <p>Built by <span>Agustín Fernández Gastón</span> · La Rioja, Argentina · 2026</p>
  </div>
</footer>

</body>
</html>## Hi there 👋

<!--
**AgusFernandezGaston/AgusFernandezGaston** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
