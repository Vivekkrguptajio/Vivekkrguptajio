<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Vivek Kumar Gupta — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;700;800&family=JetBrains+Mono:wght@300;400;700&family=Outfit:wght@300;400;600&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #060612;
    --surface: #0d0d1f;
    --card: #111128;
    --border: rgba(120,100,255,0.18);
    --accent: #7c5cff;
    --accent2: #00e5ff;
    --accent3: #ff4fd8;
    --gold: #ffd166;
    --text: #e8e6ff;
    --muted: #7b7a99;
    --glow: 0 0 40px rgba(124,92,255,0.35);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Outfit', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── Animated background ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background:
      radial-gradient(ellipse 80% 60% at 10% 10%, rgba(124,92,255,0.12) 0%, transparent 70%),
      radial-gradient(ellipse 60% 50% at 90% 80%, rgba(0,229,255,0.08) 0%, transparent 70%),
      radial-gradient(ellipse 50% 40% at 50% 50%, rgba(255,79,216,0.05) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
  }

  /* ── Grid overlay ── */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(124,92,255,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(124,92,255,0.04) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  .wrapper {
    position: relative;
    z-index: 1;
    max-width: 900px;
    margin: 0 auto;
    padding: 48px 24px 80px;
  }

  /* ── HERO ── */
  .hero {
    text-align: center;
    padding: 72px 0 48px;
    position: relative;
  }

  .hero-badge {
    display: inline-block;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent2);
    border: 1px solid rgba(0,229,255,0.3);
    padding: 6px 18px;
    border-radius: 100px;
    margin-bottom: 28px;
    animation: fadeUp 0.8s ease both;
    background: rgba(0,229,255,0.05);
  }

  .hero h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.8rem, 7vw, 5.2rem);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -2px;
    background: linear-gradient(135deg, #fff 0%, var(--accent) 40%, var(--accent2) 80%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: fadeUp 0.9s 0.1s ease both;
    margin-bottom: 8px;
  }

  .hero-sub {
    font-family: 'JetBrains Mono', monospace;
    color: var(--muted);
    font-size: 0.85rem;
    letter-spacing: 1px;
    animation: fadeUp 1s 0.2s ease both;
    margin-bottom: 28px;
  }

  .hero-tagline {
    font-size: 1.1rem;
    color: var(--text);
    opacity: 0.7;
    max-width: 500px;
    margin: 0 auto 36px;
    line-height: 1.7;
    font-weight: 300;
    animation: fadeUp 1s 0.3s ease both;
  }

  /* Animated typing cursor */
  .cursor {
    display: inline-block;
    width: 2px;
    height: 1.1em;
    background: var(--accent2);
    vertical-align: text-bottom;
    animation: blink 1s step-end infinite;
  }

  /* ── Status dots ── */
  .status-row {
    display: flex;
    gap: 12px;
    justify-content: center;
    flex-wrap: wrap;
    animation: fadeUp 1s 0.4s ease both;
    margin-bottom: 40px;
  }

  .status-pill {
    display: flex;
    align-items: center;
    gap: 7px;
    font-size: 0.78rem;
    font-family: 'JetBrains Mono', monospace;
    color: var(--muted);
    border: 1px solid var(--border);
    padding: 5px 14px;
    border-radius: 100px;
    background: rgba(255,255,255,0.03);
  }

  .dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: #22d47a;
    box-shadow: 0 0 8px #22d47a;
    animation: pulse 2s ease infinite;
  }

  .dot.blue { background: var(--accent2); box-shadow: 0 0 8px var(--accent2); }
  .dot.pink { background: var(--accent3); box-shadow: 0 0 8px var(--accent3); }

  /* ── Section titles ── */
  .section-label {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 28px;
    margin-top: 64px;
  }

  .section-label span {
    font-family: 'Syne', sans-serif;
    font-size: 1.35rem;
    font-weight: 700;
    color: #fff;
    letter-spacing: -0.5px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border), transparent);
  }

  .section-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.7rem;
    color: var(--accent);
    letter-spacing: 2px;
  }

  /* ── Cards ── */
  .card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 20px;
    padding: 28px 32px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.3s, box-shadow 0.3s;
  }

  .card:hover {
    border-color: rgba(124,92,255,0.45);
    transform: translateY(-3px);
    box-shadow: var(--glow);
  }

  .card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--accent), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .card:hover::before { opacity: 1; }

  /* ── Project cards ── */
  .projects { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }

  @media(max-width: 640px) { .projects { grid-template-columns: 1fr; } }

  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 20px;
    padding: 28px;
    position: relative;
    overflow: hidden;
    transition: all 0.35s cubic-bezier(0.23,1,0.32,1);
    cursor: pointer;
  }

  .project-card:hover {
    border-color: rgba(124,92,255,0.5);
    transform: translateY(-5px) scale(1.01);
    box-shadow: 0 24px 60px rgba(0,0,0,0.5), var(--glow);
  }

  .project-card .glow-corner {
    position: absolute;
    width: 120px; height: 120px;
    border-radius: 50%;
    filter: blur(40px);
    top: -30px; right: -30px;
    opacity: 0.5;
    transition: opacity 0.3s;
  }

  .project-card:hover .glow-corner { opacity: 0.9; }

  .project-card.p1 .glow-corner { background: var(--accent); }
  .project-card.p2 .glow-corner { background: var(--accent3); }
  .project-card.p3 .glow-corner { background: var(--accent2); }

  .proj-icon {
    font-size: 2rem;
    margin-bottom: 14px;
    display: block;
  }

  .proj-title {
    font-family: 'Syne', sans-serif;
    font-size: 1.05rem;
    font-weight: 700;
    color: #fff;
    margin-bottom: 10px;
  }

  .proj-desc {
    font-size: 0.82rem;
    color: var(--muted);
    line-height: 1.65;
    margin-bottom: 18px;
  }

  .proj-tags { display: flex; flex-wrap: wrap; gap: 6px; }

  .tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.65rem;
    padding: 3px 10px;
    border-radius: 100px;
    background: rgba(124,92,255,0.12);
    border: 1px solid rgba(124,92,255,0.25);
    color: var(--accent);
    letter-spacing: 0.5px;
  }

  .tag.cyan { background: rgba(0,229,255,0.08); border-color: rgba(0,229,255,0.2); color: var(--accent2); }
  .tag.pink { background: rgba(255,79,216,0.08); border-color: rgba(255,79,216,0.2); color: var(--accent3); }

  .proj-link {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 0.75rem;
    font-family: 'JetBrains Mono', monospace;
    color: var(--accent2);
    text-decoration: none;
    margin-top: 16px;
    border-bottom: 1px solid transparent;
    transition: border-color 0.2s;
  }

  .proj-link:hover { border-color: var(--accent2); }

  /* ── Skills grid ── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
    gap: 12px;
  }

  .skill-chip {
    background: rgba(255,255,255,0.03);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 14px 12px;
    text-align: center;
    font-size: 0.75rem;
    font-family: 'JetBrains Mono', monospace;
    color: var(--muted);
    transition: all 0.25s;
    cursor: default;
  }

  .skill-chip:hover {
    background: rgba(124,92,255,0.1);
    border-color: rgba(124,92,255,0.4);
    color: #fff;
    transform: translateY(-2px);
  }

  .skill-chip .skill-icon { font-size: 1.4rem; display: block; margin-bottom: 6px; }

  /* ── Stats row ── */
  .stats-row { display: grid; grid-template-columns: repeat(3,1fr); gap: 16px; }

  @media(max-width:560px) { .stats-row { grid-template-columns: 1fr; } }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 22px 20px;
    text-align: center;
    transition: all 0.3s;
  }

  .stat-card:hover {
    border-color: rgba(124,92,255,0.45);
    transform: translateY(-3px);
    box-shadow: var(--glow);
  }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 2rem;
    font-weight: 800;
    background: linear-gradient(135deg, #fff, var(--accent));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .stat-label {
    font-size: 0.72rem;
    font-family: 'JetBrains Mono', monospace;
    color: var(--muted);
    letter-spacing: 1px;
    margin-top: 4px;
  }

  /* ── Contact ── */
  .contact-row { display: flex; gap: 14px; flex-wrap: wrap; }

  .contact-btn {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    padding: 12px 24px;
    border-radius: 12px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
    font-weight: 700;
    letter-spacing: 1px;
    text-decoration: none;
    transition: all 0.25s;
    border: 1px solid transparent;
  }

  .contact-btn.primary {
    background: linear-gradient(135deg, var(--accent), #5a3de0);
    color: #fff;
    box-shadow: 0 8px 24px rgba(124,92,255,0.4);
  }

  .contact-btn.primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 14px 32px rgba(124,92,255,0.55);
  }

  .contact-btn.ghost {
    border-color: var(--border);
    color: var(--muted);
    background: rgba(255,255,255,0.03);
  }

  .contact-btn.ghost:hover {
    border-color: rgba(124,92,255,0.5);
    color: #fff;
    background: rgba(124,92,255,0.1);
  }

  /* ── About card ── */
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  @media(max-width:560px){ .about-grid { grid-template-columns: 1fr; } }

  .about-item {
    background: rgba(255,255,255,0.02);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 18px 20px;
    display: flex;
    align-items: flex-start;
    gap: 14px;
  }

  .about-item-icon { font-size: 1.4rem; flex-shrink: 0; margin-top: 2px; }

  .about-item-title {
    font-size: 0.7rem;
    font-family: 'JetBrains Mono', monospace;
    color: var(--accent);
    letter-spacing: 1.5px;
    text-transform: uppercase;
    margin-bottom: 4px;
  }

  .about-item-val {
    font-size: 0.83rem;
    color: var(--text);
    opacity: 0.85;
    line-height: 1.5;
  }

  /* ── Currently learning ── */
  .learning-pills { display: flex; flex-wrap: wrap; gap: 10px; }

  .learning-pill {
    display: flex;
    align-items: center;
    gap: 8px;
    background: rgba(0,229,255,0.07);
    border: 1px solid rgba(0,229,255,0.2);
    border-radius: 100px;
    padding: 8px 18px;
    font-size: 0.78rem;
    font-family: 'JetBrains Mono', monospace;
    color: var(--accent2);
    transition: all 0.25s;
  }

  .learning-pill:hover {
    background: rgba(0,229,255,0.15);
    transform: scale(1.04);
  }

  /* ── Footer ── */
  .footer {
    margin-top: 80px;
    padding-top: 32px;
    border-top: 1px solid var(--border);
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: gap;
    gap: 16px;
  }

  .footer-sig {
    font-family: 'Syne', sans-serif;
    font-size: 0.85rem;
    font-weight: 700;
    color: var(--muted);
  }

  .footer-sig span {
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .footer-star {
    font-size: 0.72rem;
    font-family: 'JetBrains Mono', monospace;
    color: var(--muted);
    display: flex;
    align-items: center;
    gap: 6px;
  }

  /* ── Animations ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes blink {
    50% { opacity: 0; }
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50%       { opacity: 0.6; transform: scale(0.85); }
  }

  @keyframes float {
    0%, 100% { transform: translateY(0); }
    50%       { transform: translateY(-8px); }
  }

  /* Staggered card animations */
  .project-card { animation: fadeUp 0.7s ease both; }
  .project-card:nth-child(1) { animation-delay: 0.1s; }
  .project-card:nth-child(2) { animation-delay: 0.2s; }
  .project-card:nth-child(3) { animation-delay: 0.3s; }

  .skill-chip { animation: fadeUp 0.5s ease both; }

  /* ── Floating orbs ── */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    pointer-events: none;
    z-index: 0;
    animation: float 8s ease-in-out infinite;
  }

  .orb1 { width: 400px; height: 400px; background: rgba(124,92,255,0.07); top: -100px; left: -100px; }
  .orb2 { width: 300px; height: 300px; background: rgba(0,229,255,0.05); bottom: 100px; right: -80px; animation-delay: -4s; }
  .orb3 { width: 200px; height: 200px; background: rgba(255,79,216,0.05); top: 50%; left: 60%; animation-delay: -2s; }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: rgba(124,92,255,0.3); border-radius: 10px; }
  ::-webkit-scrollbar-thumb:hover { background: rgba(124,92,255,0.6); }

  /* Divider line */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), transparent);
    margin: 56px 0;
  }
