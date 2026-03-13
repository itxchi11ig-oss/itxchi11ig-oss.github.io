<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ML Lernpfad — Von LSTM bis RAG</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;600;700&family=Fraunces:ital,wght@0,300;0,600;0,900;1,300&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/highlight.min.js"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/styles/github-dark.min.css">
<script>
  window.MathJax = {
    tex: {
      inlineMath: [['$','$']],
      displayMath: [['$$','$$']],
      tags: 'none'
    },
    options: { skipHtmlTags: ['script','noscript','style','textarea','pre','code'] },
    startup: {
      typeset: true,   // auto-typeset the whole page on load
      ready() {
        MathJax.startup.defaultReady();
      }
    }
  };
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js" id="MathJax-script" async></script>
<style>
  :root {
    --bg: #0a0c0f;
    --bg2: #111318;
    --bg3: #181c23;
    --border: #1e2330;
    --accent: #4fffb0;
    --accent2: #7b61ff;
    --accent3: #ff6b6b;
    --accent4: #ffd93d;
    --text: #e8eaf0;
    --muted: #6b7280;
    --card: #13171f;
  }
  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* GRID BACKGROUND */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(79,255,176,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(79,255,176,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  /* HEADER */
  header {
    position: sticky; top: 0; z-index: 100;
    background: rgba(10,12,15,0.92);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
    padding: 0 2rem;
    display: flex; align-items: center; gap: 2rem;
    height: 60px;
  }
  .logo {
    font-family: 'Fraunces', serif;
    font-weight: 900;
    font-size: 1.1rem;
    color: var(--accent);
    letter-spacing: -0.02em;
    white-space: nowrap;
  }
  .logo span { color: var(--muted); }

  /* NAV PILLS */
  nav { display: flex; gap: 0.4rem; overflow-x: auto; flex: 1; }
  nav::-webkit-scrollbar { display: none; }
  .nav-pill {
    padding: 0.35rem 0.9rem;
    border-radius: 999px;
    border: 1px solid var(--border);
    background: transparent;
    color: var(--muted);
    cursor: pointer;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.72rem;
    white-space: nowrap;
    transition: all 0.2s;
    text-decoration: none;
  }
  .nav-pill:hover { border-color: var(--accent); color: var(--accent); }
  .nav-pill.active { background: var(--accent); color: #000; border-color: var(--accent); font-weight: 700; }

  /* LAYOUT */
  .layout { display: flex; position: relative; z-index: 1; }

  /* SIDEBAR */
  aside {
    width: 260px; min-width: 260px;
    position: sticky; top: 60px;
    height: calc(100vh - 60px);
    overflow-y: auto;
    border-right: 1px solid var(--border);
    padding: 1.5rem 1rem;
    background: rgba(10,12,15,0.5);
  }
  aside::-webkit-scrollbar { width: 4px; }
  aside::-webkit-scrollbar-thumb { background: var(--border); border-radius: 2px; }

  .sidebar-section { margin-bottom: 1.5rem; }
  .sidebar-label {
    font-size: 0.6rem;
    color: var(--muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 0.6rem;
    padding-left: 0.5rem;
  }
  .sidebar-item {
    display: flex; align-items: center; gap: 0.6rem;
    padding: 0.5rem 0.7rem;
    border-radius: 6px;
    cursor: pointer;
    color: var(--muted);
    font-size: 0.78rem;
    transition: all 0.15s;
    text-decoration: none;
    border: 1px solid transparent;
  }
  .sidebar-item:hover { color: var(--text); background: var(--bg3); }
  .sidebar-item.active { color: var(--accent); background: rgba(79,255,176,0.07); border-color: rgba(79,255,176,0.2); }
  .sidebar-dot { width: 6px; height: 6px; border-radius: 50%; background: currentColor; flex-shrink: 0; }
  .sidebar-num { font-size: 0.6rem; color: var(--muted); margin-left: auto; }

  /* MAIN CONTENT */
  main { flex: 1; overflow-y: auto; }

  /* HERO */
  .hero {
    padding: 4rem 3rem 3rem;
    border-bottom: 1px solid var(--border);
    position: relative;
    overflow: hidden;
  }
  .hero::after {
    content: '';
    position: absolute;
    right: -100px; top: -100px;
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(79,255,176,0.08) 0%, transparent 70%);
    pointer-events: none;
  }
  .hero-tag {
    display: inline-block;
    padding: 0.2rem 0.7rem;
    border: 1px solid rgba(79,255,176,0.3);
    border-radius: 4px;
    color: var(--accent);
    font-size: 0.68rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 1.5rem;
  }
  .hero h1 {
    font-family: 'Fraunces', serif;
    font-weight: 900;
    font-size: clamp(2rem, 4vw, 3.5rem);
    line-height: 1.05;
    letter-spacing: -0.03em;
    margin-bottom: 1rem;
  }
  .hero h1 em { font-style: italic; color: var(--accent); }
  .hero p { color: var(--muted); font-size: 0.85rem; max-width: 560px; line-height: 1.7; }

  /* ROADMAP BAR */
  .roadmap {
    padding: 1.5rem 3rem;
    border-bottom: 1px solid var(--border);
    display: flex; align-items: center; gap: 0;
    overflow-x: auto;
  }
  .rm-node {
    display: flex; flex-direction: column; align-items: center;
    cursor: pointer;
    min-width: 100px;
  }
  .rm-bubble {
    width: 44px; height: 44px;
    border-radius: 50%;
    border: 2px solid var(--border);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.1rem;
    transition: all 0.2s;
    background: var(--bg3);
    position: relative;
  }
  .rm-node:hover .rm-bubble, .rm-node.active .rm-bubble {
    border-color: var(--accent);
    background: rgba(79,255,176,0.1);
    box-shadow: 0 0 20px rgba(79,255,176,0.2);
  }
  .rm-label { font-size: 0.6rem; color: var(--muted); margin-top: 0.4rem; text-align: center; }
  .rm-node.active .rm-label { color: var(--accent); }
  .rm-line { flex: 1; height: 2px; background: var(--border); min-width: 30px; margin-bottom: 20px; }

  /* SECTIONS */
  .section { padding: 3rem; border-bottom: 1px solid var(--border); }
  .section-header {
    display: flex; align-items: flex-start; gap: 1.5rem;
    margin-bottom: 2.5rem;
  }
  .section-num {
    font-size: 0.6rem;
    color: var(--muted);
    border: 1px solid var(--border);
    padding: 0.3rem 0.5rem;
    border-radius: 4px;
    margin-top: 0.3rem;
    min-width: 38px;
    text-align: center;
  }
  .section-title {
    font-family: 'Fraunces', serif;
    font-weight: 900;
    font-size: clamp(1.5rem, 3vw, 2.2rem);
    letter-spacing: -0.02em;
    line-height: 1.1;
  }
  .section-title .accent { color: var(--accent); }
  .section-subtitle { color: var(--muted); font-size: 0.8rem; margin-top: 0.4rem; }

  /* TABS */
  .tabs {
    display: flex; gap: 0; border-bottom: 1px solid var(--border);
    margin-bottom: 2rem;
  }
  .tab {
    padding: 0.7rem 1.4rem;
    cursor: pointer;
    font-size: 0.78rem;
    color: var(--muted);
    border-bottom: 2px solid transparent;
    transition: all 0.15s;
    user-select: none;
  }
  .tab:hover { color: var(--text); }
  .tab.active { color: var(--accent); border-bottom-color: var(--accent); }

  .tab-content { display: none; }
  .tab-content.active { display: block; }

  /* CARDS */
  .card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 1.5rem;
    margin-bottom: 1.2rem;
  }
  .card-title {
    font-size: 0.75rem;
    color: var(--accent);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-bottom: 0.8rem;
    display: flex; align-items: center; gap: 0.5rem;
  }
  .card-title::before {
    content: '';
    display: inline-block;
    width: 12px; height: 2px;
    background: var(--accent);
  }
  .card p { color: var(--text); font-size: 0.83rem; line-height: 1.8; }
  .card ul { list-style: none; padding: 0; }
  .card ul li {
    padding: 0.4rem 0;
    color: var(--text);
    font-size: 0.83rem;
    line-height: 1.7;
    padding-left: 1.2rem;
    position: relative;
  }
  .card ul li::before { content: '→'; position: absolute; left: 0; color: var(--accent); }

  /* MATH BLOCK */
  .math-block {
    background: #0d1117;
    border: 1px solid var(--border);
    border-left: 3px solid var(--accent2);
    border-radius: 8px;
    padding: 1.5rem;
    margin: 1rem 0;
    overflow-x: auto;
  }
  .math-label {
    font-size: 0.65rem;
    color: var(--accent2);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 0.8rem;
  }
  .math-formula {
    color: #e2c08d;
    line-height: 2.1;
    overflow-x: auto;
    padding: 0.5rem 0 0.2rem;
  }
  .math-formula mjx-container { color: #e2c08d !important; }
  .math-block mjx-container[jax="CHTML"] { color: #e2c08d !important; }
  mjx-math { color: inherit !important; }
  /* MathJax SVG / CHTML on dark bg */
  .math-block .MathJax { font-size: 1.08em !important; }
  mjx-merror { background: rgba(255,107,107,0.15); color: #ff6b6b; padding: 2px 6px; border-radius: 4px; font-size:0.8rem; }
  .math-comment { color: var(--muted); font-size: 0.75rem; font-style: italic; }

  /* CODE */
  pre { border-radius: 8px !important; font-size: 0.78rem !important; }
  .code-header {
    display: flex; align-items: center; justify-content: space-between;
    background: #0d1117;
    border: 1px solid var(--border);
    border-bottom: none;
    border-radius: 8px 8px 0 0;
    padding: 0.6rem 1rem;
    font-size: 0.7rem; color: var(--muted);
  }
  .code-header .lang { color: var(--accent4); }
  .code-wrap pre { border-radius: 0 0 8px 8px !important; margin: 0 !important; }

  /* DIAGRAM */
  .diagram {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 2rem;
    margin: 1.2rem 0;
    overflow-x: auto;
  }
  .diagram svg { display: block; margin: 0 auto; }

  /* GRID */
  .grid2 { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  @media (max-width: 800px) { .grid2 { grid-template-columns: 1fr; } }

  /* HIGHLIGHT BOX */
  .highlight-box {
    border-radius: 8px;
    padding: 1rem 1.2rem;
    margin: 1rem 0;
    font-size: 0.82rem;
    line-height: 1.7;
  }
  .highlight-box.green { background: rgba(79,255,176,0.06); border: 1px solid rgba(79,255,176,0.2); color: var(--accent); }
  .highlight-box.purple { background: rgba(123,97,255,0.06); border: 1px solid rgba(123,97,255,0.2); color: #a78bfa; }
  .highlight-box.red { background: rgba(255,107,107,0.06); border: 1px solid rgba(255,107,107,0.2); color: #fca5a5; }
  .highlight-box.yellow { background: rgba(255,217,61,0.06); border: 1px solid rgba(255,217,61,0.2); color: var(--accent4); }

  /* INTERACTIVE LSTM */
  .lstm-demo {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 2rem;
    margin: 1.2rem 0;
  }
  .lstm-demo h4 { color: var(--accent); font-size: 0.78rem; margin-bottom: 1rem; text-transform: uppercase; letter-spacing: 0.1em; }
  .gate-row { display: flex; gap: 1rem; margin-bottom: 1rem; flex-wrap: wrap; }
  .gate-card {
    flex: 1; min-width: 140px;
    padding: 1rem;
    border-radius: 8px;
    border: 1px solid var(--border);
    background: var(--bg3);
    text-align: center;
    transition: all 0.3s;
    cursor: pointer;
  }
  .gate-card:hover { border-color: var(--accent); transform: translateY(-2px); }
  .gate-name { font-size: 0.7rem; color: var(--muted); margin-bottom: 0.3rem; }
  .gate-value { font-size: 1.4rem; font-weight: 700; color: var(--accent); font-family: 'Fraunces', serif; }
  .gate-formula { font-size: 0.65rem; color: var(--muted); margin-top: 0.3rem; }

  .slider-row { display: flex; align-items: center; gap: 1rem; margin: 0.6rem 0; }
  .slider-row label { font-size: 0.72rem; color: var(--muted); min-width: 120px; }
  .slider-row input[type=range] { flex: 1; accent-color: var(--accent); }
  .slider-val { font-size: 0.72rem; color: var(--accent); min-width: 40px; text-align: right; }

  /* ATTENTION VIZ */
  .attention-grid {
    display: grid;
    gap: 2px;
    margin: 1rem 0;
  }
  .att-cell {
    border-radius: 3px;
    display: flex; align-items: center; justify-content: center;
    font-size: 0.6rem;
    color: rgba(0,0,0,0.7);
    font-weight: 700;
    cursor: pointer;
    transition: transform 0.15s;
  }
  .att-cell:hover { transform: scale(1.2); z-index: 2; }
  .att-tokens { display: flex; gap: 2px; margin-top: 4px; }
  .att-token { font-size: 0.65rem; color: var(--muted); text-align: center; }

  /* QUIZ */
  .quiz-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 1.5rem;
    margin: 1rem 0;
  }
  .quiz-q { font-size: 0.85rem; color: var(--text); margin-bottom: 1rem; line-height: 1.6; }
  .quiz-options { display: flex; flex-direction: column; gap: 0.5rem; }
  .quiz-opt {
    padding: 0.7rem 1rem;
    border: 1px solid var(--border);
    border-radius: 6px;
    cursor: pointer;
    font-size: 0.78rem;
    color: var(--muted);
    transition: all 0.15s;
    background: var(--bg3);
  }
  .quiz-opt:hover { border-color: var(--accent2); color: var(--text); }
  .quiz-opt.correct { border-color: var(--accent); background: rgba(79,255,176,0.1); color: var(--accent); }
  .quiz-opt.wrong { border-color: var(--accent3); background: rgba(255,107,107,0.1); color: var(--accent3); }
  .quiz-feedback { margin-top: 0.8rem; font-size: 0.78rem; line-height: 1.6; color: var(--muted); }

  /* VECTOR VIZ */
  canvas { border-radius: 8px; }

  /* PROGRESS */
  .progress-bar {
    height: 3px; background: var(--border);
    border-radius: 2px; overflow: hidden;
    margin: 0.5rem 0;
  }
  .progress-fill { height: 100%; background: var(--accent); border-radius: 2px; transition: width 0.5s; }

  /* FOOTER */
  footer {
    padding: 2rem 3rem;
    border-top: 1px solid var(--border);
    text-align: center;
    color: var(--muted);
    font-size: 0.72rem;
  }

  @media (max-width: 900px) {
    aside { display: none; }
    .section { padding: 2rem 1.5rem; }
    .hero { padding: 2.5rem 1.5rem; }
    .roadmap { padding: 1rem 1.5rem; }
  }

  /* DB VIZ BUTTONS */
  .db-btn {
    padding: 0.35rem 0.85rem;
    border-radius: 6px;
    border: 1px solid var(--border);
    background: var(--bg3);
    color: var(--muted);
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.7rem;
    cursor: pointer;
    transition: all 0.15s;
  }
  .db-btn:hover { border-color: var(--accent); color: var(--text); }
  .db-btn.active { background: rgba(79,255,176,0.1); border-color: var(--accent); color: var(--accent); font-weight: 600; }
</style>
</head>
<body>

<header>
  <div class="logo">ML<span>/</span>Lernpfad</div>
  <nav>
    <a class="nav-pill active" href="#grundlagen" onclick="scrollTo('grundlagen')">Grundlagen</a>
    <a class="nav-pill" href="#lstm" onclick="scrollTo('lstm')">LSTM</a>
    <a class="nav-pill" href="#transformer" onclick="scrollTo('transformer')">Transformer</a>
    <a class="nav-pill" href="#llm" onclick="scrollTo('llm')">LLM</a>
    <a class="nav-pill" href="#vectordb" onclick="scrollTo('vectordb')">Vector DB</a>
    <a class="nav-pill" href="#rag" onclick="scrollTo('rag')">RAG</a>
  </nav>
</header>

<div class="layout">
<aside>
  <div class="sidebar-section">
    <div class="sidebar-label">Lernpfad</div>
    <a class="sidebar-item active" href="#grundlagen" onclick="sideNav(this)">
      <span class="sidebar-dot"></span> Grundlagen
      <span class="sidebar-num">00</span>
    </a>
    <a class="sidebar-item" href="#lstm" onclick="sideNav(this)">
      <span class="sidebar-dot"></span> LSTM
      <span class="sidebar-num">01</span>
    </a>
    <a class="sidebar-item" href="#transformer" onclick="sideNav(this)">
      <span class="sidebar-dot"></span> Transformer
      <span class="sidebar-num">02</span>
    </a>
    <a class="sidebar-item" href="#llm" onclick="sideNav(this)">
      <span class="sidebar-dot"></span> LLM
      <span class="sidebar-num">03</span>
    </a>
    <a class="sidebar-item" href="#vectordb" onclick="sideNav(this)">
      <span class="sidebar-dot"></span> Vector DB
      <span class="sidebar-num">04</span>
    </a>
    <a class="sidebar-item" href="#rag" onclick="sideNav(this)">
      <span class="sidebar-dot"></span> RAG
      <span class="sidebar-num">05</span>
    </a>
  </div>
  <div class="sidebar-section">
    <div class="sidebar-label">Fortschritt</div>
    <div style="padding: 0 0.5rem;">
      <div style="display:flex;justify-content:space-between;font-size:0.65rem;color:var(--muted);margin-bottom:0.3rem;">
        <span>Grundlagen</span><span id="prog0">0%</span>
      </div>
      <div class="progress-bar"><div class="progress-fill" id="pf0" style="width:0%"></div></div>
      <div style="display:flex;justify-content:space-between;font-size:0.65rem;color:var(--muted);margin:0.5rem 0 0.3rem;">
        <span>LSTM</span><span id="prog1">0%</span>
      </div>
      <div class="progress-bar"><div class="progress-fill" id="pf1" style="width:0%"></div></div>
      <div style="display:flex;justify-content:space-between;font-size:0.65rem;color:var(--muted);margin:0.5rem 0 0.3rem;">
        <span>Transformer</span><span id="prog2">0%</span>
      </div>
      <div class="progress-bar"><div class="progress-fill" id="pf2" style="width:0%"></div></div>
      <div style="display:flex;justify-content:space-between;font-size:0.65rem;color:var(--muted);margin:0.5rem 0 0.3rem;">
        <span>LLM</span><span id="prog3">0%</span>
      </div>
      <div class="progress-bar"><div class="progress-fill" id="pf3" style="width:0%"></div></div>
      <div style="display:flex;justify-content:space-between;font-size:0.65rem;color:var(--muted);margin:0.5rem 0 0.3rem;">
        <span>Vector DB</span><span id="prog4">0%</span>
      </div>
      <div class="progress-bar"><div class="progress-fill" id="pf4" style="width:0%"></div></div>
      <div style="display:flex;justify-content:space-between;font-size:0.65rem;color:var(--muted);margin:0.5rem 0 0.3rem;">
        <span>RAG</span><span id="prog5">0%</span>
      </div>
      <div class="progress-bar"><div class="progress-fill" id="pf5" style="width:0%"></div></div>
    </div>
  </div>
  <div class="sidebar-section">
    <div class="sidebar-label">Voraussetzungen</div>
    <div style="padding:0 0.5rem;font-size:0.72rem;color:var(--muted);line-height:1.7;">
      ✓ CNN / Backprop<br>
      ✓ Gradient Descent<br>
      ✓ Python / PyTorch<br>
      ✓ Lineare Algebra
    </div>
  </div>
</aside>

<main>
  <!-- HERO -->
  <div class="hero">
    <div class="hero-tag">B.Sc. Informatik · Machine Learning</div>
    <h1>Von <em>Lin. Regression</em><br>bis RAG — Vollständig</h1>
    <p>Interaktive Lernzettel mit Theorie, Mathematik und Implementierung. Beginnend mit den Grundlagen (LinReg → CNN) und aufbauend bis zu modernen LLMs und RAG.</p>
  </div>

  <!-- ROADMAP -->
  <div class="roadmap">
    <div class="rm-node active" onclick="jumpTo('grundlagen')">
      <div class="rm-bubble">📐</div>
      <div class="rm-label">Grundlagen</div>
    </div>
    <div class="rm-line"></div>
    <div class="rm-node" onclick="jumpTo('lstm')">
      <div class="rm-bubble">🧠</div>
      <div class="rm-label">LSTM</div>
    </div>
    <div class="rm-line"></div>
    <div class="rm-node" onclick="jumpTo('transformer')">
      <div class="rm-bubble">⚡</div>
      <div class="rm-label">Transformer</div>
    </div>
    <div class="rm-line"></div>
    <div class="rm-node" onclick="jumpTo('llm')">
      <div class="rm-bubble">🤖</div>
      <div class="rm-label">LLM</div>
    </div>
    <div class="rm-line"></div>
    <div class="rm-node" onclick="jumpTo('vectordb')">
      <div class="rm-bubble">🗄️</div>
      <div class="rm-label">Vector DB</div>
    </div>
    <div class="rm-line"></div>
    <div class="rm-node" onclick="jumpTo('rag')">
      <div class="rm-bubble">🔍</div>
      <div class="rm-label">RAG</div>
    </div>
  </div>

  <!-- ===== SECTION 0: GRUNDLAGEN RECAP ===== -->
  <div class="section" id="grundlagen">
    <div class="section-header">
      <div class="section-num">00</div>
      <div>
        <div class="section-title">Grundlagen <span class="accent">Recap</span></div>
        <div class="section-subtitle">Lin. Regression · Log. Regression · Perceptron · FNN · CNN — das Fundament</div>
      </div>
    </div>

    <div class="tabs" id="tabs-grundlagen">
      <div class="tab active" onclick="switchTab('grundlagen','theory')">Theorie</div>
      <div class="tab" onclick="switchTab('grundlagen','math')">Mathematik</div>
      <div class="tab" onclick="switchTab('grundlagen','impl')">Implementierung</div>
      <div class="tab" onclick="switchTab('grundlagen','interaktiv')">Interaktiv</div>
      <div class="tab" onclick="switchTab('grundlagen','quiz')">Quiz</div>
    </div>

    <!-- THEORY -->
    <div class="tab-content active" id="tc-grundlagen-theory">
      <div class="highlight-box yellow">
        📐 Diese fünf Bausteine bilden das Fundament von allem, was danach kommt. Transformer, LLMs und RAG sind im Kern Erweiterungen dieser Ideen — verstehe sie tief, nicht oberflächlich.
      </div>

      <!-- Sub-Navigation -->
      <div style="display:flex;gap:0.5rem;flex-wrap:wrap;margin-bottom:1.5rem;" id="grundlagen-subnav">
        <button class="g-sub active" onclick="showGSub('linreg')" style="padding:0.4rem 1rem;border-radius:6px;border:1px solid rgba(79,255,176,0.4);background:rgba(79,255,176,0.08);color:var(--accent);font-family:monospace;font-size:0.72rem;cursor:pointer;">Lin. Regression</button>
        <button class="g-sub" onclick="showGSub('logreg')" style="padding:0.4rem 1rem;border-radius:6px;border:1px solid var(--border);background:transparent;color:var(--muted);font-family:monospace;font-size:0.72rem;cursor:pointer;">Log. Regression</button>
        <button class="g-sub" onclick="showGSub('perceptron')" style="padding:0.4rem 1rem;border-radius:6px;border:1px solid var(--border);background:transparent;color:var(--muted);font-family:monospace;font-size:0.72rem;cursor:pointer;">Perceptron</button>
        <button class="g-sub" onclick="showGSub('fnn')" style="padding:0.4rem 1rem;border-radius:6px;border:1px solid var(--border);background:transparent;color:var(--muted);font-family:monospace;font-size:0.72rem;cursor:pointer;">FNN</button>
        <button class="g-sub" onclick="showGSub('cnn')" style="padding:0.4rem 1rem;border-radius:6px;border:1px solid var(--border);background:transparent;color:var(--muted);font-family:monospace;font-size:0.72rem;cursor:pointer;">CNN</button>
      </div>

      <!-- Lin. Regression -->
      <div class="gsub-content" id="gsub-linreg">
        <div class="grid2">
          <div class="card">
            <div class="card-title">Was ist Lineare Regression?</div>
            <p>Das einfachste parametrische Modell: Finde eine lineare Funktion f(x) = wᵀx + b, die kontinuierliche Ausgaben möglichst gut vorhersagt. Ziel: Minimiere den mittleren quadratischen Fehler (MSE) zwischen Vorhersage und tatsächlichem Wert über alle Trainingsdaten.</p>
          </div>
          <div class="card">
            <div class="card-title">Annahmen & Grenzen</div>
            <ul>
              <li>Lineare Beziehung zwischen Feature und Label</li>
              <li>Residuen normalverteilt und homoskedastisch</li>
              <li>Features linear unabhängig (kein Multikollinearität)</li>
              <li>Nicht für Klassifikation geeignet — hier kommt Log. Reg.</li>
            </ul>
          </div>
        </div>
        <div class="card">
          <div class="card-title">Von LinReg zu Deep Learning</div>
          <p>Lineare Regression ist ein neuronales Netz mit <strong>einer Schicht, keiner Aktivierungsfunktion</strong>. Der Gradient der MSE-Loss ist analytisch lösbar (Normalengleichung) — das wird bei tiefen Netzen unmöglich, weshalb Gradient Descent nötig wird. Alles spätere baut hierauf auf.</p>
        </div>
      </div>

      <!-- Log. Regression -->
      <div class="gsub-content" id="gsub-logreg" style="display:none;">
        <div class="grid2">
          <div class="card">
            <div class="card-title">Sigmoid statt lineare Ausgabe</div>
            <p>Für binäre Klassifikation brauchen wir Ausgaben in [0,1] — interpretierbar als Wahrscheinlichkeit P(y=1|x). Trick: Wende Sigmoid auf den linearen Output an: σ(z) = 1/(1+e⁻ᶻ). Das "quetscht" jeden reellen Wert in (0,1).</p>
          </div>
          <div class="card">
            <div class="card-title">Warum nicht MSE für Klassifikation?</div>
            <ul>
              <li>MSE mit Sigmoid → nicht-konvexe Loss-Landscape</li>
              <li>Binary Cross-Entropy ist konvex → garantiertes globales Minimum</li>
              <li>BCE bestraft falsch-konfidente Vorhersagen exponentiell stärker</li>
              <li>Probabilistische Interpretation durch Maximum-Likelihood</li>
            </ul>
          </div>
        </div>
        <div class="card">
          <div class="card-title">Decision Boundary & Softmax</div>
          <p>Bei zwei Klassen teilt die Decision Boundary den Raum linear (Hyperebene). Für k Klassen → <strong>Softmax-Regression</strong> (Multinomiale Log. Reg.): softmax(z)_i = e^z_i / Σe^z_j. Das ist genau die letzte Schicht eines Classifiers im neuronalen Netz!</p>
        </div>
      </div>

      <!-- Perceptron -->
      <div class="gsub-content" id="gsub-perceptron" style="display:none;">
        <div class="card">
          <div class="card-title">Das biologische Neuron als Modell (1957, Rosenblatt)</div>
          <p>Das Perceptron ist das einfachste "künstliche Neuron": Berechne gewichtete Summe der Eingaben, wende Schwellenwertfunktion an. Wenn Aktivierung > θ → feuert (Output 1), sonst 0. Lernregel: w ← w + α·(y - ŷ)·x — Update nur bei Fehler.</p>
        </div>
        <div class="grid2">
          <div class="card">
            <div class="card-title">Konvergenz-Theorem</div>
            <p>Falls die Daten linear separierbar sind, konvergiert der Perceptron-Algorithmus garantiert in endlich vielen Schritten. Das war der erste theoretische Beweis, dass ein Lernalgorithmus konvergiert.</p>
          </div>
          <div class="card">
            <div class="card-title">XOR-Problem & der AI Winter</div>
            <p>1969 zeigte Minsky & Papert: Ein einzelnes Perceptron kann XOR nicht lösen (nicht linear separierbar). Führte zum ersten "AI Winter". Lösung: Mehrere Schichten — das FNN. Die Aktivierungsfunktion muss dabei nicht-linear sein, sonst kollabiert das mehrschichtige Netz zu einem linearen Modell.</p>
          </div>
        </div>
      </div>

      <!-- FNN -->
      <div class="gsub-content" id="gsub-fnn" style="display:none;">
        <div class="card">
          <div class="card-title">Feedforward Neural Network (MLP)</div>
          <p>Mehrere hintereinander geschaltete Schichten: Input → Hidden Layer(s) → Output. Jede Schicht: z = Wx + b, dann Aktivierung a = f(z). Durch Stapelung entstehen hierarchische Repräsentationen — flache Schichten lernen einfache Features, tiefe Schichten lernen Kompositionen davon.</p>
        </div>
        <div class="grid2">
          <div class="card">
            <div class="card-title">Aktivierungsfunktionen im Vergleich</div>
            <ul>
              <li><strong style="color:#ff6b6b">Sigmoid</strong> — Vanishing Gradient in tiefen Netzen, nur für Output</li>
              <li><strong style="color:#ffd93d">Tanh</strong> — Nullzentriert, besser als Sigmoid, aber noch Vanishing</li>
              <li><strong style="color:#4fffb0">ReLU</strong> — max(0,x), sparse Aktivierungen, aber "Dead Neurons"</li>
              <li><strong style="color:#7b61ff">GELU</strong> — Smooth ReLU, Transformer-Standard (BERT, GPT)</li>
              <li><strong>SiLU/Swish</strong> — x·σ(x), LLaMA-Standard</li>
            </ul>
          </div>
          <div class="card">
            <div class="card-title">Backpropagation — Chain Rule</div>
            <p>∂L/∂w = ∂L/∂a · ∂a/∂z · ∂z/∂w. Gradienten fließen von der Loss-Schicht rückwärts durch das Netz. Jede Aktivierungsfunktion muss differenzierbar sein (oder fast überall, wie ReLU). Das ist genau warum die Stufenfunktion des Perceptrons durch Sigmoid/ReLU ersetzt wurde.</p>
          </div>
        </div>
        <div class="highlight-box purple">
          🧠 <strong>Universal Approximation Theorem:</strong> Ein FNN mit einer hinreichend breiten Hidden Layer kann jede stetige Funktion beliebig genau approximieren. Tiefe (statt Breite) ist jedoch effizienter — weniger Parameter für dieselbe Ausdruckskraft.
        </div>
      </div>

      <!-- CNN -->
      <div class="gsub-content" id="gsub-cnn" style="display:none;">
        <div class="card">
          <div class="card-title">Warum CNNs für Bilder?</div>
          <p>Ein FNN für ein 224×224×3 Bild hätte in der ersten Schicht allein schon 150k Eingaben — bei 1024 Neuronen = 150M Parameter nur für Layer 1. CNNs nutzen <strong>Translationsinvarianz</strong> (eine Katze ist überall im Bild eine Katze) und <strong>lokale Konnektivität</strong> (benachbarte Pixel hängen zusammen) als Induktiver Bias.</p>
        </div>
        <div class="grid2">
          <div class="card">
            <div class="card-title">Faltung (Convolution)</div>
            <ul>
              <li>Filter/Kernel K gleitet über das Bild: (I * K)(x,y) = Σ I(x+i,y+j)·K(i,j)</li>
              <li>Parameter-Sharing: Derselbe Filter für jede Position → massive Reduktion</li>
              <li>Tiefe Filter lernen Kanten → Texturen → Formen → Objekte</li>
              <li>1×1 Convolution = Linear-Projektion über Kanäle (dimensionality reduction)</li>
            </ul>
          </div>
          <div class="card">
            <div class="card-title">Pooling & Receptive Field</div>
            <ul>
              <li><strong>Max-Pooling</strong>: Nimmt das Maximum im Fenster → Translation-Robustheit, Feature-Detektion</li>
              <li><strong>Average-Pooling</strong>: Durchschnitt → Smooth, für Global Average Pooling vor Classifier</li>
              <li><strong>Receptive Field</strong>: Nach n Conv-Schichten "sieht" jedes Neuron einen größeren Bildausschnitt</li>
              <li>Stride 2 statt Pooling (moderne Netze wie ResNet) — end-to-end lernbar</li>
            </ul>
          </div>
        </div>
        <div class="card">
          <div class="card-title">Architectur-Evolution: Von LeNet zu ResNet</div>
          <ul>
            <li><strong style="color:#4fffb0">LeNet-5 (1998)</strong> — Erste erfolgreiche CNN-Architektur für Handschrifterkennung (MNIST)</li>
            <li><strong style="color:#7b61ff">AlexNet (2012)</strong> — Breakthrough auf ImageNet, ReLU statt Sigmoid, GPU-Training, Dropout</li>
            <li><strong style="color:#ffd93d">VGG (2014)</strong> — Tiefe Netze mit kleinen 3×3 Filtern, sehr einflussreich</li>
            <li><strong style="color:#ff6b6b">ResNet (2015)</strong> — Skip Connections: x → F(x) + x. Trainiert 152 Schichten! Gradienten fließen direkt zurück → no vanishing gradient</li>
            <li><strong>Brücke zu Transformern:</strong> Vision Transformer (ViT, 2020) ersetzt Faltung durch Self-Attention auf Bild-Patches</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- MATH -->
    <div class="tab-content" id="tc-grundlagen-math">
      <div class="math-block">
        <div class="math-label">Lineare Regression — MSE Loss & Normalengleichung</div>
        <div class="math-formula">
$$\hat{y} = \mathbf{w}^\top \mathbf{x} + b$$
$$\mathcal{L}_{\text{MSE}} = \frac{1}{n} \sum_{i=1}^n (y_i - \hat{y}_i)^2$$
$$\mathbf{w}^* = (\mathbf{X}^\top \mathbf{X})^{-1} \mathbf{X}^\top \mathbf{y}$$
$$\mathbf{w} \leftarrow \mathbf{w} - \alpha \cdot \frac{\partial \mathcal{L}}{\partial \mathbf{w}}, \qquad \frac{\partial \mathcal{L}}{\partial \mathbf{w}} = -\frac{2}{n}\,\mathbf{X}^\top(\mathbf{y} - \mathbf{X}\mathbf{w})$$
        </div>
        <div class="math-comment">// Normalengleichung: O(n³) durch Matrixinversion — bei n > 10k unbrauchbar
// Stochastic Gradient Descent (SGD): Benutze Mini-Batches → skalierbar</div>
      </div>

      <div class="math-block">
        <div class="math-label">Logistische Regression — Sigmoid & Binary Cross-Entropy</div>
        <div class="math-formula">
$$\sigma(z) = \frac{1}{1+e^{-z}}, \qquad z = \mathbf{w}^\top\mathbf{x} + b$$
$$P(y=1\mid\mathbf{x}) = \sigma(\mathbf{w}^\top\mathbf{x}+b)$$
$$\mathcal{L}_{\text{BCE}} = -\frac{1}{n}\sum_{i=1}^n\!\Big[y_i\log\hat{y}_i + (1-y_i)\log(1-\hat{y}_i)\Big]$$
$$\frac{\partial \mathcal{L}_{\text{BCE}}}{\partial \mathbf{w}} = \frac{1}{n}\,\mathbf{X}^\top(\hat{\mathbf{y}} - \mathbf{y})$$
        </div>
        <div class="math-comment">// Schöne Eigenschaft: Gradient hat dieselbe Form wie MSE-Gradient
// Maximum Likelihood Estimation (MLE) → Cross-Entropy Loss</div>
      </div>

      <div class="math-block">
        <div class="math-label">Perceptron Lernregel</div>
        <div class="math-formula">
$$\hat{y} = \text{step}(\mathbf{w}^\top\mathbf{x}+b) = \begin{cases} 1 & \text{falls } \mathbf{w}^\top\mathbf{x}+b \ge 0 \\ 0 & \text{sonst}\end{cases}$$
$$\mathbf{w} \leftarrow \mathbf{w} + \alpha\,(y-\hat{y})\,\mathbf{x}, \qquad b \leftarrow b + \alpha\,(y-\hat{y})$$
        </div>
        <div class="math-comment">// Kein Gradient nötig! Aber: Stufenfunktion nicht differenzierbar
// Konvergiert NUR bei linear separierbaren Daten</div>
      </div>

      <div class="math-block">
        <div class="math-label">FNN Forward Pass & Backpropagation</div>
        <div class="math-formula">
$$\textbf{Forward:}\quad \mathbf{z}^{(l)} = \mathbf{W}^{(l)}\mathbf{a}^{(l-1)}+\mathbf{b}^{(l)}, \qquad \mathbf{a}^{(l)} = f\!\left(\mathbf{z}^{(l)}\right)$$
$$\textbf{Backward:}\quad \boldsymbol{\delta}^{(L)} = \frac{\partial\mathcal{L}}{\partial\mathbf{z}^{(L)}}$$
$$\boldsymbol{\delta}^{(l)} = \left(\mathbf{W}^{(l+1)}\right)^\top\boldsymbol{\delta}^{(l+1)} \odot f'\!\left(\mathbf{z}^{(l)}\right)$$
$$\frac{\partial\mathcal{L}}{\partial\mathbf{W}^{(l)}} = \boldsymbol{\delta}^{(l)}\left(\mathbf{a}^{(l-1)}\right)^\top, \qquad \mathbf{W}^{(l)} \leftarrow \mathbf{W}^{(l)} - \alpha\,\frac{\partial\mathcal{L}}{\partial\mathbf{W}^{(l)}}$$
        </div>
        <div class="math-comment">// ⊙ = element-wise (Hadamard-Produkt)
// f'(z) bei ReLU = 1 falls z > 0, sonst 0</div>
      </div>

      <div class="math-block">
        <div class="math-label">CNN — Diskrete Kreuzkorrelation (in der Praxis als "Convolution" bezeichnet)</div>
        <div class="math-formula">
$$(\mathbf{I} \star \mathbf{K})[i,j] = \sum_m\sum_n \mathbf{I}[i+m,\,j+n]\cdot\mathbf{K}[m,n]$$
$$H_{\text{out}} = \left\lfloor\frac{H_{\text{in}} - K_h + 2P}{S}\right\rfloor + 1, \qquad W_{\text{out}} = \left\lfloor\frac{W_{\text{in}} - K_w + 2P}{S}\right\rfloor + 1$$
$$\#\text{params} = C_{\text{out}}\cdot(C_{\text{in}}\cdot K_h\cdot K_w + 1)$$
        </div>
        <div class="math-comment">// P = Padding, S = Stride, K = Kernel-Größe
// Beispiel: Conv2d(3, 64, 3×3) → 64 · (3·9 + 1) = 1.792 Parameter</div>
      </div>

      <div class="highlight-box green">
        🔗 <strong>Verbindung zu Transformern:</strong> ResNet's Skip Connections (x + F(x)) erscheinen 1:1 in Transformer-Blöcken als Residual Connections. Die Idee: Gradienten sollen ungehindert durchfließen können — tiefer Netze, stabiles Training.
      </div>
    </div>

    <!-- IMPL -->
    <div class="tab-content" id="tc-grundlagen-impl">
      <div class="code-header"><span class="lang">Python · NumPy + PyTorch</span><span>Alle 5 Modelle von Scratch</span></div>
      <div class="code-wrap">
<pre><code class="language-python">import numpy as np
import torch
import torch.nn as nn
import torch.nn.functional as F

# ══════════════════════════════════════════════════════════════════
# 1. LINEARE REGRESSION — reines NumPy
# ══════════════════════════════════════════════════════════════════
class LinearRegressionNumpy:
    def __init__(self, lr=0.01, n_iter=1000):
        self.lr, self.n_iter = lr, n_iter
        self.w, self.b = None, None

    def fit(self, X, y):
        n, d = X.shape
        self.w = np.zeros(d)
        self.b = 0.0
        for _ in range(self.n_iter):
            y_hat = X @ self.w + self.b
            error = y_hat - y
            # Gradienten
            dw = (2/n) * X.T @ error
            db = (2/n) * error.sum()
            self.w -= self.lr * dw
            self.b -= self.lr * db

    def predict(self, X):
        return X @ self.w + self.b

    def mse(self, X, y):
        return np.mean((self.predict(X) - y) ** 2)

# Analytische Lösung (Normalengleichung) — nur für kleine n!
def normal_equation(X, y):
    X_b = np.c_[np.ones(len(X)), X]   # Bias-Term hinzufügen
    return np.linalg.pinv(X_b.T @ X_b) @ X_b.T @ y  # (XᵀX)⁻¹Xᵀy


# ══════════════════════════════════════════════════════════════════
# 2. LOGISTISCHE REGRESSION — NumPy
# ══════════════════════════════════════════════════════════════════
class LogisticRegressionNumpy:
    def __init__(self, lr=0.1, n_iter=500):
        self.lr, self.n_iter = lr, n_iter

    def _sigmoid(self, z):
        return 1 / (1 + np.exp(-np.clip(z, -500, 500)))

    def fit(self, X, y):
        n, d = X.shape
        self.w = np.zeros(d)
        self.b = 0.0
        for _ in range(self.n_iter):
            z = X @ self.w + self.b
            p = self._sigmoid(z)          # P(y=1|x)
            error = p - y                 # Gradient BCE hat dieselbe Form wie MSE!
            self.w -= self.lr * (X.T @ error) / n
            self.b -= self.lr * error.mean()

    def predict_proba(self, X):
        return self._sigmoid(X @ self.w + self.b)

    def predict(self, X, threshold=0.5):
        return (self.predict_proba(X) >= threshold).astype(int)


# ══════════════════════════════════════════════════════════════════
# 3. PERCEPTRON — NumPy
# ══════════════════════════════════════════════════════════════════
class Perceptron:
    def __init__(self, lr=0.1, n_iter=100):
        self.lr, self.n_iter = lr, n_iter

    def fit(self, X, y):
        self.w = np.zeros(X.shape[1])
        self.b = 0.0
        for _ in range(self.n_iter):
            for xi, yi in zip(X, y):
                y_hat = 1 if (self.w @ xi + self.b) >= 0 else 0
                error = yi - y_hat
                if error != 0:            # Update NUR bei Fehler
                    self.w += self.lr * error * xi
                    self.b += self.lr * error

    def predict(self, X):
        return (X @ self.w + self.b >= 0).astype(int)


# ══════════════════════════════════════════════════════════════════
# 4. FEEDFORWARD NEURAL NETWORK — PyTorch
# ══════════════════════════════════════════════════════════════════
class FNN(nn.Module):
    def __init__(self, in_dim, hidden_dims, out_dim, dropout=0.3):
        super().__init__()
        dims = [in_dim] + hidden_dims + [out_dim]
        layers = []
        for i in range(len(dims) - 1):
            layers.append(nn.Linear(dims[i], dims[i+1]))
            if i < len(dims) - 2:             # Keine Aktivierung nach letzter Schicht
                layers.append(nn.GELU())       # GELU: smooth, Transformer-Standard
                layers.append(nn.Dropout(dropout))
                layers.append(nn.LayerNorm(dims[i+1]))
        self.net = nn.Sequential(*layers)

    def forward(self, x):
        return self.net(x)

# Training loop (generisch, wiederverwendbar)
def train_model(model, X_train, y_train, epochs=50, lr=1e-3):
    optimizer = torch.optim.AdamW(model.parameters(), lr=lr, weight_decay=1e-4)
    scheduler = torch.optim.lr_scheduler.CosineAnnealingLR(optimizer, T_max=epochs)
    criterion = nn.CrossEntropyLoss()

    for epoch in range(epochs):
        model.train()
        logits = model(X_train)
        loss = criterion(logits, y_train)
        optimizer.zero_grad()
        loss.backward()
        optimizer.step()
        scheduler.step()
        if epoch % 10 == 0:
            acc = (logits.argmax(1) == y_train).float().mean()
            print(f"Epoch {epoch:3d} | Loss: {loss:.4f} | Acc: {acc:.3f}")


# ══════════════════════════════════════════════════════════════════
# 5. CNN — PyTorch (ResNet-Style mit Skip Connections)
# ══════════════════════════════════════════════════════════════════
class ResBlock(nn.Module):
    """Basis-ResNet Block mit Skip Connection"""
    def __init__(self, channels, stride=1):
        super().__init__()
        self.conv1 = nn.Conv2d(channels, channels, 3, stride, padding=1, bias=False)
        self.bn1   = nn.BatchNorm2d(channels)
        self.conv2 = nn.Conv2d(channels, channels, 3, 1, padding=1, bias=False)
        self.bn2   = nn.BatchNorm2d(channels)

    def forward(self, x):
        residual = x
        out = F.relu(self.bn1(self.conv1(x)))
        out = self.bn2(self.conv2(out))
        out += residual          # ← DIE Skip Connection: x + F(x)
        return F.relu(out)

class MiniResNet(nn.Module):
    def __init__(self, num_classes=10):
        super().__init__()
        # Stem: Erstes Conv-Layer
        self.stem = nn.Sequential(
            nn.Conv2d(3, 32, 3, stride=1, padding=1, bias=False),
            nn.BatchNorm2d(32), nn.ReLU(),
        )
        # Residual Blocks
        self.layer1 = ResBlock(32)
        self.layer2 = nn.Sequential(
            nn.Conv2d(32, 64, 3, stride=2, padding=1, bias=False),  # Downsampling
            nn.BatchNorm2d(64), nn.ReLU(),
            ResBlock(64),
        )
        self.layer3 = nn.Sequential(
            nn.Conv2d(64, 128, 3, stride=2, padding=1, bias=False),
            nn.BatchNorm2d(128), nn.ReLU(),
            ResBlock(128),
        )
        # Global Average Pooling + Classifier
        self.head = nn.Sequential(
            nn.AdaptiveAvgPool2d(1),   # → (batch, 128, 1, 1)
            nn.Flatten(),              # → (batch, 128)
            nn.Linear(128, num_classes),
        )

    def forward(self, x):
        x = self.stem(x)
        x = self.layer1(x)
        x = self.layer2(x)
        x = self.layer3(x)
        return self.head(x)

# Parameteranzahl ausgeben
model = MiniResNet(num_classes=10)
params = sum(p.numel() for p in model.parameters())
print(f"MiniResNet: {params:,} Parameter")  # ~230k
x = torch.randn(4, 3, 32, 32)  # CIFAR-10 Format
print(f"Output: {model(x).shape}")          # (4, 10)</code></pre>
      </div>
    </div>

    <!-- INTERAKTIV -->
    <div class="tab-content" id="tc-grundlagen-interaktiv">
      <div class="card">
        <div class="card-title">Interaktiver Entscheidungsgrenzen-Vergleich</div>
        <p style="margin-bottom:1rem;font-size:0.8rem;color:var(--muted)">Wähle ein Modell und einen Datensatz. Beobachte wie komplex die Entscheidungsgrenze werden kann.</p>
        <div style="display:flex;gap:0.8rem;flex-wrap:wrap;margin-bottom:1.2rem;">
          <div>
            <div style="font-size:0.65rem;color:var(--muted);margin-bottom:0.4rem;text-transform:uppercase;letter-spacing:0.08em;">Modell</div>
            <div style="display:flex;gap:0.4rem;">
              <button class="db-btn active" onclick="setModel('logreg')" id="btn-logreg">Log. Reg.</button>
              <button class="db-btn" onclick="setModel('perceptron')" id="btn-perceptron">Perceptron</button>
              <button class="db-btn" onclick="setModel('fnn')" id="btn-fnn">FNN</button>
            </div>
          </div>
          <div>
            <div style="font-size:0.65rem;color:var(--muted);margin-bottom:0.4rem;text-transform:uppercase;letter-spacing:0.08em;">Datensatz</div>
            <div style="display:flex;gap:0.4rem;">
              <button class="db-btn active" onclick="setDataset('linear')" id="btn-linear">Linear</button>
              <button class="db-btn" onclick="setDataset('xor')" id="btn-xor">XOR</button>
              <button class="db-btn" onclick="setDataset('circles')" id="btn-circles">Kreise</button>
            </div>
          </div>
        </div>
        <canvas id="dbCanvas" width="560" height="340" style="width:100%;background:#0d1117;border:1px solid var(--border);border-radius:8px;cursor:crosshair;"></canvas>
        <div id="dbInfo" style="margin-top:0.8rem;font-size:0.75rem;color:var(--muted);line-height:1.7;"></div>
      </div>

      <div class="card" style="margin-top:1.2rem;">
        <div class="card-title">Aktivierungsfunktionen Visualisierung</div>
        <canvas id="actCanvas" width="560" height="200" style="width:100%;background:#0d1117;border:1px solid var(--border);border-radius:8px;"></canvas>
        <div style="display:flex;gap:1rem;flex-wrap:wrap;margin-top:0.8rem;font-size:0.72rem;">
          <span style="color:#4fffb0">— ReLU</span>
          <span style="color:#7b61ff">— Sigmoid</span>
          <span style="color:#ffd93d">— Tanh</span>
          <span style="color:#ff6b6b">— GELU</span>
        </div>
      </div>
    </div>

    <!-- QUIZ -->
    <div class="tab-content" id="tc-grundlagen-quiz">
      <div class="quiz-card">
        <div class="quiz-q">1. Ein FNN mit ausschließlich linearen Aktivierungsfunktionen (f(x) = x) verhält sich wie welches Modell, egal wie viele Schichten es hat?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Ein Perceptron</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Ein einschichtiges lineares Modell (lineare Regression)</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Ein CNN</div>
        </div>
        <div class="quiz-feedback"></div>
      </div>
      <div class="quiz-card">
        <div class="quiz-q">2. Warum verwendet ResNet Skip Connections (x + F(x))?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Um das Modell schneller zu machen durch Überspringen von Schichten</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Um den Gradienten-Fluss zu verbessern — Gradienten können direkt über die Skip Connection fließen, ohne durch nichtlineare Schichten zu schrumpfen</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Weil CNNs ohne Skip Connections keine Bilder klassifizieren können</div>
        </div>
        <div class="quiz-feedback"></div>
      </div>
      <div class="quiz-card">
        <div class="quiz-q">3. Was ist der Hauptvorteil von Cross-Entropy Loss gegenüber MSE für Klassifikation?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Cross-Entropy ist einfacher zu berechnen</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">MSE funktioniert gar nicht für Klassifikation</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Cross-Entropy ist konvex mit Sigmoid/Softmax und bestraft falsch-konfidente Vorhersagen logarithmisch stärker — bessere Kalibrierung der Wahrscheinlichkeiten</div>
        </div>
        <div class="quiz-feedback"></div>
      </div>
      <div class="quiz-card">
        <div class="quiz-q">4. Parameter-Sharing in CNNs bedeutet: Derselbe Filter wird an jeder Position angewendet. Welchen Vorteil hat das?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Drastisch weniger Parameter + das Netz lernt automatisch translationsinvariante Features (eine Kante ist überall gleich)</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Das Training wird schneller auf der GPU</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Jede Bildposition wird genauer analysiert</div>
        </div>
        <div class="quiz-feedback"></div>
      </div>
    </div>
  </div>

  <!-- ===== SECTION 1: LSTM ===== -->
  <div class="section" id="lstm">
    <div class="section-header">
      <div class="section-num">01</div>
      <div>
        <div class="section-title">Long Short-Term <span class="accent">Memory</span></div>
        <div class="section-subtitle">Sequenzmodellierung mit selektivem Gedächtnis</div>
      </div>
    </div>

    <div class="tabs" id="tabs-lstm">
      <div class="tab active" onclick="switchTab('lstm','theory')">Theorie</div>
      <div class="tab" onclick="switchTab('lstm','math')">Mathematik</div>
      <div class="tab" onclick="switchTab('lstm','impl')">Implementierung</div>
      <div class="tab" onclick="switchTab('lstm','interaktiv')">Interaktiv</div>
      <div class="tab" onclick="switchTab('lstm','quiz')">Quiz</div>
    </div>

    <!-- THEORY -->
    <div class="tab-content active" id="tc-lstm-theory">
      <div class="highlight-box yellow">
        ⚡ Warum nicht einfach ein RNN? — Vanishing Gradient Problem: Bei langen Sequenzen verschwinden die Gradienten beim Backpropagation-Through-Time. LSTM löst das mit Gates.
      </div>
      <div class="grid2">
        <div class="card">
          <div class="card-title">Das Problem mit RNNs</div>
          <p>Standard-RNNs haben einen einzigen Hidden State, der bei jedem Zeitschritt überschrieben wird. Informationen von Zeitschritt 1 sind bei Schritt 100 praktisch verschwunden — der Gradient wird entweder exponentiell klein (vanishing) oder riesig (exploding).</p>
        </div>
        <div class="card">
          <div class="card-title">LSTMs Lösung: Cell State</div>
          <p>LSTM trennt "Arbeitsgedächtnis" (Hidden State h) vom "Langzeitgedächtnis" (Cell State C). Der Cell State fließt fast unverändert durch die Zeit — Informationen können bewusst gespeichert oder gelöscht werden.</p>
        </div>
      </div>
      <div class="card">
        <div class="card-title">Die vier Gates</div>
        <ul>
          <li><strong style="color:#4fffb0">Forget Gate (f)</strong> — Was soll aus dem Langzeitgedächtnis gelöscht werden? Sigmoid → [0,1], wobei 0 = alles vergessen, 1 = alles behalten</li>
          <li><strong style="color:#7b61ff">Input Gate (i)</strong> — Welche neuen Informationen sollen gespeichert werden? Sigmoid entscheidet WIE VIEL, Tanh liefert den INHALT</li>
          <li><strong style="color:#ffd93d">Cell Update (g/C̃)</strong> — Neue Kandidaten-Werte, die zum Cell State addiert werden könnten</li>
          <li><strong style="color:#ff6b6b">Output Gate (o)</strong> — Was wird als Hidden State ausgegeben? Cell State wird durch Tanh gequetscht, Output Gate filtert</li>
        </ul>
      </div>
      <div class="diagram">
        <svg width="600" height="200" viewBox="0 0 600 200">
          <!-- Cell state line -->
          <line x1="30" y1="40" x2="570" y2="40" stroke="#4fffb0" stroke-width="3" opacity="0.6"/>
          <text x="15" y="44" fill="#6b7280" font-size="11" font-family="monospace">C(t-1)</text>
          <text x="555" y="44" fill="#4fffb0" font-size="11" font-family="monospace">C(t)</text>
          <!-- Hidden state -->
          <line x1="30" y1="170" x2="100" y2="170" stroke="#a78bfa" stroke-width="2"/>
          <line x1="500" y1="170" x2="570" y2="170" stroke="#a78bfa" stroke-width="2"/>
          <text x="10" y="174" fill="#6b7280" font-size="11" font-family="monospace">h(t-1)</text>
          <text x="555" y="174" fill="#a78bfa" font-size="11" font-family="monospace">h(t)</text>
          <!-- Forget Gate -->
          <circle cx="130" cy="40" r="18" fill="#1e2330" stroke="#ffd93d" stroke-width="2"/>
          <text x="130" y="45" text-anchor="middle" fill="#ffd93d" font-size="14" font-weight="bold">×</text>
          <rect x="105" y="100" width="50" height="30" rx="6" fill="#1e2330" stroke="#ffd93d" stroke-width="1.5"/>
          <text x="130" y="120" text-anchor="middle" fill="#ffd93d" font-size="11" font-family="monospace">f</text>
          <line x1="130" y1="130" x2="130" y2="58" stroke="#ffd93d" stroke-width="1.5"/>
          <line x1="100" y1="170" x2="130" y2="115" stroke="#ffd93d" stroke-width="1" stroke-dasharray="4,2"/>
          <!-- Input Gate -->
          <circle cx="270" cy="40" r="18" fill="#1e2330" stroke="#4fffb0" stroke-width="2"/>
          <text x="270" y="45" text-anchor="middle" fill="#4fffb0" font-size="14" font-weight="bold">+</text>
          <rect x="220" y="100" width="50" height="30" rx="6" fill="#1e2330" stroke="#7b61ff" stroke-width="1.5"/>
          <text x="245" y="120" text-anchor="middle" fill="#7b61ff" font-size="11" font-family="monospace">i</text>
          <rect x="280" y="100" width="50" height="30" rx="6" fill="#1e2330" stroke="#4fffb0" stroke-width="1.5"/>
          <text x="305" y="120" text-anchor="middle" fill="#4fffb0" font-size="11" font-family="monospace">g</text>
          <!-- Multiply i*g -->
          <circle cx="270" cy="155" r="13" fill="#1e2330" stroke="#4fffb0" stroke-width="1.5"/>
          <text x="270" y="160" text-anchor="middle" fill="#4fffb0" font-size="12" font-weight="bold">×</text>
          <line x1="245" y1="130" x2="262" y2="142" stroke="#7b61ff" stroke-width="1.5"/>
          <line x1="305" y1="130" x2="278" y2="142" stroke="#4fffb0" stroke-width="1.5"/>
          <line x1="270" y1="142" x2="270" y2="58" stroke="#4fffb0" stroke-width="1.5"/>
          <!-- Output Gate -->
          <rect x="400" y="100" width="50" height="30" rx="6" fill="#1e2330" stroke="#ff6b6b" stroke-width="1.5"/>
          <text x="425" y="120" text-anchor="middle" fill="#ff6b6b" font-size="11" font-family="monospace">o</text>
          <!-- tanh + output -->
          <circle cx="450" cy="40" r="14" fill="#1e2330" stroke="#a78bfa" stroke-width="1.5"/>
          <text x="450" y="45" text-anchor="middle" fill="#a78bfa" font-size="9" font-family="monospace">tanh</text>
          <circle cx="490" cy="155" r="13" fill="#1e2330" stroke="#ff6b6b" stroke-width="1.5"/>
          <text x="490" y="160" text-anchor="middle" fill="#ff6b6b" font-size="12" font-weight="bold">×</text>
          <line x1="450" y1="54" x2="450" y2="130" stroke="#a78bfa" stroke-width="1.5" stroke-dasharray="3,2"/>
          <line x1="450" y1="130" x2="490" y2="142" stroke="#a78bfa" stroke-width="1.5"/>
          <line x1="425" y1="130" x2="490" y2="142" stroke="#ff6b6b" stroke-width="1.5"/>
          <line x1="490" y1="168" x2="490" y2="174" stroke="#a78bfa" stroke-width="2"/>
          <line x1="490" y1="174" x2="570" y2="174" stroke="#a78bfa" stroke-width="2"/>
          <!-- Labels -->
          <text x="100" y="90" fill="#ffd93d" font-size="9" font-family="monospace">Forget</text>
          <text x="220" y="90" fill="#7b61ff" font-size="9" font-family="monospace">Input</text>
          <text x="290" y="90" fill="#4fffb0" font-size="9" font-family="monospace">Update</text>
          <text x="400" y="90" fill="#ff6b6b" font-size="9" font-family="monospace">Output</text>
        </svg>
      </div>
    </div>

    <!-- MATH -->
    <div class="tab-content" id="tc-lstm-math">
      <div class="math-block">
        <div class="math-label">Forget Gate</div>
        <div class="math-formula">$$\mathbf{f}^{(t)} = \sigma\!\left(\mathbf{W}_f\cdot[\mathbf{h}^{(t-1)},\,\mathbf{x}^{(t)}] + \mathbf{b}_f\right)$$</div>
        <div class="math-comment">// Entscheidet, was vergessen wird. σ → [0,1]</div>
      </div>
      <div class="math-block">
        <div class="math-label">Input Gate & Kandidaten</div>
        <div class="math-formula">
$$\mathbf{i}^{(t)} = \sigma\!\left(\mathbf{W}_i\cdot[\mathbf{h}^{(t-1)},\mathbf{x}^{(t)}]+\mathbf{b}_i\right)$$
$$\tilde{\mathbf{C}}^{(t)} = \tanh\!\left(\mathbf{W}_C\cdot[\mathbf{h}^{(t-1)},\mathbf{x}^{(t)}]+\mathbf{b}_C\right)$$
        </div>
        <div class="math-comment">// i: Wie viel? C̃: Welchen Inhalt?</div>
      </div>
      <div class="math-block">
        <div class="math-label">Cell State Update</div>
        <div class="math-formula">$$\mathbf{C}^{(t)} = \mathbf{f}^{(t)}\odot\mathbf{C}^{(t-1)} + \mathbf{i}^{(t)}\odot\tilde{\mathbf{C}}^{(t)}$$</div>
        <div class="math-comment">// ⊙ = element-wise Multiplikation (Hadamard-Produkt)
// Altes Gedächtnis × Vergessrate + Neue Info × Einlassrate</div>
      </div>
      <div class="math-block">
        <div class="math-label">Output Gate & Hidden State</div>
        <div class="math-formula">
$$\mathbf{o}^{(t)} = \sigma\!\left(\mathbf{W}_o\cdot[\mathbf{h}^{(t-1)},\mathbf{x}^{(t)}]+\mathbf{b}_o\right)$$
$$\mathbf{h}^{(t)} = \mathbf{o}^{(t)}\odot\tanh\!\left(\mathbf{C}^{(t)}\right)$$
        </div>
        <div class="math-comment">// h(t) ist die Ausgabe des LSTM-Cells</div>
      </div>
      <div class="card">
        <div class="card-title">Dimensionen (wichtig!)</div>
        <ul>
          <li>x(t) ∈ ℝ^d — Eingabe zum Zeitpunkt t (z.B. Embedding-Vektor)</li>
          <li>h(t), C(t) ∈ ℝ^h — Hidden und Cell State (hidden_size = h)</li>
          <li>W_f, W_i, W_C, W_o ∈ ℝ^(h × (h+d)) — Gewichtsmatrizen</li>
          <li>Gesamt Parameter: 4 × h × (h + d + 1) — faktor 4 wegen 4 Gates!</li>
        </ul>
      </div>
      <div class="highlight-box purple">
        🔑 <strong>Intuitiver Trick:</strong> Der Cell State C(t) ist eine "Autobahn" — die Gradienten können direkt hindurchfließen (additive Verbindung statt multiplikativer), was das Vanishing-Gradient-Problem mindert.
      </div>
    </div>

    <!-- IMPL -->
    <div class="tab-content" id="tc-lstm-impl">
      <div class="code-header"><span class="lang">Python · PyTorch</span><span>LSTM von Grund auf</span></div>
      <div class="code-wrap">
<pre><code class="language-python">import torch
import torch.nn as nn

# ── 1. PyTorch Built-in LSTM ─────────────────────────────────────
class TextClassifierLSTM(nn.Module):
    def __init__(self, vocab_size, embed_dim=64, hidden_size=128, num_classes=2):
        super().__init__()
        self.embedding = nn.Embedding(vocab_size, embed_dim)
        
        # batch_first=True → (batch, seq_len, features)
        self.lstm = nn.LSTM(
            input_size=embed_dim,
            hidden_size=hidden_size,
            num_layers=2,          # Gestapelte LSTMs
            batch_first=True,
            dropout=0.3,           # Zwischen den Layers
            bidirectional=False    # Alternativ: True für BiLSTM
        )
        self.classifier = nn.Linear(hidden_size, num_classes)
    
    def forward(self, x):
        # x: (batch, seq_len) → Token-IDs
        emb = self.embedding(x)       # (batch, seq_len, embed_dim)
        
        out, (h_n, c_n) = self.lstm(emb)
        # out: (batch, seq_len, hidden_size) — alle Zeitschritte
        # h_n: (num_layers, batch, hidden_size) — letzter Hidden State
        # c_n: (num_layers, batch, hidden_size) — letzter Cell State
        
        # Letzter Zeitschritt als Sequenzrepräsentation
        last = out[:, -1, :]          # (batch, hidden_size)
        return self.classifier(last)


# ── 2. LSTM Cell manuell (zum Verstehen!) ────────────────────────
class ManualLSTMCell(nn.Module):
    def __init__(self, input_size, hidden_size):
        super().__init__()
        self.hidden_size = hidden_size
        
        # Alle 4 Gates in EINER Matrix — effizienter!
        # W: (4*hidden_size, input_size + hidden_size)
        self.W = nn.Linear(input_size + hidden_size, 4 * hidden_size)
    
    def forward(self, x, h_prev, c_prev):
        # x:      (batch, input_size)
        # h_prev: (batch, hidden_size)
        # c_prev: (batch, hidden_size)
        
        combined = torch.cat([h_prev, x], dim=1)   # (batch, input+hidden)
        gates = self.W(combined)                    # (batch, 4*hidden)
        
        # Gates aufteilen
        f, i, g, o = gates.chunk(4, dim=1)
        
        f = torch.sigmoid(f)    # Forget Gate
        i = torch.sigmoid(i)    # Input Gate
        g = torch.tanh(g)       # Cell Kandidaten
        o = torch.sigmoid(o)    # Output Gate
        
        # Cell State Update
        c_next = f * c_prev + i * g
        h_next = o * torch.tanh(c_next)
        
        return h_next, c_next


# ── 3. Training Loop ─────────────────────────────────────────────
def train_step(model, optimizer, x_batch, y_batch):
    model.train()
    optimizer.zero_grad()
    
    logits = model(x_batch)
    loss = nn.CrossEntropyLoss()(logits, y_batch)
    loss.backward()
    
    # WICHTIG: Gradient Clipping gegen exploding gradients!
    torch.nn.utils.clip_grad_norm_(model.parameters(), max_norm=1.0)
    
    optimizer.step()
    return loss.item()

# Beispiel-Aufruf:
model = TextClassifierLSTM(vocab_size=10000)
optimizer = torch.optim.Adam(model.parameters(), lr=1e-3)
x = torch.randint(0, 10000, (32, 50))   # batch=32, seq_len=50
y = torch.randint(0, 2, (32,))
loss = train_step(model, optimizer, x, y)
print(f"Loss: {loss:.4f}")</code></pre>
      </div>
    </div>

    <!-- INTERAKTIV -->
    <div class="tab-content" id="tc-lstm-interaktiv">
      <div class="lstm-demo">
        <h4>🎛️ LSTM Gate Simulator — Stelle die Eingaben ein</h4>
        <div class="slider-row">
          <label>x(t) — Eingabe</label>
          <input type="range" min="-3" max="3" step="0.1" value="1.5" id="sl-x" oninput="updateGates()">
          <span class="slider-val" id="sv-x">1.5</span>
        </div>
        <div class="slider-row">
          <label>h(t-1) — Prev Hidden</label>
          <input type="range" min="-2" max="2" step="0.1" value="0.5" id="sl-h" oninput="updateGates()">
          <span class="slider-val" id="sv-h">0.5</span>
        </div>
        <div class="slider-row">
          <label>C(t-1) — Prev Cell</label>
          <input type="range" min="-3" max="3" step="0.1" value="1.0" id="sl-c" oninput="updateGates()">
          <span class="slider-val" id="sv-c">1.0</span>
        </div>
        <div class="gate-row" id="gate-display">
          <div class="gate-card">
            <div class="gate-name">Forget Gate f</div>
            <div class="gate-value" id="gv-f">0.82</div>
            <div class="gate-formula">σ(w·[h,x] + b)</div>
          </div>
          <div class="gate-card">
            <div class="gate-name">Input Gate i</div>
            <div class="gate-value" id="gv-i">0.73</div>
            <div class="gate-formula">σ(w·[h,x] + b)</div>
          </div>
          <div class="gate-card">
            <div class="gate-name">Cell Update g</div>
            <div class="gate-value" id="gv-g">0.91</div>
            <div class="gate-formula">tanh(w·[h,x] + b)</div>
          </div>
          <div class="gate-card" style="border-color:var(--accent3);">
            <div class="gate-name">New Cell C(t)</div>
            <div class="gate-value" id="gv-c" style="color:var(--accent3)">1.49</div>
            <div class="gate-formula">f·C(t-1) + i·g</div>
          </div>
        </div>
        <div id="gate-interpretation" class="highlight-box green" style="margin-top:1rem;font-size:0.75rem;">
          Das Forget Gate behält 82% des alten Gedächtnisses. 73% der neuen Information wird hinzugefügt.
        </div>
      </div>
    </div>

    <!-- QUIZ -->
    <div class="tab-content" id="tc-lstm-quiz">
      <div class="quiz-card">
        <div class="quiz-q">1. Warum verwendet LSTM zwei separate States (h und C), während ein normales RNN nur einen hat?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Um Langzeitinformationen (C) von der aktuellen Ausgabe (h) zu trennen und den Vanishing Gradient zu reduzieren</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Um doppelt so viele Parameter zu haben</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Weil das Training sonst nicht konvergiert</div>
        </div>
        <div class="quiz-feedback" id="qf1"></div>
      </div>
      <div class="quiz-card">
        <div class="quiz-q">2. Was bedeutet Forget Gate = 0 für einen bestimmten Neuron?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Das Neuron lernt nicht mehr</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Der entsprechende Cell State wird komplett auf 0 gesetzt (vollständig vergessen)</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Die Eingabe wird ignoriert</div>
        </div>
      </div>
      <div class="quiz-card">
        <div class="quiz-q">3. Wozu dient Gradient Clipping beim LSTM-Training?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Um den Vanishing Gradient zu beheben</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Um Overfitting zu verhindern</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Um explodierende Gradienten zu begrenzen, die zu instabilem Training führen</div>
        </div>
      </div>
    </div>
  </div>

  <!-- ===== SECTION 2: TRANSFORMER ===== -->
  <div class="section" id="transformer">
    <div class="section-header">
      <div class="section-num">02</div>
      <div>
        <div class="section-title">The <span class="accent">Transformer</span></div>
        <div class="section-subtitle">Attention Is All You Need — Vaswani et al., 2017</div>
      </div>
    </div>

    <div class="tabs" id="tabs-transformer">
      <div class="tab active" onclick="switchTab('transformer','theory')">Theorie</div>
      <div class="tab" onclick="switchTab('transformer','math')">Mathematik</div>
      <div class="tab" onclick="switchTab('transformer','impl')">Implementierung</div>
      <div class="tab" onclick="switchTab('transformer','interaktiv')">Interaktiv</div>
      <div class="tab" onclick="switchTab('transformer','quiz')">Quiz</div>
    </div>

    <div class="tab-content active" id="tc-transformer-theory">
      <div class="highlight-box red">
        🚀 Der Kern-Durchbruch: Transformer verarbeiten Sequenzen <strong>parallel</strong> — kein sequenzieller Rechenfluss wie bei LSTMs. Das macht massives Training möglich.
      </div>
      <div class="grid2">
        <div class="card">
          <div class="card-title">Self-Attention Intuition</div>
          <p>Jedes Token "schaut" auf alle anderen Tokens und entscheidet, wie relevant jedes für das eigene Verständnis ist. Der Satz "Die Bank am Fluss" — das Wort "Bank" schaut auf "Fluss" und erkennt: es geht um ein Ufer, nicht ein Finanzinstitut.</p>
        </div>
        <div class="card">
          <div class="card-title">Query, Key, Value</div>
          <p>Analog zu einer Datenbank: <strong style="color:#7b61ff">Query</strong> (Was suche ich?), <strong style="color:#4fffb0">Key</strong> (Was biete ich an?), <strong style="color:#ffd93d">Value</strong> (Was ist mein Inhalt?). Attention = Dot-Product zwischen Q und K, dann weighted sum über V.</p>
        </div>
      </div>
      <div class="card">
        <div class="card-title">Multi-Head Attention</div>
        <p>Statt einmal Attention zu berechnen, wird es h-mal parallel gemacht (z.B. h=8 Köpfe). Jeder Kopf lernt eine andere Art von Beziehung: Kopf 1 → syntaktische Abhängigkeiten, Kopf 2 → koreferenzielle Beziehungen, Kopf 3 → semantische Ähnlichkeit, etc. Die Ergebnisse werden konkateniert und linear projiziert.</p>
      </div>
      <div class="card">
        <div class="card-title">Positional Encoding</div>
        <p>Da Transformer keine Reihenfolge kennen (alles parallel), wird die Position explizit hinzugefügt. Die originale Arbeit nutzt Sinus/Cosinus-Funktionen verschiedener Frequenzen. Moderne Modelle verwenden Rotary Position Embeddings (RoPE) oder ALiBi.</p>
      </div>
      <div class="card">
        <div class="card-title">Feed-Forward + Residual + LayerNorm</div>
        <ul>
          <li>Nach jedem Attention-Block: 2-layer MLP (FFN) mit dimensionaler Erweiterung (typisch 4×)</li>
          <li>Residual Connections: x → x + Sublayer(x) — verhindert Vanishing Gradient in tiefen Netzen</li>
          <li>Layer Normalization: Normiert über die Feature-Dimension (nicht Batch wie BatchNorm)</li>
        </ul>
      </div>
    </div>

    <div class="tab-content" id="tc-transformer-math">
      <div class="math-block">
        <div class="math-label">Scaled Dot-Product Attention</div>
        <div class="math-formula">$$\text{Attention}(\mathbf{Q},\mathbf{K},\mathbf{V}) = \text{softmax}\!\left(\frac{\mathbf{Q}\mathbf{K}^\top}{\sqrt{d_k}}\right)\mathbf{V}$$</div>
        <div class="math-comment">// Q: (seq, d_k)  K: (seq, d_k)  V: (seq, d_v)
// Division durch √d_k verhindert zu große Dot-Products (Gradient-Stabilität)
// Ergebnis: (seq, d_v) — gewichtete Summe der Values</div>
      </div>
      <div class="math-block">
        <div class="math-label">Multi-Head Attention</div>
        <div class="math-formula">
$$\text{head}_i = \text{Attention}\!\left(\mathbf{Q}\mathbf{W}_i^Q,\;\mathbf{K}\mathbf{W}_i^K,\;\mathbf{V}\mathbf{W}_i^V\right)$$
$$\text{MultiHead}(\mathbf{Q},\mathbf{K},\mathbf{V}) = \text{Concat}(\text{head}_1,\ldots,\text{head}_h)\,\mathbf{W}^O$$
        </div>
        <div class="math-comment">// W_i^Q ∈ ℝ^(d_model × d_k)  mit d_k = d_model / h
// W^O ∈ ℝ^(h·d_v × d_model)</div>
      </div>
      <div class="math-block">
        <div class="math-label">Positional Encoding (original)</div>
        <div class="math-formula">
$$\text{PE}(\text{pos},2i) = \sin\!\left(\frac{\text{pos}}{10000^{2i/d_{\text{model}}}}\right), \qquad \text{PE}(\text{pos},2i+1) = \cos\!\left(\frac{\text{pos}}{10000^{2i/d_{\text{model}}}}\right)$$
        </div>
        <div class="math-comment">// pos: Position in der Sequenz, i: Dimension
// Addition zum Token-Embedding (nicht Konkatenation!)</div>
      </div>
      <div class="math-block">
        <div class="math-label">Transformer Block (Pre-LN Variante)</div>
        <div class="math-formula">
$$\mathbf{x}' = \mathbf{x} + \text{MultiHead}\!\left(\text{LayerNorm}(\mathbf{x})\right)$$
$$\mathbf{x}'' = \mathbf{x}' + \text{FFN}\!\left(\text{LayerNorm}(\mathbf{x}')\right)$$
        </div>
        <div class="math-comment">// Pre-LN: Stabiler als Post-LN, von modernen Modellen bevorzugt
// FFN(x) = max(0, x·W_1 + b_1)·W_2 + b_2  (GELU statt ReLU in GPT)</div>
      </div>
      <div class="highlight-box purple">
        📐 Komplexität: Self-Attention ist O(n²·d) — quadratisch in der Sequenzlänge! Das ist das Skalierungsproblem für sehr lange Kontexte. Lösungen: Sparse Attention, Flash Attention, Sliding Window.
      </div>
    </div>

    <div class="tab-content" id="tc-transformer-impl">
      <div class="code-header"><span class="lang">Python · PyTorch</span><span>Transformer von Scratch</span></div>
      <div class="code-wrap">
<pre><code class="language-python">import torch
import torch.nn as nn
import torch.nn.functional as F
import math

class MultiHeadAttention(nn.Module):
    def __init__(self, d_model, num_heads):
        super().__init__()
        assert d_model % num_heads == 0
        self.d_model = d_model
        self.h = num_heads
        self.d_k = d_model // num_heads
        
        # Alle Q, K, V Projektionen auf einmal
        self.qkv_proj = nn.Linear(d_model, 3 * d_model, bias=False)
        self.out_proj = nn.Linear(d_model, d_model)
        self.dropout = nn.Dropout(0.1)
    
    def forward(self, x, mask=None):
        B, T, C = x.shape  # batch, seq_len, d_model
        
        # Q, K, V projizieren und in Heads aufteilen
        qkv = self.qkv_proj(x)            # (B, T, 3*C)
        qkv = qkv.reshape(B, T, 3, self.h, self.d_k)
        qkv = qkv.permute(2, 0, 3, 1, 4)  # (3, B, h, T, d_k)
        Q, K, V = qkv.unbind(0)           # je (B, h, T, d_k)
        
        # Scaled Dot-Product Attention
        scale = math.sqrt(self.d_k)
        scores = Q @ K.transpose(-2, -1) / scale  # (B, h, T, T)
        
        if mask is not None:
            # Causal Mask für Decoder: zukünftige Tokens maskieren
            scores = scores.masked_fill(mask == 0, float('-inf'))
        
        attn_weights = F.softmax(scores, dim=-1)
        attn_weights = self.dropout(attn_weights)
        
        out = attn_weights @ V             # (B, h, T, d_k)
        out = out.transpose(1, 2).reshape(B, T, C)  # (B, T, C)
        return self.out_proj(out), attn_weights


class TransformerBlock(nn.Module):
    def __init__(self, d_model, num_heads, d_ff, dropout=0.1):
        super().__init__()
        self.attn = MultiHeadAttention(d_model, num_heads)
        self.ffn = nn.Sequential(
            nn.Linear(d_model, d_ff),
            nn.GELU(),                  # GELU statt ReLU (GPT-Style)
            nn.Dropout(dropout),
            nn.Linear(d_ff, d_model),
        )
        self.ln1 = nn.LayerNorm(d_model)
        self.ln2 = nn.LayerNorm(d_model)
        self.dropout = nn.Dropout(dropout)
    
    def forward(self, x, mask=None):
        # Pre-LN Residual Connections
        attn_out, weights = self.attn(self.ln1(x), mask)
        x = x + self.dropout(attn_out)
        x = x + self.dropout(self.ffn(self.ln2(x)))
        return x, weights


class GPTStyle(nn.Module):
    """Minimales Decoder-Only Transformer (GPT-ähnlich)"""
    def __init__(self, vocab_size, d_model=256, num_heads=8,
                 num_layers=4, max_len=512, dropout=0.1):
        super().__init__()
        self.token_emb = nn.Embedding(vocab_size, d_model)
        self.pos_emb = nn.Embedding(max_len, d_model)
        
        self.blocks = nn.ModuleList([
            TransformerBlock(d_model, num_heads, 4*d_model, dropout)
            for _ in range(num_layers)
        ])
        self.ln_final = nn.LayerNorm(d_model)
        self.head = nn.Linear(d_model, vocab_size, bias=False)
        
        # Weight Tying: Embedding & Output teilen Gewichte (GPT-2)
        self.head.weight = self.token_emb.weight
    
    def forward(self, idx):
        B, T = idx.shape
        pos = torch.arange(T, device=idx.device).unsqueeze(0)  # (1, T)
        
        x = self.token_emb(idx) + self.pos_emb(pos)   # (B, T, d_model)
        
        # Causal Mask: Token kann nur vorherige sehen
        mask = torch.tril(torch.ones(T, T, device=idx.device))
        
        for block in self.blocks:
            x, _ = block(x, mask)
        
        x = self.ln_final(x)
        logits = self.head(x)  # (B, T, vocab_size)
        return logits

# Mini-Modell erstellen:
model = GPTStyle(vocab_size=50257, d_model=128, num_heads=4, num_layers=2)
params = sum(p.numel() for p in model.parameters())
print(f"Parameter: {params:,}")  # ~5M
x = torch.randint(0, 50257, (2, 64))  # 2 Sequenzen, Länge 64
logits = model(x)
print(f"Output: {logits.shape}")  # (2, 64, 50257)</code></pre>
      </div>
    </div>

    <div class="tab-content" id="tc-transformer-interaktiv">
      <div class="card">
        <div class="card-title">Attention Heatmap Visualisierung</div>
        <p style="margin-bottom:1rem;font-size:0.8rem;color:var(--muted)">Simulierte Attention-Weights für einen Satz. Klicke auf ein Token um dessen Attention-Pattern zu sehen.</p>
        <div id="attn-viz"></div>
      </div>
    </div>

    <div class="tab-content" id="tc-transformer-quiz">
      <div class="quiz-card">
        <div class="quiz-q">1. Warum wird die Attention Score durch √d_k dividiert?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Um die Werte zwischen 0 und 1 zu halten</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Weil bei großem d_k die Dot-Products sehr groß werden, was Softmax in Regionen mit kleinen Gradienten drückt</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Um Overfitting zu verhindern</div>
        </div>
      </div>
      <div class="quiz-card">
        <div class="quiz-q">2. Was ist der Unterschied zwischen Encoder-Only, Decoder-Only und Encoder-Decoder Transformer?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Nur die Anzahl der Schichten unterscheidet sich</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Encoder-Only (BERT) sieht alles; Decoder-Only (GPT) hat Causal Mask; Encoder-Decoder (T5) für Seq2Seq Tasks</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Encoder verarbeitet Text, Decoder verarbeitet Bilder</div>
        </div>
      </div>
    </div>
  </div>

  <!-- ===== SECTION 3: LLM ===== -->
  <div class="section" id="llm">
    <div class="section-header">
      <div class="section-num">03</div>
      <div>
        <div class="section-title">Large Language <span class="accent">Models</span></div>
        <div class="section-subtitle">Pre-Training, Fine-Tuning, RLHF & Prompt Engineering</div>
      </div>
    </div>

    <div class="tabs" id="tabs-llm">
      <div class="tab active" onclick="switchTab('llm','theory')">Theorie</div>
      <div class="tab" onclick="switchTab('llm','math')">Mathematik</div>
      <div class="tab" onclick="switchTab('llm','impl')">Implementierung</div>
      <div class="tab" onclick="switchTab('llm','quiz')">Quiz</div>
    </div>

    <div class="tab-content active" id="tc-llm-theory">
      <div class="highlight-box green">
        💡 Ein LLM ist im Kern nichts anderes als ein Transformer, der trainiert wurde, das nächste Token vorherzusagen — aber in gigantischem Maßstab mit emergenten Fähigkeiten.
      </div>
      <div class="card">
        <div class="card-title">Scaling Laws (Chinchilla)</div>
        <p>Hoffmann et al. (2022) zeigten: Für optimales Training braucht ein Modell mit N Parametern etwa 20×N Tokens. GPT-3 (175B Parameter) war mit 300B Tokens unter-trainiert. LLaMA-2 7B wurde mit 2T Tokens trainiert — compute-optimal!</p>
      </div>
      <div class="grid2">
        <div class="card">
          <div class="card-title">Pre-Training</div>
          <ul>
            <li>Next-Token Prediction auf riesigen Web-Corpora (Common Crawl, Books, Code)</li>
            <li>Self-supervised: Label = nächstes Token im Text</li>
            <li>Emergente Fähigkeiten: Ab ~10B Parametern treten Fähigkeiten auf, die nicht direkt trainiert wurden</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-title">Fine-Tuning Pipeline</div>
          <ul>
            <li><strong style="color:#4fffb0">SFT</strong> — Supervised Fine-Tuning auf Instruction-Daten</li>
            <li><strong style="color:#7b61ff">RLHF</strong> — Reinforcement Learning from Human Feedback</li>
            <li><strong style="color:#ffd93d">DPO</strong> — Direct Preference Optimization (stabiler als RLHF)</li>
            <li><strong style="color:#ff6b6b">LoRA</strong> — Low-Rank Adaptation (parameter-effizient)</li>
          </ul>
        </div>
      </div>
      <div class="card">
        <div class="card-title">Tokenisierung</div>
        <p>LLMs arbeiten nicht mit Zeichen oder Wörtern, sondern mit <strong>Subword-Tokens</strong> (BPE — Byte-Pair Encoding). "unbelievable" → ["un", "believ", "able"]. GPT-4 hat ~100k Tokens. Das beeinflusst, wie das Modell "denkt" — häufige Wörter sind ein Token, seltene viele.</p>
      </div>
      <div class="card">
        <div class="card-title">Context Window & KV-Cache</div>
        <ul>
          <li>Context Window: Maximale Sequenzlänge (GPT-4: 128k Tokens, Gemini: 1M)</li>
          <li>KV-Cache: Beim Inference werden Key- und Value-Matrizen gecacht → kein re-compute bei Generation</li>
          <li>Speicherverbrauch KV-Cache: 2 × layers × heads × d_k × seq_len × 2 bytes (FP16)</li>
        </ul>
      </div>
    </div>

    <div class="tab-content" id="tc-llm-math">
      <div class="math-block">
        <div class="math-label">Language Model Objective (Next-Token Prediction)</div>
        <div class="math-formula">
$$\mathcal{L} = -\frac{1}{T}\sum_{t=1}^T \log P(x_t \mid x_1,\ldots,x_{t-1};\,\theta)$$
$$P(x_t\mid\text{context}) = \text{softmax}\!\left(\mathbf{h}_t\,\mathbf{W}_{\text{vocab}}+\mathbf{b}\right)[x_t]$$
        </div>
        <div class="math-comment">// Cross-Entropy Loss über alle Tokens
// h_t: Hidden State des letzten Transformer-Blocks
// W_vocab ∈ ℝ^(d_model × vocab_size)</div>
      </div>
      <div class="math-block">
        <div class="math-label">LoRA — Low-Rank Adaptation</div>
        <div class="math-formula">
$$\mathbf{W}' = \mathbf{W}_0 + \Delta\mathbf{W} = \mathbf{W}_0 + \mathbf{B}\mathbf{A}$$
$$\mathbf{A}\in\mathbb{R}^{r\times d_{\text{in}}},\quad\mathbf{B}\in\mathbb{R}^{d_{\text{out}}\times r},\quad r \ll d_{\text{in}}$$
$$\#\text{trainierbare Parameter} = r\,(d_{\text{in}}+d_{\text{out}}) \;\ll\; d_{\text{in}}\cdot d_{\text{out}}$$
        </div>
        <div class="math-comment">// Rank r=8 bei W ∈ ℝ^(4096 × 4096): 65.5k statt 16.8M Parameter!
// W₀ bleibt eingefroren — nur A und B werden trainiert</div>
      </div>
      <div class="math-block">
        <div class="math-label">Sampling Strategien</div>
        <div class="math-formula">
$$P'(x) = \text{softmax}\!\left(\frac{\text{logits}}{T}\right)$$
$$\text{Top-}k\text{:}\quad \text{behalte die } k \text{ wahrscheinlichsten Tokens}$$
$$\text{Top-}p\text{ (Nucleus):}\quad \text{kleinste Menge } \mathcal{S} \text{ mit } \sum_{x\in\mathcal{S}} P(x) \ge p$$
        </div>
        <div class="math-comment">// T→0: argmax (deterministisch), T→∞: uniform random
// Top-p=0.9: nutze Tokens, die zusammen 90% der Wahrscheinlichkeit ausmachen</div>
      </div>
    </div>

    <div class="tab-content" id="tc-llm-impl">
      <div class="code-header"><span class="lang">Python · HuggingFace + PEFT</span><span>LoRA Fine-Tuning</span></div>
      <div class="code-wrap">
<pre><code class="language-python">from transformers import AutoModelForCausalLM, AutoTokenizer, TrainingArguments
from peft import LoraConfig, get_peft_model, TaskType
from trl import SFTTrainer
import torch

# ── 1. Basis-Modell laden ─────────────────────────────────────────
model_name = "microsoft/phi-2"  # kleines, gutes Basis-Modell
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForCausalLM.from_pretrained(
    model_name,
    torch_dtype=torch.float16,
    device_map="auto",
)

# ── 2. LoRA Config ────────────────────────────────────────────────
lora_config = LoraConfig(
    task_type=TaskType.CAUSAL_LM,
    r=16,                          # Rank — höher = mehr Parameter
    lora_alpha=32,                 # Skalierung (α/r = effektive LR)
    lora_dropout=0.05,
    target_modules=["q_proj", "k_proj", "v_proj", "out_proj"],
    # Nur Attention-Matrizen mit LoRA anpassen
    bias="none",
)

model = get_peft_model(model, lora_config)
model.print_trainable_parameters()
# "trainable params: 2,097,152 || all params: 2,781,749,248 || 0.08%"

# ── 3. Training mit SFT Trainer ───────────────────────────────────
training_args = TrainingArguments(
    output_dir="./lora_output",
    num_train_epochs=3,
    per_device_train_batch_size=4,
    gradient_accumulation_steps=4,   # Effektive Batch Size = 16
    learning_rate=2e-4,
    fp16=True,
    logging_steps=10,
    save_strategy="epoch",
    warmup_ratio=0.03,
    lr_scheduler_type="cosine",
)

# Instruction-Format
def format_instruction(sample):
    return f"""### Instruction:
{sample['instruction']}

### Response:
{sample['output']}"""

trainer = SFTTrainer(
    model=model,
    tokenizer=tokenizer,
    args=training_args,
    train_dataset=train_dataset,    # dein HF-Dataset
    formatting_func=format_instruction,
    max_seq_length=512,
)
trainer.train()

# ── 4. Inference mit Temperature Sampling ─────────────────────────
def generate(prompt, max_new_tokens=200, temperature=0.7, top_p=0.9):
    inputs = tokenizer(prompt, return_tensors="pt").to("cuda")
    with torch.no_grad():
        output = model.generate(
            **inputs,
            max_new_tokens=max_new_tokens,
            temperature=temperature,
            top_p=top_p,
            do_sample=True,
            repetition_penalty=1.1,
        )
    return tokenizer.decode(output[0], skip_special_tokens=True)

print(generate("### Instruction:\nErkläre Transformers einfach.\n\n### Response:"))</code></pre>
      </div>
    </div>

    <div class="tab-content" id="tc-llm-quiz">
      <div class="quiz-card">
        <div class="quiz-q">1. Was bedeutet "Chinchilla Optimal" beim LLM-Training?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Das Modell wurde in China trainiert</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Die Balance zwischen Modellgröße und Training-Tokens ist optimal: ~20 Tokens pro Parameter</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Das Modell hat weniger als 10B Parameter</div>
        </div>
      </div>
      <div class="quiz-card">
        <div class="quiz-q">2. Warum ist LoRA so effizient? Was wird tatsächlich trainiert?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Es trainiert nur die letzten Schichten des Modells</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Zwei kleine Matrizen A und B mit niedrigem Rang r, deren Produkt die Gewichtsänderung approximiert</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Es komprimiert das Modell durch Quantisierung</div>
        </div>
      </div>
    </div>
  </div>

  <!-- ===== SECTION 4: VECTOR DB ===== -->
  <div class="section" id="vectordb">
    <div class="section-header">
      <div class="section-num">04</div>
      <div>
        <div class="section-title">Vektor<span class="accent">datenbanken</span></div>
        <div class="section-subtitle">Semantische Suche mit Embeddings & ANN-Algorithmen</div>
      </div>
    </div>

    <div class="tabs" id="tabs-vectordb">
      <div class="tab active" onclick="switchTab('vectordb','theory')">Theorie</div>
      <div class="tab" onclick="switchTab('vectordb','math')">Mathematik</div>
      <div class="tab" onclick="switchTab('vectordb','impl')">Implementierung</div>
      <div class="tab" onclick="switchTab('vectordb','interaktiv')">Interaktiv</div>
      <div class="tab" onclick="switchTab('vectordb','quiz')">Quiz</div>
    </div>

    <div class="tab-content active" id="tc-vectordb-theory">
      <div class="highlight-box yellow">
        🗄️ Vektordatenbanken speichern keine Zeilen & Spalten, sondern hochdimensionale Vektoren und erlauben extrem schnelle semantische Ähnlichkeitssuche — das Fundament von RAG.
      </div>
      <div class="card">
        <div class="card-title">Embeddings — Text zu Vektoren</div>
        <p>Embedding-Modelle (BERT, text-embedding-ada-002, E5) transformieren Text in dichte Vektoren (typisch 768–1536 Dimensionen). Ähnlicher Text → ähnliche Vektoren → kleiner Abstand im Vektorraum. "König - Mann + Frau ≈ Königin" — das klassische Beispiel für semantische Arithmetik.</p>
      </div>
      <div class="grid2">
        <div class="card">
          <div class="card-title">Das Problem: Exact KNN</div>
          <p>Brute-Force k-Nearest-Neighbor über eine Million Vektoren à 768 Dimensionen: jede Suche braucht ~1M Dot-Products. Bei Millisekunden-Anforderungen unmöglich.</p>
        </div>
        <div class="card">
          <div class="card-title">Lösung: ANN Algorithmen</div>
          <ul>
            <li><strong style="color:#4fffb0">HNSW</strong> — Hierarchical Navigable Small World (Graphbasiert, default in den meisten DBs)</li>
            <li><strong style="color:#7b61ff">IVF</strong> — Inverted File Index (Clustering)</li>
            <li><strong style="color:#ffd93d">LSH</strong> — Locality Sensitive Hashing</li>
            <li><strong style="color:#ff6b6b">PQ</strong> — Product Quantization (Kompression)</li>
          </ul>
        </div>
      </div>
      <div class="card">
        <div class="card-title">HNSW — Hierarchical Navigable Small World</div>
        <p>Baut einen mehrschichtigen Graphen: obere Schichten sind dünn (schnelle Navigation), untere Schichten sind dicht (präzise Suche). Ähnlich wie eine Autobahn mit Auf- und Abfahrten. Suche beginnt oben, navigiert greedy zum nächsten Nachbarn und steigt in feinere Schichten ab. Recall ~99% bei 100x Speedup gegenüber Brute-Force.</p>
      </div>
      <div class="card">
        <div class="card-title">Beliebte Vektordatenbanken</div>
        <ul>
          <li><strong style="color:#4fffb0">Chroma</strong> — Einfach, lokal, perfekt zum Lernen & Prototyping</li>
          <li><strong style="color:#7b61ff">Pinecone</strong> — Managed Cloud, einfache API, teuer bei Scale</li>
          <li><strong style="color:#ffd93d">Weaviate</strong> — Open Source, GraphQL API, mit Hybrid Search</li>
          <li><strong style="color:#ff6b6b">Qdrant</strong> — Rust-basiert, sehr performant, gute Filter-Unterstützung</li>
          <li><strong>pgvector</strong> — PostgreSQL Extension, wenn du schon Postgres nutzt</li>
        </ul>
      </div>
    </div>

    <div class="tab-content" id="tc-vectordb-math">
      <div class="math-block">
        <div class="math-label">Cosine Similarity (häufigste Metrik für Embeddings)</div>
        <div class="math-formula">
$$\cos(\mathbf{A},\mathbf{B}) = \frac{\mathbf{A}\cdot\mathbf{B}}{\|\mathbf{A}\|\,\|\mathbf{B}\|} = \frac{\displaystyle\sum_i a_i b_i}{\displaystyle\sqrt{\sum_i a_i^2}\;\sqrt{\sum_i b_i^2}}$$
        </div>
        <div class="math-comment">// cos ∈ [-1, 1]: 1 = identisch, 0 = orthogonal, -1 = entgegengesetzt
// Normalisierte Vektoren: cos(A,B) = A·B (Dot Product reicht!)</div>
      </div>
      <div class="math-block">
        <div class="math-label">Weitere Distanzmaße</div>
        <div class="math-formula">
$$d_{\text{eukl.}}(\mathbf{A},\mathbf{B}) = \sqrt{\sum_i (a_i - b_i)^2}$$
$$d_{\text{Manhattan}}(\mathbf{A},\mathbf{B}) = \sum_i |a_i - b_i|$$
$$\text{Dot Product:}\quad s(\mathbf{A},\mathbf{B}) = \mathbf{A}\cdot\mathbf{B} \quad\text{(wenn Magnitude relevant)}$$
        </div>
        <div class="math-comment">// Für normalisierte Embeddings: Cosine ≡ Dot Product ≡ Euklidisch (monoton)
// Dot Product beachtet auch die Magnitude → für unnormalisierte Embeddings</div>
      </div>
      <div class="math-block">
        <div class="math-label">IVF — Inverted File Index</div>
        <div class="math-formula">
$$1.\;\text{k-Means: } n_{\text{clusters}}\text{ Centroids } \mathbf{c}_1,\ldots,\mathbf{c}_k$$
$$2.\;\text{Für Query }\mathbf{q}\text{: finde die } n_{\text{probe}} \text{ nächsten Centroids}$$
$$3.\;\text{Suche nur in diesen Clustern} \;\Rightarrow\; \mathcal{O}\!\left(\frac{n}{k}\right) \text{ statt } \mathcal{O}(n)$$
        </div>
        <div class="math-comment">// n_clusters = √N (Faustregel), n_probe = Tradeoff Recall vs Speed</div>
      </div>
    </div>

    <div class="tab-content" id="tc-vectordb-impl">
      <div class="code-header"><span class="lang">Python · ChromaDB + Sentence-Transformers</span><span>Vollständiges Beispiel</span></div>
      <div class="code-wrap">
<pre><code class="language-python">from sentence_transformers import SentenceTransformer
import chromadb
import numpy as np

# ── 1. Embedding Modell laden ─────────────────────────────────────
model = SentenceTransformer('intfloat/multilingual-e5-large')
# Kostengünstige Alternative: 'all-MiniLM-L6-v2' (384 dim, schnell)

# ── 2. ChromaDB initialisieren ────────────────────────────────────
client = chromadb.PersistentClient(path="./chroma_db")
collection = client.get_or_create_collection(
    name="knowledge_base",
    metadata={"hnsw:space": "cosine"}  # Distanzmetrik
)

# ── 3. Dokumente einbetten und speichern ──────────────────────────
documents = [
    "LSTMs verwenden Gates um selektiv Informationen zu speichern.",
    "Transformer nutzen Self-Attention statt Rekurrenz.",
    "RAG kombiniert Retrieval mit generativen Modellen.",
    "Vektordatenbanken ermöglichen semantische Ähnlichkeitssuche.",
    "Embeddings sind dichte Repräsentationen von Text.",
    "HNSW ist ein graphbasierter ANN-Algorithmus.",
]

# Wichtig: E5 Modelle brauchen Prefix "passage: " beim Indexieren
prefixed_docs = [f"passage: {d}" for d in documents]
embeddings = model.encode(prefixed_docs, normalize_embeddings=True)

collection.add(
    documents=documents,
    embeddings=embeddings.tolist(),
    ids=[f"doc_{i}" for i in range(len(documents))],
    metadatas=[{"topic": "ml", "source": "lernzettel"}] * len(documents)
)

# ── 4. Semantische Suche ──────────────────────────────────────────
def semantic_search(query, k=3):
    # Query mit "query: " prefix (E5-spezifisch)
    query_emb = model.encode(f"query: {query}", normalize_embeddings=True)
    
    results = collection.query(
        query_embeddings=[query_emb.tolist()],
        n_results=k,
        where={"topic": "ml"},          # Metadata Filter!
        include=["documents", "distances", "metadatas"]
    )
    
    print(f"\nQuery: '{query}'")
    print("-" * 50)
    for doc, dist in zip(results['documents'][0], results['distances'][0]):
        similarity = 1 - dist  # ChromaDB gibt cosine distance zurück
        print(f"[{similarity:.3f}] {doc}")
    
    return results

semantic_search("Wie funktioniert selektives Gedächtnis?")
# → [0.847] LSTMs verwenden Gates um selektiv Informationen zu speichern.
# → [0.623] Transformer nutzen Self-Attention statt Rekurrenz.

# ── 5. Manueller HNSW mit FAISS ───────────────────────────────────
import faiss

dim = 384
index = faiss.IndexHNSWFlat(dim, 32)  # 32 = Verbindungen pro Knoten
index.hnsw.efConstruction = 200        # Qualität beim Aufbau
index.hnsw.efSearch = 50               # Qualität bei der Suche

# Vektoren hinzufügen
vecs = np.random.rand(10000, dim).astype('float32')
faiss.normalize_L2(vecs)  # Für Cosine Similarity normalisieren
index.add(vecs)

# Suche
query = np.random.rand(1, dim).astype('float32')
faiss.normalize_L2(query)
D, I = index.search(query, k=5)  # D: Distanzen, I: Indices
print(f"Nächste Nachbarn: {I[0]}")
print(f"Ähnlichkeiten: {1 - D[0]}")  # cosine distance → similarity</code></pre>
      </div>
    </div>

    <div class="tab-content" id="tc-vectordb-interaktiv">
      <div class="card">
        <div class="card-title">2D Vektor-Ähnlichkeit Visualisierung</div>
        <p style="margin-bottom:1rem;font-size:0.8rem;color:var(--muted)">Klicke auf den Canvas, um einen Query-Punkt zu setzen. Die nächsten Nachbarn werden hervorgehoben.</p>
        <canvas id="vecCanvas" width="560" height="320" style="width:100%;cursor:crosshair;background:#0d1117;border:1px solid var(--border);border-radius:8px;"></canvas>
        <div id="vecInfo" style="margin-top:0.8rem;font-size:0.75rem;color:var(--muted);"></div>
      </div>
    </div>

    <div class="tab-content" id="tc-vectordb-quiz">
      <div class="quiz-card">
        <div class="quiz-q">1. Warum ist Cosine Similarity oft besser als euklidische Distanz für Text-Embeddings?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Cosine ist immer genauer als euklidische Distanz</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Cosine misst den Winkel und ignoriert die Magnitude — ein kurzer und langer Text über dasselbe Thema haben ähnliche Richtungen, aber unterschiedliche Längen</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Cosine-Berechnung ist schneller</div>
        </div>
      </div>
      <div class="quiz-card">
        <div class="quiz-q">2. Was bedeutet der "ef"-Parameter in HNSW?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Die Anzahl der Dimensionen der Vektoren</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Die Kompressionsrate der Vektoren</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Die Größe der dynamischen Kandidatenliste während der Suche — höher = besserer Recall, aber langsamer</div>
        </div>
      </div>
    </div>
  </div>

  <!-- ===== SECTION 5: RAG ===== -->
  <div class="section" id="rag">
    <div class="section-header">
      <div class="section-num">05</div>
      <div>
        <div class="section-title">Retrieval-Augmented <span class="accent">Generation</span></div>
        <div class="section-subtitle">Kombiniere Wissensdatenbanken mit generativen LLMs</div>
      </div>
    </div>

    <div class="tabs" id="tabs-rag">
      <div class="tab active" onclick="switchTab('rag','theory')">Theorie</div>
      <div class="tab" onclick="switchTab('rag','math')">Mathematik</div>
      <div class="tab" onclick="switchTab('rag','impl')">Implementierung</div>
      <div class="tab" onclick="switchTab('rag','quiz')">Quiz</div>
    </div>

    <div class="tab-content active" id="tc-rag-theory">
      <div class="highlight-box green">
        🔍 Das Problem mit reinen LLMs: Sie halluzinieren, ihr Wissen ist auf den Training-Cutoff begrenzt, und sie kennen deine privaten Daten nicht. RAG löst das — elegant.
      </div>
      <div class="card">
        <div class="card-title">Das RAG-Prinzip</div>
        <p>Statt alles Wissen ins Modell zu packen (teures Fine-Tuning), wird die relevante Information zur Laufzeit aus einer externen Datenbank abgerufen und als Kontext an das LLM übergeben. Retrieve → Augment → Generate.</p>
      </div>
      <div class="card">
        <div class="card-title">RAG Pipeline Schritt für Schritt</div>
        <ul>
          <li><strong style="color:#4fffb0">1. Indexierung (offline)</strong> — Dokumente chunken, einbetten, in Vektordatenbank speichern</li>
          <li><strong style="color:#7b61ff">2. Retrieval</strong> — User-Query einbetten, top-k ähnliche Chunks suchen</li>
          <li><strong style="color:#ffd93d">3. Augmentation</strong> — Chunks in System-Prompt einfügen als Kontext</li>
          <li><strong style="color:#ff6b6b">4. Generation</strong> — LLM antwortet basierend auf abgerufenem Kontext</li>
        </ul>
      </div>
      <div class="grid2">
        <div class="card">
          <div class="card-title">Chunking Strategien</div>
          <ul>
            <li>Fixed Size (500 Tokens, 50 Overlap)</li>
            <li>Semantic Chunking (Satzbedeutung)</li>
            <li>Recursive Character Splitter</li>
            <li>Document-Aware (Markdown-Abschnitte)</li>
          </ul>
        </div>
        <div class="card">
          <div class="card-title">Fortgeschrittene RAG Techniken</div>
          <ul>
            <li><strong>HyDE</strong> — Hypothetisches Dokument generieren und suchen</li>
            <li><strong>Reranking</strong> — Cross-Encoder für präziseres Ranking</li>
            <li><strong>Hybrid Search</strong> — BM25 + Vektorsuche kombinieren</li>
            <li><strong>RAG-Fusion</strong> — Multiple Queries, dann fusionieren</li>
          </ul>
        </div>
      </div>
      <div class="diagram">
        <svg width="580" height="130" viewBox="0 0 580 130">
          <!-- Boxes -->
          <rect x="10" y="40" width="80" height="50" rx="8" fill="#1e2330" stroke="#4fffb0" stroke-width="1.5"/>
          <text x="50" y="61" text-anchor="middle" fill="#4fffb0" font-size="9" font-family="monospace">User</text>
          <text x="50" y="75" text-anchor="middle" fill="#4fffb0" font-size="9" font-family="monospace">Query</text>
          
          <rect x="120" y="40" width="90" height="50" rx="8" fill="#1e2330" stroke="#7b61ff" stroke-width="1.5"/>
          <text x="165" y="61" text-anchor="middle" fill="#7b61ff" font-size="9" font-family="monospace">Embedding</text>
          <text x="165" y="75" text-anchor="middle" fill="#7b61ff" font-size="9" font-family="monospace">Model</text>
          
          <rect x="240" y="15" width="90" height="100" rx="8" fill="#1e2330" stroke="#ffd93d" stroke-width="1.5"/>
          <text x="285" y="45" text-anchor="middle" fill="#ffd93d" font-size="9" font-family="monospace">Vector</text>
          <text x="285" y="59" text-anchor="middle" fill="#ffd93d" font-size="9" font-family="monospace">Database</text>
          <text x="285" y="77" text-anchor="middle" fill="#6b7280" font-size="8" font-family="monospace">top-k chunks</text>
          <text x="285" y="91" text-anchor="middle" fill="#6b7280" font-size="8" font-family="monospace">retrieved</text>
          
          <rect x="360" y="40" width="90" height="50" rx="8" fill="#1e2330" stroke="#ff6b6b" stroke-width="1.5"/>
          <text x="405" y="61" text-anchor="middle" fill="#ff6b6b" font-size="9" font-family="monospace">Context</text>
          <text x="405" y="75" text-anchor="middle" fill="#ff6b6b" font-size="9" font-family="monospace">+ Prompt</text>
          
          <rect x="480" y="40" width="90" height="50" rx="8" fill="#1e2330" stroke="#a78bfa" stroke-width="1.5"/>
          <text x="525" y="61" text-anchor="middle" fill="#a78bfa" font-size="9" font-family="monospace">LLM</text>
          <text x="525" y="75" text-anchor="middle" fill="#a78bfa" font-size="9" font-family="monospace">Answer</text>
          
          <!-- Arrows -->
          <line x1="90" y1="65" x2="118" y2="65" stroke="#6b7280" stroke-width="1.5" marker-end="url(#arr)"/>
          <line x1="210" y1="65" x2="238" y2="65" stroke="#6b7280" stroke-width="1.5" marker-end="url(#arr)"/>
          <line x1="330" y1="65" x2="358" y2="65" stroke="#6b7280" stroke-width="1.5" marker-end="url(#arr)"/>
          <line x1="450" y1="65" x2="478" y2="65" stroke="#6b7280" stroke-width="1.5" marker-end="url(#arr)"/>
          
          <defs>
            <marker id="arr" markerWidth="8" markerHeight="6" refX="8" refY="3" orient="auto">
              <polygon points="0 0, 8 3, 0 6" fill="#6b7280"/>
            </marker>
          </defs>
          
          <!-- Labels -->
          <text x="50" y="110" text-anchor="middle" fill="#4fffb0" font-size="8" font-family="monospace">1. Input</text>
          <text x="165" y="110" text-anchor="middle" fill="#7b61ff" font-size="8" font-family="monospace">2. Embed</text>
          <text x="285" y="125" text-anchor="middle" fill="#ffd93d" font-size="8" font-family="monospace">3. Retrieve</text>
          <text x="405" y="110" text-anchor="middle" fill="#ff6b6b" font-size="8" font-family="monospace">4. Augment</text>
          <text x="525" y="110" text-anchor="middle" fill="#a78bfa" font-size="8" font-family="monospace">5. Generate</text>
        </svg>
      </div>
    </div>

    <div class="tab-content" id="tc-rag-math">
      <div class="math-block">
        <div class="math-label">RAG Wahrscheinlichkeitsformulierung (Lewis et al., 2020)</div>
        <div class="math-formula">
$$p(y\mid x) = \sum_z p_\eta(z\mid x)\cdot p_\theta(y\mid x,z)$$
$$p_\eta(z\mid x) = \text{top-}k\text{ Retrieval:}\quad \text{score}(z,x) = \mathbf{E}(x)\cdot\mathbf{E}(z)$$
        </div>
        <div class="math-comment">// x: Query, z: retrieved document, y: generierte Antwort
// p_η: Retrieval-Modell, p_θ: Generator (LLM)
// Marginalisierung über alle retrieved docs</div>
      </div>
      <div class="math-block">
        <div class="math-label">BM25 (Hybrid Search Komponente)</div>
        <div class="math-formula">
$$\text{BM25}(q,d) = \sum_{t\in q} \text{IDF}(t)\cdot\frac{\text{tf}(t,d)\cdot(k_1+1)}{\text{tf}(t,d)+k_1\!\left(1-b+b\,\dfrac{|d|}{\text{avgdl}}\right)}$$
$$\text{IDF}(t) = \log\frac{N - \text{df}(t) + 0.5}{\text{df}(t)+0.5}$$
        </div>
        <div class="math-comment">// k=1.2, b=0.75 (typische Defaults)
// Hybrid: final_score = α·dense_score + (1-α)·sparse_score</div>
      </div>
      <div class="math-block">
        <div class="math-label">Reciprocal Rank Fusion (RAG-Fusion)</div>
        <div class="math-formula">$$\text{RRF}(d) = \sum_{q} \frac{1}{k + \text{rank}_q(d)}, \qquad k=60\text{ (typisch)}$$</div>
        <div class="math-comment">// Kombiniert Rankings aus mehreren Retrieval-Strategien
// Robust gegen Ausreißer, benötigt keine Normalisierung</div>
      </div>
    </div>

    <div class="tab-content" id="tc-rag-impl">
      <div class="code-header"><span class="lang">Python · LangChain + ChromaDB + OpenAI</span><span>Vollständiges RAG System</span></div>
      <div class="code-wrap">
<pre><code class="language-python">from langchain.text_splitter import RecursiveCharacterTextSplitter
from langchain_community.document_loaders import DirectoryLoader
from langchain_community.vectorstores import Chroma
from langchain_community.embeddings import HuggingFaceEmbeddings
from langchain.chains import RetrievalQA
from langchain_openai import ChatOpenAI
from langchain.prompts import PromptTemplate

# ── 1. INDEXIERUNG (einmalig / bei Update) ────────────────────────

# Dokumente laden (PDF, MD, TXT, etc.)
loader = DirectoryLoader('./docs/', glob="**/*.md")
raw_docs = loader.load()

# Chunking: Rekursiv mit Overlap für Kontext
splitter = RecursiveCharacterTextSplitter(
    chunk_size=512,
    chunk_overlap=64,          # Overlap verhindert Kontext-Verlust
    separators=["\n\n", "\n", ".", "!", "?", " "],
    length_function=len,
)
chunks = splitter.split_documents(raw_docs)
print(f"{len(raw_docs)} Dokumente → {len(chunks)} Chunks")

# Embedding & Speicherung
embeddings = HuggingFaceEmbeddings(
    model_name="intfloat/multilingual-e5-large",
    model_kwargs={'device': 'cuda'},
    encode_kwargs={'normalize_embeddings': True}
)

vectordb = Chroma.from_documents(
    documents=chunks,
    embedding=embeddings,
    persist_directory="./chroma_store",
    collection_metadata={"hnsw:space": "cosine"}
)
vectordb.persist()


# ── 2. RAG CHAIN ──────────────────────────────────────────────────

# Custom Prompt Template — sehr wichtig!
RAG_PROMPT = PromptTemplate(
    template="""Du bist ein hilfreicher Assistent. Beantworte die Frage NUR 
basierend auf dem bereitgestellten Kontext. Wenn die Antwort nicht im Kontext 
steht, sage das klar und deutlich.

Kontext:
{context}

Frage: {question}

Antwort:""",
    input_variables=["context", "question"]
)

# Retriever konfigurieren
retriever = vectordb.as_retriever(
    search_type="mmr",        # Maximum Marginal Relevance: Diversity!
    search_kwargs={
        "k": 5,               # Anzahl der Chunks
        "fetch_k": 20,        # MMR: aus 20 kandidieren, 5 auswählen
        "lambda_mult": 0.5    # MMR: 0=Diversity, 1=Relevance
    }
)

# LLM (kann auch lokales Ollama sein)
llm = ChatOpenAI(model="gpt-4o-mini", temperature=0.1)

# RAG Chain zusammenbauen
qa_chain = RetrievalQA.from_chain_type(
    llm=llm,
    chain_type="stuff",       # Alle Chunks in einem Prompt
    retriever=retriever,
    chain_type_kwargs={"prompt": RAG_PROMPT},
    return_source_documents=True,
)


# ── 3. ANFRAGEN ───────────────────────────────────────────────────

def ask(question):
    result = qa_chain.invoke({"query": question})
    
    print(f"\n❓ {question}")
    print(f"\n💬 {result['result']}")
    print("\n📄 Quellen:")
    for doc in result['source_documents']:
        print(f"  → {doc.metadata.get('source', 'unbekannt')} "
              f"(Chunk: {doc.metadata.get('chunk', '?')})")
    return result

ask("Wie unterscheiden sich LSTMs von Transformern?")


# ── 4. ERWEITERT: Hybrid Search (BM25 + Dense) ───────────────────
from langchain.retrievers import BM25Retriever, EnsembleRetriever

# BM25 (Keyword-basiert)
bm25_retriever = BM25Retriever.from_documents(chunks)
bm25_retriever.k = 5

# Ensemble: BM25 + Dense Retrieval
ensemble_retriever = EnsembleRetriever(
    retrievers=[bm25_retriever, retriever],
    weights=[0.3, 0.7],       # 30% BM25, 70% semantisch
)
# Ersetze retriever durch ensemble_retriever in der Chain</code></pre>
      </div>
    </div>

    <div class="tab-content" id="tc-rag-quiz">
      <div class="quiz-card">
        <div class="quiz-q">1. Was ist der Unterschied zwischen RAG und Fine-Tuning, um einem LLM neues Wissen beizubringen?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Es gibt keinen Unterschied, beide haben dieselbe Qualität</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">RAG fügt Wissen dynamisch zur Inferenz hinzu (kein Re-Training nötig, aktualisierbar), Fine-Tuning backt es in die Gewichte (teuer, statisch, kann halluzinieren)</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Fine-Tuning ist immer besser, nur teurer</div>
        </div>
      </div>
      <div class="quiz-card">
        <div class="quiz-q">2. Was ist Maximum Marginal Relevance (MMR) beim Retrieval?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Eine Methode zur Verbesserung des Embeddings</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Eine Strategie, die Relevanz UND Diversität der abgerufenen Chunks balanciert — verhindert, dass alle Chunks dasselbe sagen</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Eine Art von Reranking mit einem separaten Modell</div>
        </div>
      </div>
      <div class="quiz-card">
        <div class="quiz-q">3. Warum ist Chunk-Overlap beim Text-Splitting wichtig?</div>
        <div class="quiz-options">
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Um mehr Chunks zu erstellen und den Index zu vergrößern</div>
          <div class="quiz-opt" onclick="checkQuiz(this, false)">Overlap verbessert die Embedding-Qualität</div>
          <div class="quiz-opt" onclick="checkQuiz(this, true)">Damit Informationen, die an Chunk-Grenzen stehen, nicht verloren gehen — der Kontext bleibt über Chunk-Grenzen hinweg erhalten</div>
        </div>
      </div>
    </div>
  </div>

  <footer>
    <div style="margin-bottom:0.5rem">ML Lernpfad · B.Sc. Informatik · Interaktive Lernzettel</div>
    <div>LSTM → Transformer → LLM → Vektordatenbanken → RAG</div>
  </footer>
</main>
</div>

<script>
// ── INIT ──────────────────────────────────────────────────────────
document.addEventListener('DOMContentLoaded', () => {
  hljs.highlightAll();
  initAttentionViz();
  initVecViz();
  updateGates();
  trackProgress();
  drawDB();
  drawActivations();
});

// ── TAB SWITCHING ─────────────────────────────────────────────────
function switchTab(section, tabName) {
  const tabs = document.querySelectorAll(`#tabs-${section} .tab`);
  const tabContents = document.querySelectorAll(`[id^="tc-${section}-"]`);
  
  tabContents.forEach(tc => tc.classList.remove('active'));
  tabs.forEach(t => t.classList.remove('active'));
  
  document.getElementById(`tc-${section}-${tabName}`).classList.add('active');
  event.target.classList.add('active');
  
  updateProgress(section, tabName);
  // Re-typeset LaTeX in the newly visible tab (safe guard)
  if (window.MathJax && MathJax.typesetPromise) {
    MathJax.typesetPromise([document.getElementById(`tc-${section}-${tabName}`)]).catch(() => {});
  }
}

// ── PROGRESS TRACKING ─────────────────────────────────────────────
const sectionProgress = { grundlagen: 0, lstm: 0, transformer: 0, llm: 0, vectordb: 0, rag: 0 };
const sectionMap = { grundlagen: 0, lstm: 1, transformer: 2, llm: 3, vectordb: 4, rag: 5 };
const tabCounts = { grundlagen: 5, lstm: 5, transformer: 5, llm: 4, vectordb: 5, rag: 4 };
// Track which tabs have already been visited per section
const visitedTabs = { grundlagen: new Set(), lstm: new Set(), transformer: new Set(), llm: new Set(), vectordb: new Set(), rag: new Set() };

function updateProgress(section, tabName) {
  if (!tabName || visitedTabs[section].has(tabName)) return; // already visited → no change
  visitedTabs[section].add(tabName);
  const total = tabCounts[section];
  sectionProgress[section] = Math.round((visitedTabs[section].size / total) * 100);
  const n = sectionMap[section];
  document.getElementById(`prog${n}`).textContent = sectionProgress[section] + '%';
  document.getElementById(`pf${n}`).style.width = sectionProgress[section] + '%';
}

function trackProgress() {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        const section = e.target.id;
        if (sectionMap.hasOwnProperty(section)) {
          updateProgress(section, 'theory'); // count landing on section as visiting theory tab
        }
      }
    });
  }, { threshold: 0.3 });
  
  ['grundlagen','lstm','transformer','llm','vectordb','rag'].forEach(id => {
    const el = document.getElementById(id);
    if (el) observer.observe(el);
  });
}

