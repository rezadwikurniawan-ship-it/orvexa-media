<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Orvexa Media — Media Intelektual Indonesia</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400;1,500&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,400&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --dark: #1e1f26;
    --dark-2: #2b2d3a;
    --mid: #5a5c6e;
    --muted: #9a9baa;
    --light: #e8e7e2;
    --cream: #f4f2ec;
    --warm: #c9b99a;
    --bg: #f7f5f0;
    --white: #ffffff;
    --serif: 'Cormorant Garamond', Georgia, serif;
    --sans: 'DM Sans', system-ui, sans-serif;
    --transition: 0.22s ease;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: var(--sans);
    background: var(--bg);
    color: var(--dark);
    font-size: 16px;
    line-height: 1.6;
    min-height: 100vh;
  }

  /* ── NAVIGATION ── */
  .nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.1rem 3rem;
    background: rgba(247, 245, 240, 0.92);
    backdrop-filter: blur(12px);
    border-bottom: 0.5px solid rgba(90,92,110,0.15);
  }
  .nav-logo { display: flex; align-items: center; gap: 10px; text-decoration: none; }
  .nav-monogram {
    width: 38px; height: 38px; border-radius: 50%;
    border: 1px solid rgba(90,92,110,0.25);
    display: flex; align-items: center; justify-content: center;
    font-family: var(--serif); font-size: 16px; font-weight: 600;
    color: var(--dark); background: var(--white);
    letter-spacing: 0.02em;
  }
  .nav-text { display: flex; flex-direction: column; }
  .nav-brand { font-size: 14px; font-weight: 500; color: var(--dark); letter-spacing: 0.1em; text-transform: uppercase; line-height: 1; }
  .nav-sub { font-size: 10px; color: var(--muted); letter-spacing: 0.18em; text-transform: uppercase; margin-top: 2px; }
  .nav-links { display: flex; gap: 2rem; align-items: center; list-style: none; }
  .nav-links a { font-size: 13px; color: var(--mid); text-decoration: none; letter-spacing: 0.04em; transition: color var(--transition); }
  .nav-links a:hover { color: var(--dark); }
  .nav-links .nav-cta {
    padding: 8px 20px; background: var(--dark); color: var(--white);
    border-radius: 2px; font-size: 12px; letter-spacing: 0.08em; text-transform: uppercase;
    transition: background var(--transition);
  }
  .nav-cta:hover { background: var(--dark-2) !important; color: var(--white) !important; }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: flex; flex-direction: column; justify-content: flex-end;
    padding: 0 3rem 5rem;
    position: relative;
    overflow: hidden;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse 60% 50% at 70% 40%, rgba(201,185,154,0.18) 0%, transparent 70%),
      radial-gradient(ellipse 40% 60% at 20% 80%, rgba(90,92,110,0.08) 0%, transparent 60%),
      var(--bg);
  }
  .hero-date {
    font-size: 11px; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--muted); margin-bottom: 2rem; position: relative; z-index: 1;
    display: flex; align-items: center; gap: 1rem;
  }
  .hero-date::before { content: ''; display: block; width: 40px; height: 0.5px; background: var(--warm); }
  .hero-eyebrow {
    font-size: 12px; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--muted); margin-bottom: 1.25rem; position: relative; z-index: 1;
  }
  .hero-title {
    font-family: var(--serif);
    font-size: clamp(52px, 8vw, 96px);
    font-weight: 500; line-height: 0.95;
    color: var(--dark); letter-spacing: -0.02em;
    position: relative; z-index: 1; margin-bottom: 1.75rem;
  }
  .hero-title em { font-style: italic; color: var(--mid); }
  .hero-desc {
    font-size: 16px; color: var(--mid); line-height: 1.8;
    max-width: 480px; position: relative; z-index: 1; margin-bottom: 2.5rem;
  }
  .hero-actions { display: flex; gap: 1rem; position: relative; z-index: 1; flex-wrap: wrap; }
  .btn-dark {
    padding: 13px 32px; background: var(--dark); color: var(--white);
    border: none; border-radius: 2px; font-family: var(--sans);
    font-size: 13px; letter-spacing: 0.08em; text-transform: uppercase;
    cursor: pointer; text-decoration: none; display: inline-block;
    transition: background var(--transition);
  }
  .btn-dark:hover { background: var(--dark-2); }
  .btn-outline {
    padding: 13px 32px; background: transparent; color: var(--dark);
    border: 0.5px solid rgba(90,92,110,0.4); border-radius: 2px; font-family: var(--sans);
    font-size: 13px; letter-spacing: 0.08em; text-transform: uppercase;
    cursor: pointer; text-decoration: none; display: inline-block;
    transition: all var(--transition);
  }
  .btn-outline:hover { background: var(--dark); color: var(--white); border-color: var(--dark); }
  .hero-scroll {
    position: absolute; right: 3rem; bottom: 3rem; z-index: 1;
    display: flex; flex-direction: column; align-items: center; gap: 8px;
  }
  .hero-scroll-text { font-size: 10px; letter-spacing: 0.2em; text-transform: uppercase; color: var(--muted); writing-mode: vertical-rl; }
  .hero-scroll-line { width: 0.5px; height: 48px; background: var(--warm); }

  /* ── SECTIONS ── */
  section { padding: 6rem 3rem; }
  .section-inner { max-width: 960px; margin: 0 auto; }
  .section-label {
    font-size: 11px; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--muted); margin-bottom: 2.5rem;
    display: flex; align-items: center; gap: 1rem;
  }
  .section-label::after { content: ''; flex: 1; height: 0.5px; background: rgba(90,92,110,0.2); }
  .section-title {
    font-family: var(--serif); font-size: clamp(28px, 4vw, 42px);
    font-weight: 500; color: var(--dark); line-height: 1.2;
    margin-bottom: 1.25rem; letter-spacing: -0.01em;
  }
  .section-desc { font-size: 15px; color: var(--mid); line-height: 1.8; max-width: 560px; }

  /* ── ABOUT ── */
  .about { background: var(--white); }
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: start; margin-top: 3rem; }
  .about-left {}
  .about-right { padding-top: 1rem; }
  .about-quote {
    font-family: var(--serif); font-size: 22px; font-style: italic;
    color: var(--dark); line-height: 1.65; margin-bottom: 1.5rem;
    padding-left: 1.5rem; border-left: 2px solid var(--warm);
  }
  .about-text { font-size: 14px; color: var(--mid); line-height: 1.85; }
  .about-founder { display: flex; align-items: center; gap: 12px; margin-top: 2rem; padding-top: 1.5rem; border-top: 0.5px solid rgba(90,92,110,0.12); }
  .founder-av {
    width: 48px; height: 48px; border-radius: 50%;
    background: var(--cream); border: 1px solid rgba(90,92,110,0.2);
    display: flex; align-items: center; justify-content: center;
    font-family: var(--serif); font-size: 16px; font-weight: 500; color: var(--dark); flex-shrink: 0;
  }
  .founder-name { font-size: 14px; font-weight: 500; color: var(--dark); }
  .founder-role { font-size: 11px; color: var(--muted); letter-spacing: 0.08em; text-transform: uppercase; margin-top: 2px; }

  /* ── PILLARS ── */
  .pillars { background: var(--cream); }
  .pillars-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-top: 3rem; }
  .pillar-card {
    background: var(--white); border: 0.5px solid rgba(90,92,110,0.12);
    border-radius: 4px; padding: 2.5rem;
    transition: transform var(--transition), box-shadow var(--transition);
    position: relative; overflow: hidden;
  }
  .pillar-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px; background: var(--warm); transform: scaleX(0); transform-origin: left; transition: transform var(--transition); }
  .pillar-card:hover { transform: translateY(-3px); box-shadow: 0 12px 32px rgba(30,31,38,0.08); }
  .pillar-card:hover::before { transform: scaleX(1); }
  .pillar-num { font-size: 11px; letter-spacing: 0.16em; text-transform: uppercase; color: var(--warm); margin-bottom: 1.25rem; }
  .pillar-icon { font-size: 28px; color: var(--muted); margin-bottom: 1.25rem; line-height: 1; }
  .pillar-name { font-family: var(--serif); font-size: 26px; font-weight: 500; color: var(--dark); margin-bottom: 0.75rem; }
  .pillar-desc { font-size: 14px; color: var(--mid); line-height: 1.75; margin-bottom: 1.5rem; }
  .pillar-tags { display: flex; flex-wrap: wrap; gap: 6px; }
  .ptag { padding: 4px 12px; border: 0.5px solid rgba(90,92,110,0.2); border-radius: 999px; font-size: 12px; color: var(--mid); }

  /* ── PRESS DETAIL ── */
  .press-detail { background: var(--white); }
  .formats-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin-top: 2rem; }
  .format-item { padding: 1.5rem; border: 0.5px solid rgba(90,92,110,0.1); border-radius: 4px; }
  .format-item-icon { font-size: 20px; color: var(--muted); margin-bottom: 0.75rem; }
  .format-item-title { font-size: 14px; font-weight: 500; color: var(--dark); margin-bottom: 4px; }
  .format-item-desc { font-size: 13px; color: var(--mid); line-height: 1.6; }

  .topics-wrap { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 2rem; }
  .topic-chip { display: flex; align-items: center; gap: 6px; padding: 7px 16px; border: 0.5px solid rgba(90,92,110,0.18); border-radius: 999px; font-size: 13px; color: var(--mid); background: var(--cream); }

  .principles-row { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 0; border: 0.5px solid rgba(90,92,110,0.12); border-radius: 4px; overflow: hidden; margin-top: 2rem; }
  .principle-box { padding: 1.75rem 1.25rem; text-align: center; border-right: 0.5px solid rgba(90,92,110,0.12); }
  .principle-box:last-child { border-right: none; }
  .principle-n { font-family: var(--serif); font-size: 32px; font-weight: 500; color: var(--dark); margin-bottom: 6px; }
  .principle-t { font-size: 13px; font-weight: 500; color: var(--dark); margin-bottom: 6px; }
  .principle-d { font-size: 12px; color: var(--muted); line-height: 1.6; }

  /* ── PUBLISHING DETAIL ── */
  .pub-detail { background: var(--cream); }
  .pub-process-row { display: grid; grid-template-columns: repeat(4, 1fr); gap: 0; border: 0.5px solid rgba(90,92,110,0.12); border-radius: 4px; overflow: hidden; margin-top: 2rem; }
  .pub-step { padding: 1.5rem 1rem; text-align: center; border-right: 0.5px solid rgba(90,92,110,0.12); background: var(--white); }
  .pub-step:last-child { border-right: none; }
  .pub-step-n { font-family: var(--serif); font-size: 28px; font-weight: 500; color: var(--dark); margin-bottom: 4px; }
  .pub-step-t { font-size: 13px; font-weight: 500; color: var(--dark); margin-bottom: 4px; }
  .pub-step-d { font-size: 12px; color: var(--muted); line-height: 1.55; }

  .open-box { background: var(--white); border: 0.5px solid rgba(90,92,110,0.12); border-radius: 4px; padding: 2rem; margin-top: 2rem; }
  .open-box-title { font-family: var(--serif); font-size: 20px; font-weight: 500; color: var(--dark); margin-bottom: 0.5rem; }
  .open-box-desc { font-size: 14px; color: var(--mid); line-height: 1.75; margin-bottom: 1.25rem; }
  .open-list { list-style: none; display: flex; flex-direction: column; gap: 8px; }
  .open-list li { font-size: 13px; color: var(--mid); display: flex; align-items: flex-start; gap: 10px; line-height: 1.55; }
  .open-list li::before { content: '✓'; color: var(--warm); font-weight: 600; flex-shrink: 0; margin-top: 1px; }

  /* ── ARTIKEL PERDANA ── */
  .artikel { background: var(--white); }
  .artikel-inner { max-width: 720px; margin: 0 auto; }
  .artikel-header { padding-bottom: 2rem; border-bottom: 0.5px solid rgba(90,92,110,0.12); margin-bottom: 2rem; }
  .artikel-cat { display: inline-block; padding: 4px 14px; border: 0.5px solid rgba(90,92,110,0.2); border-radius: 999px; font-size: 11px; letter-spacing: 0.12em; text-transform: uppercase; color: var(--mid); margin-bottom: 1.25rem; }
  .artikel-title { font-family: var(--serif); font-size: clamp(26px, 4vw, 38px); font-weight: 500; color: var(--dark); line-height: 1.25; margin-bottom: 1rem; letter-spacing: -0.01em; }
  .artikel-deck { font-family: var(--serif); font-size: 18px; font-style: italic; color: var(--mid); line-height: 1.7; margin-bottom: 1.5rem; }
  .artikel-meta { display: flex; align-items: center; gap: 1rem; flex-wrap: wrap; }
  .artikel-author { display: flex; align-items: center; gap: 10px; }
  .artikel-av { width: 36px; height: 36px; border-radius: 50%; background: var(--cream); border: 1px solid rgba(90,92,110,0.2); display: flex; align-items: center; justify-content: center; font-family: var(--serif); font-size: 13px; font-weight: 500; color: var(--dark); flex-shrink: 0; }
  .artikel-author-name { font-size: 13px; font-weight: 500; color: var(--dark); }
  .artikel-author-role { font-size: 11px; color: var(--muted); }
  .artikel-meta-sep { color: var(--light); }
  .artikel-meta-info { font-size: 12px; color: var(--muted); }
  .artikel-body p { font-size: 16px; color: var(--mid); line-height: 1.9; margin-bottom: 1.5rem; }
  .artikel-body p:last-child { margin-bottom: 0; }
  .artikel-body p.lead::first-letter { font-family: var(--serif); font-size: 4rem; font-weight: 500; float: left; line-height: 0.82; margin-right: 6px; margin-top: 6px; color: var(--dark); }
  .artikel-pullquote { padding: 0.75rem 1.5rem; border-left: 2px solid var(--warm); margin: 2rem 0; }
  .artikel-pullquote p { font-family: var(--serif); font-size: 20px; font-style: italic; color: var(--dark); line-height: 1.65; margin-bottom: 0 !important; }
  .artikel-subhead { font-family: var(--serif); font-size: 20px; font-weight: 500; color: var(--dark); margin-top: 0.5rem; margin-bottom: 0.75rem; }
  .artikel-tags { display: flex; gap: 6px; flex-wrap: wrap; margin-top: 2.5rem; padding-top: 1.5rem; border-top: 0.5px solid rgba(90,92,110,0.12); }
  .artikel-tag { padding: 4px 12px; border: 0.5px solid rgba(90,92,110,0.2); border-radius: 999px; font-size: 11px; color: var(--mid); background: var(--cream); }

  /* ── VALUES ── */
  .values { background: var(--dark); }
  .values .section-label { color: rgba(255,255,255,0.35); }
  .values .section-label::after { background: rgba(255,255,255,0.1); }
  .values .section-title { color: var(--cream); }
  .values-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 2rem; margin-top: 3rem; }
  .value-item { padding: 2rem; border: 0.5px solid rgba(255,255,255,0.1); border-radius: 4px; }
  .value-item:hover { border-color: rgba(201,185,154,0.4); }
  .value-num { font-family: var(--serif); font-size: 36px; font-weight: 500; color: var(--warm); margin-bottom: 0.75rem; line-height: 1; }
  .value-title { font-size: 14px; font-weight: 500; color: var(--cream); margin-bottom: 6px; letter-spacing: 0.04em; }
  .value-desc { font-size: 13px; color: rgba(255,255,255,0.45); line-height: 1.7; }

  /* ── QUOTE BAND ── */
  .quote-band { background: var(--cream); padding: 5rem 3rem; text-align: center; border-top: 0.5px solid rgba(90,92,110,0.1); border-bottom: 0.5px solid rgba(90,92,110,0.1); }
  .quote-band blockquote { font-family: var(--serif); font-size: clamp(20px, 3vw, 28px); font-style: italic; color: var(--dark); line-height: 1.65; max-width: 680px; margin: 0 auto 1.25rem; }
  .quote-band cite { font-size: 12px; color: var(--muted); letter-spacing: 0.14em; text-transform: uppercase; }

  /* ── FOOTER ── */
  footer { background: var(--dark); padding: 3rem; }
  .footer-inner { max-width: 960px; margin: 0 auto; display: flex; justify-content: space-between; align-items: flex-start; flex-wrap: wrap; gap: 2rem; }
  .footer-left {}
  .footer-brand { font-family: var(--serif); font-size: 22px; font-weight: 500; color: var(--cream); margin-bottom: 4px; }
  .footer-tagline { font-size: 12px; color: rgba(255,255,255,0.35); letter-spacing: 0.08em; margin-bottom: 1rem; }
  .footer-copy { font-size: 12px; color: rgba(255,255,255,0.25); }
  .footer-right { text-align: right; }
  .footer-links { display: flex; flex-direction: column; gap: 6px; align-items: flex-end; }
  .footer-links a { font-size: 13px; color: rgba(255,255,255,0.45); text-decoration: none; letter-spacing: 0.04em; transition: color var(--transition); }
  .footer-links a:hover { color: var(--cream); }
  .footer-date { font-size: 11px; color: rgba(255,255,255,0.2); margin-top: 1rem; letter-spacing: 0.1em; text-transform: uppercase; }

  /* ── DIVIDERS ── */
  .divider { height: 0.5px; background: rgba(90,92,110,0.12); margin: 0 3rem; }
  .section-gap { margin-top: 3.5rem; }
  .mt-2 { margin-top: 2rem; }

  /* ── FADE IN ── */
  @keyframes fadeUp { from { opacity: 0; transform: translateY(16px); } to { opacity: 1; transform: none; } }
  .hero-date { animation: fadeUp 0.6s 0.2s both; }
  .hero-eyebrow { animation: fadeUp 0.6s 0.35s both; }
  .hero-title { animation: fadeUp 0.7s 0.5s both; }
  .hero-desc { animation: fadeUp 0.6s 0.7s both; }
  .hero-actions { animation: fadeUp 0.6s 0.85s both; }

  /* ── RESPONSIVE ── */
  @media (max-width: 768px) {
    .nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    .hero { padding: 0 1.5rem 4rem; }
    section { padding: 4rem 1.5rem; }
    .about-grid, .pillars-grid, .formats-grid, .values-grid { grid-template-columns: 1fr; }
    .principles-row, .pub-process-row { grid-template-columns: 1fr; }
    .principle-box, .pub-step { border-right: none; border-bottom: 0.5px solid rgba(90,92,110,0.12); }
    .principle-box:last-child, .pub-step:last-child { border-bottom: none; }
    .footer-inner { flex-direction: column; }
    .footer-right { text-align: left; }
    .footer-links { align-items: flex-start; }
    .hero-scroll { display: none; }
  }
