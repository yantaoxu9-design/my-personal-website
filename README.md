# my-personal-website
My first personal website

<div class="page">
  <nav>
    <strong>Alex's Space</strong>
    <a href="#about">关于我</a>
  </nav>

  <main>
    <p class="tag">WELCOME TO MY WEBSITE</p>
    <h1>你好，我是 <span>Alex</span> 👋</h1>
    <p class="intro">
      欢迎来到我的个人空间！<br>
      这里记录我的想法、兴趣和正在探索的世界。
    </p>

    <a class="button" href="#about">认识一下我 ↓</a>

    <section id="about">
      <h2>关于我</h2>
      <p>我是一个喜欢探索新事物、学习新技能的人。</p>

      <div class="cards">
        <article>
          <h3>💻 编程</h3>
          <p>学习制作网站和实用工具。</p>
        </article>
        <article>
          <h3>🌏 探索</h3>
          <p>发现有趣的事物和新想法。</p>
        </article>
        <article>
          <h3>✨ 目标</h3>
          <p>把脑海中的创意变成现实。</p>
        </article>
      </div>
    </section>

    <section>
      <h2>联系我</h2>
      <p>以后可以在这里添加你的社交账号或邮箱。</p>
      <a class="button" href="mailto:hello@example.com">
        给我发邮件
      </a>
    </section>
  </main>

  <footer>© 2026 Alex · Made with curiosity.</footer>
</div>

<style>
  * { box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    margin: 0;
    background: #0b1020;
    color: #f4f5ff;
    font-family: -apple-system, BlinkMacSystemFont,
      "Segoe UI", sans-serif;
    line-height: 1.7;
  }

  .page {
    max-width: 900px;
    margin: auto;
    padding: 24px;
  }

  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
    flex-wrap: wrap;
  }

  a {
    color: #a5b4fc;
    text-decoration: none;
  }

  main { padding-top: 65px; }

  .tag {
    color: #a5b4fc;
    letter-spacing: 3px;
    font-size: 12px;
  }

  h1 {
    font-size: clamp(32px, 7vw, 58px);
    line-height: 1.2;
  }

  h1 span { color: #a5b4fc; }

  .intro { color: #c3c9dd; }

  .button {
    display: inline-block;
    margin: 18px 0;
    padding: 12px 20px;
    border-radius: 30px;
    background: #818cf8;
    color: #10142a;
    font-weight: 700;
  }

  section { margin-top: 65px; }

  .cards {
    display: grid;
    grid-template-columns: repeat(
      auto-fit, minmax(180px, 1fr)
    );
    gap: 14px;
  }

  article {
    padding: 18px;
    border: 1px solid #303750;
    border-radius: 18px;
    background: #141b30;
  }

  article p { color: #c3c9dd; }

  footer {
    margin-top: 70px;
    padding: 24px 0;
    border-top: 1px solid #303750;
    color: #9ca3b8;
    font-size: 13px;
  }
</style>