// ── NAV ───────────────────────────────────────────────────────────
function sideNav(el) {
  document.querySelectorAll('.sidebar-item').forEach(i => i.classList.remove('active'));
  el.classList.add('active');
}

function jumpTo(id) {
  document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
}

// Sync sidebar on scroll
window.addEventListener('scroll', () => {
  const sections = ['grundlagen','lstm','transformer','llm','vectordb','rag'];
  const scrollY = window.scrollY + 120;
  
  for (let id of sections) {
    const el = document.getElementById(id);
    if (el && el.offsetTop <= scrollY) {
      document.querySelectorAll('.sidebar-item').forEach(i => i.classList.remove('active'));
      const sideItem = document.querySelector(`.sidebar-item[href="#${id}"]`);
      if (sideItem) sideItem.classList.add('active');
      
      document.querySelectorAll('.nav-pill').forEach(p => p.classList.remove('active'));
      const navPill = document.querySelector(`.nav-pill[href="#${id}"]`);
      if (navPill) navPill.classList.add('active');
    }
  }
});

// ── QUIZ ──────────────────────────────────────────────────────────
function checkQuiz(el, correct) {
  const parent = el.closest('.quiz-options');
  if (parent.querySelector('.correct, .wrong')) return; // already answered
  
  el.classList.add(correct ? 'correct' : 'wrong');
  
  if (!correct) {
    parent.querySelectorAll('[onclick*="true"]').forEach(opt => {
      opt.classList.add('correct');
    });
  }
  
  const feedback = el.closest('.quiz-card').querySelector('.quiz-feedback');
  if (feedback) {
    feedback.textContent = correct
      ? '✓ Richtig! Gut gemacht.'
      : '✗ Nicht ganz — die richtige Antwort ist grün markiert.';
    feedback.style.color = correct ? 'var(--accent)' : 'var(--accent3)';
  }
}