</style>
</head>
<body>

<!-- NAVIGATION -->
<nav class="nav">
  <a href="#home" class="nav-logo">
    <div class="nav-monogram">OV</div>
    <div class="nav-text">
      <span class="nav-brand">Orvexa</span>
      <span class="nav-sub">Media</span>
    </div>
  </a>
  <ul class="nav-links">
    <li><a href="#tentang">Tentang</a></li>
    <li><a href="#publishing">Publishing</a></li>
    <li><a href="#press">Press</a></li>
    <li><a href="#artikel">Artikel</a></li>
    <li><a href="#kontak" class="nav-cta">Kontak</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="home" class="hero">
  <div class="hero-bg"></div>
  <div class="hero-date">27 · 05 · 2026</div>
  <div class="hero-eyebrow">Media Intelektual Indonesia</div>
  <h1 class="hero-title">Orvexa<br><em>Media</em></h1>
  <p class="hero-desc">Rumah bagi dua pilar kreatif dan intelektual — Orvexa Publishing dan Orvexa Press — yang bersama membangun ekosistem pengetahuan, narasi, dan gagasan yang berpengaruh.</p>
  <div class="hero-actions">
    <a href="#pillars" class="btn-dark">Jelajahi Pilar Kami</a>
    <a href="#artikel" class="btn-outline">Baca Artikel Perdana</a>
  </div>
  <div class="hero-scroll">
    <span class="hero-scroll-text">Gulir</span>
    <div class="hero-scroll-line"></div>
  </div>
