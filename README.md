<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="我的第一个个人网站">
  <title>我的个人网站</title>

  <style>
    /* ---------- 配色变量（浅色 / 深色） ---------- */
    :root {
      --bg: #f7f8fa;
      --card: #ffffff;
      --text: #22252b;
      --muted: #6b7280;
      --accent: #4f7cff;
      --border: #e5e7eb;
      --tag-bg: #eef2ff;
      --tag-bd: #d8e2ff;
    }
    html[data-theme="dark"] {
      --bg: #12141a;
      --card: #1b1e26;
      --text: #e8eaf0;
      --muted: #9aa1b1;
      --accent: #6d96ff;
      --border: #2a2e3a;
      --tag-bg: #1e2740;
      --tag-bd: #2c3a5e;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; scroll-padding-top: 20px; }

    body {
      margin: 0;
      font-family: system-ui, -apple-system, "Segoe UI", "PingFang SC", "Microsoft YaHei", sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.75;
      transition: background .3s ease, color .3s ease;
    }

    .container { max-width: 820px; margin: 0 auto; padding: 0 20px; }

    /* ---------- 顶部个人名片 ---------- */
    .hero { text-align: center; padding: 76px 20px 36px; }

    .avatar {
      width: 96px; height: 96px;
      margin: 0 auto 20px;
      display: grid; place-items: center;
      font-size: 44px;
      border-radius: 50%;
      background: var(--card);
      border: 1px solid var(--border);
      box-shadow: 0 6px 20px rgba(0,0,0,.06);
    }

    h1 { font-size: clamp(26px, 5vw, 36px); margin: 0 0 10px; }
    .accent { color: var(--accent); }
    .tagline { color: var(--muted); margin: 0 0 26px; }

    /* ---------- 导航 ---------- */
    .nav a {
      display: inline-block;
      margin: 4px 5px;
      padding: 6px 15px;
      border-radius: 999px;
      border: 1px solid var(--border);
      color: var(--text);
      text-decoration: none;
      font-size: 14px;
      transition: .2s;
    }
    .nav a:hover { background: var(--accent); border-color: var(--accent); color: #fff; }
    .nav a:focus-visible,
    .links a:focus-visible,
    .theme-btn:focus-visible {
      outline: 3px solid var(--accent);
      outline-offset: 3px;
    }

    /* ---------- 通用区块 ---------- */
    section { padding: 30px 0; }
    .card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 26px 28px;
      box-shadow: 0 2px 10px rgba(0,0,0,.04);
    }
    h2 { font-size: 20px; margin: 0 0 14px; }

    /* ---------- 技能标签 ---------- */
    .tags { display: flex; flex-wrap: wrap; gap: 10px; }
    .tag {
      padding: 6px 14px;
      border-radius: 999px;
      font-size: 14px;
      background: var(--tag-bg);
      color: var(--accent);
      border: 1px solid var(--tag-bd);
    }

    /* ---------- 爱好网格 ---------- */
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 16px;
    }
    .hobby {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 20px;
      transition: transform .2s, box-shadow .2s;
    }
    .hobby:hover { transform: translateY(-4px); box-shadow: 0 10px 24px rgba(0,0,0,.08); }
    .hobby .emoji { font-size: 26px; }
    .hobby h3 { margin: 8px 0 6px; font-size: 16px; }
    .hobby p { margin: 0; color: var(--muted); font-size: 14px; }

    /* ---------- 联系方式按钮 ---------- */
    .links a {
      display: inline-block;
      margin: 6px 8px 6px 0;
      padding: 10px 18px;
      border-radius: 10px;
      background: var(--accent);
      color: #fff;
      text-decoration: none;
      font-size: 14px;
      transition: .2s;
    }
    .links a:hover { opacity: .85; }

    /* ---------- 页脚 ---------- */
    footer {
      text-align: center;
      color: var(--muted);
      font-size: 13px;
      padding: 40px 20px 30px;
      margin-top: 30px;
      border-top: 1px solid var(--border);
    }

    /* ---------- 右上角主题按钮 ---------- */
    .theme-btn {
      position: fixed;
      top: 18px; right: 18px;
      width: 44px; height: 44px;
      border-radius: 50%;
      border: 1px solid var(--border);
      background: var(--card);
      font-size: 20px;
      cursor: pointer;
      box-shadow: 0 4px 14px rgba(0,0,0,.08);
      transition: transform .2s;
      z-index: 10;
    }
    .theme-btn:hover { transform: scale(1.08); }

    @media (max-width: 480px) {
      .hero { padding-top: 68px; }
      .card { padding: 22px 20px; }
      .grid { grid-template-columns: 1fr; }
    }

    @media (prefers-reduced-motion: reduce) {
      html { scroll-behavior: auto; }
      *, *::before, *::after { transition-duration: .01ms !important; }
    }
  </style>
</head>