// ── LSTM GATE SIMULATOR ───────────────────────────────────────────
function sigmoid(x) { return 1 / (1 + Math.exp(-x)); }
function tanh(x) { return Math.tanh(x); }

function updateGates() {
  const x = parseFloat(document.getElementById('sl-x').value);
  const h = parseFloat(document.getElementById('sl-h').value);
  const c = parseFloat(document.getElementById('sl-c').value);
  
  document.getElementById('sv-x').textContent = x.toFixed(1);
  document.getElementById('sv-h').textContent = h.toFixed(1);
  document.getElementById('sv-c').textContent = c.toFixed(1);
  
  // Feste Gewichte für Demo
  const f = sigmoid(0.4*x + 0.6*h + 0.3);
  const i = sigmoid(0.5*x + 0.3*h - 0.2);
  const g = tanh(0.7*x + 0.4*h + 0.1);
  const o = sigmoid(0.3*x + 0.8*h + 0.5);
  const c_new = f * c + i * g;
  const h_new = o * tanh(c_new);
  
  document.getElementById('gv-f').textContent = f.toFixed(3);
  document.getElementById('gv-i').textContent = i.toFixed(3);
  document.getElementById('gv-g').textContent = g.toFixed(3);
  document.getElementById('gv-c').textContent = c_new.toFixed(3);
  
  const retained = (f * 100).toFixed(0);
  const added = (i * 100).toFixed(0);
  const info = document.getElementById('gate-interpretation');
  info.textContent = `Das Forget Gate behält ${retained}% des alten Gedächtnisses (C=${c.toFixed(1)}). ${added}% der neuen Information (g=${g.toFixed(2)}) wird hinzugefügt. Neues C(t) = ${c_new.toFixed(3)}, h(t) = ${h_new.toFixed(3)}`;
}