</section>

<!-- TENTANG -->
<section id="tentang" class="about">
  <div class="section-inner">
    <div class="section-label">Tentang Kami</div>
    <div class="about-grid">
      <div class="about-left">
        <h2 class="section-title">Membangun wacana,<br>mewariskan gagasan.</h2>
        <p class="section-desc">Orvexa Media lahir dari keyakinan bahwa pikiran yang baik berhak mendapat ruang yang layak — dan publik berhak mendapatkan informasi yang jujur, mendalam, dan bermakna.</p>
      </div>
      <div class="about-right">
        <blockquote class="about-quote">"Membangun ekosistem media intelektual yang menjembatani gagasan dengan publik — lewat kata yang jernih, narasi yang jujur, dan pengetahuan yang merdeka."</blockquote>
        <p class="about-text">Didirikan pada 27 Mei 2026, Orvexa Media menaungi dua entitas: Orvexa Publishing sebagai rumah penerbitan jangka panjang, dan Orvexa Press sebagai ruang jurnalisme dan liputan editorial. Bersama, keduanya membentuk satu ekosistem media yang utuh.</p>
        <div class="about-founder">
          <div class="founder-av">RD</div>
          <div>
            <div class="founder-name">Reza Dwi Kurniawan</div>
            <div class="founder-role">Founder & Director — Orvexa Media</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PILLARS -->
