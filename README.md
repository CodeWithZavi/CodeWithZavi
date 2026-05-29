<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Noman Shakir — Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;700;800&family=DM+Mono:ital,wght@0,400;0,500;1,400&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0d1117;
    --bg2: #161b22;
    --bg3: #1c2330;
    --border: rgba(255,255,255,0.08);
    --border2: rgba(255,255,255,0.14);
    --text: #e6edf3;
    --text2: #8b949e;
    --text3: #6e7681;
    --accent: #58a6ff;
    --accent2: #3fb950;
    --purple: #bc8cff;
    --pink: #ff7b72;
    --radius: 12px;
    --radius-sm: 8px;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    padding: 2rem 1rem;
  }

  .page { max-width: 760px; margin: 0 auto; }

  /* ── HERO ── */
  .hero {
    display: flex;
    align-items: center;
    gap: 1.75rem;
    padding: 2rem;
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    margin-bottom: 1.5rem;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 200px; height: 200px;
    background: radial-gradient(circle, rgba(88,166,255,0.12) 0%, transparent 70%);
    pointer-events: none;
  }
  .avatar {
    width: 88px; height: 88px;
    border-radius: 50%;
    background: linear-gradient(135deg, #1a2744 0%, #0d1117 100%);
    border: 2px solid var(--border2);
    display: flex; align-items: center; justify-content: center;
    font-size: 2.5rem;
    flex-shrink: 0;
    position: relative;
  }
  .avatar::after {
    content: '';
    position: absolute;
    inset: -4px;
    border-radius: 50%;
    border: 1px solid rgba(88,166,255,0.3);
  }
  .hero-info h1 {
    font-size: 1.75rem;
    font-weight: 800;
    letter-spacing: -0.5px;
    color: var(--text);
    margin-bottom: 0.4rem;
  }
  .hero-info h1 span { color: var(--accent); }
  .hero-info p {
    font-size: 0.9rem;
    color: var(--text2);
    line-height: 1.65;
    margin-bottom: 0.75rem;
  }
  .tag-row { display: flex; flex-wrap: wrap; gap: 6px; }
  .tag {
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    padding: 3px 10px;
    border-radius: 99px;
    background: rgba(88,166,255,0.1);
    border: 1px solid rgba(88,166,255,0.25);
    color: var(--accent);
  }

  /* ── SECTION LABEL ── */
  .section-label {
    font-size: 0.7rem;
    letter-spacing: 1.8px;
    text-transform: uppercase;
    color: var(--text3);
    margin-bottom: 0.85rem;
    font-family: 'DM Mono', monospace;
  }

  /* ── STATS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin-bottom: 1.5rem;
  }
  @media(max-width: 560px) { .stats-grid { grid-template-columns: 1fr; } }
  .stat-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: var(--radius-sm);
    overflow: hidden;
  }
  .stat-card img { width: 100%; display: block; }

  /* ── TOOLS ── */
  .tools-wrap { margin-bottom: 1.5rem; }
  .tools-grid { display: flex; flex-wrap: wrap; gap: 8px; }
  .tool-chip {
    display: flex; align-items: center; gap: 8px;
    padding: 7px 14px;
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: var(--radius-sm);
    font-size: 0.82rem;
    color: var(--text);
    transition: border-color 0.2s, background 0.2s;
    cursor: default;
  }
  .tool-chip:hover { border-color: var(--border2); background: var(--bg3); }
  .tool-chip img { width: 20px; height: 20px; }

  /* ── ABOUT ── */
  .about-card {
    padding: 1.5rem;
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    margin-bottom: 1.5rem;
  }
  .about-card p {
    font-size: 0.9rem;
    line-height: 1.75;
    color: var(--text2);
  }
  .hobbies-row { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 1rem; }
  .hobby {
    font-size: 0.82rem;
    padding: 5px 13px;
    border-radius: 99px;
    background: rgba(63,185,80,0.08);
    border: 1px solid rgba(63,185,80,0.2);
    color: var(--accent2);
  }

  /* ── SOCIAL ── */
  .social-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
    gap: 10px;
    margin-bottom: 1.5rem;
  }
  .social-link {
    display: flex; align-items: center; gap: 10px;
    padding: 10px 14px;
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: var(--radius-sm);
    text-decoration: none;
    color: var(--text);
    font-size: 0.85rem;
    font-weight: 500;
    transition: border-color 0.2s, background 0.2s;
  }
  .social-link:hover { border-color: var(--border2); background: var(--bg3); }
  .social-dot { width: 9px; height: 9px; border-radius: 50%; flex-shrink: 0; }

  /* ── DIVIDER ── */
  .divider { height: 1px; background: var(--border); margin: 1.5rem 0; }

  /* ── TROPHIES ── */
  .trophy-wrap {
    text-align: center;
    padding: 1.5rem;
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    margin-bottom: 1.5rem;
  }
  .trophy-wrap img { max-width: 100%; border-radius: var(--radius-sm); }

  /* ── CODING GIF ── */
  .gif-wrap {
    text-align: center;
    border-radius: var(--radius);
    overflow: hidden;
    border: 1px solid var(--border);
  }
  .gif-wrap img { width: 100%; display: block; max-height: 280px; object-fit: cover; }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    margin-top: 1.5rem;
    font-size: 0.75rem;
    color: var(--text3);
    font-family: 'DM Mono', monospace;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  .hero        { animation: fadeUp 0.5s ease both; }
  .stats-grid  { animation: fadeUp 0.5s 0.1s ease both; }
  .tools-wrap  { animation: fadeUp 0.5s 0.2s ease both; }
  .about-card  { animation: fadeUp 0.5s 0.3s ease both; }
  .social-grid { animation: fadeUp 0.5s 0.4s ease both; }
  .trophy-wrap { animation: fadeUp 0.5s 0.5s ease both; }
  .gif-wrap    { animation: fadeUp 0.5s 0.6s ease both; }