// ── ATTENTION VISUALIZATION ───────────────────────────────────────
function initAttentionViz() {
  const container = document.getElementById('attn-viz');
  if (!container) return;
  
  const tokens = ['Die', 'Bank', 'am', 'Fluss', 'ist', 'schön'];
  const n = tokens.length;
  
  // Simulierte Attention Weights (normalisiert)
  const attentions = [
    [0.6, 0.1, 0.05, 0.1, 0.1, 0.05],
    [0.05, 0.3, 0.05, 0.4, 0.1, 0.1],  // Bank -> Fluss
    [0.1, 0.1, 0.5, 0.1, 0.1, 0.1],
    [0.05, 0.35, 0.05, 0.4, 0.1, 0.05],
    [0.1, 0.1, 0.1, 0.1, 0.5, 0.1],
    [0.1, 0.1, 0.05, 0.1, 0.15, 0.5],
  ];
  
  let selectedRow = 1; // Bank ist standardmäßig ausgewählt
  
  function render() {
    const cellSize = 52;
    const totalW = n * cellSize + 80;
    container.innerHTML = `
      <div style="display:flex;align-items:flex-start;gap:1rem;flex-wrap:wrap;">
        <div>
          <div style="font-size:0.65rem;color:var(--muted);margin-bottom:0.5rem;text-transform:uppercase;letter-spacing:0.1em;">Query Token (Zeile klicken)</div>
          <div style="display:grid;grid-template-columns:repeat(${n},${cellSize}px);gap:2px;">
            ${attentions.map((row, ri) => 
              row.map((val, ci) => {
                const alpha = selectedRow === ri ? val : val * 0.3;
                const bg = selectedRow === ri 
                  ? `rgba(79,255,176,${Math.pow(val, 0.5)})` 
                  : `rgba(79,255,176,${val * 0.2})`;
                return `<div class="att-cell" style="width:${cellSize}px;height:${cellSize}px;background:${bg};border-radius:4px;" 
                  onclick="selectRow(${ri})" title="attn: ${val.toFixed(2)}">
                  ${val > 0.2 ? (val*100).toFixed(0)+'%' : ''}
                </div>`;
              }).join('')
            ).join('')}
          </div>
          <div style="display:grid;grid-template-columns:repeat(${n},${cellSize}px);gap:2px;margin-top:4px;">
            ${tokens.map(t => `<div class="att-token" style="width:${cellSize}px;text-align:center;">${t}</div>`).join('')}
          </div>
        </div>
        <div style="min-width:160px;">
          <div style="font-size:0.65rem;color:var(--muted);text-transform:uppercase;letter-spacing:0.1em;margin-bottom:0.5rem;">Attention von "${tokens[selectedRow]}"</div>
          ${tokens.map((t, i) => {
            const v = attentions[selectedRow][i];
            return `<div style="display:flex;align-items:center;gap:0.5rem;margin:0.3rem 0;">
              <div style="width:50px;font-size:0.68rem;color:var(--muted);">${t}</div>
              <div style="flex:1;height:16px;background:var(--border);border-radius:3px;overflow:hidden;">
                <div style="height:100%;width:${v*100}%;background:rgba(79,255,176,${0.4+v*0.6});transition:width 0.3s;"></div>
              </div>
              <div style="width:38px;font-size:0.68rem;color:var(--accent);text-align:right;">${(v*100).toFixed(0)}%</div>
            </div>`;
          }).join('')}
          <div style="margin-top:0.8rem;font-size:0.72rem;color:var(--muted);line-height:1.6;">
            ${selectedRow === 1 ? '💡 "Bank" schaut stark auf "Fluss" → erkennt die Bedeutung!' : `"${tokens[selectedRow]}" und sein Attention-Muster`}
          </div>
        </div>
      </div>
    `;
  }
  
  window.selectRow = function(ri) {
    selectedRow = ri;
    render();
  };
  
  render();
}