<section id="pillars" class="pillars">
  <div class="section-inner">
    <div class="section-label">Dua Pilar Utama</div>
    <h2 class="section-title">Satu atap, dua misi.</h2>
    <div class="pillars-grid">
      <div class="pillar-card">
        <div class="pillar-num">01 — Publishing</div>
        <div class="pillar-icon">📚</div>
        <div class="pillar-name">Orvexa Publishing</div>
        <p class="pillar-desc">Platform penerbitan karya intelektual — buku, esai panjang, antologi, dan publikasi berkala yang membangun wacana dan mewariskan gagasan melampaui zaman.</p>
        <div class="pillar-tags">
          <span class="ptag">Buku</span>
          <span class="ptag">Esai</span>
          <span class="ptag">Antologi</span>
          <span class="ptag">Jurnal</span>
        </div>
      </div>
      <div class="pillar-card">
        <div class="pillar-num">02 — Press</div>
        <div class="pillar-icon">🗞️</div>
        <div class="pillar-name">Orvexa Press</div>
        <p class="pillar-desc">Media jurnalisme dan liputan editorial yang bergerak dengan prinsip kejujuran, kedalaman, dan keberanian — dari berita dan opini hingga investigasi mendalam.</p>
        <div class="pillar-tags">
          <span class="ptag">Jurnalisme</span>
          <span class="ptag">Opini</span>
          <span class="ptag">Investigasi</span>
          <span class="ptag">Wawancara</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ORVEXA PRESS DETAIL -->
