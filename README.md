<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Portfolio & CV</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

    :root {
      --bg: #F7F6F3;
      --surface: #FFFFFF;
      --text-primary: #37352F;
      --text-secondary: #6B6B6B;
      --text-muted: #9B9A97;
      --accent: #2383E2;
      --accent-light: #E8F0FE;
      --border: #E9E9E7;
      --tag-blue: #D3E5EF;
      --tag-green: #DBEDDB;
      --tag-purple: #E8DEEE;
      --tag-orange: #FADEC9;
      --tag-pink: #F5E0E9;
      --tag-yellow: #FDECC8;
      --tag-red: #FFE2DD;
      --tag-gray: #E3E2E0;
      --shadow-sm: 0 1px 2px rgba(0,0,0,0.04);
      --shadow-md: 0 2px 8px rgba(0,0,0,0.06), 0 0 1px rgba(0,0,0,0.04);
      --shadow-lg: 0 8px 24px rgba(0,0,0,0.08), 0 0 1px rgba(0,0,0,0.04);
      --radius: 10px;
      --radius-lg: 16px;
    }

    [data-theme="dark"] {
      --bg: #191919;
      --surface: #202020;
      --text-primary: #E6E6E4;
      --text-secondary: #9B9B9B;
      --text-muted: #6B6B6B;
      --accent: #529CCA;
      --accent-light: #143A52;
      --border: #2F2F2F;
      --tag-blue: #1F3A5F;
      --tag-green: #1C3829;
      --tag-purple: #3B2454;
      --tag-orange: #4A2E1B;
      --tag-pink: #4A2035;
      --tag-yellow: #4A3520;
      --tag-red: #4A2020;
      --tag-gray: #353535;
      --shadow-sm: 0 1px 2px rgba(0,0,0,0.2);
      --shadow-md: 0 2px 8px rgba(0,0,0,0.3), 0 0 1px rgba(0,0,0,0.2);
      --shadow-lg: 0 8px 24px rgba(0,0,0,0.4), 0 0 1px rgba(0,0,0,0.2);
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
      background: var(--bg);
      color: var(--text-primary);
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
    }

    .page-wrapper {
      max-width: 900px;
      margin: 0 auto;
      padding: 40px 24px 80px;
    }

    /* ── Theme Toggle ── */
    .theme-toggle {
      position: fixed;
      top: 20px;
      right: 24px;
      z-index: 100;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 50%;
      width: 40px;
      height: 40px;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      box-shadow: var(--shadow-md);
      transition: transform 0.2s, box-shadow 0.2s;
      font-size: 18px;
    }
    .theme-toggle:hover { transform: scale(1.1); box-shadow: var(--shadow-lg); }

    /* ── Cover Banner ── */
    .cover-banner {
      width: 100%;
      height: 200px;
      border-radius: var(--radius-lg);
      background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
      position: relative;
      overflow: hidden;
      margin-bottom: -50px;
    }
    .cover-banner::after {
      content: '';
      position: absolute;
      inset: 0;
      background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.06'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
    }

    /* ── Profile Header ── */
    .profile-header {
      display: flex;
      align-items: flex-end;
      gap: 24px;
      padding: 0 20px;
      position: relative;
      z-index: 2;
      margin-bottom: 32px;
    }
    .avatar {
      width: 100px;
      height: 100px;
      border-radius: 50%;
      border: 4px solid var(--surface);
      background: linear-gradient(135deg, #f093fb, #667eea);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 40px;
      font-weight: 700;
      color: #fff;
      box-shadow: var(--shadow-lg);
      flex-shrink: 0;
    }
    .profile-info { padding-bottom: 4px; }
    .profile-info h1 {
      font-size: 28px;
      font-weight: 700;
      letter-spacing: -0.5px;
      line-height: 1.2;
    }
    .profile-info .tagline {
      font-size: 15px;
      color: var(--text-secondary);
      margin-top: 2px;
    }

    /* ── Quick Links ── */
    .quick-links {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
      padding: 0 20px;
      margin-bottom: 40px;
    }
    .quick-link {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 6px 14px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 20px;
      font-size: 13px;
      color: var(--text-secondary);
      text-decoration: none;
      transition: all 0.2s;
    }
    .quick-link:hover {
      border-color: var(--accent);
      color: var(--accent);
      box-shadow: var(--shadow-sm);
    }
    .quick-link svg { width: 14px; height: 14px; }

    /* ── Section ── */
    .section { margin-bottom: 40px; }
    .section-header {
      display: flex;
      align-items: center;
      gap: 8px;
      margin-bottom: 16px;
      padding: 0 4px;
    }
    .section-icon {
      font-size: 20px;
      width: 28px;
      height: 28px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .section-header h2 {
      font-size: 18px;
      font-weight: 600;
      letter-spacing: -0.3px;
    }
    .section-divider {
      height: 1px;
      background: var(--border);
      margin-bottom: 16px;
    }

    /* ── Card Grid ── */
    .card-grid {
      display: grid;
      gap: 12px;
    }
    .card-grid.cols-2 { grid-template-columns: repeat(2, 1fr); }
    .card-grid.cols-3 { grid-template-columns: repeat(3, 1fr); }

    @media (max-width: 700px) {
      .card-grid.cols-2, .card-grid.cols-3 { grid-template-columns: 1fr; }
      .profile-header { flex-direction: column; align-items: flex-start; gap: 16px; }
      .cover-banner { height: 140px; margin-bottom: -40px; }
    }

    /* ── Card ── */
    .card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 20px;
      transition: box-shadow 0.25s, transform 0.25s;
      position: relative;
    }
    .card:hover {
      box-shadow: var(--shadow-lg);
      transform: translateY(-2px);
    }
    .card-accent {
      position: absolute;
      top: 0; left: 20px; right: 20px;
      height: 3px;
      border-radius: 0 0 3px 3px;
    }

    .card .title {
      font-size: 15px;
      font-weight: 600;
      margin-bottom: 4px;
      line-height: 1.3;
    }
    .card .subtitle {
      font-size: 13px;
      color: var(--text-secondary);
      margin-bottom: 4px;
    }
    .card .date {
      font-size: 12px;
      color: var(--text-muted);
      margin-bottom: 8px;
    }
    .card .description {
      font-size: 13px;
      color: var(--text-secondary);
      line-height: 1.55;
    }

    /* ── Tags ── */
    .tags { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 10px; }
    .tag {
      display: inline-block;
      padding: 2px 8px;
      border-radius: 4px;
      font-size: 12px;
      font-weight: 500;
      line-height: 1.5;
    }
    .tag.blue   { background: var(--tag-blue);   color: #1a5276; }
    .tag.green  { background: var(--tag-green);  color: #1e6f3e; }
    .tag.purple { background: var(--tag-purple); color: #5b3a8c; }
    .tag.orange { background: var(--tag-orange); color: #8b4513; }
    .tag.pink   { background: var(--tag-pink);   color: #8b2252; }
    .tag.yellow { background: var(--tag-yellow); color: #7d5a00; }
    .tag.red    { background: var(--tag-red);    color: #8b2020; }
    .tag.gray   { background: var(--tag-gray);   color: var(--text-secondary); }

    [data-theme="dark"] .tag.blue   { color: #7db8e0; }
    [data-theme="dark"] .tag.green  { color: #7dbe8e; }
    [data-theme="dark"] .tag.purple { color: #b89ad4; }
    [data-theme="dark"] .tag.orange { color: #d4a574; }
    [data-theme="dark"] .tag.pink   { color: #d48aa4; }
    [data-theme="dark"] .tag.yellow { color: #d4b074; }
    [data-theme="dark"] .tag.red    { color: #d48a8a; }
    [data-theme="dark"] .tag.gray   { color: var(--text-secondary); }

    /* ── About Card (full width) ── */
    .about-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 24px;
      font-size: 14px;
      color: var(--text-secondary);
      line-height: 1.7;
    }

    /* ── Skill Bars ── */
    .skill-item {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 12px;
    }
    .skill-item:last-child { margin-bottom: 0; }
    .skill-name {
      font-size: 13px;
      font-weight: 500;
      min-width: 110px;
      flex-shrink: 0;
    }
    .skill-bar-bg {
      flex: 1;
      height: 8px;
      background: var(--border);
      border-radius: 4px;
      overflow: hidden;
    }
    .skill-bar-fill {
      height: 100%;
      border-radius: 4px;
      transition: width 1s ease;
      width: 0;
    }

    /* ── Project Card Image ── */
    .project-thumb {
      width: 100%;
      height: 140px;
      border-radius: 6px;
      margin-bottom: 14px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 36px;
      overflow: hidden;
    }

    /* ── Timeline ── */
    .timeline-card {
      padding-left: 28px;
      position: relative;
    }
    .timeline-card::before {
      content: '';
      position: absolute;
      left: 8px;
      top: 24px;
      bottom: -12px;
      width: 2px;
      background: var(--border);
    }
    .timeline-card:last-child::before { display: none; }
    .timeline-card::after {
      content: '';
      position: absolute;
      left: 4px;
      top: 24px;
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: var(--accent);
      border: 2px solid var(--surface);
    }

    /* ── Contact Grid ── */
    .contact-item {
      display: flex;
      align-items: center;
      gap: 12px;
      padding: 14px 18px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      transition: all 0.2s;
      text-decoration: none;
      color: var(--text-primary);
    }
    .contact-item:hover {
      box-shadow: var(--shadow-md);
      border-color: var(--accent);
      transform: translateY(-1px);
    }
    .contact-icon {
      width: 40px;
      height: 40px;
      border-radius: 8px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
      flex-shrink: 0;
    }
    .contact-label { font-size: 12px; color: var(--text-muted); }
    .contact-value { font-size: 14px; font-weight: 500; }

    /* ── Stat Cards ── */
    .stat-card {
      text-align: center;
      padding: 24px 16px;
    }
    .stat-number {
      font-size: 32px;
      font-weight: 800;
      letter-spacing: -1px;
      background: linear-gradient(135deg, #667eea, #764ba2);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .stat-label {
      font-size: 13px;
      color: var(--text-muted);
      margin-top: 4px;
    }

    /* ── Callout ── */
    .callout {
      display: flex;
      align-items: flex-start;
      gap: 12px;
      padding: 16px 18px;
      background: var(--accent-light);
      border-radius: var(--radius);
      margin-bottom: 12px;
    }
    .callout-icon { font-size: 20px; flex-shrink: 0; padding-top: 1px; }
    .callout-text { font-size: 14px; line-height: 1.55; }

    /* ── Footer ── */
    .footer {
      text-align: center;
      padding: 40px 0 0;
      font-size: 13px;
      color: var(--text-muted);
    }

    /* ── Animations ── */
    .fade-in {
      opacity: 0;
      transform: translateY(16px);
      animation: fadeIn 0.5s ease forwards;
    }
    @keyframes fadeIn {
      to { opacity: 1; transform: translateY(0); }
    }
    .delay-1 { animation-delay: 0.05s; }
    .delay-2 { animation-delay: 0.1s; }
    .delay-3 { animation-delay: 0.15s; }
    .delay-4 { animation-delay: 0.2s; }
    .delay-5 { animation-delay: 0.25s; }
    .delay-6 { animation-delay: 0.3s; }
    .delay-7 { animation-delay: 0.35s; }
    .delay-8 { animation-delay: 0.4s; }
  </style>
</head>
<body>
  <button class="theme-toggle" onclick="toggleTheme()" title="Toggle theme">
    <span id="theme-icon">&#9790;</span>
  </button>

  <div class="page-wrapper">

    <!-- Cover Banner -->
    <div class="cover-banner fade-in"></div>

    <!-- Profile Header -->
    <div class="profile-header fade-in delay-1">
      <div class="avatar">YN</div>
      <div class="profile-info">
        <h1>Your Name</h1>
        <p class="tagline">Creative Developer & UI/UX Designer</p>
      </div>
    </div>

    <!-- Quick Links -->
    <div class="quick-links fade-in delay-2">
      <a href="#about" class="quick-link">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M12 16v-4M12 8h.01"/></svg>
        About
      </a>
      <a href="#experience" class="quick-link">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="7" width="20" height="14" rx="2"/><path d="M16 7V5a2 2 0 00-2-2h-4a2 2 0 00-2 2v2"/></svg>
        Experience
      </a>
      <a href="#projects" class="quick-link">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 19a2 2 0 01-2 2H4a2 2 0 01-2-2V5a2 2 0 012-2h5l2 3h9a2 2 0 012 2z"/></svg>
        Projects
      </a>
      <a href="#skills" class="quick-link">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
        Skills
      </a>
      <a href="#contact" class="quick-link">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        Contact
      </a>
    </div>

    <!-- Stats -->
    <div class="card-grid cols-3 fade-in delay-3" style="margin-bottom: 40px;">
      <div class="card stat-card">
        <div class="stat-number">5+</div>
        <div class="stat-label">Years Experience</div>
      </div>
      <div class="card stat-card">
        <div class="stat-number">30+</div>
        <div class="stat-label">Projects Delivered</div>
      </div>
      <div class="card stat-card">
        <div class="stat-number">15+</div>
        <div class="stat-label">Happy Clients</div>
      </div>
    </div>

    <!-- About -->
    <section class="section fade-in delay-4" id="about">
      <div class="section-header">
        <div class="section-icon">&#128075;</div>
        <h2>About Me</h2>
      </div>
      <div class="section-divider"></div>
      <div class="about-card">
        <p>I'm a passionate developer and designer who loves building elegant, user-centric digital experiences. With a strong foundation in front-end technologies and a keen eye for design, I bridge the gap between aesthetics and functionality.</p>
        <br />
        <p>When I'm not coding, you'll find me exploring new design trends, contributing to open-source projects, or sketching ideas for my next side project.</p>
      </div>
    </section>

    <!-- Experience -->
    <section class="section fade-in delay-5" id="experience">
      <div class="section-header">
        <div class="section-icon">&#128188;</div>
        <h2>Experience</h2>
      </div>
      <div class="section-divider"></div>
      <div class="card" style="padding: 24px;">
        <div class="timeline-card" style="margin-bottom: 24px;">
          <div class="title">Senior Frontend Developer</div>
          <div class="subtitle">TechCorp Inc.</div>
          <div class="date">Jan 2023 &ndash; Present</div>
          <div class="description">Led the redesign of the core product dashboard, improving user engagement by 40%. Mentored junior developers and established front-end coding standards across the team.</div>
          <div class="tags">
            <span class="tag blue">React</span>
            <span class="tag purple">TypeScript</span>
            <span class="tag green">Next.js</span>
          </div>
        </div>
        <div class="timeline-card" style="margin-bottom: 24px;">
          <div class="title">UI/UX Designer & Developer</div>
          <div class="subtitle">Creative Studio</div>
          <div class="date">Mar 2021 &ndash; Dec 2022</div>
          <div class="description">Designed and developed responsive web applications for 10+ clients. Created design systems and component libraries that reduced development time by 30%.</div>
          <div class="tags">
            <span class="tag orange">Figma</span>
            <span class="tag blue">Vue.js</span>
            <span class="tag pink">Sass</span>
          </div>
        </div>
        <div class="timeline-card">
          <div class="title">Junior Web Developer</div>
          <div class="subtitle">StartupXYZ</div>
          <div class="date">Jun 2019 &ndash; Feb 2021</div>
          <div class="description">Built and maintained client-facing web applications. Collaborated with designers to implement pixel-perfect interfaces and optimize performance.</div>
          <div class="tags">
            <span class="tag yellow">JavaScript</span>
            <span class="tag red">HTML/CSS</span>
            <span class="tag gray">WordPress</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Projects -->
    <section class="section fade-in delay-6" id="projects">
      <div class="section-header">
        <div class="section-icon">&#128640;</div>
        <h2>Featured Projects</h2>
      </div>
      <div class="section-divider"></div>
      <div class="callout">
        <div class="callout-icon">&#128161;</div>
        <div class="callout-text">These are some of my favorite projects that showcase my skills across design, development, and problem-solving.</div>
      </div>
      <div class="card-grid cols-2">
        <div class="card">
          <div class="card-accent" style="background: linear-gradient(90deg, #667eea, #764ba2);"></div>
          <div class="project-thumb" style="background: linear-gradient(135deg, #667eea20, #764ba220); border: 1px solid var(--border);">&#127912;</div>
          <div class="title">Design System Pro</div>
          <div class="description">A comprehensive design system with 50+ components, built for scalability and consistency across products.</div>
          <div class="tags">
            <span class="tag blue">React</span>
            <span class="tag purple">Storybook</span>
            <span class="tag green">Figma</span>
          </div>
        </div>
        <div class="card">
          <div class="card-accent" style="background: linear-gradient(90deg, #f093fb, #f5576c);"></div>
          <div class="project-thumb" style="background: linear-gradient(135deg, #f093fb20, #f5576c20); border: 1px solid var(--border);">&#128202;</div>
          <div class="title">Analytics Dashboard</div>
          <div class="description">Real-time analytics dashboard with interactive charts, filters, and customizable widgets for data visualization.</div>
          <div class="tags">
            <span class="tag purple">Next.js</span>
            <span class="tag orange">D3.js</span>
            <span class="tag blue">PostgreSQL</span>
          </div>
        </div>
        <div class="card">
          <div class="card-accent" style="background: linear-gradient(90deg, #43e97b, #38f9d7);"></div>
          <div class="project-thumb" style="background: linear-gradient(135deg, #43e97b20, #38f9d720); border: 1px solid var(--border);">&#128241;</div>
          <div class="title">TaskFlow App</div>
          <div class="description">A minimalist task management app with drag-and-drop, tags, and collaborative features for remote teams.</div>
          <div class="tags">
            <span class="tag green">Vue.js</span>
            <span class="tag yellow">Firebase</span>
            <span class="tag pink">Tailwind</span>
          </div>
        </div>
        <div class="card">
          <div class="card-accent" style="background: linear-gradient(90deg, #fa709a, #fee140);"></div>
          <div class="project-thumb" style="background: linear-gradient(135deg, #fa709a20, #fee14020); border: 1px solid var(--border);">&#127760;</div>
          <div class="title">E-Commerce Platform</div>
          <div class="description">Full-stack e-commerce solution with payment integration, inventory management, and admin dashboard.</div>
          <div class="tags">
            <span class="tag red">Node.js</span>
            <span class="tag blue">Stripe</span>
            <span class="tag gray">MongoDB</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills -->
    <section class="section fade-in delay-7" id="skills">
      <div class="section-header">
        <div class="section-icon">&#9889;</div>
        <h2>Skills & Tools</h2>
      </div>
      <div class="section-divider"></div>
      <div class="card-grid cols-2">
        <div class="card">
          <div class="title" style="margin-bottom: 16px;">Development</div>
          <div class="skill-item">
            <span class="skill-name">JavaScript</span>
            <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="95%" style="background: linear-gradient(90deg, #667eea, #764ba2);"></div></div>
          </div>
          <div class="skill-item">
            <span class="skill-name">TypeScript</span>
            <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="90%" style="background: linear-gradient(90deg, #667eea, #764ba2);"></div></div>
          </div>
          <div class="skill-item">
            <span class="skill-name">React / Next.js</span>
            <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="92%" style="background: linear-gradient(90deg, #667eea, #764ba2);"></div></div>
          </div>
          <div class="skill-item">
            <span class="skill-name">Node.js</span>
            <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="80%" style="background: linear-gradient(90deg, #667eea, #764ba2);"></div></div>
          </div>
          <div class="skill-item">
            <span class="skill-name">Python</span>
            <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="70%" style="background: linear-gradient(90deg, #667eea, #764ba2);"></div></div>
          </div>
        </div>
        <div class="card">
          <div class="title" style="margin-bottom: 16px;">Design & Tools</div>
          <div class="skill-item">
            <span class="skill-name">Figma</span>
            <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="95%" style="background: linear-gradient(90deg, #f093fb, #f5576c);"></div></div>
          </div>
          <div class="skill-item">
            <span class="skill-name">UI/UX Design</span>
            <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="90%" style="background: linear-gradient(90deg, #f093fb, #f5576c);"></div></div>
          </div>
          <div class="skill-item">
            <span class="skill-name">Tailwind CSS</span>
            <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="88%" style="background: linear-gradient(90deg, #f093fb, #f5576c);"></div></div>
          </div>
          <div class="skill-item">
            <span class="skill-name">Adobe Suite</span>
            <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="75%" style="background: linear-gradient(90deg, #f093fb, #f5576c);"></div></div>
          </div>
          <div class="skill-item">
            <span class="skill-name">Git / GitHub</span>
            <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="85%" style="background: linear-gradient(90deg, #f093fb, #f5576c);"></div></div>
          </div>
        </div>
      </div>
    </section>

    <!-- Education -->
    <section class="section fade-in delay-8" id="education">
      <div class="section-header">
        <div class="section-icon">&#127891;</div>
        <h2>Education</h2>
      </div>
      <div class="section-divider"></div>
      <div class="card-grid cols-2">
        <div class="card">
          <div class="card-accent" style="background: linear-gradient(90deg, #43e97b, #38f9d7);"></div>
          <div class="title">B.Sc. in Computer Science</div>
          <div class="subtitle">University of Technology</div>
          <div class="date">2015 &ndash; 2019</div>
          <div class="description">Graduated with honors. Focused on software engineering, human-computer interaction, and web technologies.</div>
        </div>
        <div class="card">
          <div class="card-accent" style="background: linear-gradient(90deg, #fa709a, #fee140);"></div>
          <div class="title">UX Design Professional Certificate</div>
          <div class="subtitle">Google &mdash; Coursera</div>
          <div class="date">2020</div>
          <div class="description">Completed the full Google UX Design program covering user research, wireframing, prototyping, and usability testing.</div>
        </div>
      </div>
    </section>

    <!-- Contact -->
    <section class="section fade-in delay-8" id="contact">
      <div class="section-header">
        <div class="section-icon">&#128236;</div>
        <h2>Get in Touch</h2>
      </div>
      <div class="section-divider"></div>
      <div class="card-grid cols-3">
        <a href="mailto:hello@yourname.com" class="contact-item">
          <div class="contact-icon" style="background: var(--tag-blue);">&#9993;</div>
          <div>
            <div class="contact-label">Email</div>
            <div class="contact-value">hello@yourname.com</div>
          </div>
        </a>
        <a href="tel:+918769659799" class="contact-item">
          <div class="contact-icon" style="background: var(--tag-green);">&#128222;</div>
          <div>
            <div class="contact-label">Phone</div>
            <div class="contact-value">+91-8769659799</div>
          </div>
        </a>
        <a href="http://designernaruka.com/" class="contact-item" target="_blank">
          <div class="contact-icon" style="background: var(--tag-purple);">&#127760;</div>
          <div>
            <div class="contact-label">Website</div>
            <div class="contact-value">designernaruka.com</div>
          </div>
        </a>
        <a href="https://github.com/yourname" class="contact-item" target="_blank">
          <div class="contact-icon" style="background: var(--tag-gray);">&#128187;</div>
          <div>
            <div class="contact-label">GitHub</div>
            <div class="contact-value">github.com/yourname</div>
          </div>
        </a>
        <a href="https://linkedin.com/in/yourname" class="contact-item" target="_blank">
          <div class="contact-icon" style="background: var(--tag-blue);">&#128100;</div>
          <div>
            <div class="contact-label">LinkedIn</div>
            <div class="contact-value">linkedin.com/in/yourname</div>
          </div>
        </a>
        <a href="https://yourname.com" class="contact-item" target="_blank">
          <div class="contact-icon" style="background: var(--tag-orange);">&#128232;</div>
          <div>
            <div class="contact-label">Portfolio</div>
            <div class="contact-value">yourname.com</div>
          </div>
        </a>
      </div>
    </section>

    <!-- Footer -->
    <div class="footer fade-in delay-8">
      Built with care &bull; Last updated March 2026
    </div>

  </div>

  <script>
    function toggleTheme() {
      const body = document.documentElement;
      const isDark = body.getAttribute('data-theme') === 'dark';
      body.setAttribute('data-theme', isDark ? '' : 'dark');
      document.getElementById('theme-icon').innerHTML = isDark ? '&#9790;' : '&#9788;';
      localStorage.setItem('theme', isDark ? 'light' : 'dark');
    }

    if (localStorage.getItem('theme') === 'dark' || 
        (!localStorage.getItem('theme') && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
      document.documentElement.setAttribute('data-theme', 'dark');
      document.getElementById('theme-icon').innerHTML = '&#9788;';
    }

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.querySelectorAll('.skill-bar-fill').forEach(bar => {
            bar.style.width = bar.dataset.width;
          });
        }
      });
    }, { threshold: 0.3 });

    document.querySelectorAll('#skills .card').forEach(card => observer.observe(card));
  </script>
</body>
</html>