</style>
</head>
<body>
<div class="page">

  <!-- HERO -->
  <div class="hero">
    <div class="avatar">👨‍💻</div>
    <div class="hero-info">
      <h1>Hello, I'm <span>Noman Shakir</span> 👋</h1>
      <p>Full-stack developer crafting innovative &amp; efficient web solutions.<br>Passionate about clean code and seamless user experiences.</p>
      <div class="tag-row">
        <span class="tag">full-stack</span>
        <span class="tag">open source</span>
        <span class="tag">web dev</span>
        <span class="tag">always learning</span>
      </div>
    </div>
  </div>

  <!-- GITHUB STATS -->
  <p class="section-label">GitHub stats</p>
  <div class="stats-grid">
    <div class="stat-card">
      <img
        src="https://github-readme-stats.vercel.app/api?username=maurodesouza&hide_title=false&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&theme=github_dark&hide_border=true&bg_color=161b22"
        alt="GitHub stats"
        loading="lazy"
      />
    </div>
    <div class="stat-card">
      <img
        src="https://github-readme-stats.vercel.app/api/top-langs?username=maurodesouza&locale=en&layout=compact&langs_count=6&theme=github_dark&hide_border=true&bg_color=161b22"
        alt="Top languages"
        loading="lazy"
      />
    </div>
  </div>

  <!-- TOOLS -->
  <p class="section-label">Languages &amp; tools</p>
  <div class="tools-wrap">
    <div class="tools-grid">
      <div class="tool-chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt=""/>JavaScript</div>
      <div class="tool-chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" alt=""/>TypeScript</div>
      <div class="tool-chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt=""/>React</div>
      <div class="tool-chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" alt=""/>Node.js</div>
      <div class="tool-chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/express/express-original.svg" alt=""/>Express.js</div>
      <div class="tool-chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt=""/>HTML5</div>
      <div class="tool-chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt=""/>CSS3</div>
      <div class="tool-chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt=""/>Python</div>
      <div class="tool-chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/django/django-plain.svg" alt=""/>Django</div>
      <div class="tool-chip"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/csharp/csharp-original.svg" alt=""/>C#</div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ABOUT -->
  <p class="section-label">About me</p>
  <div class="about-card">
    <p>Dedicated full-stack developer with a passion for building innovative, efficient web solutions. Strong foundation in both front-end and back-end technologies — always chasing high-quality code and seamless user experiences.</p>
    <div class="hobbies-row">
      <span class="hobby">🎮 Gaming</span>
      <span class="hobby">📺 Streaming on Twitch</span>
      <span class="hobby">🔭 Exploring new tech</span>
      <span class="hobby">✍️ Blogging on Medium</span>
    </div>
  </div>

  <!-- SOCIAL / CONNECT -->
  <p class="section-label">Connect with me</p>
  <div class="social-grid">
    <a class="social-link" href="https://www.linkedin.com/in/sardar-noman-shakir-83a48626a/" target="_blank">
      <span class="social-dot" style="background:#0077B5"></span>LinkedIn
    </a>
    <a class="social-link" href="https://www.youtube.com/" target="_blank">
      <span class="social-dot" style="background:#FF0000"></span>YouTube
    </a>
    <a class="social-link" href="https://www.instagram.com/" target="_blank">
      <span class="social-dot" style="background:#E4405F"></span>Instagram
    </a>
    <a class="social-link" href="https://discord.com/" target="_blank">
      <span class="social-dot" style="background:#7289DA"></span>Discord
    </a>
    <a class="social-link" href="https://www.twitch.tv/" target="_blank">
      <span class="social-dot" style="background:#9146FF"></span>Twitch
    </a>
    <a class="social-link" href="mailto:your-email@gmail.com">
      <span class="social-dot" style="background:#D14836"></span>Gmail
    </a>
  </div>

  <div class="divider"></div>

  <!-- TROPHIES -->
  <p class="section-label">GitHub trophies</p>
  <div class="trophy-wrap">
    <img
      src="https://github-profile-trophy.vercel.app/?username=maurodesouza&theme=darkhub&no-frame=true&no-bg=true&margin-w=6&column=6"
      alt="GitHub trophies"
      loading="lazy"
    />
  </div>

  <!-- CODING GIF -->
  <div class="gif-wrap">
    <img src="https://media.giphy.com/media/qgQUggAC3Pfv687qPC/giphy.gif" alt="Coding animation" />
  </div>

  <p class="footer">© 2025 Noman Shakir · Built with passion</p>