<section id="press" class="press-detail">
  <div class="section-inner">
    <div class="section-label">Orvexa Press — Detail</div>
    <h2 class="section-title">Jurnalisme yang tidak<br>berhenti bertanya.</h2>
    <p class="section-desc">Orvexa Press meliput dunia dari banyak sudut — bukan sekadar menyampaikan berita, tapi membangun pemahaman.</p>

    <div class="section-gap">
      <div class="section-label">Format Konten</div>
      <div class="formats-grid">
        <div class="format-item">
          <div class="format-item-icon">📰</div>
          <div class="format-item-title">Artikel & Reportase</div>
          <p class="format-item-desc">Liputan faktual dan naratif dari peristiwa terkini — ditulis dengan konteks yang kuat dan verifikasi yang ketat.</p>
        </div>
        <div class="format-item">
          <div class="format-item-icon">✍️</div>
          <div class="format-item-title">Opini & Kolom</div>
          <p class="format-item-desc">Ruang bagi suara-suara yang berpikir — analisis mendalam dari penulis dan kontributor intelektual Orvexa.</p>
        </div>
        <div class="format-item">
          <div class="format-item-icon">🔍</div>
          <div class="format-item-title">Investigasi Mendalam</div>
          <p class="format-item-desc">Liputan panjang yang menggali fakta tersembunyi — jurnalisme yang memerlukan waktu, riset, dan keberanian.</p>
        </div>
        <div class="format-item">
          <div class="format-item-icon">💬</div>
          <div class="format-item-title">Wawancara & Dialog</div>
          <p class="format-item-desc">Percakapan langsung dengan tokoh, pemikir, dan pelaku perubahan yang membentuk wacana publik Indonesia.</p>
        </div>
      </div>
    </div>

    <div class="section-gap">
      <div class="section-label">Cakupan Topik</div>
      <div class="topics-wrap">
        <span class="topic-chip">🏛️ Sosial & Politik</span>
        <span class="topic-chip">💻 Teknologi & Inovasi</span>
        <span class="topic-chip">🎨 Budaya & Seni</span>
        <span class="topic-chip">📖 Sastra & Bahasa</span>
        <span class="topic-chip">🌏 Isu Global</span>
        <span class="topic-chip">🎓 Pendidikan & Ilmu</span>
        <span class="topic-chip">🤝 Kehidupan & Masyarakat</span>
        <span class="topic-chip">📈 Ekonomi & Bisnis</span>
      </div>
    </div>

    <div class="section-gap">
      <div class="section-label">Prinsip Redaksi</div>
      <div class="principles-row">
        <div class="principle-box">
          <div class="principle-n">01</div>
          <div class="principle-t">Akurasi</div>
          <div class="principle-d">Fakta adalah segalanya. Setiap klaim diverifikasi sebelum tayang.</div>
        </div>
        <div class="principle-box">
          <div class="principle-n">02</div>
          <div class="principle-t">Keberanian</div>
          <div class="principle-d">Kami meliput apa yang perlu diketahui publik, bukan apa yang mudah ditulis.</div>
        </div>
        <div class="principle-box">
          <div class="principle-n">03</div>
          <div class="principle-t">Kedalaman</div>
          <div class="principle-d">Setiap cerita berhak mendapat konteks, latar, dan nuansa yang utuh.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ORVEXA PUBLISHING DETAIL -->
