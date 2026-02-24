<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ali Azzam — Founder & CEO, Paramount Intelligence</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=DM+Mono:wght@300;400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #080c10;
    --surface: #0d1117;
    --surface2: #141b24;
    --border: rgba(99,179,237,0.12);
    --accent: #63b3ed;
    --accent2: #f6ad55;
    --text: #e2e8f0;
    --muted: #718096;
    --subtle: #2d3748;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* Ambient background */
  body::before {
    content: '';
    position: fixed;
    top: -200px;
    right: -200px;
    width: 700px;
    height: 700px;
    background: radial-gradient(circle, rgba(99,179,237,0.06) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
  }
  body::after {
    content: '';
    position: fixed;
    bottom: -200px;
    left: -200px;
    width: 600px;
    height: 600px;
    background: radial-gradient(circle, rgba(246,173,85,0.05) 0%, transparent 70%);
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

  /* ── HERO ── */
  .hero {
    padding: 80px 0 60px;
    border-bottom: 1px solid var(--border);
  }

  .hero-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 20px;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.1s;
  }

  .hero-eyebrow span {
    display: inline-block;
    background: rgba(99,179,237,0.08);
    border: 1px solid rgba(99,179,237,0.2);
    border-radius: 2px;
    padding: 4px 10px;
  }

  .hero-name {
    font-family: 'Playfair Display', serif;
    font-size: clamp(42px, 7vw, 72px);
    font-weight: 900;
    line-height: 1.05;
    letter-spacing: -0.02em;
    color: #f0f4f8;
    margin-bottom: 16px;
    opacity: 0;
    animation: fadeUp 0.7s ease forwards 0.2s;
  }

  .hero-name .accent-line {
    display: block;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-tagline {
    font-size: 16px;
    color: var(--muted);
    max-width: 520px;
    margin-bottom: 36px;
    opacity: 0;
    animation: fadeUp 0.7s ease forwards 0.3s;
  }

  .hero-links {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
    opacity: 0;
    animation: fadeUp 0.7s ease forwards 0.4s;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    letter-spacing: 0.05em;
    padding: 10px 18px;
    border-radius: 3px;
    text-decoration: none;
    transition: all 0.2s ease;
    cursor: pointer;
  }

  .btn-primary {
    background: var(--accent);
    color: var(--bg);
    font-weight: 500;
    border: 1px solid var(--accent);
  }
  .btn-primary:hover { background: #90cdf4; border-color: #90cdf4; transform: translateY(-1px); }

  .btn-outline {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--subtle);
  }
  .btn-outline:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-1px); }

  /* ── SECTION ── */
  section {
    padding: 56px 0;
    border-bottom: 1px solid var(--border);
    opacity: 0;
    transform: translateY(20px);
    animation: fadeUp 0.7s ease forwards;
  }
  section:nth-child(2) { animation-delay: 0.5s; }
  section:nth-child(3) { animation-delay: 0.6s; }
  section:nth-child(4) { animation-delay: 0.7s; }
  section:nth-child(5) { animation-delay: 0.8s; }
  section:nth-child(6) { animation-delay: 0.9s; }

  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--accent2);
    margin-bottom: 28px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(22px, 3vw, 30px);
    font-weight: 700;
    color: #f0f4f8;
    margin-bottom: 8px;
  }

  .section-sub {
    color: var(--muted);
    font-size: 14px;
    margin-bottom: 36px;
  }

  /* ── TECH STACK ── */
  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }

  .stack-item {
    background: var(--surface);
    padding: 20px;
    transition: background 0.2s;
  }
  .stack-item:hover { background: var(--surface2); }

  .stack-category {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 8px;
  }

  .stack-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
  }

  .tag {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--subtle);
    border-radius: 2px;
    padding: 3px 7px;
    transition: all 0.2s;
  }
  .tag:hover { color: var(--text); border-color: var(--accent); }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }

  .project-card {
    background: var(--surface);
    padding: 28px 32px;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 16px;
    align-items: start;
    transition: background 0.2s;
    text-decoration: none;
    color: inherit;
    position: relative;
  }
  .project-card::before {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    bottom: 0;
    width: 2px;
    background: transparent;
    transition: background 0.2s;
  }
  .project-card:hover { background: var(--surface2); }
  .project-card:hover::before { background: var(--accent); }

  .project-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 8px;
  }

  .project-num {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.1em;
  }

  .project-title {
    font-family: 'Playfair Display', serif;
    font-size: 17px;
    font-weight: 700;
    color: #f0f4f8;
    transition: color 0.2s;
  }
  .project-card:hover .project-title { color: var(--accent); }

  .project-desc {
    font-size: 13.5px;
    color: var(--muted);
    line-height: 1.6;
    max-width: 560px;
    margin-bottom: 14px;
  }

  .project-meta {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
  }

  .project-badge {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.05em;
    color: var(--accent2);
    background: rgba(246,173,85,0.08);
    border: 1px solid rgba(246,173,85,0.2);
    border-radius: 2px;
    padding: 2px 8px;
  }

  .project-arrow {
    color: var(--muted);
    font-size: 18px;
    margin-top: 4px;
    transition: all 0.2s;
  }
  .project-card:hover .project-arrow { color: var(--accent); transform: translate(2px, -2px); }

  /* ── CURRENTLY BUILDING ── */
  .building-list {
    display: flex;
    flex-direction: column;
    gap: 0;
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }

  .building-item {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 18px 24px;
    background: var(--surface);
    border-bottom: 1px solid var(--border);
    transition: background 0.2s;
  }
  .building-item:last-child { border-bottom: none; }
  .building-item:hover { background: var(--surface2); }

  .building-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--accent);
    flex-shrink: 0;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.8); }
  }

  .building-text {
    font-size: 14px;
    color: var(--text);
  }

  /* ── CONTACT ── */
  .contact-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }

  .contact-item {
    background: var(--surface);
    padding: 24px;
    text-decoration: none;
    transition: background 0.2s;
    display: block;
  }
  .contact-item:hover { background: var(--surface2); }

  .contact-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 6px;
  }

  .contact-value {
    font-size: 14px;
    color: var(--accent);
    font-weight: 400;
  }

  /* ── FOOTER ── */
  .footer {
    padding: 40px 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: gap;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 1.1s;
  }

  .footer-note {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.05em;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* scrollbar */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: var(--subtle); border-radius: 2px; }

  @media (max-width: 600px) {
    .project-card { grid-template-columns: 1fr; }
    .project-arrow { display: none; }
  }