// ── VECTOR VISUALIZATION ──────────────────────────────────────────
function initVecViz() {
  const canvas = document.getElementById('vecCanvas');
  if (!canvas) return;
  const ctx = canvas.getContext('2d');
  
  const W = canvas.width, H = canvas.height;
  const colors = ['#4fffb0','#7b61ff','#ff6b6b','#ffd93d','#60a5fa','#f472b6','#34d399','#fb923c'];
  const labels = ['LSTM','Transformer','LLM','Vector DB','CNN','RNN','BERT','GPT'];
  
  // Fixed positions for demo
  const points = [
    {x: 120, y: 100, label: 'LSTM', color: colors[0]},
    {x: 300, y: 80, label: 'Transformer', color: colors[1]},
    {x: 360, y: 140, label: 'LLM', color: colors[2]},
    {x: 430, y: 220, label: 'Vector DB', color: colors[3]},
    {x: 80, y: 200, label: 'CNN', color: colors[4]},
    {x: 150, y: 160, label: 'RNN', color: colors[5]},
    {x: 260, y: 190, label: 'BERT', color: colors[6]},
    {x: 390, y: 90, label: 'GPT', color: colors[7]},
  ];
  
  let query = null;
  
  function drawScene() {
    ctx.clearRect(0, 0, W, H);
    
    // Grid
    ctx.strokeStyle = 'rgba(79,255,176,0.05)';
    ctx.lineWidth = 1;
    for (let x = 0; x < W; x += 40) { ctx.beginPath(); ctx.moveTo(x,0); ctx.lineTo(x,H); ctx.stroke(); }
    for (let y = 0; y < H; y += 40) { ctx.beginPath(); ctx.moveTo(0,y); ctx.lineTo(W,y); ctx.stroke(); }
    
    // If query: draw distances and highlight nearest
    let sorted = [];
    if (query) {
      sorted = points.map(p => {
        const d = Math.sqrt((p.x-query.x)**2 + (p.y-query.y)**2);
        return {...p, dist: d};
      }).sort((a,b) => a.dist - b.dist);
      
      // Draw connection lines to nearest 3
      sorted.slice(0,3).forEach((p, i) => {
        ctx.beginPath();
        ctx.moveTo(query.x, query.y);
        ctx.lineTo(p.x, p.y);
        ctx.strokeStyle = `rgba(79,255,176,${0.6 - i*0.15})`;
        ctx.lineWidth = 2 - i*0.4;
        ctx.setLineDash([4, 4]);
        ctx.stroke();
        ctx.setLineDash([]);
      });
    }
    
    // Draw points
    points.forEach((p, idx) => {
      const isNearest = query && sorted.slice(0,3).some(s => s.label === p.label);
      const size = isNearest ? 10 : 7;
      
      ctx.beginPath();
      ctx.arc(p.x, p.y, size, 0, Math.PI*2);
      ctx.fillStyle = p.color + (isNearest ? 'ff' : '88');
      ctx.fill();
      
      if (isNearest) {
        ctx.beginPath();
        ctx.arc(p.x, p.y, size + 4, 0, Math.PI*2);
        ctx.strokeStyle = p.color;
        ctx.lineWidth = 1.5;
        ctx.stroke();
      }
      
      ctx.fillStyle = isNearest ? p.color : 'rgba(200,200,200,0.6)';
      ctx.font = `${isNearest ? 'bold ' : ''}11px JetBrains Mono, monospace`;
      ctx.fillText(p.label, p.x + 13, p.y + 4);
    });
    
    // Draw query
    if (query) {
      ctx.beginPath();
      ctx.arc(query.x, query.y, 9, 0, Math.PI*2);
      ctx.fillStyle = '#fff';
      ctx.fill();
      ctx.beginPath();
      ctx.arc(query.x, query.y, 9, 0, Math.PI*2);
      ctx.strokeStyle = '#fff';
      ctx.lineWidth = 2;
      ctx.stroke();
      
      // Pulsing ring
      ctx.beginPath();
      ctx.arc(query.x, query.y, 16, 0, Math.PI*2);
      ctx.strokeStyle = 'rgba(255,255,255,0.3)';
      ctx.lineWidth = 1;
      ctx.stroke();
      
      ctx.fillStyle = '#fff';
      ctx.font = 'bold 10px monospace';
      ctx.fillText('Query', query.x + 13, query.y + 4);
      
      // Info
      const info = document.getElementById('vecInfo');
      if (info && sorted.length) {
        info.innerHTML = `<span style="color:var(--accent)">Nächste Nachbarn:</span> ${sorted.slice(0,3).map((p,i) => 
          `<span style="color:${p.color}">${p.label}</span> (d=${p.dist.toFixed(0)}px)`
        ).join(' → ')}`;
      }
    }
  }
  
  canvas.addEventListener('click', e => {
    const rect = canvas.getBoundingClientRect();
    const scaleX = canvas.width / rect.width;
    const scaleY = canvas.height / rect.height;
    query = {
      x: (e.clientX - rect.left) * scaleX,
      y: (e.clientY - rect.top) * scaleY,
    };
    drawScene();
  });
  
  drawScene();
} // end initVecViz