<section id="publishing" class="pub-detail">
  <div class="section-inner">
    <div class="section-label">Orvexa Publishing — Detail</div>
    <h2 class="section-title">Gagasan besar berhak<br>mendapat rumah yang layak.</h2>
    <p class="section-desc">Orvexa Publishing adalah tempat di mana pikiran panjang mendapat wadah yang sepadan — karya yang dirancang untuk bertahan melampaui zaman.</p>

    <div class="section-gap">
      <div class="section-label">Format Terbitan</div>
      <div class="formats-grid">
        <div class="format-item">
          <div class="format-item-icon">📕</div>
          <div class="format-item-title">Buku & Monografi</div>
          <p class="format-item-desc">Karya tulis panjang yang mengeksplorasi satu gagasan secara mendalam — dari nonfiksi ilmiah hingga memoar intelektual.</p>
        </div>
        <div class="format-item">
          <div class="format-item-icon">📚</div>
          <div class="format-item-title">Antologi & Bunga Rampai</div>
          <p class="format-item-desc">Kumpulan tulisan dari berbagai suara yang disatukan dalam satu tema besar yang relevan dan bermakna.</p>
        </div>
        <div class="format-item">
          <div class="format-item-icon">📄</div>
          <div class="format-item-title">Esai Panjang</div>
          <p class="format-item-desc">Format longform untuk pemikiran yang memerlukan ruang bernafas — antara artikel dan buku, dengan kedalaman yang penuh.</p>
        </div>
        <div class="format-item">
          <div class="format-item-icon">📋</div>
          <div class="format-item-title">Jurnal & Publikasi Berkala</div>
          <p class="format-item-desc">Terbitan reguler yang mendokumentasikan perkembangan pemikiran dan wacana intelektual komunitas Orvexa.</p>
        </div>
      </div>
    </div>

    <div class="section-gap">
      <div class="section-label">Proses Penerbitan</div>
      <div class="pub-process-row">
        <div class="pub-step">
          <div class="pub-step-n">01</div>
          <div class="pub-step-t">Kurasi</div>
          <div class="pub-step-d">Seleksi naskah berdasarkan kualitas gagasan dan kedalaman argumen.</div>
        </div>
        <div class="pub-step">
          <div class="pub-step-n">02</div>
          <div class="pub-step-t">Editorial</div>
          <div class="pub-step-d">Proses penyuntingan intensif bersama penulis untuk memperkuat naskah.</div>
        </div>
        <div class="pub-step">
          <div class="pub-step-n">03</div>
          <div class="pub-step-t">Desain</div>
          <div class="pub-step-d">Tata letak dan visual yang mencerminkan identitas intelektual Orvexa.</div>
        </div>
        <div class="pub-step">
          <div class="pub-step-n">04</div>
          <div class="pub-step-t">Distribusi</div>
          <div class="pub-step-d">Penyebaran karya secara digital dan cetak ke pembaca yang tepat.</div>
        </div>
      </div>
    </div>

    <div class="section-gap">
      <div class="open-box">
        <div class="open-box-title">Terbuka untuk Kontributor</div>
        <p class="open-box-desc">Kami membuka pintu bagi penulis, akademisi, peneliti, dan pemikir yang ingin menerbitkan karya mereka bersama Orvexa. Yang kami cari:</p>
        <ul class="open-list">
          <li>Naskah dengan gagasan orisinal yang belum pernah diterbitkan sebelumnya</li>
          <li>Tulisan yang menghormati pembaca dengan argumen yang kuat dan sumber yang jelas</li>
          <li>Penulis yang berkomitmen pada proses editorial yang kolaboratif</li>
          <li>Karya dalam Bahasa Indonesia maupun Bahasa Inggris</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- ARTIKEL PERDANA -->
