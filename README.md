# -course-promotion-site
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>LearnForge — Full-Stack Web Development</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet" />
<style>
  :root {
    --ink: #0f0e0c;
    --cream: #f7f4ee;
    --warm: #f0ebe0;
    --gold: #c8963e;
    --gold-dark: #9e7025;
    --emerald: #1e6b52;
    --emerald-light: #e4f2ec;
    --ruby: #b83232;
    --sky: #1a5fa8;
    --muted: #6b6760;
    --border: #ddd8ce;
    --card: #ffffff;
    --radius: 12px;
    --nav-h: 68px;
  }
  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body { font-family: 'DM Sans', sans-serif; background: var(--cream); color: var(--ink); line-height: 1.7; overflow-x: hidden; }

  /* ─── NAV ─────────────────────────────────────────────── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 1000;
    height: var(--nav-h);
    background: rgba(15,14,12,0.96);
    backdrop-filter: blur(12px);
    display: flex; align-items: center;
    padding: 0 5%;
    border-bottom: 1px solid rgba(200,150,62,0.25);
  }
  .nav-brand {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem; font-weight: 900;
    color: var(--gold);
    letter-spacing: -0.5px;
    flex: 1;
    text-decoration: none;
  }
  .nav-links {
    display: flex; align-items: center; gap: 6px;
    list-style: none;
  }
  .nav-links a {
    color: rgba(255,255,255,0.8);
    text-decoration: none; font-size: 0.88rem; font-weight: 400;
    padding: 7px 14px; border-radius: 8px;
    transition: all 0.2s;
  }
  .nav-links a:hover { background: rgba(255,255,255,0.1); color: #fff; }
  .btn-nav {
    background: var(--gold); color: var(--ink) !important;
    font-weight: 600 !important;
    border-radius: 8px !important;
    padding: 8px 18px !important;
    transition: background 0.2s !important;
  }
  .btn-nav:hover { background: #e0a840 !important; }
  .hamburger { display: none; background: none; border: none; cursor: pointer; flex-direction: column; gap: 5px; }
  .hamburger span { display: block; width: 24px; height: 2px; background: #fff; border-radius: 2px; transition: 0.3s; }

  /* ─── HERO ────────────────────────────────────────────── */
  #home {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: calc(var(--nav-h) + 60px) 5% 80px;
    background: linear-gradient(135deg, #0f0e0c 0%, #1a1917 55%, #0e2118 100%);
    position: relative; overflow: hidden;
  }
  #home::before {
    content: '';
    position: absolute; top: -20%; right: -10%;
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(200,150,62,0.12) 0%, transparent 65%);
    pointer-events: none;
  }
  #home::after {
    content: '';
    position: absolute; bottom: -10%; left: 5%;
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(30,107,82,0.15) 0%, transparent 65%);
    pointer-events: none;
  }
  .hero-inner { max-width: 700px; position: relative; z-index: 1; }
  .hero-badge {
    display: inline-flex; align-items: center; gap: 8px;
    background: rgba(200,150,62,0.15);
    border: 1px solid rgba(200,150,62,0.35);
    color: var(--gold);
    font-size: 0.8rem; font-weight: 600;
    letter-spacing: 1.2px; text-transform: uppercase;
    padding: 6px 14px; border-radius: 100px;
    margin-bottom: 24px;
  }
  .hero-badge span { width: 6px; height: 6px; background: var(--gold); border-radius: 50%; animation: pulse 1.5s infinite; }
  @keyframes pulse { 0%,100%{opacity:1;} 50%{opacity:0.4;} }
  .hero-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.4rem, 5vw, 3.8rem);
    font-weight: 900; line-height: 1.1;
    color: #fff;
    margin-bottom: 20px;
  }
  .hero-title em { color: var(--gold); font-style: normal; }
  .hero-sub { color: rgba(255,255,255,0.65); font-size: 1.08rem; font-weight: 300; margin-bottom: 36px; max-width: 520px; }
  .hero-stats {
    display: flex; gap: 32px; margin-bottom: 40px;
  }
  .hero-stat strong { display: block; font-size: 1.5rem; font-weight: 700; color: var(--gold); }
  .hero-stat span { font-size: 0.8rem; color: rgba(255,255,255,0.5); text-transform: uppercase; letter-spacing: 0.8px; }
  .hero-cta { display: flex; gap: 14px; flex-wrap: wrap; }
  .btn {
    display: inline-flex; align-items: center; gap: 8px;
    padding: 14px 28px; border-radius: 10px;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.95rem; font-weight: 600;
    cursor: pointer; border: none;
    text-decoration: none;
    transition: all 0.2s;
  }
  .btn-primary { background: var(--gold); color: var(--ink); }
  .btn-primary:hover { background: #e0a840; transform: translateY(-1px); }
  .btn-outline { background: transparent; color: #fff; border: 1.5px solid rgba(255,255,255,0.3); }
  .btn-outline:hover { border-color: #fff; background: rgba(255,255,255,0.07); }
  .btn-emerald { background: var(--emerald); color: #fff; }
  .btn-emerald:hover { background: #17573f; }
  .btn-ruby { background: var(--ruby); color: #fff; }
  .btn-ruby:hover { background: #952828; }

  /* ─── SECTIONS ────────────────────────────────────────── */
  section { padding: 90px 5%; }
  .section-label {
    font-size: 0.75rem; font-weight: 600; letter-spacing: 2px;
    text-transform: uppercase; color: var(--gold);
    margin-bottom: 10px;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.8rem, 3.5vw, 2.6rem);
    font-weight: 700; line-height: 1.2;
    margin-bottom: 14px;
  }
  .section-sub { color: var(--muted); max-width: 520px; margin-bottom: 50px; }
  .divider { width: 48px; height: 3px; background: var(--gold); margin: 18px 0 40px; border-radius: 2px; }

  /* ─── COURSE DETAILS ──────────────────────────────────── */
  #course-details { background: var(--card); }
  .details-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 60px; align-items: start; }
  .details-meta { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-bottom: 32px; }
  .meta-card {
    background: var(--cream);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 18px;
  }
  .meta-card .label { font-size: 0.72rem; font-weight: 600; text-transform: uppercase; letter-spacing: 1px; color: var(--muted); margin-bottom: 4px; }
  .meta-card .value { font-size: 1rem; font-weight: 600; color: var(--ink); }
  .feature-list { list-style: none; }
  .feature-list li {
    display: flex; align-items: flex-start; gap: 12px;
    padding: 10px 0; border-bottom: 1px solid var(--border);
    font-size: 0.95rem;
  }
  .feature-list li:last-child { border: none; }
  .check { width: 20px; height: 20px; min-width: 20px; background: var(--emerald-light); border-radius: 50%; display: flex; align-items: center; justify-content: center; margin-top: 2px; }
  .check::before { content: '✓'; font-size: 11px; color: var(--emerald); font-weight: 700; }
  .course-image {
    width: 100%; aspect-ratio: 4/3;
    background: linear-gradient(135deg, #1a1917, #0e2118);
    border-radius: var(--radius);
    display: flex; align-items: center; justify-content: center;
    position: relative; overflow: hidden;
  }
  .course-image-inner { text-align: center; color: rgba(255,255,255,0.6); font-size: 0.85rem; }
  .course-image-inner .icon { font-size: 4rem; margin-bottom: 12px; }
  .course-image::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; bottom: 0;
    background: radial-gradient(circle at 30% 40%, rgba(200,150,62,0.2), transparent 60%),
                radial-gradient(circle at 70% 70%, rgba(30,107,82,0.2), transparent 60%);
  }
  .details-actions { display: flex; gap: 12px; flex-wrap: wrap; margin-top: 28px; }

  /* ─── SYLLABUS ────────────────────────────────────────── */
  #syllabus { background: var(--warm); }
  .syllabus-controls { display: flex; gap: 12px; margin-bottom: 32px; flex-wrap: wrap; align-items: center; }
  .syllabus-wrapper { transition: all 0.4s ease; overflow: hidden; }
  .accordion-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    margin-bottom: 12px;
    overflow: hidden;
  }
  .accordion-header {
    width: 100%; text-align: left;
    background: none; border: none; cursor: pointer;
    padding: 18px 22px;
    display: flex; align-items: center; justify-content: space-between;
    font-family: 'DM Sans', sans-serif;
    font-size: 1rem; font-weight: 600; color: var(--ink);
    transition: background 0.15s;
  }
  .accordion-header:hover { background: var(--cream); }
  .accordion-header .acc-left { display: flex; align-items: center; gap: 14px; }
  .acc-num {
    width: 32px; height: 32px;
    background: var(--emerald); color: #fff;
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-size: 0.8rem; font-weight: 700;
    flex-shrink: 0;
  }
  .acc-meta { font-size: 0.78rem; font-weight: 400; color: var(--muted); margin-top: 1px; }
  .acc-icon {
    width: 28px; height: 28px; border-radius: 50%;
    background: var(--cream); display: flex; align-items: center; justify-content: center;
    font-size: 0.75rem; color: var(--muted);
    transition: transform 0.3s;
    flex-shrink: 0;
  }
  .accordion-item.open .acc-icon { transform: rotate(180deg); }
  .accordion-body {
    max-height: 0; overflow: hidden;
    transition: max-height 0.35s ease, padding 0.35s;
    padding: 0 22px;
  }
  .accordion-item.open .accordion-body { max-height: 600px; padding: 0 22px 20px; }
  .topic-list { list-style: none; display: grid; grid-template-columns: 1fr 1fr; gap: 6px 20px; }
  .topic-list li { font-size: 0.88rem; color: var(--muted); padding: 4px 0; padding-left: 14px; position: relative; }
  .topic-list li::before { content: '→'; position: absolute; left: 0; color: var(--gold); font-size: 0.78rem; }

  /* ─── FEE CALCULATOR ─────────────────────────────────── */
  #fee-calc { background: var(--card); }
  .calc-wrapper {
    max-width: 560px;
    background: var(--cream); border: 1px solid var(--border);
    border-radius: var(--radius); padding: 36px;
  }
  .calc-title { font-family: 'Playfair Display', serif; font-size: 1.4rem; font-weight: 700; margin-bottom: 28px; }
  .calc-field { margin-bottom: 22px; }
  .calc-field label { display: block; font-size: 0.85rem; font-weight: 600; margin-bottom: 8px; color: var(--ink); }
  .calc-field select, .calc-field input {
    width: 100%; padding: 11px 14px;
    border: 1.5px solid var(--border); border-radius: 9px;
    font-family: 'DM Sans', sans-serif; font-size: 0.95rem;
    background: var(--card); color: var(--ink);
    outline: none; transition: border 0.2s;
  }
  .calc-field select:focus, .calc-field input:focus { border-color: var(--gold); }
  .calc-result {
    background: var(--ink); color: #fff;
    border-radius: 10px; padding: 24px;
    margin-top: 20px; display: none;
  }
  .calc-result.visible { display: block; }
  .calc-row { display: flex; justify-content: space-between; align-items: center; padding: 7px 0; font-size: 0.92rem; }
  .calc-row.total { border-top: 1px solid rgba(255,255,255,0.15); padding-top: 14px; margin-top: 6px; }
  .calc-row.total span:last-child { font-size: 1.4rem; font-weight: 700; color: var(--gold); }
  .calc-row span:first-child { color: rgba(255,255,255,0.65); }
  .discount-badge {
    display: inline-flex; align-items: center; gap: 6px;
    background: rgba(30,107,82,0.3); color: #6fddb0;
    font-size: 0.8rem; font-weight: 600; padding: 3px 10px; border-radius: 100px;
    margin-left: 8px;
  }

  /* ─── TESTIMONIALS SLIDER ─────────────────────────────── */
  #testimonials { background: linear-gradient(135deg, #0f0e0c, #1a1917); }
  #testimonials .section-title { color: #fff; }
  #testimonials .section-label { color: var(--gold); }
  .slider-wrap { position: relative; overflow: hidden; border-radius: var(--radius); }
  .slider-track { display: flex; transition: transform 0.5s cubic-bezier(.4,0,.2,1); }
  .slide {
    min-width: 100%; padding: 48px 52px;
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: var(--radius);
  }
  .slide-quote {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.1rem, 2vw, 1.3rem);
    font-style: italic; line-height: 1.65;
    color: rgba(255,255,255,0.85);
    margin-bottom: 28px;
  }
  .slide-author { display: flex; align-items: center; gap: 14px; }
  .slide-avatar {
    width: 48px; height: 48px; border-radius: 50%;
    background: var(--gold); display: flex; align-items: center; justify-content: center;
    font-weight: 700; font-size: 1rem; color: var(--ink); flex-shrink: 0;
  }
  .slide-name { font-weight: 600; color: #fff; font-size: 0.95rem; }
  .slide-role { font-size: 0.8rem; color: rgba(255,255,255,0.5); }
  .slide-stars { color: var(--gold); font-size: 0.85rem; margin-top: 2px; letter-spacing: 2px; }
  .slider-controls { display: flex; align-items: center; gap: 14px; margin-top: 28px; }
  .slider-btn {
    width: 42px; height: 42px; border-radius: 50%;
    background: rgba(255,255,255,0.08); border: 1px solid rgba(255,255,255,0.15);
    color: #fff; cursor: pointer; font-size: 1rem;
    display: flex; align-items: center; justify-content: center;
    transition: all 0.2s;
  }
  .slider-btn:hover { background: var(--gold); border-color: var(--gold); color: var(--ink); }
  .slider-dots { display: flex; gap: 8px; }
  .slider-dot {
    width: 8px; height: 8px; border-radius: 50%;
    background: rgba(255,255,255,0.25);
    cursor: pointer; transition: all 0.3s;
  }
  .slider-dot.active { width: 24px; border-radius: 4px; background: var(--gold); }

  /* ─── CONTACT ────────────────────────────────────────── */
  #contact { background: var(--warm); }
  .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 60px; align-items: start; }
  .contact-card {
    background: var(--card); border: 1px solid var(--border);
    border-radius: var(--radius); padding: 32px;
  }
  .contact-info-item { display: flex; align-items: flex-start; gap: 14px; padding: 16px 0; border-bottom: 1px solid var(--border); }
  .contact-info-item:last-child { border: none; }
  .contact-icon {
    width: 40px; height: 40px; min-width: 40px;
    background: var(--emerald-light); border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.1rem;
  }
  .contact-label { font-size: 0.78rem; font-weight: 600; text-transform: uppercase; letter-spacing: 0.8px; color: var(--muted); margin-bottom: 3px; }
  .contact-val { font-size: 0.95rem; font-weight: 500; }
  .form-group { margin-bottom: 18px; }
  .form-group label { display: block; font-size: 0.85rem; font-weight: 600; margin-bottom: 7px; }
  .form-group input, .form-group textarea, .form-group select {
    width: 100%; padding: 11px 14px;
    border: 1.5px solid var(--border); border-radius: 9px;
    font-family: 'DM Sans', sans-serif; font-size: 0.93rem;
    background: var(--cream); color: var(--ink);
    outline: none; transition: border 0.2s;
    resize: vertical;
  }
  .form-group input:focus, .form-group textarea:focus, .form-group select:focus { border-color: var(--gold); }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  #form-msg { padding: 12px 16px; border-radius: 8px; font-size: 0.88rem; margin-top: 12px; display: none; }
  #form-msg.success { background: var(--emerald-light); color: var(--emerald); display: block; }
  #form-msg.error { background: #fde8e8; color: var(--ruby); display: block; }

  /* ─── FOOTER ─────────────────────────────────────────── */
  footer {
    background: #0f0e0c; color: rgba(255,255,255,0.5);
    text-align: center; padding: 36px 5%;
    font-size: 0.85rem;
  }
  footer strong { color: var(--gold); }

  /* ─── RESPONSIVE ──────────────────────────────────────── */
  @media (max-width: 768px) {
    .nav-links { display: none; flex-direction: column; position: absolute; top: var(--nav-h); left: 0; right: 0; background: #0f0e0c; padding: 20px; gap: 4px; }
    .nav-links.open { display: flex; }
    .hamburger { display: flex; margin-left: auto; }
    .details-grid, .contact-grid { grid-template-columns: 1fr; gap: 36px; }
    .topic-list { grid-template-columns: 1fr; }
    .form-row { grid-template-columns: 1fr; }
    .hero-stats { gap: 20px; flex-wrap: wrap; }
    .slide { padding: 32px 24px; }
    .details-actions { flex-direction: column; }
    .details-actions .btn { justify-content: center; }
  }

  /* ─── SCROLL REVEAL ───────────────────────────────────── */
  .reveal { opacity: 0; transform: translateY(28px); transition: opacity 0.6s ease, transform 0.6s ease; }
  .reveal.visible { opacity: 1; transform: none; }
</style>
</head>
<body>

<!-- ═══ NAV ════════════════════════════════════════════════ -->
<nav>
  <a class="nav-brand" href="#home">LearnForge</a>
  <ul class="nav-links" id="nav-links">
    <li><a href="#home">Home</a></li>
    <li><a href="#course-details">Course Details</a></li>
    <li><a href="#syllabus">Syllabus</a></li>
    <li><a href="#fee-calc">Fee Calculator</a></li>
    <li><a href="#testimonials">Reviews</a></li>
    <li><a href="#contact" class="btn-nav">Contact</a></li>
  </ul>
  <button class="hamburger" id="hamburger" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- ═══ HOME ═══════════════════════════════════════════════ -->
<section id="home">
  <div class="hero-inner">
    <div class="hero-badge"><span></span>Now Enrolling — Batch 2025</div>
    <h1 class="hero-title">Master <em>Full-Stack</em><br>Web Development</h1>
    <p class="hero-sub">A rigorous, project-driven course that takes you from HTML beginner to deploying production-ready applications — in 6 months.</p>
    <div class="hero-stats">
      <div class="hero-stat"><strong>6</strong><span>Months</span></div>
      <div class="hero-stat"><strong>120+</strong><span>Hours Live</span></div>
      <div class="hero-stat"><strong>4,800+</strong><span>Graduates</span></div>
      <div class="hero-stat"><strong>93%</strong><span>Placed</span></div>
    </div>
    <div class="hero-cta">
      <a href="#contact" class="btn btn-primary">Enroll Now →</a>
      <a href="#syllabus" class="btn btn-outline">View Syllabus</a>
    </div>
  </div>
</section>

<!-- ═══ COURSE DETAILS ══════════════════════════════════════ -->
<section id="course-details">
  <div class="reveal">
    <p class="section-label">About the Course</p>
    <h2 class="section-title">Everything You Need to Know</h2>
    <div class="divider"></div>
  </div>
  <div class="details-grid">
    <div class="reveal">
      <div class="details-meta">
        <div class="meta-card"><div class="label">Duration</div><div class="value">6 Months</div></div>
        <div class="meta-card"><div class="label">Mode</div><div class="value">Online + Live</div></div>
        <div class="meta-card"><div class="label">Level</div><div class="value">Beginner → Pro</div></div>
        <div class="meta-card"><div class="label">Certificate</div><div class="value">Industry-Verified</div></div>
        <div class="meta-card"><div class="label">Batch Size</div><div class="value">Max 40 Students</div></div>
        <div class="meta-card"><div class="label">Placement</div><div class="value">Guaranteed*</div></div>
      </div>
      <ul class="feature-list">
        <li><span class="check"></span>HTML, CSS, JavaScript — from ground up</li>
        <li><span class="check"></span>React.js for frontend development</li>
        <li><span class="check"></span>Node.js + Express.js backend</li>
        <li><span class="check"></span>MongoDB & SQL databases</li>
        <li><span class="check"></span>Cloud deployment (AWS / Vercel)</li>
        <li><span class="check"></span>Git, GitHub, CI/CD workflows</li>
        <li><span class="check"></span>3 capstone portfolio projects</li>
        <li><span class="check"></span>1-on-1 mentorship sessions</li>
      </ul>
      <div class="details-actions">
        <a href="#syllabus" class="btn btn-emerald">View Syllabus</a>
        <a href="#fee-calc" class="btn btn-primary">Calculate Fees</a>
        <a href="#contact" class="btn btn-outline" style="border-color:var(--border);color:var(--ink)">Contact Us</a>
      </div>
    </div>
    <div class="reveal" style="transition-delay:0.15s">
      <div class="course-image">
        <div class="course-image-inner">
          <div class="icon">💻</div>
          <p>Full-Stack Web Development</p>
          <p style="margin-top:6px;font-size:0.75rem;">React · Node · MongoDB · AWS</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ SYLLABUS ═════════════════════════════════════════════ -->
<section id="syllabus">
  <div class="reveal">
    <p class="section-label">Curriculum</p>
    <h2 class="section-title">Course Syllabus</h2>
    <div class="divider"></div>
    <p class="section-sub">Six carefully structured modules, building skill on skill.</p>
  </div>
  <div class="syllabus-controls reveal">
    <button class="btn btn-emerald" id="btn-show-syllabus" onclick="toggleSyllabus(true)">View Syllabus</button>
    <button class="btn btn-outline" id="btn-hide-syllabus" style="border-color:var(--border);color:var(--ink)" onclick="toggleSyllabus(false)">Hide Syllabus</button>
    <button class="btn btn-primary" onclick="expandAll()">Expand All</button>
  </div>
  <div class="syllabus-wrapper reveal" id="syllabus-wrapper">
    <div id="accordion-container"></div>
  </div>
</section>

<!-- ═══ FEE CALCULATOR ═══════════════════════════════════════ -->
<section id="fee-calc">
  <div class="reveal">
    <p class="section-label">Pricing</p>
    <h2 class="section-title">Fee Calculator</h2>
    <div class="divider"></div>
    <p class="section-sub">Choose your plan, apply a discount code, and see your final fee instantly.</p>
  </div>
  <div class="calc-wrapper reveal">
    <h3 class="calc-title">Calculate Your Course Fee</h3>
    <div class="calc-field">
      <label>Select Plan</label>
      <select id="plan-select" onchange="calcFee()">
        <option value="29999">Standard Plan — ₹29,999</option>
        <option value="39999">Pro Plan — ₹39,999 (includes mentorship)</option>
        <option value="49999">Elite Plan — ₹49,999 (placement guarantee)</option>
      </select>
    </div>
    <div class="calc-field">
      <label>Payment Mode</label>
      <select id="payment-mode" onchange="calcFee()">
        <option value="0">Full Payment (no extra charge)</option>
        <option value="5">EMI — 3 months (+5% processing)</option>
        <option value="8">EMI — 6 months (+8% processing)</option>
      </select>
    </div>
    <div class="calc-field">
      <label>Discount Code</label>
      <div style="display:flex;gap:10px;">
        <input type="text" id="discount-code" placeholder="e.g. EARLY20 · STUDENT10 · REFER15" style="flex:1" />
        <button class="btn btn-primary" style="padding:11px 20px;border-radius:9px;font-size:0.9rem" onclick="applyDiscount()">Apply Discount</button>
      </div>
      <p id="discount-msg" style="font-size:0.82rem;margin-top:7px;color:var(--muted)"></p>
    </div>
    <button class="btn btn-emerald" style="width:100%;justify-content:center;padding:14px" onclick="calcFee()">Calculate Fee</button>
    <div class="calc-result" id="calc-result">
      <div class="calc-row"><span>Base Fee</span><span id="r-base">—</span></div>
      <div class="calc-row"><span>EMI Surcharge</span><span id="r-emi">—</span></div>
      <div class="calc-row"><span id="r-disc-label">Discount</span><span id="r-disc">—</span></div>
      <div class="calc-row total"><span>Total Payable</span><span id="r-total">—</span></div>
    </div>
  </div>
</section>

<!-- ═══ TESTIMONIALS / SLIDER ════════════════════════════════ -->
<section id="testimonials">
  <div class="reveal">
    <p class="section-label">Student Reviews</p>
    <h2 class="section-title">What Our Graduates Say</h2>
    <div class="divider"></div>
  </div>
  <div class="reveal">
    <div class="slider-wrap">
      <div class="slider-track" id="slider-track"></div>
    </div>
    <div class="slider-controls">
      <button class="slider-btn" onclick="slide(-1)">&#8592;</button>
      <div class="slider-dots" id="slider-dots"></div>
      <button class="slider-btn" onclick="slide(1)">&#8594;</button>
    </div>
  </div>
</section>

<!-- ═══ CONTACT ══════════════════════════════════════════════ -->
<section id="contact">
  <div class="reveal">
    <p class="section-label">Get In Touch</p>
    <h2 class="section-title">Contact & Enroll</h2>
    <div class="divider"></div>
  </div>
  <div class="contact-grid">
    <div class="reveal">
      <div class="contact-card">
        <h3 style="font-family:'Playfair Display',serif;font-size:1.2rem;margin-bottom:16px">Reach Us Directly</h3>
        <div class="contact-info-item">
          <div class="contact-icon">📧</div>
          <div><div class="contact-label">Email</div><div class="contact-val">admissions@learnforge.in</div></div>
        </div>
        <div class="contact-info-item">
          <div class="contact-icon">📞</div>
          <div><div class="contact-label">Phone / WhatsApp</div><div class="contact-val">+91 98765 43210</div></div>
        </div>
        <div class="contact-info-item">
          <div class="contact-icon">📍</div>
          <div><div class="contact-label">Address</div><div class="contact-val">LearnForge Pvt. Ltd., Ahmedabad, Gujarat</div></div>
        </div>
        <div class="contact-info-item">
          <div class="contact-icon">🕐</div>
          <div><div class="contact-label">Office Hours</div><div class="contact-val">Mon–Sat, 9 AM – 7 PM IST</div></div>
        </div>
      </div>
    </div>
    <div class="reveal" style="transition-delay:0.15s">
      <div class="contact-card">
        <h3 style="font-family:'Playfair Display',serif;font-size:1.2rem;margin-bottom:20px">Enrollment Form</h3>
        <div class="form-row">
          <div class="form-group"><label>First Name</label><input type="text" id="fname" placeholder="Riya" /></div>
          <div class="form-group"><label>Last Name</label><input type="text" id="lname" placeholder="Sharma" /></div>
        </div>
        <div class="form-group"><label>Email Address</label><input type="email" id="femail" placeholder="riya@example.com" /></div>
        <div class="form-group"><label>Phone Number</label><input type="tel" id="fphone" placeholder="+91 98765 43210" /></div>
        <div class="form-group">
          <label>Interested Plan</label>
          <select id="fplan">
            <option>Standard Plan — ₹29,999</option>
            <option>Pro Plan — ₹39,999</option>
            <option>Elite Plan — ₹49,999</option>
          </select>
        </div>
        <div class="form-group"><label>Message (optional)</label><textarea id="fmsg" rows="3" placeholder="Any questions or requirements..."></textarea></div>
        <button class="btn btn-primary" style="width:100%;justify-content:center;padding:14px;font-size:1rem" onclick="submitForm()">Enroll Now →</button>
        <div id="form-msg"></div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ FOOTER ═══════════════════════════════════════════════ -->
<footer>
  <p style="margin-bottom:8px;font-size:1rem"><strong>LearnForge</strong></p>
  <p>© 2025 LearnForge Pvt. Ltd. · Full-Stack Web Development Course · Ahmedabad, India</p>
  <p style="margin-top:6px;font-size:0.78rem">Built with HTML · CSS · JavaScript &nbsp;|&nbsp; IWP Project Submission</p>
</footer>

<script>
// ─── DATA ───────────────────────────────────────────────────
const modules = [
  {
    num:'01', title:'Web Foundations', meta:'4 weeks · 18 hours',
    topics:['HTML5 semantics','CSS3 & Flexbox','CSS Grid layouts','Responsive design','Bootstrap 5','Media queries','Forms & validation','Git basics']
  },
  {
    num:'02', title:'JavaScript Essentials', meta:'4 weeks · 22 hours',
    topics:['Variables & data types','Functions & scope','DOM manipulation','Events & listeners','Fetch API & AJAX','ES6+ syntax','Promises & async/await','Error handling']
  },
  {
    num:'03', title:'React.js Frontend', meta:'5 weeks · 28 hours',
    topics:['JSX & components','Props & state','React Hooks','Context API','React Router','Form handling','API integration','Performance optimisation']
  },
  {
    num:'04', title:'Node.js & Express', meta:'4 weeks · 22 hours',
    topics:['Node.js runtime','Express.js setup','REST API design','Middleware','Authentication & JWT','File uploads','Rate limiting','Error middleware']
  },
  {
    num:'05', title:'Databases', meta:'3 weeks · 16 hours',
    topics:['MongoDB Atlas','Mongoose ODM','SQL & MySQL','Joins & indexes','Schema design','CRUD operations','Aggregation pipelines','Transactions']
  },
  {
    num:'06', title:'Deployment & Capstone', meta:'4 weeks · 18 hours',
    topics:['AWS EC2 & S3','Vercel & Netlify','Docker basics','CI/CD with GitHub Actions','Environment variables','SSL & security','Portfolio projects','Resume & interview prep']
  }
];

const testimonials = [
  {
    quote:"LearnForge completely changed my career. I went from knowing nothing about code to landing a job as a junior developer at a product startup — all within three months of graduating.",
    name:"Priya Nair", role:"Frontend Developer · Bangalore", initials:"PN", stars:"★★★★★"
  },
  {
    quote:"The fee calculator and transparent pricing made it easy to plan financially. But the real value was in the quality of instruction and the supportive community. Worth every rupee.",
    name:"Arjun Mehta", role:"Full-Stack Engineer · Pune", initials:"AM", stars:"★★★★★"
  },
  {
    quote:"I was a BCA graduate with no practical experience. After the Elite plan I had three portfolio projects and a placement offer. The mentorship sessions made all the difference.",
    name:"Sneha Gupta", role:"Software Developer · Hyderabad", initials:"SG", stars:"★★★★☆"
  },
  {
    quote:"The accordion-style curriculum helped me understand the learning journey before enrolling. Each module built naturally on the previous one — no confusion, no gaps.",
    name:"Rohan Desai", role:"React Developer · Mumbai", initials:"RD", stars:"★★★★★"
  }
];

const discountCodes = {
  'EARLY20': { pct: 20, label: '✓ Early Bird 20% applied!' },
  'STUDENT10': { pct: 10, label: '✓ Student 10% applied!' },
  'REFER15': { pct: 15, label: '✓ Referral 15% applied!' },
  'WELCOME5': { pct: 5, label: '✓ Welcome 5% applied!' }
};

// ─── STATE ──────────────────────────────────────────────────
let activeDiscount = 0;
let sliderIdx = 0;
let sliderTimer;

// ─── ACCORDION BUILD ─────────────────────────────────────────
function buildAccordion() {
  const c = document.getElementById('accordion-container');
  modules.forEach((m, i) => {
    const item = document.createElement('div');
    item.className = 'accordion-item';
    item.id = 'acc-' + i;
    item.innerHTML = `
      <button class="accordion-header" onclick="toggleAcc(${i})">
        <div class="acc-left">
          <div class="acc-num">${m.num}</div>
          <div>
            <div>${m.title}</div>
            <div class="acc-meta">${m.meta}</div>
          </div>
        </div>
        <div class="acc-icon">▾</div>
      </button>
      <div class="accordion-body">
        <ul class="topic-list">
          ${m.topics.map(t => `<li>${t}</li>`).join('')}
        </ul>
      </div>`;
    c.appendChild(item);
  });
}

function toggleAcc(idx) {
  const item = document.getElementById('acc-' + idx);
  const wasOpen = item.classList.contains('open');
  document.querySelectorAll('.accordion-item').forEach(el => el.classList.remove('open'));
  if (!wasOpen) item.classList.add('open');
}

function expandAll() {
  document.querySelectorAll('.accordion-item').forEach(el => el.classList.add('open'));
}

// ─── SHOW / HIDE SYLLABUS ─────────────────────────────────────
function toggleSyllabus(show) {
  const w = document.getElementById('syllabus-wrapper');
  if (show) {
    w.style.maxHeight = w.scrollHeight + 2000 + 'px';
    w.style.opacity = '1';
    w.style.overflow = 'visible';
  } else {
    w.style.maxHeight = '0';
    w.style.opacity = '0';
    w.style.overflow = 'hidden';
  }
}

// init syllabus visible
document.addEventListener('DOMContentLoaded', () => {
  buildAccordion();
  const w = document.getElementById('syllabus-wrapper');
  w.style.transition = 'max-height 0.5s ease, opacity 0.4s ease';
  w.style.overflow = 'hidden';
  w.style.maxHeight = '3000px';
  w.style.opacity = '1';
  buildSlider();
  startSliderAuto();
  setupReveal();
});

// ─── FEE CALCULATOR ──────────────────────────────────────────
function applyDiscount() {
  const code = document.getElementById('discount-code').value.trim().toUpperCase();
  const msg = document.getElementById('discount-msg');
  if (discountCodes[code]) {
    activeDiscount = discountCodes[code].pct;
    msg.style.color = 'var(--emerald)';
    msg.textContent = discountCodes[code].label;
  } else if (code === '') {
    msg.style.color = 'var(--ruby)';
    msg.textContent = '✗ Please enter a discount code.';
    activeDiscount = 0;
  } else {
    msg.style.color = 'var(--ruby)';
    msg.textContent = '✗ Invalid code. Try EARLY20, STUDENT10, REFER15, or WELCOME5.';
    activeDiscount = 0;
  }
  calcFee();
}

function calcFee() {
  const base = parseInt(document.getElementById('plan-select').value);
  const emiPct = parseInt(document.getElementById('payment-mode').value);
  const emiCharge = Math.round(base * emiPct / 100);
  const subtotal = base + emiCharge;
  const discAmt = Math.round(subtotal * activeDiscount / 100);
  const total = subtotal - discAmt;

  const fmt = n => '₹' + n.toLocaleString('en-IN');
  document.getElementById('r-base').textContent = fmt(base);
  document.getElementById('r-emi').textContent = emiPct > 0 ? '+' + fmt(emiCharge) + ' (' + emiPct + '%)' : 'None';
  document.getElementById('r-disc-label').innerHTML = 'Discount' + (activeDiscount > 0 ? `<span class="discount-badge">−${activeDiscount}%</span>` : '');
  document.getElementById('r-disc').textContent = discAmt > 0 ? '−' + fmt(discAmt) : 'None';
  document.getElementById('r-total').textContent = fmt(total);
  document.getElementById('calc-result').classList.add('visible');
}

// ─── SLIDER ──────────────────────────────────────────────────
function buildSlider() {
  const track = document.getElementById('slider-track');
  const dots = document.getElementById('slider-dots');
  testimonials.forEach((t, i) => {
    const slide = document.createElement('div');
    slide.className = 'slide';
    slide.innerHTML = `
      <p class="slide-quote">"${t.quote}"</p>
      <div class="slide-author">
        <div class="slide-avatar">${t.initials}</div>
        <div>
          <div class="slide-name">${t.name}</div>
          <div class="slide-role">${t.role}</div>
          <div class="slide-stars">${t.stars}</div>
        </div>
      </div>`;
    track.appendChild(slide);
    const dot = document.createElement('div');
    dot.className = 'slider-dot' + (i === 0 ? ' active' : '');
    dot.onclick = () => goSlide(i);
    dots.appendChild(dot);
  });
}

function goSlide(idx) {
  sliderIdx = (idx + testimonials.length) % testimonials.length;
  document.getElementById('slider-track').style.transform = `translateX(-${sliderIdx * 100}%)`;
  document.querySelectorAll('.slider-dot').forEach((d, i) => {
    d.classList.toggle('active', i === sliderIdx);
  });
}

function slide(dir) {
  clearInterval(sliderTimer);
  goSlide(sliderIdx + dir);
  startSliderAuto();
}

function startSliderAuto() {
  sliderTimer = setInterval(() => goSlide(sliderIdx + 1), 5000);
}

// ─── CONTACT FORM ─────────────────────────────────────────────
function submitForm() {
  const fname = document.getElementById('fname').value.trim();
  const lname = document.getElementById('lname').value.trim();
  const email = document.getElementById('femail').value.trim();
  const phone = document.getElementById('fphone').value.trim();
  const msg = document.getElementById('form-msg');
  if (!fname || !email || !phone) {
    msg.className = 'error';
    msg.textContent = '✗ Please fill in First Name, Email, and Phone.';
    return;
  }
  if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) {
    msg.className = 'error';
    msg.textContent = '✗ Please enter a valid email address.';
    return;
  }
  msg.className = 'success';
  msg.textContent = `✓ Thank you, ${fname}! Your enrollment request has been received. We'll contact you within 24 hours.`;
  ['fname','lname','femail','fphone','fmsg'].forEach(id => document.getElementById(id).value = '');
}

// ─── NAV HAMBURGER ────────────────────────────────────────────
document.getElementById('hamburger').onclick = () => {
  document.getElementById('nav-links').classList.toggle('open');
};
document.querySelectorAll('.nav-links a').forEach(a => {
  a.addEventListener('click', () => document.getElementById('nav-links').classList.remove('open'));
});

// ─── SCROLL REVEAL ────────────────────────────────────────────
function setupReveal() {
  const els = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); io.unobserve(e.target); } });
  }, { threshold: 0.12 });
  els.forEach(el => io.observe(el));
}
</script>
</body>
</html>