// ── GRUNDLAGEN SUB-NAV ────────────────────────────────────────────
function showGSub(id) {
  document.querySelectorAll('.gsub-content').forEach(el => el.style.display = 'none');
  document.getElementById('gsub-' + id).style.display = 'block';
  document.querySelectorAll('.g-sub').forEach(btn => {
    btn.style.background = 'transparent';
    btn.style.borderColor = 'var(--border)';
    btn.style.color = 'var(--muted)';
    btn.classList.remove('active');
  });
  const active = document.querySelector(`.g-sub[onclick*="${id}"]`);
  if (active) {
    active.style.background = 'rgba(79,255,176,0.08)';
    active.style.borderColor = 'rgba(79,255,176,0.4)';
    active.style.color = 'var(--accent)';
    active.classList.add('active');
  }
}

// ── DECISION BOUNDARY VIZ ─────────────────────────────────────────
let dbModel = 'logreg', dbDataset = 'linear';
const W = 560, H = 340;

function setModel(m) {
  dbModel = m;
  document.querySelectorAll('[id^="btn-logreg"],[id^="btn-perceptron"],[id^="btn-fnn"]').forEach(b => b.classList.remove('active'));
  document.getElementById('btn-' + m).classList.add('active');
  drawDB();
}
function setDataset(d) {
  dbDataset = d;
  document.querySelectorAll('[id^="btn-linear"],[id^="btn-xor"],[id^="btn-circles"]').forEach(b => b.classList.remove('active'));
  document.getElementById('btn-' + d).classList.add('active');
  drawDB();
}

