<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Karan Aswal — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #070B12;
    --surface: #0D1421;
    --border: #1A2540;
    --accent: #00E5FF;
    --accent2: #7B5EA7;
    --accent3: #FF6B35;
    --text: #E8EDF5;
    --muted: #6B7A99;
    --card: #111827;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 40px 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 32px;
    align-items: start;
    margin-bottom: 48px;
    animation: fadeUp 0.7s ease both;
  }

  .hero-label {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 3px;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 12px;
    opacity: 0.8;
  }

  h1 {
    font-size: clamp(2.4rem, 6vw, 3.6rem);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -1px;
    color: #fff;
    margin-bottom: 6px;
  }

  .role-tag {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    margin-bottom: 18px;
  }

  .role-tag span {
    color: var(--accent);
    font-size: 16px;
  }

  .summary {
    font-size: 14px;
    line-height: 1.75;
    color: #A0AEBE;
    max-width: 540px;
    margin-bottom: 24px;
  }

  .links-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .link-chip {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.5px;
    padding: 7px 14px;
    border: 1px solid var(--border);
    border-radius: 4px;
    color: var(--muted);
    text-decoration: none;
    transition: all 0.2s;
    background: var(--surface);
  }

  .link-chip:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(0,229,255,0.05);
  }

  .link-chip svg { width: 13px; height: 13px; }

  /* Status badge */
  .status-badge {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    padding: 20px;
    border: 1px solid var(--border);
    border-radius: 8px;
    background: var(--surface);
    white-space: nowrap;
    min-width: 140px;
  }

  .status-dot {
    width: 8px; height: 8px;
    background: #22c55e;
    border-radius: 50%;
    box-shadow: 0 0 8px #22c55e;
    animation: pulse 2s ease infinite;
  }

  .status-badge .label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--muted);
    text-transform: uppercase;
  }

  .status-badge .value {
    font-size: 12px;
    font-weight: 700;
    color: #22c55e;
    text-align: center;
  }

  /* ── SECTION HEADERS ── */
  .section { margin-bottom: 44px; animation: fadeUp 0.7s ease both; }

  .section-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 20px;
  }

  .section-tag {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 3px;
    color: var(--accent);
    text-transform: uppercase;
    padding: 4px 10px;
    border: 1px solid rgba(0,229,255,0.3);
    border-radius: 2px;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── SKILLS GRID ── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(190px, 1fr));
    gap: 12px;
  }

  .skill-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 16px;
    transition: border-color 0.2s, transform 0.2s;
  }

  .skill-card:hover {
    border-color: var(--accent2);
    transform: translateY(-2px);
  }

  .skill-card .sk-label {
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    letter-spacing: 2px;
    color: var(--accent2);
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .skill-card .sk-items {
    font-size: 12px;
    color: #8A9AB8;
    line-height: 1.8;
  }

  .skill-card .sk-items strong { color: var(--text); font-weight: 600; }

  /* ── STATS ROW ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin-bottom: 44px;
    animation: fadeUp 0.7s ease 0.1s both;
  }

  .stat-box {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 18px 16px;
    text-align: center;
  }

  .stat-box .num {
    font-family: 'Space Mono', monospace;
    font-size: 1.6rem;
    font-weight: 700;
    color: var(--accent);
    display: block;
  }

  .stat-box .desc {
    font-size: 11px;
    color: var(--muted);
    margin-top: 4px;
    line-height: 1.4;
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 20px;
    text-decoration: none;
    color: inherit;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
    display: block;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transition: transform 0.3s;
  }

  .project-card:hover::before { transform: scaleX(1); }
  .project-card:hover {
    border-color: rgba(0,229,255,0.25);
    transform: translateY(-3px);
    box-shadow: 0 12px 40px rgba(0,0,0,0.4);
  }

  .proj-title {
    font-size: 14px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 6px;
  }

  .proj-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
    margin-bottom: 10px;
  }

  .proj-tag {
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    padding: 2px 7px;
    border-radius: 2px;
    background: rgba(0,229,255,0.08);
    border: 1px solid rgba(0,229,255,0.2);
    color: var(--accent);
    letter-spacing: 0.5px;
  }

  .proj-desc {
    font-size: 12px;
    color: #6B7A99;
    line-height: 1.65;
  }

  .proj-impact {
    margin-top: 10px;
    font-size: 11px;
    font-family: 'Space Mono', monospace;
    color: var(--accent3);
  }

  /* ── EXPERIENCE ── */
  .exp-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 22px 24px;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 16px;
    align-items: start;
  }

  .exp-role { font-size: 15px; font-weight: 700; color: #fff; margin-bottom: 4px; }
  .exp-company { font-size: 13px; color: var(--accent); margin-bottom: 10px; }
  .exp-period {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 1px;
    white-space: nowrap;
  }

  .exp-bullets { list-style: none; }
  .exp-bullets li {
    font-size: 12px;
    color: #8A9AB8;
    line-height: 1.7;
    padding-left: 14px;
    position: relative;
    margin-bottom: 3px;
  }

  .exp-bullets li::before {
    content: '▸';
    position: absolute;
    left: 0;
    color: var(--accent);
    font-size: 10px;
    top: 2px;
  }

  /* ── CERTS ── */
  .certs-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
    gap: 10px;
  }

  .cert-chip {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 10px 14px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 5px;
    font-size: 11px;
    color: #8A9AB8;
    text-decoration: none;
    transition: all 0.2s;
    font-weight: 600;
  }

  .cert-chip:hover {
    border-color: var(--accent3);
    color: var(--accent3);
    background: rgba(255,107,53,0.05);
  }

  .cert-chip .dot {
    width: 6px; height: 6px;
    background: var(--accent3);
    border-radius: 50%;
    flex-shrink: 0;
  }

  /* ── FOOTER ── */
  .footer {
    border-top: 1px solid var(--border);
    padding-top: 24px;
    margin-top: 12px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 12px;
  }

  .footer-text {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
  }

  .footer-contact {
    display: flex;
    gap: 12px;
    align-items: center;
  }

  .footer-contact a {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    text-decoration: none;
    transition: color 0.2s;
  }

  .footer-contact a:hover { color: var(--accent); }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes pulse {
    0%, 100% { box-shadow: 0 0 6px #22c55e; }
    50% { box-shadow: 0 0 14px #22c55e, 0 0 24px rgba(34,197,94,0.3); }
  }

  .section:nth-child(2) { animation-delay: 0.1s; }
  .section:nth-child(3) { animation-delay: 0.2s; }
  .section:nth-child(4) { animation-delay: 0.3s; }
  .section:nth-child(5) { animation-delay: 0.4s; }

  @media (max-width: 600px) {
    .hero { grid-template-columns: 1fr; }
    .projects-grid { grid-template-columns: 1fr; }
    .stats-row { grid-template-columns: repeat(2, 1fr); }
    .status-badge { display: none; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div>
      <div class="hero-label">// portfolio &amp; profile</div>
      <h1>Karan Aswal</h1>
      <div class="role-tag">
        <span>▸</span>
        Data Analyst &nbsp;·&nbsp; Aspiring Data Scientist &nbsp;·&nbsp; BCA @ Graphic Era University
      </div>
      <p class="summary">
        Data Analyst with hands-on experience in Python, SQL, and Power BI. Built 10+ automated dashboards cutting report generation time by 60%. Solved 500+ SQL problems on LeetCode, HackerRank &amp; StrataScratch. Building end-to-end data science projects — seeking a Data Science Internship.
      </p>
      <div class="links-row">
        <a class="link-chip" href="https://linkedin.com/in/karan-aswal" target="_blank">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-4 0v7h-4v-7a6 6 0 0 1 6-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
          LinkedIn
        </a>
        <a class="link-chip" href="https://github.com/Karan7088" target="_blank">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
          GitHub
        </a>
        <a class="link-chip" href="https://karanaswal.netlify.app" target="_blank">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/></svg>
          Portfolio
        </a>
        <a class="link-chip" href="mailto:aswalkaran87@gmail.com">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
          Email
        </a>
        <a class="link-chip" href="tel:7088455127">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12 19.79 19.79 0 0 1 1.61 3.38 2 2 0 0 1 3.58 1h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L7.91 8.06a16 16 0 0 0 6 6l.88-.88a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
          +91 7088455127
        </a>
      </div>
    </div>
    <div class="status-badge">
      <div class="status-dot"></div>
      <div class="label">Open to</div>
      <div class="value">Internship<br>Opportunities</div>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-row">
    <div class="stat-box">
      <span class="num">500+</span>
      <div class="desc">SQL Problems Solved</div>
    </div>
    <div class="stat-box">
      <span class="num">10+</span>
      <div class="desc">Automated Dashboards Built</div>
    </div>
    <div class="stat-box">
      <span class="num">60%</span>
      <div class="desc">Report Time Reduction</div>
    </div>
    <div class="stat-box">
      <span class="num">8.5</span>
      <div class="desc">CGPA / 10.0</div>
    </div>
  </div>

  <!-- EXPERIENCE -->
  <div class="section">
    <div class="section-header">
      <div class="section-tag">Experience</div>
      <div class="section-line"></div>
    </div>
    <div class="exp-card">
      <div>
        <div class="exp-role">Data Analyst Intern</div>
        <div class="exp-company">Evoa Pvt. Ltd. — Bareilly, India</div>
        <ul class="exp-bullets">
          <li>Extracted &amp; transformed data with Python &amp; SQL — <strong>40% faster</strong> processing</li>
          <li>Wrote complex MySQL queries (JOINs, aggregations) to optimize analytical performance</li>
          <li>Developed Power BI dashboards with DAX for real-time business insights</li>
          <li>Ensured data quality, consistency &amp; governance compliance across datasets</li>
        </ul>
      </div>
      <div class="exp-period">Jul 2024 – Nov 2024</div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-header">
      <div class="section-tag">Projects</div>
      <div class="section-line"></div>
    </div>
    <div class="projects-grid">

      <a class="project-card" href="https://github.com/Karan7088" target="_blank">
        <div class="proj-title">YouTube Analytics Dashboard</div>
        <div class="proj-tags">
          <span class="proj-tag">Python</span>
          <span class="proj-tag">Power BI</span>
          <span class="proj-tag">SerpAPI</span>
        </div>
        <div class="proj-desc">Automated extraction of 10,000+ engagement metrics. Built interactive dashboard to visualize content performance trends.</div>
        <div class="proj-impact">↑ 20% avg watch time improvement</div>
      </a>

      <a class="project-card" href="https://github.com/Karan7088" target="_blank">
        <div class="proj-title">Ola Booking Insights Dashboard</div>
        <div class="proj-tags">
          <span class="proj-tag">Excel</span>
          <span class="proj-tag">Power BI</span>
          <span class="proj-tag">Julius AI</span>
        </div>
        <div class="proj-desc">Consolidated 50,000+ ride records. Analyzed cancellation hotspots with geospatial visualization.</div>
        <div class="proj-impact">↓ 10% cancellation rate</div>
      </a>

      <a class="project-card" href="https://github.com/Karan7088" target="_blank">
        <div class="proj-title">Amazon Sales Analysis</div>
        <div class="proj-tags">
          <span class="proj-tag">Python</span>
          <span class="proj-tag">Power BI</span>
          <span class="proj-tag">Julius AI</span>
        </div>
        <div class="proj-desc">Cleaned 10,000+ transactional records. Visualized seasonal sales trends &amp; top-performing products.</div>
        <div class="proj-impact">↓ 15% overstocking reduction</div>
      </a>

      <a class="project-card" href="https://github.com/Karan7088" target="_blank">
        <div class="proj-title">Netflix Viewing Trends</div>
        <div class="proj-tags">
          <span class="proj-tag">MySQL</span>
          <span class="proj-tag">Window Functions</span>
          <span class="proj-tag">CTEs</span>
        </div>
        <div class="proj-desc">Advanced SQL analysis on 100,000+ records — regional preferences, viewing patterns, retention insights.</div>
        <div class="proj-impact">→ Actionable marketing insights</div>
      </a>

      <a class="project-card" href="https://github.com/Karan7088" target="_blank">
        <div class="proj-title">Hospital DB Management</div>
        <div class="proj-tags">
          <span class="proj-tag">MySQL</span>
          <span class="proj-tag">SQL</span>
        </div>
        <div class="proj-desc">Designed comprehensive hospital DB — patients, appointments, billing. Optimized queries for faster retrieval.</div>
        <div class="proj-impact">↑ 35% operational efficiency</div>
      </a>

      <a class="project-card" href="https://github.com/Karan7088" target="_blank">
        <div class="proj-title">Automation Mini-Projects</div>
        <div class="proj-tags">
          <span class="proj-tag">Python</span>
          <span class="proj-tag">BeautifulSoup</span>
          <span class="proj-tag">REST APIs</span>
        </div>
        <div class="proj-desc">Excel-to-SQL uploader, web scraper, REST API Power BI connector, &amp; data export automation scripts.</div>
        <div class="proj-impact">→ 3+ hours saved weekly</div>
      </a>

    </div>
  </div>

  <!-- SKILLS -->
  <div class="section">
    <div class="section-header">
      <div class="section-tag">Tech Stack</div>
      <div class="section-line"></div>
    </div>
    <div class="skills-grid">
      <div class="skill-card">
        <div class="sk-label">Languages</div>
        <div class="sk-items"><strong>Python</strong> · Pandas · NumPy · Matplotlib · Seaborn<br><strong>MySQL</strong></div>
      </div>
      <div class="skill-card">
        <div class="sk-label">Visualization</div>
        <div class="sk-items"><strong>Power BI</strong> · DAX<br><strong>Tableau</strong><br><strong>Excel</strong> · Power Query</div>
      </div>
      <div class="skill-card">
        <div class="sk-label">Machine Learning</div>
        <div class="sk-items">Forecasting · Feature Engineering<br>Model Training · Hyperparameter Tuning</div>
      </div>
      <div class="skill-card">
        <div class="sk-label">Data Engineering</div>
        <div class="sk-items">ETL Pipelines · Data Cleaning<br>Normalization · Encoding<br>Missing Value Handling</div>
      </div>
      <div class="skill-card">
        <div class="sk-label">Database</div>
        <div class="sk-items">Query Optimization · Indexing<br>Backup · Access Control<br>Data Validation</div>
      </div>
      <div class="skill-card">
        <div class="sk-label">Statistics</div>
        <div class="sk-items">Descriptive &amp; Inferential Stats<br>Hypothesis Testing<br>Correlation Analysis</div>
      </div>
    </div>
  </div>

  <!-- CERTIFICATIONS -->
  <div class="section">
    <div class="section-header">
      <div class="section-tag">Certifications</div>
      <div class="section-line"></div>
    </div>
    <div class="certs-grid">
      <a class="cert-chip" href="#" target="_blank"><span class="dot"></span>Data Science</a>
      <a class="cert-chip" href="#" target="_blank"><span class="dot"></span>Advanced MS Excel</a>
      <a class="cert-chip" href="https://www.hackerrank.com" target="_blank"><span class="dot"></span>SQL Advanced · HackerRank</a>
      <a class="cert-chip" href="#" target="_blank"><span class="dot"></span>Data Analytics Advanced</a>
      <a class="cert-chip" href="https://learn.microsoft.com" target="_blank"><span class="dot"></span>Power BI · Microsoft</a>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="footer-text">// currently open to Data Science Internship opportunities</div>
    <div class="footer-contact">
      <a href="mailto:aswalkaran87@gmail.com">aswalkaran87@gmail.com</a>
      <a href="https://karanaswal.netlify.app" target="_blank">karanaswal.netlify.app</a>
    </div>
  </div>

</div>
</body>
</html>