<section id="artikel" class="artikel">
  <div class="section-label" style="max-width:720px; margin: 0 auto 2rem;">Artikel Perdana · Orvexa Press</div>
  <div class="artikel-inner">
    <div class="artikel-header">
      <span class="artikel-cat">Editorial</span>
      <h2 class="artikel-title">Mengapa Dunia Masih Membutuhkan Jurnalisme yang Jujur</h2>
      <p class="artikel-deck">Di tengah banjir informasi dan kebisingan digital, Orvexa Press hadir dengan satu keyakinan sederhana: kebenaran layak diperjuangkan, dan publik berhak mendapatkannya.</p>
      <div class="artikel-meta">
        <div class="artikel-author">
          <div class="artikel-av">RD</div>
          <div>
            <div class="artikel-author-name">Reza Dwi Kurniawan</div>
            <div class="artikel-author-role">Founder & Pemimpin Redaksi, Orvexa Media</div>
          </div>
        </div>
        <span class="artikel-meta-sep">·</span>
        <span class="artikel-meta-info">5 menit baca</span>
        <span class="artikel-meta-sep">·</span>
        <span class="artikel-meta-info">27 Mei 2026</span>
      </div>
    </div>
    <div class="artikel-body">
      <p class="lead">Ada sesuatu yang berubah dalam cara kita mengonsumsi informasi. Berita bergerak lebih cepat dari pemahaman. Opini diproduksi lebih deras dari fakta. Dan di tengah semua itu, kepercayaan publik terhadap media perlahan tergerus — bukan tanpa alasan.</p>
      <p>Orvexa Press lahir dari kegelisahan itu. Bukan untuk menambah kebisingan, tapi untuk menjadi ruang yang berbeda — tempat di mana setiap kalimat dipertimbangkan, setiap klaim diverifikasi, dan setiap cerita dihormati sebagaimana mestinya.</p>
      <div class="artikel-pullquote">
        <p>"Jurnalisme bukan sekadar melaporkan apa yang terjadi. Ia adalah upaya memastikan apa yang terjadi dipahami dengan benar oleh mereka yang berhak tahu."</p>
      </div>
      <p class="artikel-subhead">Bukan soal kecepatan, tapi kedalaman</p>
      <p>Di era di mana kecepatan dianggap sebagai kualitas utama, kami memilih kedalaman. Sebuah artikel yang ditulis terburu-buru mungkin tayang lebih awal, tapi artikel yang ditulis dengan teliti akan diingat lebih lama. Orvexa Press percaya bahwa pembaca yang cerdas tidak hanya ingin tahu apa yang terjadi — mereka ingin memahami mengapa hal itu terjadi, dan apa artinya bagi mereka.</p>
      <p class="artikel-subhead">Media sebagai ruang intelektual</p>
      <p>Sebagai bagian dari Orvexa Media yang juga menaungi Orvexa Publishing, kami memandang jurnalisme sebagai perpanjangan dari tradisi intelektual. Artikel bukan hanya laporan — ia adalah dokumen zaman. Opini bukan hanya pendapat — ia adalah percakapan yang mengundang respons. Investigasi bukan hanya pengungkapan — ia adalah bentuk pertanggungjawaban terhadap publik.</p>
      <p class="artikel-subhead">Kepada pembaca kami</p>
      <p>Hari ini, 27 Mei 2026, Orvexa Press resmi hadir. Kami tidak datang dengan klaim menjadi yang terbaik atau paling lengkap. Kami datang dengan komitmen: untuk terus bertanya, terus menggali, dan terus menyampaikan — dengan cara yang pantas untuk sebuah media yang menghormati pembacanya.</p>
      <p>Selamat datang di Orvexa Press. Ini baru permulaan.</p>
      <div class="artikel-tags">
        <span class="artikel-tag">Editorial</span>
        <span class="artikel-tag">Jurnalisme</span>
        <span class="artikel-tag">Media</span>
        <span class="artikel-tag">Orvexa Press</span>
      </div>
    </div>
  </div>
