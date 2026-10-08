# Portfolio_DataEngineering
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Shri Ram M R | Data Engineer</title>
<meta name="description" content="Data engineer building reliable pipelines with Python, SQL, PostgreSQL and Docker. Portfolio of Shri Ram M R.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Sora:wght@600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#080b1e; --bg2:#0d1226; --card:#0f1530; --line:#1d2548;
    --gold:#e2b93b; --gold-soft:rgba(226,185,59,.12);
    --text:#eef0f8; --muted:#9aa3c0; --dim:#6b7494;
    --radius:14px;
    --display:'Sora','Segoe UI',system-ui,sans-serif;
    --body:'Inter','Segoe UI',system-ui,sans-serif;
  }
  *{box-sizing:border-box;margin:0;padding:0}
  html{scroll-behavior:smooth;scroll-padding-top:80px}
  body{background:var(--bg);color:var(--text);font-family:var(--body);line-height:1.65;-webkit-font-smoothing:antialiased}
  a{color:inherit;text-decoration:none}
  :focus-visible{outline:2px solid var(--gold);outline-offset:3px;border-radius:6px}
  .wrap{max-width:1100px;margin:0 auto;padding:0 24px}
  section{padding:96px 0}
  h2{font-family:var(--display);font-size:clamp(28px,4vw,40px);font-weight:700;letter-spacing:-.02em;margin-bottom:12px}
  .lead{color:var(--muted);max-width:62ch;margin-bottom:44px}

  /* NAV */
  nav{position:fixed;inset:0 0 auto 0;z-index:50;background:rgba(8,11,30,.82);backdrop-filter:blur(10px);border-bottom:1px solid transparent;transition:border-color .3s}
  nav.scrolled{border-bottom-color:var(--line)}
  .nav-in{display:flex;align-items:center;justify-content:space-between;height:64px}
  .links{display:flex;gap:30px}
  .links a{font-size:15px;font-weight:500;color:var(--muted);padding:6px 0;border-bottom:2px solid transparent;transition:color .2s,border-color .2s}
  .links a:hover,.links a.active{color:var(--text);border-bottom-color:var(--gold)}
  .brand{font-family:var(--display);font-weight:700;color:var(--gold)}
  .burger{display:none;background:none;border:1px solid var(--line);color:var(--text);width:42px;height:42px;border-radius:10px;font-size:20px;cursor:pointer}

  /* HERO */
  .hero{min-height:100vh;display:flex;align-items:center;justify-content:center;text-align:center;position:relative;overflow:hidden;padding:120px 0 80px;
    background:linear-gradient(180deg,var(--bg) 0%,#0b1128 100%)}
  .ring{position:absolute;border:1px solid rgba(226,185,59,.14);border-radius:50%;pointer-events:none}
  .ring.a{width:480px;height:480px;right:-40px;top:12%}
  .ring.b{width:360px;height:360px;left:-80px;bottom:10%}
  .hero .wrap{position:relative;max-width:900px}
  .role{color:var(--gold);font-weight:600;letter-spacing:.14em;font-size:15px}
  .status{color:var(--muted);font-size:14px;margin-top:4px}
  .hero h1{font-family:var(--display);font-size:clamp(46px,9vw,96px);font-weight:800;letter-spacing:-.035em;line-height:1.05;margin:30px 0 28px;
    background:linear-gradient(100deg,#d9ac2c 0%,#f1d77a 35%,#eef0f8 52%,#e2b93b 70%,#d9ac2c 100%);-webkit-background-clip:text;background-clip:text;color:transparent}
  .tag{font-size:clamp(18px,2.4vw,24px);font-weight:500}
  .tag b{color:var(--gold);font-weight:600}
  .sub{color:var(--muted);font-size:18px;max-width:60ch;margin:22px auto 0}
  .cta{display:flex;gap:14px;justify-content:center;flex-wrap:wrap;margin-top:40px}
  .btn{display:inline-flex;align-items:center;gap:8px;padding:12px 28px;border-radius:10px;font-weight:600;font-size:16px;border:1px solid var(--line);transition:transform .2s,background .2s,box-shadow .2s;cursor:pointer;font-family:inherit}
  .btn.gold{background:var(--gold);color:#16130a;border-color:var(--gold)}
  .btn.gold:hover{box-shadow:0 8px 30px rgba(226,185,59,.3);transform:translateY(-2px)}
  .btn.ghost{color:var(--gold);background:transparent}
  .btn.ghost:hover{background:var(--gold-soft);transform:translateY(-2px)}
  .icons{display:flex;gap:16px;justify-content:center;margin-top:48px}
  .icon{width:56px;height:56px;border-radius:14px;border:1px solid var(--line);background:rgba(15,21,48,.6);display:grid;place-items:center;color:var(--gold);transition:border-color .2s,transform .2s}
  .icon:hover{border-color:var(--gold);transform:translateY(-3px)}
  .icon svg{width:22px;height:22px}

  /* ABOUT */
  .about-grid{display:grid;grid-template-columns:1.4fr 1fr;gap:48px;align-items:start}
  .about p{color:var(--muted);margin-bottom:16px}
  .about p b{color:var(--text);font-weight:600}
  .stats{display:grid;grid-template-columns:1fr 1fr;gap:14px}
  .stat{background:var(--card);border:1px solid var(--line);border-radius:var(--radius);padding:22px}
  .stat .n{font-family:var(--display);font-size:32px;font-weight:700;color:var(--gold);line-height:1.1}
  .stat .l{color:var(--muted);font-size:14px;margin-top:6px}

  /* PIPELINE */
  .pipe{background:var(--bg2);border-block:1px solid var(--line)}
  .stages{display:grid;grid-template-columns:repeat(5,1fr);gap:0;position:relative;margin-bottom:28px}
  .stage{background:var(--card);border:1px solid var(--line);padding:18px 14px;text-align:left;cursor:pointer;color:var(--text);font-family:inherit;position:relative;transition:background .2s,border-color .2s}
  .stage:first-child{border-radius:var(--radius) 0 0 var(--radius)}
  .stage:last-child{border-radius:0 var(--radius) var(--radius) 0}
  .stage+.stage{margin-left:-1px}
  .stage:not(:last-child)::after{content:"";position:absolute;right:-9px;top:50%;width:16px;height:16px;background:inherit;border-top:1px solid var(--line);border-right:1px solid var(--line);transform:translateY(-50%) rotate(45deg);z-index:2}
  .stage .s-n{font-size:12px;color:var(--dim);font-weight:600}
  .stage .s-t{font-family:var(--display);font-weight:600;font-size:17px;margin-top:2px}
  .stage:hover{border-color:var(--gold)}
  .stage.on{background:#1a1f3d;border-color:var(--gold)}
  .stage.on .s-n{color:var(--gold)}
  .detail{background:var(--card);border:1px solid var(--line);border-left:3px solid var(--gold);border-radius:var(--radius);padding:26px 28px;min-height:150px}
  .detail h3{font-family:var(--display);font-size:20px;margin-bottom:8px}
  .detail p{color:var(--muted);max-width:70ch}
  .chips{display:flex;flex-wrap:wrap;gap:8px;margin-top:14px}
  .chip{font-size:13px;padding:4px 12px;border-radius:999px;background:var(--gold-soft);color:var(--gold);border:1px solid rgba(226,185,59,.25);font-weight:500}
  .chip.plain{background:transparent;color:var(--muted);border-color:var(--line)}

  /* TIMELINE */
  .tl{position:relative;padding-left:34px;border-left:2px solid var(--line)}
  .tl::before{content:"";position:absolute;left:-7px;top:6px;width:12px;height:12px;border-radius:50%;background:var(--gold);box-shadow:0 0 0 5px var(--gold-soft)}
  .tl h3{font-family:var(--display);font-size:22px}
  .tl .org{color:var(--gold);font-weight:600}
  .tl .meta{color:var(--dim);font-size:14px;margin:2px 0 16px}
  .tl ul{list-style:none;display:grid;gap:12px;color:var(--muted)}
  .tl li{position:relative;padding-left:20px}
  .tl li::before{content:"";position:absolute;left:0;top:11px;width:8px;height:2px;background:var(--gold)}
  .tl li b{color:var(--text);font-weight:600}
  .edu{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-top:48px}
  .edu .box{background:var(--card);border:1px solid var(--line);border-radius:var(--radius);padding:22px}
  .edu h4{font-family:var(--display);font-size:17px}
  .edu p{color:var(--muted);font-size:15px}
  .edu .when{color:var(--dim);font-size:13px;margin-top:6px}

  /* PROJECTS */
  .projects{display:grid;gap:22px}
  .proj{background:var(--card);border:1px solid var(--line);border-radius:var(--radius);padding:30px;display:grid;grid-template-columns:1.1fr 1fr;gap:34px;transition:border-color .25s}
  .proj:hover{border-color:rgba(226,185,59,.5)}
  .proj h3{font-family:var(--display);font-size:24px;letter-spacing:-.01em}
  .proj .kind{color:var(--gold);font-size:14px;font-weight:600;margin:2px 0 14px}
  .proj p{color:var(--muted);margin-bottom:12px}
  .proj .gh{display:inline-flex;align-items:center;gap:6px;color:var(--gold);font-weight:600;font-size:15px;margin-top:6px}
  .proj .gh:hover{text-decoration:underline}
  .flow{background:var(--bg);border:1px solid var(--line);border-radius:12px;padding:18px;display:flex;flex-direction:column;justify-content:center;gap:0}
  .node{border:1px solid var(--line);border-radius:10px;padding:9px 14px;font-size:14px;background:var(--card)}
  .node small{display:block;color:var(--dim);font-size:12px}
  .node.hl{border-color:rgba(226,185,59,.5);background:var(--gold-soft)}
  .arrow{height:16px;width:2px;background:var(--line);margin:0 auto;position:relative}
  .arrow::after{content:"";position:absolute;bottom:-1px;left:-3px;border:4px solid transparent;border-top:6px solid var(--line);border-bottom:0}

  /* SKILLS */
  .skills{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
  .sk{background:var(--card);border:1px solid var(--line);border-radius:var(--radius);padding:24px}
  .sk.core{grid-column:span 2;border-color:rgba(226,185,59,.4)}
  .sk h3{font-family:var(--display);font-size:17px;margin-bottom:14px}
  .sk .chips{margin-top:0}

  /* ACHIEVEMENTS */
  .ach{display:grid;grid-template-columns:repeat(2,1fr);gap:18px}
  .a-card{background:var(--card);border:1px solid var(--line);border-radius:var(--radius);padding:26px}
  .a-card .yr{color:var(--gold);font-weight:600;font-size:14px}
  .a-card h3{font-family:var(--display);font-size:19px;margin:4px 0 8px}
  .a-card p{color:var(--muted);font-size:15px}

  /* CONTACT */
  .contact{text-align:center}
  .contact .lead{margin-inline:auto}
  .c-grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:14px;max-width:760px;margin:0 auto}
  .c-item{background:var(--card);border:1px solid var(--line);border-radius:var(--radius);padding:20px;text-align:left;display:flex;gap:14px;align-items:center;transition:border-color .2s,transform .2s;min-width:0}
  .c-item:hover{border-color:var(--gold);transform:translateY(-2px)}
  .c-item svg{width:22px;height:22px;color:var(--gold);flex:none}
  .c-item span{display:block;color:var(--dim);font-size:13px}
  .c-item b{font-weight:600;font-size:15px;overflow-wrap:anywhere}
  footer{border-top:1px solid var(--line);padding:28px 0;text-align:center;color:var(--dim);font-size:14px}

  /* motion: one hero entrance only */
  .hero .wrap>*{opacity:0;animation:rise .7s ease forwards}
  .hero .wrap>*:nth-child(1){animation-delay:.05s}.hero .wrap>*:nth-child(2){animation-delay:.15s}
  .hero .wrap>*:nth-child(3){animation-delay:.25s}.hero .wrap>*:nth-child(4){animation-delay:.35s}
  .hero .wrap>*:nth-child(5){animation-delay:.45s}.hero .wrap>*:nth-child(6){animation-delay:.55s}
  @keyframes rise{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:none}}
  @media (prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important;scroll-behavior:auto!important}.hero .wrap>*{opacity:1}}

  /* RESPONSIVE */
  @media (max-width:860px){
    section{padding:72px 0}
    .burger{display:block}
    .links{position:absolute;top:64px;left:0;right:0;flex-direction:column;gap:0;background:var(--bg);border-bottom:1px solid var(--line);padding:8px 24px 16px;display:none}
    .links.open{display:flex}
    .links a{padding:12px 0;border-bottom:1px solid var(--line)}
    .about-grid,.proj,.edu{grid-template-columns:1fr}
    .stages{grid-template-columns:1fr}
    .stage,.stage:first-child,.stage:last-child{border-radius:0}
    .stage:first-child{border-radius:var(--radius) var(--radius) 0 0}.stage:last-child{border-radius:0 0 var(--radius) var(--radius)}
    .stage+.stage{margin-left:0;margin-top:-1px}
    .stage:not(:last-child)::after{display:none}
    .skills,.ach,.c-grid{grid-template-columns:1fr}
    .sk.core{grid-column:auto}
    .ring{display:none}
  }
</style>
</head>
<body>

<nav id="nav">
  <div class="wrap nav-in">
    <a href="#top" class="brand">SR</a>
    <button class="burger" id="burger" aria-label="Toggle menu" aria-expanded="false">&#9776;</button>
    <div class="links" id="links">
      <a href="#about">About</a>
      <a href="#approach">Approach</a>
      <a href="#experience">Experience</a>
      <a href="#projects">Projects</a>
      <a href="#skills">Skills</a>
      <a href="#achievements">Achievements</a>
      <a href="#contact">Contact</a>
    </div>
  </div>
</nav>

<!-- HERO -->
<header class="hero" id="top">
  <div class="ring a"></div><div class="ring b"></div>
  <div class="wrap">
    <div>
      <div class="role">DATA ENGINEER</div>
      <div class="status">Open to full-time roles &bull; Class of 2027</div>
    </div>
    <h1>Shri Ram M R</h1>
    <p class="tag">I build data pipelines and backends with Python, SQL, PostgreSQL and Docker. <b>Ingestion &bull; Transformation &bull; Secure, organization-scoped data access</b></p>
    <p class="sub">From messy CSV, PDF and sensor input to clean tables, trained models and dashboards people can actually use.</p>
    <div class="cta">
      <a class="btn gold" href="#projects">Explore Projects</a>
      <a class="btn ghost" href="DE_Resume.pdf" download>
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><path d="M7 10l5 5 5-5"/><path d="M12 15V3"/></svg>
        Resume
      </a>
    </div>
    <div class="icons">
      <a class="icon" href="https://github.com/shri-ram8" target="_blank" rel="noopener" aria-label="GitHub">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
      </a>
      <a class="icon" href="https://linkedin.com/in/shri-ram-m-r" target="_blank" rel="noopener" aria-label="LinkedIn">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-4 0v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
      </a>
      <a class="icon" href="mailto:ramsulochana08@gmail.com" aria-label="Email">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-10 6L2 7"/></svg>
      </a>
    </div>
  </div>
</header>

<!-- ABOUT -->
<section id="about" class="about">
  <div class="wrap about-grid">
    <div>
      <h2>About</h2>
      <p>I'm a final-year Electronics and Communication Engineering student at SSN College of Engineering who found the most interesting part of every project was the <b>data</b>: where it comes from, how it gets cleaned, and whether the next person can trust it.</p>
      <p>That shows up in my work. I've built an <b>ingestion layer</b> for CSV, Excel, JSON, PDF and Word files (with OCR for scans), an <b>ML pipeline</b> that took raw news text through preprocessing to a deployed BERT model, and an <b>edge pipeline</b> that classifies sensor readings on a Raspberry Pi with no cloud connection.</p>
      <p>During my internship I designed a <b>multi-tenant PostgreSQL backend</b> where every query is scoped to an organization, which is the same discipline good data platforms need for governance and access control.</p>
      <p>I'm looking for a data engineering role where I can build pipelines that are tested, observable and easy to hand over.</p>
    </div>
    <div class="stats">
      <div class="stat"><div class="n">150+</div><div class="l">LeetCode problems solved</div></div>
      <div class="stat"><div class="n">3</div><div class="l">Data and ML pipelines built end to end</div></div>
      <div class="stat"><div class="n">5</div><div class="l">File formats ingested in Data Pilot</div></div>
      <div class="stat"><div class="n">7.93</div><div class="l">CGPA, B.E. ECE</div></div>
    </div>
  </div>
</section>

<!-- APPROACH (interactive pipeline) -->
<section id="approach" class="pipe">
  <div class="wrap">
    <h2>How I build data systems</h2>
    <p class="lead">Every project of mine follows the same five stages. Select a stage to see what I did there and the tools involved.</p>
    <div class="stages" id="stages" role="tablist"></div>
    <div class="detail" id="detail" aria-live="polite"></div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="wrap">
    <h2>Experience</h2>
    <p class="lead">Hands-on work on the data layer of a production-style backend.</p>
    <div class="tl">
      <h3>Software Developer Intern</h3>
      <div class="org">AssistLana</div>
      <div class="meta">May 2026 &ndash; Jun 2026 &bull; Puducherry, India</div>
      <ul>
        <li>Engineered a <b>multi-tenant backend</b> with Node.js, Express.js, PostgreSQL and Docker, with <b>organization-level data isolation</b> and role-based access control (RBAC).</li>
        <li>Designed REST APIs with <b>JWT authentication</b>, refresh-token workflows and <b>audit logging</b>, so every change to data can be traced.</li>
        <li>Added <b>optimized PostgreSQL indexing</b> to keep organization-scoped queries fast and secure as data grows.</li>
      </ul>
    </div>
    <div class="edu">
      <div class="box">
        <h4>B.E. Electronics and Communication</h4>
        <p>SSN College of Engineering, Chennai &bull; CGPA 7.93</p>
        <div class="when">Sep 2023 &ndash; May 2027</div>
      </div>
      <div class="box">
        <h4>Class XII</h4>
        <p>A.R.L.M Matriculation Higher Secondary School, Cuddalore &bull; 93%</p>
        <div class="when">March 2023</div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects" style="background:var(--bg2);border-block:1px solid var(--line)">
  <div class="wrap">
    <h2>Projects</h2>
    <p class="lead">Each one shows the path the data takes, from input to something useful.</p>
    <div class="projects">

      <article class="proj">
        <div>
          <h3>Data Pilot</h3>
          <div class="kind">AI-powered data analytics chatbot &bull; 2026</div>
          <p>Upload a CSV, Excel, JSON, PDF or Word file and ask questions in plain English. Gemini detects the intent, Pandas does the computation, and Chart.js charts are generated automatically.</p>
          <p>JWT authentication keeps each user's data isolated. Tesseract OCR handles scanned PDFs, answers are cached, and chat history persists for fast follow-up questions.</p>
          <div class="chips"><span class="chip">Python</span><span class="chip">Flask</span><span class="chip">React</span><span class="chip">PostgreSQL</span><span class="chip">Supabase</span><span class="chip">Pandas</span><span class="chip">Gemini</span><span class="chip">Tesseract OCR</span></div>
          <a class="gh" href="https://github.com/shri-ram8" target="_blank" rel="noopener">View on GitHub</a>
        </div>
        <div class="flow" aria-label="Data Pilot data flow">
          <div class="node">Files<small>CSV, Excel, JSON, PDF, Word</small></div><div class="arrow"></div>
          <div class="node">Parse and OCR<small>Tesseract for scanned PDFs</small></div><div class="arrow"></div>
          <div class="node hl">Intent detection and Pandas compute<small>Gemini + cached answers</small></div><div class="arrow"></div>
          <div class="node">Chart.js visuals<small>Per-user isolated history in PostgreSQL</small></div>
        </div>
      </article>

      <article class="proj">
        <div>
          <h3>ScanBuzz</h3>
          <div class="kind">AI-powered fake news detection platform &bull; 2026</div>
          <p>An end-to-end ML pipeline: news text is preprocessed, a BERT model is trained on Kaggle, and it is benchmarked against classical baselines (Logistic Regression, KNN) so the best performer is picked on evidence.</p>
          <p>The trained model is served inside a web app that returns real-time predictions on any news text a user submits.</p>
          <div class="chips"><span class="chip">Python</span><span class="chip">BERT</span><span class="chip">scikit-learn</span><span class="chip">Pandas</span><span class="chip">NumPy</span><span class="chip">Kaggle</span></div>
          <a class="gh" href="https://github.com/shri-ram8" target="_blank" rel="noopener">View on GitHub</a>
        </div>
        <div class="flow" aria-label="ScanBuzz data flow">
          <div class="node">Raw news text<small>Kaggle dataset</small></div><div class="arrow"></div>
          <div class="node">Preprocessing<small>Cleaning and tokenisation</small></div><div class="arrow"></div>
          <div class="node hl">Train and benchmark<small>BERT vs baseline models</small></div><div class="arrow"></div>
          <div class="node">Inference in web app<small>Real-time predictions</small></div>
        </div>
      </article>

      <article class="proj">
        <div>
          <h3>Chicken Health Monitoring</h3>
          <div class="kind">IoT and edge AI &bull; 2025 &ndash; Present</div>
          <p>A Raspberry Pi system that reads multiple sensors and classifies poultry health in real time, processing environmental and flock-level parameters locally without needing the cloud.</p>
          <p>A local dashboard shows live readings, and automated GSM SMS alerts warn the farmer early. Funded through SSN's Innovation Funding Program (Rs. 30,000).</p>
          <div class="chips"><span class="chip">Raspberry Pi</span><span class="chip">Python</span><span class="chip">Edge AI</span><span class="chip">Sensors</span><span class="chip">GSM</span></div>
          <a class="gh" href="https://github.com/shri-ram8" target="_blank" rel="noopener">View on GitHub</a>
        </div>
        <div class="flow" aria-label="Chicken health monitoring data flow">
          <div class="node">Multi-sensor input<small>Environment and flock parameters</small></div><div class="arrow"></div>
          <div class="node hl">Edge processing on Raspberry Pi<small>Local, works offline</small></div><div class="arrow"></div>
          <div class="node">Health classification<small>Real-time decision support</small></div><div class="arrow"></div>
          <div class="node">Dashboard and SMS alerts<small>GSM early warnings</small></div>
        </div>
      </article>

    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="wrap">
    <h2>Skills</h2>
    <p class="lead">Grouped by how I use them in data work.</p>
    <div class="skills">
      <div class="sk core">
        <h3>Data engineering core</h3>
        <div class="chips">
          <span class="chip">Python</span><span class="chip">SQL</span><span class="chip">PostgreSQL</span><span class="chip">Pandas</span><span class="chip">NumPy</span>
          <span class="chip">Supabase</span><span class="chip">Database Design</span><span class="chip">Indexing</span><span class="chip">Data Preprocessing</span>
        </div>
      </div>
      <div class="sk">
        <h3>Infrastructure and delivery</h3>
        <div class="chips"><span class="chip plain">Docker</span><span class="chip plain">Docker Compose</span><span class="chip plain">Git</span><span class="chip plain">GitHub</span><span class="chip plain">CI/CD</span></div>
      </div>
      <div class="sk">
        <h3>Machine learning</h3>
        <div class="chips"><span class="chip plain">BERT</span><span class="chip plain">scikit-learn</span><span class="chip plain">Model Evaluation</span></div>
      </div>
      <div class="sk">
        <h3>Backend and APIs</h3>
        <div class="chips"><span class="chip plain">Node.js</span><span class="chip plain">Express.js</span><span class="chip plain">Flask</span><span class="chip plain">Spring Boot</span><span class="chip plain">Spring Security</span><span class="chip plain">REST APIs</span><span class="chip plain">WebSockets (STOMP)</span><span class="chip plain">JWT</span></div>
      </div>
      <div class="sk">
        <h3>Languages</h3>
        <div class="chips"><span class="chip plain">Python</span><span class="chip plain">SQL</span><span class="chip plain">Java</span><span class="chip plain">C++</span><span class="chip plain">JavaScript</span></div>
      </div>
      <div class="sk">
        <h3>Problem solving and quality</h3>
        <div class="chips"><span class="chip plain">Arrays</span><span class="chip plain">HashMap</span><span class="chip plain">Trees</span><span class="chip plain">Graphs</span><span class="chip plain">Heap</span><span class="chip plain">Binary Search</span><span class="chip plain">Unit Testing</span><span class="chip plain">Integration Testing</span><span class="chip plain">SDLC</span></div>
      </div>
      <div class="sk">
        <h3>Frontend (for dashboards)</h3>
        <div class="chips"><span class="chip plain">React</span><span class="chip plain">HTML5</span><span class="chip plain">CSS3</span><span class="chip plain">Tailwind CSS</span><span class="chip plain">Chart.js</span></div>
      </div>
    </div>
  </div>
</section>

<!-- ACHIEVEMENTS -->
<section id="achievements" style="background:var(--bg2);border-block:1px solid var(--line)">
  <div class="wrap">
    <h2>Achievements</h2>
    <p class="lead">Recognition for building things that work.</p>
    <div class="ach">
      <div class="a-card"><div class="yr">2026</div><h3>Zenith Hackathon, SSN CE: Finalist</h3><p>Built SmartSlot, a real-time smart parking platform.</p></div>
      <div class="a-card"><div class="yr">2026</div><h3>NatWest Code for Purpose Hackathon: Shortlisted</h3><p>Reached the solution round with an AI-powered conversational analytics platform.</p></div>
      <div class="a-card"><div class="yr">2025</div><h3>Innovation Funding Program, SSN CE</h3><p>Awarded Rs. 30,000 to build a real-time IoT Chicken Health Monitoring System using edge computing and multi-sensor monitoring.</p></div>
      <div class="a-card"><div class="yr">Ongoing</div><h3>150+ LeetCode problems</h3><p>Regular practice in arrays, strings, hash maps, trees, graphs, greedy, backtracking, sliding window and heaps.</p></div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact" class="contact">
  <div class="wrap">
    <h2>Let's talk</h2>
    <p class="lead">I'm open to full-time data engineering roles. Email is the fastest way to reach me.</p>
    <div class="c-grid">
      <a class="c-item" href="mailto:ramsulochana08@gmail.com">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-10 6L2 7"/></svg>
        <div><span>Email</span><b>ramsulochana08@gmail.com</b></div>
      </a>
      <a class="c-item" href="tel:+916380532255">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 16.9v3a2 2 0 0 1-2.2 2 19.8 19.8 0 0 1-8.6-3.1 19.5 19.5 0 0 1-6-6A19.8 19.8 0 0 1 2.1 4.2 2 2 0 0 1 4.1 2h3a2 2 0 0 1 2 1.7c.1 1 .4 1.9.7 2.8a2 2 0 0 1-.5 2.1L8.1 9.9a16 16 0 0 0 6 6l1.3-1.3a2 2 0 0 1 2.1-.4c.9.3 1.8.6 2.8.7a2 2 0 0 1 1.7 2z"/></svg>
        <div><span>Phone</span><b>+91 63805 32255</b></div>
      </a>
      <a class="c-item" href="https://linkedin.com/in/shri-ram-m-r" target="_blank" rel="noopener">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-4 0v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
        <div><span>LinkedIn</span><b>linkedin.com/in/shri-ram-m-r</b></div>
      </a>
      <a class="c-item" href="https://github.com/shri-ram8" target="_blank" rel="noopener">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
        <div><span>GitHub</span><b>github.com/shri-ram8</b></div>
      </a>
    </div>
  </div>
</section>

<footer><div class="wrap">&copy; <span id="yr"></span> Shri Ram M R</div></footer>

<script>
  // ---- Pipeline stages (edit text here) ----
  const STAGES = [
    { t:"Ingest", h:"Get data in from anywhere",
      p:"Data Pilot accepts CSV, Excel, JSON, PDF and Word uploads. Scanned PDFs go through Tesseract OCR, and the Raspberry Pi project reads live multi-sensor input.",
      c:["CSV / Excel / JSON","PDF + OCR","Sensors","REST APIs"] },
    { t:"Clean", h:"Make the data trustworthy",
      p:"For ScanBuzz I preprocessed raw news text before any model saw it. In Data Pilot, Pandas handles type fixes and missing values before computation.",
      c:["Pandas","NumPy","Data Preprocessing"] },
    { t:"Transform", h:"Turn raw rows into answers",
      p:"Pandas does the computation behind every plain-English question, Gemini picks the intent, and BERT turns text into predictions. Edge classification runs locally on the Pi.",
      c:["Pandas","BERT","scikit-learn","Edge AI"] },
    { t:"Store", h:"Model it, index it, isolate it",
      p:"At AssistLana I designed PostgreSQL schemas with organization-level isolation and indexes that keep scoped queries fast. Data Pilot stores per-user data and chat history in Supabase.",
      c:["PostgreSQL","Supabase","Indexing","RBAC","Database Design"] },
    { t:"Serve", h:"Deliver it safely and reliably",
      p:"REST APIs secured with JWT and refresh tokens, audit logging for traceability, Dockerized services, and dashboards or SMS alerts so the result reaches the person who needs it.",
      c:["REST APIs","JWT","Audit Logging","Docker","Chart.js"] }
  ];
  const stagesEl = document.getElementById('stages');
  const detailEl = document.getElementById('detail');
  function show(i){
    stagesEl.querySelectorAll('.stage').forEach((b,j)=>{b.classList.toggle('on',i===j);b.setAttribute('aria-selected',i===j)});
    const s = STAGES[i];
    detailEl.innerHTML = '<h3>'+s.h+'</h3><p>'+s.p+'</p><div class="chips">'+s.c.map(x=>'<span class="chip">'+x+'</span>').join('')+'</div>';
  }
  STAGES.forEach((s,i)=>{
    const b = document.createElement('button');
    b.className='stage'; b.setAttribute('role','tab');
    b.innerHTML='<div class="s-n">Stage '+(i+1)+'</div><div class="s-t">'+s.t+'</div>';
    b.addEventListener('click',()=>show(i));
    stagesEl.appendChild(b);
  });
  show(0);

  // ---- Nav behaviour ----
  const nav = document.getElementById('nav');
  addEventListener('scroll',()=>nav.classList.toggle('scrolled',scrollY>10),{passive:true});
  const burger = document.getElementById('burger'), links = document.getElementById('links');
  burger.addEventListener('click',()=>{const o=links.classList.toggle('open');burger.setAttribute('aria-expanded',o)});
  links.querySelectorAll('a').forEach(a=>a.addEventListener('click',()=>links.classList.remove('open')));

  // highlight current section in nav
  const anchors = [...links.querySelectorAll('a')];
  const io = new IntersectionObserver(es=>{
    es.forEach(e=>{ if(e.isIntersecting){ anchors.forEach(a=>a.classList.toggle('active',a.getAttribute('href')==='#'+e.target.id)); } });
  },{rootMargin:'-45% 0px -50% 0px'});
  document.querySelectorAll('section[id]').forEach(s=>io.observe(s));

  document.getElementById('yr').textContent = new Date().getFullYear();
</script>
</body>
</html>
