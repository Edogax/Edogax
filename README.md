
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>0xnotkyo — Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Rajdhani:wght@400;600;700&family=Orbitron:wght@400;700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0c0f;
    --bg2: #0e1117;
    --panel: #111520;
    --border: #1e2d40;
    --accent: #00d4ff;
    --accent2: #ff3c6e;
    --accent3: #7fff6e;
    --text: #c8d8e8;
    --dim: #4a6070;
    --glow: 0 0 18px rgba(0,212,255,0.35);
    --glow2: 0 0 18px rgba(255,60,110,0.3);
  }
 
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
 
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Rajdhani', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }
 
  /* Scanline overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(
      to bottom,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.07) 2px,
      rgba(0,0,0,0.07) 4px
    );
    pointer-events: none;
    z-index: 9999;
  }
 
  /* Grid background */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }
 
  .container {
    position: relative;
    z-index: 1;
    max-width: 860px;
    margin: 0 auto;
    padding: 48px 24px;
  }
 
  /* ── HEADER ── */
  .header {
    text-align: center;
    margin-bottom: 48px;
    animation: fadeDown 0.8s ease both;
  }
 
  .header h1 {
    font-family: 'Orbitron', monospace;
    font-size: clamp(2rem, 5vw, 3.4rem);
    font-weight: 900;
    letter-spacing: 0.06em;
    color: #fff;
    text-shadow: var(--glow);
  }
 
  .header h1 span { color: var(--accent); }
 
  .header .subtitle {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.8rem;
    color: var(--dim);
    margin-top: 6px;
    letter-spacing: 0.15em;
  }
 
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--accent), var(--accent2), transparent);
    margin: 20px 0;
    opacity: 0.6;
  }
 
  .badges {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    margin-top: 18px;
  }
 
  .badge {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.72rem;
    padding: 5px 14px;
    border: 1px solid var(--accent);
    color: var(--accent);
    background: rgba(0,212,255,0.06);
    letter-spacing: 0.08em;
    clip-path: polygon(8px 0%, 100% 0%, calc(100% - 8px) 100%, 0% 100%);
    transition: all 0.3s;
    cursor: default;
  }
 
  .badge:hover {
    background: rgba(0,212,255,0.18);
    box-shadow: var(--glow);
    transform: translateY(-2px);
  }
 
  .badge.red  { border-color: var(--accent2); color: var(--accent2); background: rgba(255,60,110,0.06); }
  .badge.red:hover { background: rgba(255,60,110,0.15); box-shadow: var(--glow2); }
  .badge.green { border-color: var(--accent3); color: var(--accent3); background: rgba(127,255,110,0.06); }
 
  /* ── SECTION ── */
  .section {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 32px;
    margin-bottom: 28px;
    position: relative;
    overflow: hidden;
    animation: fadeUp 0.7s ease both;
  }
 
  .section::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
  }
 
  .section-title {
    font-family: 'Orbitron', monospace;
    font-size: 1.05rem;
    font-weight: 700;
    color: #fff;
    letter-spacing: 0.1em;
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
 
  .section-title .icon { font-size: 1.1rem; }
 
  /* ── ABOUT ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 28px;
    align-items: start;
  }
 
  .about-text p {
    font-size: 1rem;
    line-height: 1.7;
    color: var(--text);
    margin-bottom: 20px;
  }
 
  .about-text p em {
    font-style: normal;
    color: var(--accent);
    font-weight: 700;
  }
 
  .about-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
 
  .about-list li {
    font-size: 0.95rem;
    display: flex;
    align-items: flex-start;
    gap: 10px;
    color: var(--text);
  }
 
  .about-list li .bullet {
    color: var(--accent);
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.85rem;
    margin-top: 2px;
    flex-shrink: 0;
  }
 
  .avatar-wrapper {
    width: 130px;
    flex-shrink: 0;
  }
 
  .avatar-frame {
    width: 130px;
    height: 130px;
    border: 2px solid var(--accent);
    box-shadow: var(--glow), inset 0 0 20px rgba(0,212,255,0.08);
    overflow: hidden;
    clip-path: polygon(12px 0%, 100% 0%, 100% calc(100% - 12px), calc(100% - 12px) 100%, 0% 100%, 0% 12px);
    background: var(--bg2);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 3.5rem;
  }
 
  /* ── SKILLS ── */
  .skills-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }
 
  .skill-tag {
    display: flex;
    align-items: center;
    gap: 7px;
    padding: 8px 14px;
    border: 1px solid var(--border);
    background: var(--bg2);
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.78rem;
    letter-spacing: 0.06em;
    color: var(--dim);
    clip-path: polygon(6px 0%, 100% 0%, calc(100% - 6px) 100%, 0% 100%);
    transition: all 0.3s;
    cursor: default;
  }
 
  .skill-tag:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(0,212,255,0.06);
    transform: translateY(-2px);
    box-shadow: var(--glow);
  }
 
  .skill-tag .dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent3);
    flex-shrink: 0;
  }
 
  /* ── STATS ── */
  .stats-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 20px 24px;
    display: flex;
    align-items: center;
    gap: 20px;
    max-width: 420px;
    margin: 0 auto;
    position: relative;
    overflow: hidden;
  }
 
  .stats-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(0,212,255,0.04), transparent 60%);
    pointer-events: none;
  }
 
  .stats-avatar {
    width: 54px; height: 54px;
    border-radius: 50%;
    border: 2px solid var(--accent);
    background: var(--bg);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.6rem;
    flex-shrink: 0;
    box-shadow: var(--glow);
  }
 
  .stats-info { flex: 1; }
 
  .stats-name {
    font-family: 'Orbitron', monospace;
    font-size: 1rem;
    font-weight: 700;
    color: #fff;
  }
 
  .stats-name span { color: var(--accent); }
 
  .stats-meta {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.7rem;
    color: var(--dim);
    margin-top: 3px;
    letter-spacing: 0.05em;
  }
 
  .stats-row {
    display: flex;
    gap: 18px;
    margin-top: 12px;
    flex-wrap: wrap;
  }
 
  .stat-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2px;
  }
 
  .stat-val {
    font-family: 'Orbitron', monospace;
    font-size: 1rem;
    font-weight: 700;
    color: var(--accent);
  }
 
  .stat-label {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.62rem;
    color: var(--dim);
    letter-spacing: 0.06em;
  }
 
  .thm-badge {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.68rem;
    color: var(--accent3);
    border: 1px solid var(--accent3);
    padding: 2px 8px;
    opacity: 0.8;
    flex-shrink: 0;
    align-self: flex-start;
  }
 
  /* ── TERMINAL PROMPT ── */
  .terminal-line {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.8rem;
    color: var(--dim);
    margin-top: 40px;
    text-align: center;
    letter-spacing: 0.05em;
  }
 
  .terminal-line span { color: var(--accent); }
  .terminal-line .cursor {
    display: inline-block;
    width: 8px; height: 14px;
    background: var(--accent);
    animation: blink 1s step-end infinite;
    vertical-align: middle;
    margin-left: 3px;
  }
 
  /* ── ANIMATIONS ── */
  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-24px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes blink {
    0%, 100% { opacity: 1; }
    50%       { opacity: 0; }
  }
 
  .section:nth-child(2) { animation-delay: 0.15s; }
  .section:nth-child(3) { animation-delay: 0.28s; }
  .section:nth-child(4) { animation-delay: 0.40s; }
 
  @media (max-width: 560px) {
    .about-grid { grid-template-columns: 1fr; }
    .avatar-wrapper { margin: 0 auto; }
    .section { padding: 22px 16px; }
    .stats-row { gap: 12px; }
  }