function generateData(type, n = 60) {
  const pts = [];
  if (type === 'linear') {
    for (let i = 0; i < n; i++) {
      const x = Math.random() * 2 - 1, y = Math.random() * 2 - 1;
      pts.push({ x, y, label: (y > 0.4 * x + 0.1 + (Math.random() - 0.5) * 0.3) ? 1 : 0 });
    }
  } else if (type === 'xor') {
    for (let i = 0; i < n; i++) {
      const x = Math.random() * 2 - 1, y = Math.random() * 2 - 1;
      pts.push({ x, y, label: ((x > 0) !== (y > 0)) ? 1 : 0 });
    }
  } else if (type === 'circles') {
    for (let i = 0; i < n; i++) {
      const angle = Math.random() * 2 * Math.PI;
      const r = (i < n/2) ? 0.4 + Math.random() * 0.15 : 0.75 + Math.random() * 0.2;
      pts.push({ x: r * Math.cos(angle), y: r * Math.sin(angle), label: i < n/2 ? 1 : 0 });
    }
  }
  return pts;
}

// Simple logistic boundary (analytical approximation for viz)
function logRegBoundary(x, pts) {
  // Approximate learned weights via gradient steps
  let w0 = 0.1, w1 = 0.1, b = 0;
  const lr = 0.5;
  for (let iter = 0; iter < 200; iter++) {
    let dw0 = 0, dw1 = 0, db = 0;
    for (const p of pts) {
      const z = w0*p.x + w1*p.y + b;
      const pred = 1 / (1 + Math.exp(-z));
      const err = pred - p.label;
      dw0 += err * p.x; dw1 += err * p.y; db += err;
    }
    w0 -= lr * dw0 / pts.length;
    w1 -= lr * dw1 / pts.length;
    b  -= lr * db  / pts.length;
  }
  return (xi, yi) => 1 / (1 + Math.exp(-(w0*xi + w1*yi + b)));
}