<body>
  <!-- 深色模式切换 -->
  <button id="themeBtn" class="theme-btn" type="button" aria-label="切换深色模式" aria-pressed="false">🌙</button>

  <!-- 顶部名片 -->
  <header class="hero">
    <div class="avatar" aria-hidden="true">👨‍💻</div>
    <h1>你好，我是 <span class="accent">小明</span></h1>
    <p class="tagline">这是我的第一个个人网站 —— 一个正在学习编程的普通人。</p>
    <nav class="nav" aria-label="主导航">
      <a href="#about">关于我</a>
      <a href="#skills">技能</a>
      <a href="#hobbies">爱好</a>
      <a href="#contact">联系我</a>
    </nav>
  </header>

  <main class="container">

    <!-- 关于我 -->
    <section id="about">
      <div class="card">
        <h2>🙋 关于我</h2>
        <p>
          我是一名刚接触前端开发的学生 / 爱好者，喜欢把想法变成能看到的东西。
          这个网站是我学习 HTML 和 CSS 的第一个作品，会一直更新下去。
        </p>
        <p style="margin-bottom:0;color:var(--muted)">
          座右铭：慢慢来，比较快。
        </p>
      </div>
    </section>

    <!-- 技能 -->
    <section id="skills">
      <div class="card">
        <h2>🛠 正在学习</h2>
        <div class="tags">
          <span class="tag">HTML</span>
          <span class="tag">CSS</span>
          <span class="tag">JavaScript</span>
          <span class="tag">Git</span>
          <span class="tag">VS Code</span>
        </div>
      </div>
    </section>

    <!-- 爱好 -->
    <section id="hobbies">
      <h2>🎈 我的爱好</h2>
      <div class="grid">
        <div class="hobby">
          <div class="emoji" aria-hidden="true">📚</div>
          <h3>阅读</h3>
          <p>喜欢科幻和技术类书籍，最近在读《代码大全》。</p>
        </div>
        <div class="hobby">
          <div class="emoji" aria-hidden="true">🎧</div>
          <h3>听音乐</h3>
          <p>写代码必备，偏好轻音乐和民谣。</p>
        </div>
        <div class="hobby">
          <div class="emoji" aria-hidden="true">🏃</div>
          <h3>跑步</h3>
          <p>每周跑三次，跑步时想问题最清楚。</p>
        </div>
        <div class="hobby">
          <div class="emoji" aria-hidden="true">🎮</div>
          <h3>玩游戏</h3>
          <p>偶尔打打独立游戏，也会研究游戏是怎么做出来的。</p>
        </div>
      </div>
    </section>

    <!-- 联系方式 -->
    <section id="contact">
      <div class="card">
        <h2>✉️ 联系我</h2>
        <p style="color:var(--muted);margin-top:0">欢迎交流，随时给我发消息～</p>
        <div class="links">
          <a href="mailto:your@email.com">📧 邮箱</a>
          <a href="https://github.com/" target="_blank" rel="noopener noreferrer">💻 GitHub</a>
          <a href="https://weibo.com/" target="_blank" rel="noopener noreferrer">🌐 社交主页</a>
        </div>
      </div>
    </section>

  </main>

  <footer>
    © <span id="year"></span> 小明 · 用 ❤️ 与 HTML 手工打造
    <br>
    <span id="clock"></span>
  </footer>

  <script>
    /* ---------- 深色模式 ---------- */
    const root = document.documentElement;
    const themeBtn = document.getElementById('themeBtn');

    function getPreferredTheme() {
      try {
        const savedTheme = localStorage.getItem('theme');
        if (savedTheme === 'dark' || savedTheme === 'light') return savedTheme;
      } catch (error) {
        // localStorage 在禁用或受限环境下可能不可用，回退到系统设置。
      }

      return window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches
        ? 'dark'
        : 'light';
    }

    function applyTheme(theme, save = false) {
      const isDark = theme === 'dark';
      if (isDark) {
        root.dataset.theme = 'dark';
      } else {
        delete root.dataset.theme;
      }
      themeBtn.textContent = isDark ? '☀️' : '🌙';
      themeBtn.setAttribute('aria-pressed', String(isDark));

      if (save) {
        try {
          localStorage.setItem('theme', isDark ? 'dark' : 'light');
        } catch (error) {
          // 主题仍可在当前页面切换，只是不保存到下次访问。
        }
      }
    }

    applyTheme(getPreferredTheme());

    themeBtn.addEventListener('click', () => {
      const currentTheme = root.dataset.theme === 'dark' ? 'dark' : 'light';
      applyTheme(currentTheme === 'dark' ? 'light' : 'dark', true);
    });

    /* ---------- 年份 ---------- */
    document.getElementById('year').textContent = new Date().getFullYear();

    /* ---------- 实时时钟 ---------- */
    function tick() {
      document.getElementById('clock').textContent =
        '现在是：' + new Date().toLocaleString('zh-CN', { hour12: false });
    }
    tick();
    setInterval(tick, 1000);
  </script>
</body>
</html>