</section>

<!-- VALUES -->
<section class="values">
  <div class="section-inner">
    <div class="section-label">Nilai Inti</div>
    <h2 class="section-title" style="color: var(--cream);">Apa yang kami<br>pegang teguh.</h2>
    <div class="values-grid">
      <div class="value-item">
        <div class="value-num">01</div>
        <div class="value-title">Intelektualitas</div>
        <p class="value-desc">Setiap karya lahir dari pemikiran yang matang dan riset yang mendalam. Kami tidak memproduksi, kami membangun.</p>
      </div>
      <div class="value-item">
        <div class="value-num">02</div>
        <div class="value-title">Integritas</div>
        <p class="value-desc">Kejujuran dan tanggung jawab adalah fondasi dari setiap narasi yang kami bangun — tanpa kompromi.</p>
      </div>
      <div class="value-item">
        <div class="value-num">03</div>
        <div class="value-title">Inovasi</div>
        <p class="value-desc">Mendorong batas format dan medium dalam dunia media modern — selalu mencari cara baru untuk menyampaikan kebenaran.</p>
      </div>
    </div>
  </div>
</section>

<!-- QUOTE BAND -->
<div class="quote-band">
  <blockquote>"Orvexa hadir bukan hanya untuk melaporkan atau menerbitkan — tapi untuk memastikan bahwa gagasan dan kebenaran mendapat tempat yang layak di ruang publik."</blockquote>
  <cite>— Reza Dwi Kurniawan, Founder Orvexa Media · 27 Mei 2026</cite>
</div>

<!-- FOOTER -->
<footer id="kontak">
  <div class="footer-inner">
    <div class="footer-left">
      <div class="footer-brand">Orvexa Media</div>
      <div class="footer-tagline">Orvexa Publishing · Orvexa Press</div>
      <div class="footer-copy">© 27 Mei 2026 — Reza Dwi Kurniawan<br>Hak cipta dilindungi undang-undang.</div>
    </div>
    <div class="footer-right">
      <div class="footer-links">
        <a href="#tentang">Tentang Kami</a>
        <a href="#publishing">Orvexa Publishing</a>
        <a href="#press">Orvexa Press</a>
        <a href="#artikel">Artikel</a>
      </div>
      <div class="footer-date">Didirikan · 27 · 05 · 2026</div>
    </div>
  </div>
</footer>

</body>
</html>