</div>
</body>
</html>

<!-- Animated profile view counter -->
<div align="center">
    <div style="border: 2px solid #ccc; border-radius: 5px; padding: 10px; width: 150px;">
      <h3>Live Profile Views</h3>
      <div align="center">
        <img src="https://komarev.com/ghpvc/?username=maurodesouza&label=Profile%20views&color=0e75b6&style=flat" alt="Profile views" />
      </div>
    </div>
  </div>
  
  <div align="center">
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" width="100" alt="JavaScript logo" style="border-radius:50%;" />
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" width="100" alt="Python logo" style="border-radius:50%;" />
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" width="100" alt="React logo" style="border-radius:50%;" />
  </div>
  
  <hr>
  <div align="center">
    <img src="https://img.shields.io/badge/Code-HTML-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML Badge" />
    <img src="https://img.shields.io/badge/Code-CSS-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS Badge" />
    <img src="https://img.shields.io/badge/Code-JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript Badge" />
    <img src="https://img.shields.io/badge/Code-Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python Badge" />
    <img src="https://img.shields.io/badge/Framework-React-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React Badge" />
    <img src="https://img.shields.io/badge/Framework-Django-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django Badge" />
    <img src="https://img.shields.io/badge/Framework-Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js Badge" />
  </div>
  
  <hr>
  
  <!-- Footer with more badges and logos -->
  <div align="center">
    <a href="https://github.com/maurodesouza">
      <img src="https://img.shields.io/github/followers/maurodesouza?label=Follow&style=social" alt="GitHub followers" />
    </a>
    <a href="https://github.com/maurodesouza?tab=repositories">
      <img src="https://badges.frapsoft.com/os/v2/open-source.svg?v=103" alt="Open Source" />
    </a>
    <a href="https://github.com/maurodesouza">
      <img src="https://img.shields.io/github/stars/maurodesouza?affiliations=OWNER%2CCOLLABORATOR&style=social" alt="GitHub stars" />
    </a>
  </div>
  
