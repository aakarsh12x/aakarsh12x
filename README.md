<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Aakarsh Singh</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Geist+Mono:wght@300;400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0a0a0a;
    --bg2: #111111;
    --bg3: #1a1a1a;
    --border: rgba(255,255,255,0.08);
    --border-hover: rgba(255,255,255,0.16);
    --text: #ededed;
    --muted: #888;
    --subtle: #444;
    --accent: #fff;
    --green: #22c55e;
    --mono: 'Geist Mono', monospace;
    --sans: 'DM Sans', sans-serif;
  }

  html { font-size: 16px; }
  body {
    font-family: var(--sans);
    background: var(--bg);
    color: var(--text);
    line-height: 1.6;
    min-height: 100vh;
    -webkit-font-smoothing: antialiased;
  }

  /* ─── LAYOUT ─── */
  .wrapper { max-width: 860px; margin: 0 auto; padding: 0 24px; }

  /* ─── HERO ─── */
  .hero {
    padding: 80px 0 64px;
    border-bottom: 0.5px solid var(--border);
    position: relative;
  }
  .hero-grid {
    position: absolute; inset: 0; pointer-events: none;
    background-image:
      linear-gradient(rgba(255,255,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    mask-image: linear-gradient(to bottom, transparent 0%, black 20%, black 80%, transparent 100%);
  }
  .hero-inner { position: relative; z-index: 1; }

  .status {
    display: inline-flex; align-items: center; gap: 8px;
    font-family: var(--mono); font-size: 11px;
    color: var(--muted);
    border: 0.5px solid var(--border);
    border-radius: 999px; padding: 5px 14px;
    background: var(--bg2);
    margin-bottom: 32px;
    letter-spacing: 0.04em;
  }
  .status-dot {
    width: 6px; height: 6px; border-radius: 50%;
    background: var(--green);
    animation: pulse 2s ease-in-out infinite;
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.4; }
  }

  .hero-name {
    font-size: clamp(52px, 8vw, 80px);
    font-weight: 300;
    letter-spacing: -3px;
    line-height: 0.95;
    color: var(--accent);
    margin-bottom: 20px;
  }
  .hero-name em {
    font-style: normal;
    color: var(--muted);
  }

  .hero-desc {
    font-size: 15px; color: var(--muted);
    max-width: 420px; margin-bottom: 36px;
    line-height: 1.6; font-weight: 300;
  }
  .hero-desc strong { color: var(--text); font-weight: 400; }

  .hero-links { display: flex; gap: 8px; flex-wrap: wrap; }
  .chip {
    display: inline-flex; align-items: center; gap: 7px;
    font-family: var(--mono); font-size: 11px;
    color: var(--muted);
    border: 0.5px solid var(--border);
    border-radius: 6px; padding: 7px 13px;
    background: var(--bg2);
    text-decoration: none;
    transition: border-color 0.15s, color 0.15s, background 0.15s;
    letter-spacing: 0.02em;
  }
  .chip:hover { border-color: var(--border-hover); color: var(--text); background: var(--bg3); }
  .chip svg { opacity: 0.5; flex-shrink: 0; }
  .chip:hover svg { opacity: 1; }

  /* ─── SECTION ─── */
  .section { padding: 56px 0; border-bottom: 0.5px solid var(--border); }
  .section:last-of-type { border-bottom: none; }
  .section-header {
    display: flex; align-items: baseline; gap: 16px;
    margin-bottom: 36px;
  }
  .section-label {
    font-family: var(--mono); font-size: 11px;
    color: var(--subtle); letter-spacing: 0.1em; text-transform: uppercase;
  }
  .section-line {
    flex: 1; height: 0.5px; background: var(--border);
  }

  /* ─── METRICS ─── */
  .metrics { display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 1px; background: var(--border); border: 0.5px solid var(--border); border-radius: 12px; overflow: hidden; }
  .metric {
    background: var(--bg2); padding: 24px 20px;
    transition: background 0.15s;
  }
  .metric:hover { background: var(--bg3); }
  .metric-val {
    font-family: var(--mono); font-size: 28px; font-weight: 400;
    color: var(--accent); letter-spacing: -1px; line-height: 1;
    margin-bottom: 8px;
  }
  .metric-key {
    font-size: 12px; color: var(--muted); font-weight: 300;
    line-height: 1.4;
  }

  /* ─── SKILLS GRID ─── */
  .skills-outer { display: flex; flex-direction: column; gap: 32px; }
  .skill-group-label {
    font-family: var(--mono); font-size: 10px;
    color: var(--subtle); letter-spacing: 0.12em; text-transform: uppercase;
    margin-bottom: 14px;
  }
  .skills-row { display: flex; flex-wrap: wrap; gap: 8px; }

  .skill-pill {
    display: inline-flex; align-items: center; gap: 8px;
    font-family: var(--mono); font-size: 12px;
    color: var(--muted);
    border: 0.5px solid var(--border);
    border-radius: 6px; padding: 8px 14px;
    background: var(--bg2);
    cursor: default;
    transition: border-color 0.15s, color 0.15s, background 0.15s, transform 0.1s;
    letter-spacing: 0.02em;
  }
  .skill-pill:hover {
    border-color: var(--border-hover);
    color: var(--accent);
    background: var(--bg3);
    transform: translateY(-1px);
  }
  .skill-pill:hover .sdot { opacity: 1; }
  .sdot {
    width: 5px; height: 5px; border-radius: 50%;
    flex-shrink: 0; opacity: 0.5;
    transition: opacity 0.15s;
  }

  /* skill-pill featured */
  .skill-pill.feat {
    border-color: rgba(255,255,255,0.14);
    color: var(--text);
  }

  /* ─── EXPERIENCE ─── */
  .exp-list { display: flex; flex-direction: column; gap: 0; }
  .exp-row {
    display: grid; grid-template-columns: 100px 1fr;
    gap: 24px; padding: 24px 0;
    border-bottom: 0.5px solid var(--border);
    transition: background 0.15s;
  }
  .exp-row:first-child { border-top: 0.5px solid var(--border); }
  .exp-date {
    font-family: var(--mono); font-size: 11px;
    color: var(--subtle); padding-top: 3px; letter-spacing: 0.02em;
  }
  .exp-role { font-size: 14px; font-weight: 500; color: var(--text); margin-bottom: 3px; }
  .exp-company { font-size: 13px; color: var(--muted); margin-bottom: 12px; font-weight: 300; }
  .exp-points { display: flex; flex-direction: column; gap: 4px; }
  .exp-point {
    font-size: 12px; color: var(--subtle);
    display: flex; gap: 10px; align-items: flex-start;
    font-family: var(--mono); letter-spacing: 0.01em;
  }
  .exp-point::before { content: "›"; color: var(--subtle); flex-shrink: 0; }

  /* ─── FOOTER ─── */
  .footer {
    padding: 40px 0;
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 16px;
  }
  .footer-quote {
    font-size: 13px; color: var(--subtle);
    font-style: italic; font-weight: 300;
  }
  .footer-info {
    font-family: var(--mono); font-size: 11px;
    color: var(--subtle); letter-spacing: 0.04em;
  }
</style>
</head>
<body>

<div class="wrapper">

  <!-- HERO -->
  <section class="hero">
    <div class="hero-grid"></div>
    <div class="hero-inner">
      <div class="status">
        <span class="status-dot"></span>
        founding engineer · open to roles
      </div>

      <h1 class="hero-name">
        Aakarsh<br>
        <em>Singh</em>
      </h1>

      <p class="hero-desc">
        Full-stack &amp; systems engineer. Building <strong>geospatial + real-time infrastructure</strong> at Cherrie. B.Tech IT @ IIIT Bhopal '27.
      </p>

      <div class="hero-links">
        <a class="chip" href="mailto:singhaakarsh28@gmail.com">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>
          singhaakarsh28@gmail.com
        </a>
        <a class="chip" href="https://github.com/aakarsh12x" target="_blank">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>
          aakarsh12x
        </a>
        <a class="chip" href="https://www.linkedin.com/in/aakarsh-singh-b27a5228b/" target="_blank">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          LinkedIn
        </a>
        <a class="chip" href="https://www.aakarshsingh.in/" target="_blank">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><circle cx="12" cy="12" r="10"/><path d="M2 12h20M12 2a15.3 15.3 0 010 20M12 2a15.3 15.3 0 000 20"/></svg>
          aakarshsingh.in
        </a>
        <a class="chip" href="#">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"/></svg>
          700+ LeetCode
        </a>
      </div>
    </div>
  </section>

  <!-- METRICS -->
  <section class="section">
    <div class="section-header">
      <span class="section-label">Impact</span>
      <div class="section-line"></div>
    </div>
    <div class="metrics">
      <div class="metric">
        <div class="metric-val">10k+</div>
        <div class="metric-key">Daily active users</div>
      </div>
      <div class="metric">
        <div class="metric-val">100k+</div>
        <div class="metric-key">API requests / day</div>
      </div>
      <div class="metric">
        <div class="metric-val">&lt;200ms</div>
        <div class="metric-key">p95 latency</div>
      </div>
      <div class="metric">
        <div class="metric-val">700+</div>
        <div class="metric-key">DSA problems solved</div>
      </div>
      <div class="metric">
        <div class="metric-val">&lt;300</div>
        <div class="metric-key">CodeChef global rank</div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section class="section">
    <div class="section-header">
      <span class="section-label">Skills</span>
      <div class="section-line"></div>
    </div>

    <div class="skills-outer">

      <div>
        <div class="skill-group-label">Languages</div>
        <div class="skills-row">
          <span class="skill-pill feat"><span class="sdot" style="background:#f7df1e;"></span>JavaScript (ES6+)</span>
          <span class="skill-pill feat"><span class="sdot" style="background:#3178c6;"></span>TypeScript</span>
          <span class="skill-pill"><span class="sdot" style="background:#ed8b00;"></span>Java</span>
          <span class="skill-pill"><span class="sdot" style="background:#3776ab;"></span>Python</span>
          <span class="skill-pill"><span class="sdot" style="background:#0175c2;"></span>Dart</span>
          <span class="skill-pill"><span class="sdot" style="background:#e34f26;"></span>HTML</span>
          <span class="skill-pill"><span class="sdot" style="background:#1572b6;"></span>CSS</span>
          <span class="skill-pill"><span class="sdot" style="background:#336791;"></span>SQL</span>
        </div>
      </div>

      <div>
        <div class="skill-group-label">Frontend</div>
        <div class="skills-row">
          <span class="skill-pill feat"><span class="sdot" style="background:#61dafb;"></span>React</span>
          <span class="skill-pill feat"><span class="sdot" style="background:#61dafb;"></span>React Native</span>
          <span class="skill-pill feat"><span class="sdot" style="background:#fff;"></span>Next.js</span>
          <span class="skill-pill"><span class="sdot" style="background:#764abc;"></span>Redux</span>
          <span class="skill-pill"><span class="sdot" style="background:#0055ff;"></span>Framer Motion</span>
          <span class="skill-pill"><span class="sdot" style="background:#02569b;"></span>Flutter</span>
        </div>
      </div>

      <div>
        <div class="skill-group-label">Backend</div>
        <div class="skills-row">
          <span class="skill-pill feat"><span class="sdot" style="background:#339933;"></span>Node.js</span>
          <span class="skill-pill feat"><span class="sdot" style="background:#fff;"></span>Express</span>
          <span class="skill-pill feat"><span class="sdot" style="background:#010101;"></span>Socket.IO</span>
          <span class="skill-pill"><span class="sdot" style="background:#444;"></span>REST APIs</span>
          <span class="skill-pill"><span class="sdot" style="background:#444;"></span>WebSockets</span>
          <span class="skill-pill"><span class="sdot" style="background:#f7931e;"></span>scikit-learn</span>
        </div>
      </div>

      <div>
        <div class="skill-group-label">Databases</div>
        <div class="skills-row">
          <span class="skill-pill feat"><span class="sdot" style="background:#336791;"></span>PostgreSQL</span>
          <span class="skill-pill feat"><span class="sdot" style="background:#336791;"></span>PostGIS</span>
          <span class="skill-pill feat"><span class="sdot" style="background:#dc382d;"></span>Redis</span>
          <span class="skill-pill"><span class="sdot" style="background:#47a248;"></span>MongoDB</span>
          <span class="skill-pill"><span class="sdot" style="background:#f90;"></span>DynamoDB</span>
          <span class="skill-pill"><span class="sdot" style="background:#00e599;"></span>Neon</span>
        </div>
      </div>

      <div>
        <div class="skill-group-label">Cloud &amp; DevOps</div>
        <div class="skills-row">
          <span class="skill-pill feat"><span class="sdot" style="background:#ff9900;"></span>AWS</span>
          <span class="skill-pill"><span class="sdot" style="background:#527fff;"></span>Amazon RDS</span>
          <span class="skill-pill"><span class="sdot" style="background:#fff;"></span>AWS SAM</span>
          <span class="skill-pill"><span class="sdot" style="background:#2496ed;"></span>Docker</span>
          <span class="skill-pill"><span class="sdot" style="background:#f05032;"></span>Git</span>
          <span class="skill-pill"><span class="sdot" style="background:#fff;"></span>CI/CD</span>
          <span class="skill-pill"><span class="sdot" style="background:#fff;"></span>Vercel</span>
        </div>
      </div>

      <div>
        <div class="skill-group-label">Practices</div>
        <div class="skills-row">
          <span class="skill-pill"><span class="sdot" style="background:#c21325;"></span>Jest</span>
          <span class="skill-pill"><span class="sdot" style="background:#0052cc;"></span>Agile / Scrum</span>
          <span class="skill-pill"><span class="sdot" style="background:#444;"></span>Performance Engineering</span>
          <span class="skill-pill"><span class="sdot" style="background:#4285f4;"></span>Core Web Vitals</span>
          <span class="skill-pill"><span class="sdot" style="background:#4caf50;"></span>SEO</span>
          <span class="skill-pill"><span class="sdot" style="background:#444;"></span>Lazy loading</span>
          <span class="skill-pill"><span class="sdot" style="background:#444;"></span>Memoization</span>
          <span class="skill-pill"><span class="sdot" style="background:#444;"></span>Code splitting</span>
        </div>
      </div>

    </div>
  </section>

  <!-- EXPERIENCE -->
  <section class="section">
    <div class="section-header">
      <span class="section-label">Experience</span>
      <div class="section-line"></div>
    </div>

    <div class="exp-list">
      <div class="exp-row">
        <div class="exp-date">2025 — now</div>
        <div>
          <div class="exp-role">Founding Engineer</div>
          <div class="exp-company">Cherrie · Full-time</div>
          <div class="exp-points">
            <span class="exp-point">Full backend ownership — geospatial, WebSockets, performance</span>
            <span class="exp-point">Reduced backend costs via request batching &amp; Redis caching</span>
            <span class="exp-point">10k+ DAUs · 100k+ daily requests · &lt;200ms p95</span>
          </div>
        </div>
      </div>
      <div class="exp-row">
        <div class="exp-date">Prior</div>
        <div>
          <div class="exp-role">Full Stack Developer</div>
          <div class="exp-company">Wvintech Solutions · Internship</div>
          <div class="exp-points">
            <span class="exp-point">Production web development across frontend and backend stacks</span>
          </div>
        </div>
      </div>
      <div class="exp-row">
        <div class="exp-date">Prior</div>
        <div>
          <div class="exp-role">Software Developer Intern</div>
          <div class="exp-company">Aitreya Tech Solutions · Internship</div>
          <div class="exp-points">
            <span class="exp-point">Cross-functional software development across India &amp; Malaysia</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <span class="footer-quote">"Building systems that survive real load, one commit at a time."</span>
    <span class="footer-info">IIIT Bhopal · B.Tech IT · 2023–2027</span>
  </footer>

</div>

</body>
</html>