</style>
</head>
<body>

<div class="orb orb1"></div>
<div class="orb orb2"></div>
<div class="orb orb3"></div>

<div class="wrapper">

  <!-- ═══ HERO ═══ -->
  <section class="hero">
    <div class="hero-badge">// AVAILABLE FOR OPPORTUNITIES</div>
    <h1>Vivek Kumar Gupta</h1>
    <p class="hero-sub">B.Tech CSE &nbsp;·&nbsp; GEC Palamu, Jharkhand</p>
    <p class="hero-tagline">
      Web &amp; AI Developer — crafting intelligent systems<br>
      and beautiful interfaces that make a difference<span class="cursor"></span>
    </p>

    <div class="status-row">
      <div class="status-pill"><span class="dot"></span> Open to work</div>
      <div class="status-pill"><span class="dot blue"></span> Learning DevOps &amp; AWS</div>
      <div class="status-pill"><span class="dot pink"></span> Deep Learning research</div>
    </div>

    <div class="contact-row" style="justify-content:center;">
      <a href="https://www.linkedin.com/in/vivek369" class="contact-btn primary">💼 LinkedIn</a>
      <a href="mailto:vivekkrguptajio@gmail.com" class="contact-btn ghost">✉️ Email Me</a>
      <a href="https://leetcode.com/u/gkumvivek/" class="contact-btn ghost">⚔️ LeetCode</a>
    </div>
  </section>

  <div class="divider"></div>

  <!-- ═══ ABOUT ═══ -->
  <div class="section-label">
    <span class="section-num">01 /</span>
    <span>About Me</span>
  </div>

  <div class="about-grid">
    <div class="about-item">
      <span class="about-item-icon">🎓</span>
      <div>
        <div class="about-item-title">Education</div>
        <div class="about-item-val">B.Tech · Computer Science & Engineering<br>GEC Palamu, Jharkhand</div>
      </div>
    </div>
    <div class="about-item">
      <span class="about-item-icon">📍</span>
      <div>
        <div class="about-item-title">Location</div>
        <div class="about-item-val">Jharkhand, India<br>+91-9905130697</div>
      </div>
    </div>
    <div class="about-item">
      <span class="about-item-icon">💡</span>
      <div>
        <div class="about-item-title">Philosophy</div>
        <div class="about-item-val">Clean code, continuous learning & building things that matter</div>
      </div>
    </div>
    <div class="about-item">
      <span class="about-item-icon">🌐</span>
      <div>
        <div class="about-item-title">Focus Areas</div>
        <div class="about-item-val">MERN Stack · Machine Learning · Medical AI</div>
      </div>
    </div>
  </div>

  <!-- ═══ PROJECTS ═══ -->
  <div class="section-label">
    <span class="section-num">02 /</span>
    <span>Featured Projects</span>
  </div>

  <div class="projects">

    <div class="project-card p1">
      <div class="glow-corner"></div>
      <span class="proj-icon">🔒</span>
      <div class="proj-title">Secure Real-Time Chat App</div>
      <p class="proj-desc">End-to-end encrypted real-time messaging platform with private &amp; group chats. Containerized with Docker and secured with JWT + TLS/SSL.</p>
      <div class="proj-tags">
        <span class="tag">MERN Stack</span>
        <span class="tag">Socket.IO</span>
        <span class="tag">JWT</span>
        <span class="tag">Docker</span>
        <span class="tag">TLS/SSL</span>
      </div>
      <a href="https://streamify-video-calls-master-s0m7.onrender.com/" class="proj-link">Live Demo →</a>
    </div>

    <div class="project-card p2">
      <div class="glow-corner"></div>
      <span class="proj-icon">🩺</span>
      <div class="proj-title">Heart Disease Prediction</div>
      <p class="proj-desc">ML pipeline using Logistic Regression &amp; Random Forest for early cardiac risk detection. Comprehensive EDA with Seaborn visualizations.</p>
      <div class="proj-tags">
        <span class="tag pink">Python</span>
        <span class="tag pink">Scikit-learn</span>
        <span class="tag pink">Pandas</span>
        <span class="tag pink">Seaborn</span>
      </div>
    </div>

    <div class="project-card p3" style="grid-column: 1/-1;">
      <div class="glow-corner" style="background:var(--accent2);"></div>
      <span class="proj-icon">🤖</span>
      <div class="proj-title">Fetal Ultrasound Classification — 95.39% Accuracy</div>
      <p class="proj-desc">Fine-tuned ResNet18 on fetal ultrasound data to classify organ views with clinical-grade accuracy. Deployed live on Hugging Face Spaces with interactive inference.</p>
      <div class="proj-tags">
        <span class="tag cyan">PyTorch</span>
        <span class="tag cyan">ResNet18</span>
        <span class="tag cyan">Albumentations</span>
        <span class="tag cyan">OpenCV</span>
        <span class="tag cyan">HuggingFace</span>
      </div>
      <a href="https://huggingface.co/spaces/vivekgupta369/fetus-organ-classifier" class="proj-link">🤗 Live on Hugging Face →</a>
    </div>

  </div>

  <!-- ═══ STATS ═══ -->
  <div class="section-label">
    <span class="section-num">03 /</span>
    <span>By the Numbers</span>
  </div>

  <div class="stats-row">
    <div class="stat-card">
      <div class="stat-num">95.4%</div>
      <div class="stat-label">MODEL ACCURACY</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">3+</div>
      <div class="stat-label">MAJOR PROJECTS</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">15+</div>
      <div class="stat-label">TECH TOOLS</div>
    </div>
  </div>

  <!-- ═══ SKILLS ═══ -->
  <div class="section-label">
    <span class="section-num">04 /</span>
    <span>Tech Stack</span>
  </div>

  <div class="skills-grid">
    <div class="skill-chip"><span class="skill-icon">🐍</span>Python</div>
    <div class="skill-chip"><span class="skill-icon">☕</span>Java</div>
    <div class="skill-chip"><span class="skill-icon">⚡</span>JavaScript</div>
    <div class="skill-chip"><span class="skill-icon">⚙️</span>C++</div>
    <div class="skill-chip"><span class="skill-icon">⚛️</span>React</div>
    <div class="skill-chip"><span class="skill-icon">🟢</span>Node.js</div>
    <div class="skill-chip"><span class="skill-icon">🚂</span>Express</div>
    <div class="skill-chip"><span class="skill-icon">🍃</span>MongoDB</div>
    <div class="skill-chip"><span class="skill-icon">🐬</span>MySQL</div>
    <div class="skill-chip"><span class="skill-icon">🔥</span>Firebase</div>
    <div class="skill-chip"><span class="skill-icon">🔴</span>PyTorch</div>
    <div class="skill-chip"><span class="skill-icon">🤖</span>Scikit-learn</div>
    <div class="skill-chip"><span class="skill-icon">🐳</span>Docker</div>
    <div class="skill-chip"><span class="skill-icon">☁️</span>AWS</div>
    <div class="skill-chip"><span class="skill-icon">🐙</span>Git/GitHub</div>
    <div class="skill-chip"><span class="skill-icon">🎨</span>Figma</div>
  </div>

  <!-- ═══ LEARNING ═══ -->
  <div class="section-label">
    <span class="section-num">05 /</span>
    <span>Currently Learning</span>
  </div>

  <div class="learning-pills">
    <div class="learning-pill">🚀 Advanced Backend (Node + Docker + AWS)</div>
    <div class="learning-pill">🧠 Deep Learning for Medical Imaging</div>
    <div class="learning-pill">⚙️ GitHub Actions & CI/CD</div>
    <div class="learning-pill">☁️ Cloud Architecture</div>
  </div>

  <!-- ═══ GITHUB STATS ═══ -->
  <div class="section-label">
    <span class="section-num">06 /</span>
    <span>GitHub Activity</span>
  </div>

  <div class="card" style="padding:24px; text-align:center;">
    <img src="https://github-readme-stats.vercel.app/api?username=Vivekkrguptajio&show_icons=true&theme=tokyonight&bg_color=0d0d1f&border_color=7c5cff&title_color=7c5cff&text_color=e8e6ff&icon_color=00e5ff&hide_border=false&border_radius=12" alt="GitHub Stats" style="max-width:100%;border-radius:12px;margin-bottom:14px;" />
    <img src="https://streak-stats.demolab.com/?user=Vivekkrguptajio&theme=tokyonight&background=0d0d1f&border=7c5cff&ring=7c5cff&fire=ff4fd8&currStreakLabel=00e5ff&hide_border=false&border_radius=12" alt="GitHub Streak" style="max-width:100%;border-radius:12px;" />
  </div>

  <!-- ═══ FOOTER ═══ -->
  <div class="footer">
    <div class="footer-sig">Made with ❤️ by <span>Vivek Kumar Gupta</span></div>
    <div class="footer-star">⭐ Star my repos if you find them useful!</div>
  </div>

</div>

<!-- Staggered skill animations -->
<script>
  document.querySelectorAll('.skill-chip').forEach((el, i) => {
    el.style.animationDelay = `${i * 0.04}s`;
  });
</script>

</body>
</html>