</style>
</head>
<body>

<div class="container">

  <!-- HERO -->
  <header class="hero">
    <div class="hero-eyebrow"><span>Founder & CEO — Paramount Intelligence</span></div>
    <h1 class="hero-name">
      Ali Azzam
      <span class="accent-line">AI & Automation</span>
    </h1>
    <p class="hero-tagline">
      I build practical AI systems, automation platforms, and data-driven infrastructure that solve real business challenges and drive measurable outcomes.
    </p>
    <div class="hero-links">
      <a class="btn btn-primary" href="mailto:syedaliazzam@gmail.com">
        <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        syedaliazzam@gmail.com
      </a>
      <a class="btn btn-outline" href="https://linkedin.com/in/Ali" target="_blank">
        <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
        LinkedIn
      </a>
      <a class="btn btn-outline" href="https://github.com/syedaliazzam" target="_blank">
        <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
        GitHub
      </a>
    </div>
  </header>

  <!-- TECH STACK -->
  <section>
    <div class="section-label">02 — Technical Foundation</div>
    <h2 class="section-title">Technologies & Tools</h2>
    <p class="section-sub">A full-stack toolkit spanning AI, automation, cloud infrastructure, and data systems.</p>

    <div class="stack-grid">
      <div class="stack-item">
        <div class="stack-category">Languages</div>
        <div class="stack-tags">
          <span class="tag">Python</span>
          <span class="tag">JavaScript</span>
          <span class="tag">SQL</span>
          <span class="tag">R</span>
        </div>
      </div>
      <div class="stack-item">
        <div class="stack-category">AI & ML</div>
        <div class="stack-tags">
          <span class="tag">LLMs</span>
          <span class="tag">RAG</span>
          <span class="tag">NLP</span>
          <span class="tag">AI Agents</span>
          <span class="tag">Prompt Engineering</span>
        </div>
      </div>
      <div class="stack-item">
        <div class="stack-category">Backend & APIs</div>
        <div class="stack-tags">
          <span class="tag">FastAPI</span>
          <span class="tag">Node.js</span>
          <span class="tag">REST</span>
          <span class="tag">Webhooks</span>
        </div>
      </div>
      <div class="stack-item">
        <div class="stack-category">Cloud</div>
        <div class="stack-tags">
          <span class="tag">AWS Lambda</span>
          <span class="tag">S3</span>
          <span class="tag">API Gateway</span>
          <span class="tag">Serverless</span>
        </div>
      </div>
      <div class="stack-item">
        <div class="stack-category">Automation</div>
        <div class="stack-tags">
          <span class="tag">n8n</span>
          <span class="tag">Zapier</span>
          <span class="tag">Airtable</span>
          <span class="tag">API Orchestration</span>
        </div>
      </div>
      <div class="stack-item">
        <div class="stack-category">Data & Analytics</div>
        <div class="stack-tags">
          <span class="tag">ETL Pipelines</span>
          <span class="tag">Looker</span>
          <span class="tag">Data Studio</span>
          <span class="tag">Dashboards</span>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section>
    <div class="section-label">03 — Open Source Work</div>
    <h2 class="section-title">Featured Projects</h2>
    <p class="section-sub">End-to-end systems built across AI, automation, and data — all open source.</p>

    <div class="projects-grid">

      <a class="project-card" href="https://github.com/syedaliazzam/n8n-Candidate-assessment-system" target="_blank">
        <div>
          <div class="project-header">
            <span class="project-num">01</span>
            <h3 class="project-title">n8n Candidate Assessment System</h3>
          </div>
          <p class="project-desc">A no-code/low-code hiring pipeline built on n8n workflows. Automates screening, scoring, and candidate progression — eliminating manual hiring bottlenecks at scale.</p>
          <div class="project-meta">
            <span class="project-badge">n8n</span>
            <span class="project-badge">Automation</span>
            <span class="project-badge">Hiring Ops</span>
          </div>
        </div>
        <div class="project-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/syedaliazzam/Driver-Ranking-System" target="_blank">
        <div>
          <div class="project-header">
            <span class="project-num">02</span>
            <h3 class="project-title">Driver Ranking System</h3>
          </div>
          <p class="project-desc">Performance ranking engine for logistics partners. Uses data metrics to assign scores and support strategic tiering — optimizing incentives, routing, and partner selection.</p>
          <div class="project-meta">
            <span class="project-badge">Python</span>
            <span class="project-badge">ETL</span>
            <span class="project-badge">Logistics</span>
          </div>
        </div>
        <div class="project-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/syedaliazzam/Dynamic-Price-Engine" target="_blank">
        <div>
          <div class="project-header">
            <span class="project-num">03</span>
            <h3 class="project-title">Dynamic Price Engine</h3>
          </div>
          <p class="project-desc">Real-time pricing engine for demand-driven services. Models elasticity and supply/demand signals with customizable heuristics — increasing revenue through smart, adaptive pricing.</p>
          <div class="project-meta">
            <span class="project-badge">FastAPI</span>
            <span class="project-badge">Python</span>
            <span class="project-badge">Pricing</span>
          </div>
        </div>
        <div class="project-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/syedaliazzam/Freelance-Dashboards" target="_blank">
        <div>
          <div class="project-header">
            <span class="project-num">04</span>
            <h3 class="project-title">Freelance Dashboards</h3>
          </div>
          <p class="project-desc">A suite of performance dashboards tracking revenue, client acquisition, and project analytics. Converts raw data into actionable operational insights.</p>
          <div class="project-meta">
            <span class="project-badge">Dashboards</span>
            <span class="project-badge">Analytics</span>
            <span class="project-badge">Visualization</span>
          </div>
        </div>
        <div class="project-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/syedaliazzam/dark-kendra-chat-nexus" target="_blank">
        <div>
          <div class="project-header">
            <span class="project-num">05</span>
            <h3 class="project-title">Dark Kendra Chat Nexus</h3>
          </div>
          <p class="project-desc">Conversational AI platform combining vector search with generative context for developer workflows. Smart retrieval meets contextual response generation.</p>
          <div class="project-meta">
            <span class="project-badge">LLMs</span>
            <span class="project-badge">Vector Search</span>
            <span class="project-badge">RAG</span>
          </div>
        </div>
        <div class="project-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/syedaliazzam/trendly" target="_blank">
        <div>
          <div class="project-header">
            <span class="project-num">06</span>
            <h3 class="project-title">Trendly</h3>
          </div>
          <p class="project-desc">Trend discovery tool that aggregates and surfaces emerging topics from social and news sources. Built for content strategy, marketing intelligence, and media monitoring.</p>
          <div class="project-meta">
            <span class="project-badge">Web Scraping</span>
            <span class="project-badge">Data Aggregation</span>
            <span class="project-badge">Dashboard</span>
          </div>
        </div>
        <div class="project-arrow">↗</div>
      </a>

    </div>
  </section>

  <!-- CURRENTLY BUILDING -->
  <section>
    <div class="section-label">04 — Active Work</div>
    <h2 class="section-title">Currently Building</h2>
    <p class="section-sub">Open initiatives and ongoing development directions.</p>

    <div class="building-list">
      <div class="building-item">
        <div class="building-dot"></div>
        <div class="building-text">Expanding AI automation libraries for enterprise workflow patterns</div>
      </div>
      <div class="building-item">
        <div class="building-dot"></div>
        <div class="building-text">Advanced RAG systems with real-time data sync and retrieval optimization</div>
      </div>
      <div class="building-item">
        <div class="building-dot"></div>
        <div class="building-text">Open-source automation connectors for enterprise workflow integration</div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section>
    <div class="section-label">05 — Get in Touch</div>
    <h2 class="section-title">Let's Connect</h2>
    <p class="section-sub">Open to conversations about AI, automation, engineering workflows, and open source.</p>

    <div class="contact-grid">
      <a class="contact-item" href="mailto:syedaliazzam@gmail.com">
        <div class="contact-label">Email</div>
        <div class="contact-value">syedaliazzam@gmail.com</div>
      </a>
      <a class="contact-item" href="https://linkedin.com/in/Ali" target="_blank">
        <div class="contact-label">LinkedIn</div>
        <div class="contact-value">linkedin.com/in/Ali</div>
      </a>
      <a class="contact-item" href="https://github.com/syedaliazzam" target="_blank">
        <div class="contact-label">GitHub</div>
        <div class="contact-value">github.com/syedaliazzam</div>
      </a>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <span class="footer-note">Ali Azzam — Paramount Intelligence © 2025</span>
    <span class="footer-note">Building systems that replace manual work with scalable automation.</span>
  </footer>

</div>
</body>
</html>