</style>
</head>
<body>
<div class="container">
 
  <!-- HEADER -->
  <header class="header">
    <h1>Welcome to <span>my profile</span></h1>
    <p class="subtitle">// README.md — 0xnotkyo</p>
    <div class="divider"></div>
    <div class="badges">
      <span class="badge">Cybersecurity Student</span>
      <span class="badge">Penetration Tester</span>
      <span class="badge red">Red Team</span>
      <span class="badge green">CTF Player</span>
    </div>
  </header>
 
  <!-- ABOUT -->
  <section class="section">
    <h2 class="section-title"><span class="icon">👤</span> About me</h2>
    <div class="about-grid">
      <div class="about-text">
        <p>
          Hello There! <em>I'm Najwa aka 0xnotkyo</em>, a Cybersecurity student. I enjoy learning new
          technologies and problem solving at HackTheBox and TryHackMe. Now I'm working on some
          little and fun projects while documenting my knowledge and journey on my Gitbook.
        </p>
        <ul class="about-list">
          <li><span class="bullet">&gt;_</span> Self-taught Cybersecurity Student</li>
          <li><span class="bullet">&gt;_</span> Passionate about Penetration Testing &amp; Web App Hacking</li>
          <li><span class="bullet">&gt;_</span> Focusing on Offensive Development</li>
          <li><span class="bullet">&gt;_</span> Interested in Malware Dev, Bug Bounty &amp; CTFs</li>
        </ul>
      </div>
      <div class="avatar-wrapper">
        <div class="avatar-frame">⚔️</div>
      </div>
    </div>
  </section>
 
  <!-- SKILLS -->
  <section class="section">
    <h2 class="section-title"><span class="icon">⚙️</span> Skills and Tools</h2>
    <div class="skills-grid">
      <div class="skill-tag"><span class="dot"></span>LINUX</div>
      <div class="skill-tag"><span class="dot"></span>OBSIDIAN</div>
      <div class="skill-tag"><span class="dot"></span>POWERSHELL</div>
      <div class="skill-tag"><span class="dot"></span>PYTHON</div>
      <div class="skill-tag"><span class="dot"></span>NEOVIM</div>
      <div class="skill-tag"><span class="dot"></span>BASH</div>
      <div class="skill-tag"><span class="dot"></span>KALI LINUX</div>
      <div class="skill-tag"><span class="dot"></span>VS CODE</div>
      <div class="skill-tag"><span class="dot"></span>WINDOWS</div>
      <div class="skill-tag"><span class="dot"></span>GITHUB</div>
      <div class="skill-tag"><span class="dot"></span>METASPLOIT</div>
      <div class="skill-tag"><span class="dot"></span>WIRESHARK</div>
    </div>
  </section>
 
  <!-- STATS -->
  <section class="section">
    <h2 class="section-title"><span class="icon">📈</span> Stats</h2>
    <div class="stats-card">
      <div class="stats-avatar">🐉</div>
      <div class="stats-info">
        <div class="stats-name">0xnotkyo <span>⚡ [0xA]</span></div>
        <div class="stats-meta">tryhackme.com</div>
        <div class="stats-row">
          <div class="stat-item">
            <span class="stat-val">56647</span>
            <span class="stat-label">🏆 POINTS</span>
          </div>
          <div class="stat-item">
            <span class="stat-val">3</span>
            <span class="stat-label">🔥 DAYS</span>
          </div>
          <div class="stat-item">
            <span class="stat-val">26</span>
            <span class="stat-label">👤 RANK</span>
          </div>
          <div class="stat-item">
            <span class="stat-val">157</span>
            <span class="stat-label">🚩 BADGES</span>
          </div>
        </div>
      </div>
      <span class="thm-badge">Try Hack Me</span>
    </div>
  </section>
 
  <!-- TERMINAL -->
  <p class="terminal-line">
    <span>root@0xnotkyo</span>:~$ cat journey.log<span class="cursor"></span>
  </p>
 
</div>
</body>
</html>
 