function fnnBoundary(pts) {
  // Tiny 2-layer network (2→8→1) trained with simple gradient steps
  let W1 = Array.from({length: 8}, () => [Math.random()-0.5, Math.random()-0.5]);
  let b1 = Array.from({length: 8}, () => 0);
  let W2 = Array.from({length: 8}, () => Math.random()-0.5);
  let b2 = 0;
  const sigmoid = z => 1 / (1 + Math.exp(-Math.max(-20, Math.min(20, z))));
  const relu = z => Math.max(0, z);

  for (let iter = 0; iter < 500; iter++) {
    let dW2 = new Array(8).fill(0), db2 = 0;
    let dW1 = W1.map(() => [0,0]), db1 = new Array(8).fill(0);

    for (const p of pts) {
      // Forward
      const h = W1.map((w, i) => relu(w[0]*p.x + w[1]*p.y + b1[i]));
      const out = sigmoid(h.reduce((s, hi, i) => s + W2[i]*hi, b2));
      const err = out - p.label;

      // Backward
      const dout = err;
      db2 += dout;
      h.forEach((hi, i) => { dW2[i] += dout * hi; });
      h.forEach((hi, i) => {
        const dh = dout * W2[i] * (hi > 0 ? 1 : 0);
        dW1[i][0] += dh * p.x; dW1[i][1] += dh * p.y; db1[i] += dh;
      });
    }
    const n = pts.length, lr = 0.08;
    W2 = W2.map((w, i) => w - lr * dW2[i] / n);
    b2 -= lr * db2 / n;
    W1 = W1.map((w, i) => [w[0] - lr * dW1[i][0]/n, w[1] - lr * dW1[i][1]/n]);
    b1 = b1.map((b, i) => b - lr * db1[i]/n);
  }

  return (xi, yi) => {
    const h = W1.map((w, i) => relu(w[0]*xi + w[1]*yi + b1[i]));
    return sigmoid(h.reduce((s, hi, i) => s + W2[i]*hi, b2));
  };
}

function perceptronBoundary(pts) {
  let w = [0.1, 0.1], b = 0;
  for (let iter = 0; iter < 300; iter++) {
    for (const p of pts) {
      const z = w[0]*p.x + w[1]*p.y + b;
      const pred = z >= 0 ? 1 : 0;
      const err = p.label - pred;
      if (err !== 0) { w[0] += 0.1*err*p.x; w[1] += 0.1*err*p.y; b += 0.1*err; }
    }
  }
  return (xi, yi) => (w[0]*xi + w[1]*yi + b >= 0 ? 0.9 : 0.1);
}

let cachedPts = null, cachedDataset = null;

function drawDB() {
  const canvas = document.getElementById('dbCanvas');
  if (!canvas) return;
  const ctx = canvas.getContext('2d');
  const CW = canvas.width, CH = canvas.height;

  if (cachedDataset !== dbDataset) { cachedPts = generateData(dbDataset); cachedDataset = dbDataset; }
  const pts = cachedPts;

  // Train boundary function
  let boundaryFn;
  if (dbModel === 'logreg') boundaryFn = logRegBoundary(null, pts);
  else if (dbModel === 'perceptron') boundaryFn = perceptronBoundary(pts);
  else boundaryFn = fnnBoundary(pts);

  // Draw background
  ctx.clearRect(0, 0, CW, CH);
  const toCanvas = (x, y) => [(x + 1.2) / 2.4 * CW, (1 - (y + 1.2) / 2.4) * CH];

  // Decision boundary heatmap (coarse grid for speed)
  const step = 8;
  for (let px = 0; px < CW; px += step) {
    for (let py = 0; py < CH; py += step) {
      const xi = (px / CW) * 2.4 - 1.2;
      const yi = (1 - py / CH) * 2.4 - 1.2;
      const p = boundaryFn(xi, yi);
      ctx.fillStyle = p > 0.5
        ? `rgba(79,255,176,${0.07 + (p-0.5)*0.25})`
        : `rgba(123,97,255,${0.07 + (0.5-p)*0.25})`;
      ctx.fillRect(px, py, step+1, step+1);
    }
  }

  // Axes
  const [ox, oy] = toCanvas(0, 0);
  ctx.strokeStyle = 'rgba(255,255,255,0.12)';
  ctx.lineWidth = 1;
  ctx.beginPath(); ctx.moveTo(0, oy); ctx.lineTo(CW, oy); ctx.stroke();
  ctx.beginPath(); ctx.moveTo(ox, 0); ctx.lineTo(ox, CH); ctx.stroke();

  // Data points
  for (const p of pts) {
    const [cx, cy] = toCanvas(p.x, p.y);
    ctx.beginPath(); ctx.arc(cx, cy, 5, 0, Math.PI*2);
    ctx.fillStyle = p.label === 1 ? '#4fffb0' : '#7b61ff';
    ctx.fill();
    ctx.strokeStyle = 'rgba(0,0,0,0.5)'; ctx.lineWidth = 1; ctx.stroke();
  }

  // Model info
  const info = document.getElementById('dbInfo');
  const descriptions = {
    logreg: { linear: '✓ Logistische Regression findet die optimale lineare Grenze.', xor: '✗ Logistische Regression kann XOR nicht lösen — es ist nicht linear separierbar!', circles: '✗ Kreise können nicht durch eine Linie getrennt werden — LinReg/LogReg versagen hier.' },
    perceptron: { linear: '✓ Das Perceptron konvergiert auf linear separierbaren Daten.', xor: '✗ Perceptron Konvergenz-Theorem versagt: XOR ist nicht linear separierbar.', circles: '✗ Perceptron kann diese nicht-lineare Grenze nicht lernen.' },
    fnn: { linear: '✓ FNN lernt die lineare Grenze (überparametrisiert, aber es funktioniert).', xor: '✓ FNN mit einer Hidden Layer kann XOR perfekt lösen — non-linear!', circles: '✓ FNN lernt eine kurvenförmige Grenze für das Kreise-Problem.' },
  };
  if (info) info.textContent = descriptions[dbModel]?.[dbDataset] || '';
}

// ── AKTIVIERUNGSFUNKTIONEN ─────────────────────────────────────────
function drawActivations() {
  const canvas = document.getElementById('actCanvas');
  if (!canvas) return;
  const ctx = canvas.getContext('2d');
  const CW = canvas.width, CH = canvas.height;

  ctx.clearRect(0, 0, CW, CH);

  const funcs = [
    { name: 'ReLU',    color: '#4fffb0', fn: x => Math.max(0, x) },
    { name: 'Sigmoid', color: '#7b61ff', fn: x => 1/(1+Math.exp(-x)) },
    { name: 'Tanh',    color: '#ffd93d', fn: x => Math.tanh(x) },
    { name: 'GELU',    color: '#ff6b6b', fn: x => 0.5*x*(1+Math.tanh(Math.sqrt(2/Math.PI)*(x+0.044715*x**3))) },
  ];

  const xMin = -4, xMax = 4, yMin = -1.2, yMax = 1.2;
  const toC = (x, y) => [(x - xMin) / (xMax - xMin) * CW, (1 - (y - yMin) / (yMax - yMin)) * CH];

  // Grid
  ctx.strokeStyle = 'rgba(255,255,255,0.05)'; ctx.lineWidth = 1;
  for (let x = xMin; x <= xMax; x++) {
    const [cx] = toC(x, 0); ctx.beginPath(); ctx.moveTo(cx, 0); ctx.lineTo(cx, CH); ctx.stroke();
  }
  for (let y = -1; y <= 1; y += 0.5) {
    const [, cy] = toC(0, y); ctx.beginPath(); ctx.moveTo(0, cy); ctx.lineTo(CW, cy); ctx.stroke();
  }

  // Axes
  ctx.strokeStyle = 'rgba(255,255,255,0.2)'; ctx.lineWidth = 1.5;
  const [ox, oy] = toC(0, 0);
  ctx.beginPath(); ctx.moveTo(0, oy); ctx.lineTo(CW, oy); ctx.stroke();
  ctx.beginPath(); ctx.moveTo(ox, 0); ctx.lineTo(ox, CH); ctx.stroke();

  // Functions
  for (const { fn, color } of funcs) {
    ctx.beginPath(); ctx.strokeStyle = color; ctx.lineWidth = 2.5;
    for (let px = 0; px < CW; px++) {
      const x = xMin + (px / CW) * (xMax - xMin);
      const y = fn(x);
      const [cx, cy] = toC(x, y);
      px === 0 ? ctx.moveTo(cx, cy) : ctx.lineTo(cx, cy);
    }
    ctx.stroke();
  }
}

</script>
</body>
</html>
