
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Orvexa Foundations — Media Pemikiran Indonesia</title>
  <link rel="preconnect" href="https://fonts.googleapis.com"/>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=DM+Sans:opsz,wght@9..40,300;9..40,400;9..40,500;9..40,600&family=DM+Serif+Display:ital@0;1&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --ink: #0d0d0d;
      --ivory: #f8f4ee;
      --cream: #ede8df;
      --gold: #b8955a;
      --gold-light: #d4b07a;
      --rust: #8b3a2a;
      --forest: #2a4a3a;
      --muted: #6b6560;
      --border: #d6cfc4;
      --white: #ffffff;
      --shadow-sm: 0 2px 8px rgba(13,13,13,0.06);
      --shadow-md: 0 8px 24px rgba(13,13,13,0.10);
      --shadow-lg: 0 20px 60px rgba(13,13,13,0.15);
      --radius: 8px;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--ivory);
      color: var(--ink);
      overflow-x: hidden;
      -webkit-font-smoothing: antialiased;
    }

    /* ===== SPLASH SCREEN ===== */
    #splashScreen {
      position: fixed; inset: 0; z-index: 9000;
      background: #f4f4f4;
      display: flex; flex-direction: column;
      justify-content: center; align-items: center;
      font-family: 'Times New Roman', serif;
      transition: opacity 0.7s ease, visibility 0.7s ease;
    }
    #splashScreen.hidden { opacity: 0; visibility: hidden; pointer-events: none; }

    .splash-logo {
      font-size: clamp(80px, 18vw, 130px);
      font-weight: 500;
      color: #333;
      line-height: 1;
      margin-bottom: 0;
      letter-spacing: -2px;
      animation: splashFadeIn 0.9s ease 0.1s both;
    }
    .splash-brand {
      letter-spacing: 10px;
      font-size: clamp(18px, 4vw, 28px);
      margin: 14px 0 0;
      color: #333;
      text-transform: uppercase;
      animation: splashFadeIn 0.9s ease 0.35s both;
    }
    .splash-sub {
      font-size: clamp(10px, 2vw, 13px);
      letter-spacing: 5px;
      margin-top: 6px;
      color: #555;
      text-transform: uppercase;
      animation: splashFadeIn 0.9s ease 0.55s both;
    }
    .splash-tagline {
      font-size: clamp(9px, 1.8vw, 11px);
      margin-top: 14px;
      letter-spacing: 2.5px;
      color: #777;
      animation: splashFadeIn 0.9s ease 0.75s both;
    }
    .splash-divider {
      width: 1px; height: 60px;
      background: linear-gradient(to bottom, transparent, #ccc, transparent);
      margin: 32px 0 24px;
      animation: splashFadeIn 0.9s ease 0.9s both;
    }
    .splash-enter {
      font-family: 'DM Sans', sans-serif;
      font-size: 0.7rem; font-weight: 700;
      letter-spacing: 0.2em; text-transform: uppercase;
      color: #999;
      cursor: pointer;
      border: 1px solid #ccc;
      padding: 10px 28px;
      border-radius: 3px;
      background: transparent;
      transition: all 0.22s;
      animation: splashFadeIn 0.9s ease 1.1s both;
    }
    .splash-enter:hover { background: #333; color: #f4f4f4; border-color: #333; }

    @keyframes splashFadeIn {
      from { opacity: 0; transform: translateY(12px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* ===== MAIN APP ===== */
    #mainApp { display: none; }
    #mainApp.visible { display: block; animation: mainReveal 0.5s ease; }
    @keyframes mainReveal { from { opacity: 0; } to { opacity: 1; } }

    .page { display: none; }
    .page.active { display: block; animation: fadeIn 0.25s ease; }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

    /* ===== NAVBAR ===== */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 1000;
      background: rgba(248,244,238,0.97);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border);
    }

    .nav-inner {
      display: flex; align-items: center; justify-content: space-between;
      height: 66px; max-width: 1440px; margin: 0 auto; padding: 0 5%;
    }

    .logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.4rem; font-weight: 900;
      color: var(--ink); text-decoration: none;
      letter-spacing: -0.02em; cursor: pointer;
      flex-shrink: 0;
    }
    .logo span { color: var(--gold); }

    .nav-links {
      display: flex; gap: 2px; list-style: none; align-items: center;
    }

    .nav-links a {
      font-size: 0.79rem; font-weight: 500; letter-spacing: 0.05em;
      text-transform: uppercase; color: var(--muted);
      text-decoration: none; padding: 7px 12px;
      border-radius: 5px; transition: all 0.18s;
      cursor: pointer; white-space: nowrap;
    }
    .nav-links a:hover, .nav-links a.active { color: var(--ink); background: var(--cream); }

    .nav-cta {
      background: var(--ink) !important; color: var(--ivory) !important;
      margin-left: 6px !important;
    }
    .nav-cta:hover { background: var(--gold) !important; color: var(--white) !important; }

    .nav-right { display: flex; align-items: center; gap: 4px; }

    .nav-search-trigger {
      display: flex; align-items: center; gap: 8px;
      background: var(--cream); border: 1px solid var(--border);
      border-radius: 6px; padding: 6px 12px 6px 10px;
      cursor: pointer; transition: all 0.2s;
      color: var(--muted); font-size: 0.8rem;
      font-family: 'DM Sans', sans-serif;
    }
    .nav-search-trigger:hover { border-color: var(--gold); background: #fef9f2; color: var(--ink); }
    .nav-search-trigger .search-icon { font-size: 0.85rem; }
    .nav-search-trigger .search-label { display: none; }
    .nav-search-trigger .kbd {
      font-size: 0.65rem; font-weight: 700; letter-spacing: 0.04em;
      background: var(--white); border: 1px solid var(--border);
      border-radius: 3px; padding: 1px 5px; color: var(--muted);
      line-height: 1.6; margin-left: 4px;
    }

    .nav-hamburger {
      display: none; background: none; border: none; cursor: pointer;
      padding: 8px; color: var(--ink); font-size: 1.2rem;
    }

    .mobile-drawer {
      display: none; position: fixed; top: 66px; left: 0; right: 0; bottom: 0;
      background: var(--ivory); z-index: 999; overflow-y: auto;
      padding: 24px 5% 40px; border-top: 1px solid var(--border);
      flex-direction: column; gap: 4px;
    }
    .mobile-drawer.open { display: flex; }
    .mobile-drawer a {
      font-size: 1.05rem; font-weight: 500; color: var(--ink);
      text-decoration: none; padding: 14px 16px; border-radius: 6px;
      transition: background 0.15s; cursor: pointer;
    }
    .mobile-drawer a:hover { background: var(--cream); }
    .mobile-drawer .mob-cta {
      background: var(--ink); color: var(--ivory) !important;
      text-align: center; margin-top: 12px;
    }

    /* ===== SEARCH OVERLAY ===== */
    .search-overlay {
      position: fixed; inset: 0; z-index: 2000;
      background: rgba(13,13,13,0); backdrop-filter: blur(0px);
      display: none; align-items: flex-start; justify-content: center;
      padding-top: 80px; padding-left: 16px; padding-right: 16px;
      transition: background 0.22s, backdrop-filter 0.22s;
    }
    .search-overlay.open {
      display: flex;
      background: rgba(13,13,13,0.72);
      backdrop-filter: blur(8px);
      animation: overlayIn 0.2s ease forwards;
    }
    @keyframes overlayIn {
      from { background: rgba(13,13,13,0); backdrop-filter: blur(0); }
      to { background: rgba(13,13,13,0.72); backdrop-filter: blur(8px); }
    }

    .search-palette {
      width: 100%; max-width: 680px;
      background: var(--white);
      border-radius: 14px;
      border: 1px solid rgba(184,149,90,0.25);
      box-shadow: 0 32px 80px rgba(13,13,13,0.35), 0 0 0 1px rgba(255,255,255,0.05);
      overflow: hidden;
      animation: paletteIn 0.22s cubic-bezier(0.34, 1.4, 0.64, 1) forwards;
      transform-origin: top center;
    }
    @keyframes paletteIn {
      from { opacity: 0; transform: scale(0.96) translateY(-8px); }
      to { opacity: 1; transform: scale(1) translateY(0); }
    }

    .search-input-row {
      display: flex; align-items: center; gap: 12px;
      padding: 16px 20px; border-bottom: 1px solid #f0ece6;
      background: var(--white);
    }
    .search-icon-big { font-size: 1.1rem; color: var(--gold); flex-shrink: 0; width: 22px; text-align: center; }
    .search-input-main {
      flex: 1; font-family: 'Playfair Display', serif;
      font-size: 1.15rem; font-weight: 400; color: var(--ink);
      background: transparent; border: none; outline: none;
      caret-color: var(--gold);
    }
    .search-input-main::placeholder { color: #b8b0a8; }
    .search-esc-badge {
      font-size: 0.62rem; font-weight: 700; letter-spacing: 0.06em;
      background: #f0ece6; border: 1px solid var(--border);
      border-radius: 4px; padding: 3px 7px; color: var(--muted);
      cursor: pointer; flex-shrink: 0; transition: all 0.15s;
    }
    .search-esc-badge:hover { background: var(--ink); color: var(--ivory); border-color: var(--ink); }

    .search-section { padding: 10px 0; border-bottom: 1px solid #f0ece6; }
    .search-section:last-child { border-bottom: none; }
    .search-section-label {
      font-size: 0.62rem; font-weight: 700; letter-spacing: 0.14em;
      text-transform: uppercase; color: #b8b0a8; padding: 6px 20px 8px;
    }
    .search-nav-items { display: flex; flex-wrap: wrap; gap: 6px; padding: 4px 20px 10px; }
    .search-nav-chip {
      display: inline-flex; align-items: center; gap: 6px;
      font-size: 0.8rem; font-weight: 500;
      padding: 6px 14px; border-radius: 20px;
      background: var(--cream); color: var(--ink);
      border: 1px solid var(--border);
      cursor: pointer; transition: all 0.15s; text-decoration: none;
    }
    .search-nav-chip:hover { background: var(--ink); color: var(--ivory); border-color: var(--ink); }
    .search-nav-chip .chip-emoji { font-size: 0.85rem; }

    .search-results-list { max-height: 400px; overflow-y: auto; }
    .search-results-list::-webkit-scrollbar { width: 4px; }
    .search-results-list::-webkit-scrollbar-track { background: transparent; }
    .search-results-list::-webkit-scrollbar-thumb { background: var(--border); border-radius: 2px; }

    .search-result-row {
      display: flex; align-items: flex-start; gap: 14px;
      padding: 13px 20px; cursor: pointer; transition: background 0.12s;
      border-left: 2px solid transparent;
    }
    .search-result-row:hover, .search-result-row.focused { background: #fef9f2; border-left-color: var(--gold); }
    .search-result-icon { width: 34px; height: 34px; border-radius: 8px; flex-shrink: 0; display: flex; align-items: center; justify-content: center; font-size: 0.9rem; margin-top: 1px; }
    .search-result-body { flex: 1; min-width: 0; }
    .search-result-cat { font-size: 0.62rem; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; margin-bottom: 3px; }
    .search-result-title { font-family: 'Playfair Display', serif; font-size: 0.97rem; font-weight: 700; color: var(--ink); line-height: 1.3; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
    .search-result-meta { font-size: 0.75rem; color: var(--muted); margin-top: 3px; }
    .search-result-arrow { font-size: 0.8rem; color: var(--border); align-self: center; transition: color 0.12s; flex-shrink: 0; }
    .search-result-row:hover .search-result-arrow { color: var(--gold); }
    .search-highlight { color: var(--gold); font-weight: 700; }
    .search-empty { padding: 32px 20px; text-align: center; }
    .search-empty-icon { font-size: 2rem; opacity: 0.3; margin-bottom: 10px; }
    .search-empty-text { font-size: 0.88rem; color: var(--muted); }
    .search-footer {
      padding: 10px 20px; background: #fafaf8;
      border-top: 1px solid #f0ece6;
      display: flex; align-items: center; justify-content: space-between;
    }
    .search-footer-hint { font-size: 0.7rem; color: #b8b0a8; display: flex; align-items: center; gap: 8px; }
    .search-footer-hint kbd { font-size: 0.65rem; font-weight: 700; background: var(--white); border: 1px solid var(--border); border-radius: 3px; padding: 2px 5px; color: var(--muted); font-family: 'DM Sans', sans-serif; }
    .search-result-count { font-size: 0.7rem; color: #b8b0a8; }

    .icon-ekonomi { background: #fef3e2; } .icon-politik { background: #fce8e8; } .icon-sosial { background: #e8f4ec; } .icon-lingkungan { background: #e4f0e8; } .icon-pendidikan { background: #eaeeff; } .icon-opini { background: #f5e8f5; }
    .cat-text-ekonomi { color: #92650a; } .cat-text-politik { color: #8b3a2a; } .cat-text-sosial { color: #2a4a3a; } .cat-text-lingkungan { color: #2d6a4f; } .cat-text-pendidikan { color: #3a3a8b; } .cat-text-opini { color: #6a3a6a; }

    /* ===== HERO / MASTHEAD ===== */
    .hero-masthead {
      background: var(--ink); color: var(--ivory);
      padding: 100px 5% 60px; text-align: center;
      position: relative; overflow: hidden;
    }
    .hero-masthead::before {
      content: ''; position: absolute; inset: 0;
      background: radial-gradient(ellipse 80% 60% at 50% 120%, rgba(184,149,90,0.18) 0%, transparent 70%);
      pointer-events: none;
    }
    .masthead-eyebrow { font-size: 0.68rem; letter-spacing: 0.22em; text-transform: uppercase; color: var(--gold); margin-bottom: 22px; opacity: 0.9; }
    .masthead-title { font-family: 'Playfair Display', serif; font-size: clamp(3.5rem, 10vw, 8rem); font-weight: 900; line-height: 0.88; letter-spacing: -0.04em; margin-bottom: 24px; }
    .masthead-title em { color: var(--gold); font-style: italic; }
    .masthead-sub { font-size: 1.02rem; color: rgba(248,244,238,0.58); max-width: 460px; margin: 0 auto; line-height: 1.75; }
    .masthead-actions { margin-top: 36px; display: flex; gap: 12px; justify-content: center; flex-wrap: wrap; }
    .date-strip { background: var(--gold); color: var(--ink); text-align: center; padding: 9px; font-size: 0.68rem; letter-spacing: 0.14em; text-transform: uppercase; font-weight: 700; }

    /* ===== FEATURED GRID ===== */
    .featured-grid { display: grid; grid-template-columns: 1.65fr 1fr; border-bottom: 1px solid var(--border); }
    .featured-main { padding: 52px 5%; border-right: 1px solid var(--border); cursor: pointer; transition: background 0.2s; }
    .featured-main:hover { background: rgba(248,244,238,0.5); }
    .featured-main:hover .art-title { color: var(--gold); }
    .featured-sidebar { display: flex; flex-direction: column; }
    .featured-sidebar-item { padding: 30px 5% 30px 4%; border-bottom: 1px solid var(--border); cursor: pointer; transition: background 0.2s; flex: 1; }
    .featured-sidebar-item:last-child { border-bottom: none; }
    .featured-sidebar-item:hover { background: var(--cream); }
    .featured-sidebar-item:hover .art-title { color: var(--gold); }

    .category-tag { display: inline-block; font-size: 0.62rem; font-weight: 700; letter-spacing: 0.14em; text-transform: uppercase; padding: 4px 10px; border-radius: 3px; margin-bottom: 14px; }
    .cat-ekonomi { background: #fef3e2; color: #92650a; } .cat-politik { background: #fce8e8; color: var(--rust); } .cat-sosial { background: #e8f4ec; color: var(--forest); } .cat-lingkungan { background: #e4f0e8; color: #2d6a4f; } .cat-pendidikan { background: #eaeeff; color: #3a3a8b; } .cat-opini { background: #f5e8f5; color: #6a3a6a; }

    .art-title { font-family: 'Playfair Display', serif; line-height: 1.15; transition: color 0.2s; }
    .art-title.xl { font-size: clamp(1.9rem, 3.2vw, 2.9rem); font-weight: 700; margin-bottom: 16px; }
    .art-title.lg { font-size: 1.3rem; font-weight: 700; margin-bottom: 10px; }
    .art-title.md { font-size: 1.05rem; font-weight: 700; margin-bottom: 8px; }
    .art-excerpt { color: var(--muted); font-size: 0.92rem; line-height: 1.72; margin-bottom: 20px; }
    .art-meta { display: flex; align-items: center; gap: 10px; font-size: 0.74rem; color: var(--muted); flex-wrap: wrap; }
    .art-meta .author { font-weight: 600; color: var(--ink); }
    .art-meta .dot { color: var(--border); }

    .section-header { display: flex; align-items: center; gap: 16px; margin-bottom: 32px; }
    .section-title { font-family: 'Playfair Display', serif; font-size: 1.45rem; font-weight: 700; }
    .section-line { flex: 1; height: 1px; background: var(--border); }
    .section-more { font-size: 0.7rem; letter-spacing: 0.1em; text-transform: uppercase; font-weight: 700; color: var(--gold); text-decoration: none; cursor: pointer; white-space: nowrap; }
    .section-more:hover { color: var(--rust); }

    .cat-section { max-width: 1440px; margin: 0 auto; padding: 70px 5%; border-bottom: 1px solid var(--border); }
    .articles-row { display: grid; grid-template-columns: repeat(3, 1fr); gap: 32px; }
    .article-card { cursor: pointer; }
    .article-card:hover .art-title { color: var(--gold); }
    .card-img-placeholder { width: 100%; aspect-ratio: 16/9; border-radius: var(--radius); margin-bottom: 16px; background: linear-gradient(135deg, var(--cream), var(--border)); display: flex; align-items: center; justify-content: center; font-size: 2.2rem; overflow: hidden; }

    .two-col { display: grid; grid-template-columns: 1fr 360px; gap: 56px; }
    .latest-list { display: flex; flex-direction: column; }
    .latest-item { display: flex; gap: 16px; padding: 20px 0; border-bottom: 1px solid var(--border); cursor: pointer; transition: all 0.18s; border-radius: 4px; }
    .latest-item:hover { background: var(--cream); padding-left: 10px; padding-right: 10px; }
    .latest-item:hover .art-title { color: var(--gold); }
    .latest-num { font-family: 'Playfair Display', serif; font-size: 1.7rem; font-weight: 900; color: var(--border); line-height: 1; min-width: 38px; }

    .sidebar-widget { margin-bottom: 36px; }
    .sidebar-widget-title { font-size: 0.66rem; letter-spacing: 0.2em; text-transform: uppercase; font-weight: 700; color: var(--muted); margin-bottom: 14px; padding-bottom: 10px; border-bottom: 2px solid var(--ink); }
    .trending-list { list-style: none; }
    .trending-list li { display: flex; gap: 12px; align-items: flex-start; padding: 11px 0; border-bottom: 1px solid var(--border); cursor: pointer; font-size: 0.86rem; font-weight: 500; transition: color 0.18s; }
    .trending-list li:hover { color: var(--gold); }
    .trending-num { font-family: 'Playfair Display', serif; font-size: 1rem; font-weight: 900; color: var(--border); min-width: 22px; line-height: 1.4; }

    /* ===== PROFILE PAGE ===== */
    .profile-hero { background: var(--ink); color: var(--ivory); padding: 120px 5% 80px; text-align: center; position: relative; overflow: hidden; }
    .profile-hero::before { content: ''; position: absolute; inset: 0; background: radial-gradient(ellipse 60% 50% at 50% 100%, rgba(184,149,90,0.15) 0%, transparent 70%); }
    .profile-avatar { width: 130px; height: 130px; border-radius: 50%; background: linear-gradient(135deg, var(--gold), var(--rust)); margin: 0 auto 24px; display: flex; align-items: center; justify-content: center; font-size: 3rem; font-family: 'Playfair Display', serif; font-weight: 900; color: white; border: 3px solid rgba(184,149,90,0.6); position: relative; }
    .profile-name { font-family: 'Playfair Display', serif; font-size: 2.6rem; font-weight: 900; margin-bottom: 8px; }
    .profile-role { color: var(--gold); font-size: 0.82rem; letter-spacing: 0.16em; text-transform: uppercase; margin-bottom: 20px; }
    .profile-bio { max-width: 620px; margin: 0 auto; color: rgba(248,244,238,0.65); line-height: 1.8; }
    .profile-stats { display: flex; justify-content: center; gap: 0; border-bottom: 1px solid var(--border); background: var(--cream); }
    .stat { text-align: center; padding: 36px 48px; border-right: 1px solid var(--border); }
    .stat:last-child { border-right: none; }
    .stat-num { font-family: 'Playfair Display', serif; font-size: 2.4rem; font-weight: 900; color: var(--ink); line-height: 1; }
    .stat-label { font-size: 0.72rem; color: var(--muted); text-transform: uppercase; letter-spacing: 0.1em; margin-top: 6px; }
    .profile-content { max-width: 880px; margin: 0 auto; padding: 60px 5%; }

    /* ===== SUBMIT PAGE ===== */
    .jf-wrap { min-height: calc(100vh - 66px); margin-top: 66px; display: grid; grid-template-columns: 300px 1fr; background: #f0ece6; }
    .jf-sidebar { background: var(--ink); padding: 0; display: flex; flex-direction: column; position: sticky; top: 66px; height: calc(100vh - 66px); overflow-y: auto; }
    .jf-sidebar-header { padding: 36px 28px 28px; border-bottom: 1px solid rgba(255,255,255,0.08); }
    .jf-sidebar-logo { font-family: 'Playfair Display', serif; font-size: 1.1rem; font-weight: 900; color: var(--ivory); margin-bottom: 6px; }
    .jf-sidebar-logo span { color: var(--gold); }
    .jf-sidebar-tagline { font-size: 0.74rem; color: rgba(248,244,238,0.45); line-height: 1.5; }
    .jf-steps { padding: 28px 0; flex: 1; }
    .jf-step-item { display: flex; align-items: flex-start; gap: 14px; padding: 14px 28px; cursor: pointer; transition: background 0.18s; position: relative; }
    .jf-step-item:hover { background: rgba(255,255,255,0.05); }
    .jf-step-item.active { background: rgba(184,149,90,0.12); }
    .jf-step-num { width: 28px; height: 28px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 0.75rem; font-weight: 700; flex-shrink: 0; border: 1.5px solid rgba(255,255,255,0.2); color: rgba(255,255,255,0.4); transition: all 0.2s; }
    .jf-step-item.active .jf-step-num { background: var(--gold); border-color: var(--gold); color: white; }
    .jf-step-item.done .jf-step-num { background: var(--forest); border-color: var(--forest); color: white; }
    .jf-step-info { flex: 1; }
    .jf-step-label { font-size: 0.82rem; font-weight: 600; color: rgba(255,255,255,0.45); transition: color 0.2s; display: block; margin-bottom: 2px; }
    .jf-step-item.active .jf-step-label, .jf-step-item.done .jf-step-label { color: var(--ivory); }
    .jf-step-desc { font-size: 0.72rem; color: rgba(255,255,255,0.28); line-height: 1.4; }
    .jf-progress-wrap { padding: 20px 28px; border-top: 1px solid rgba(255,255,255,0.08); }
    .jf-progress-label { display: flex; justify-content: space-between; font-size: 0.7rem; color: rgba(255,255,255,0.4); margin-bottom: 8px; }
    .jf-progress-track { height: 4px; background: rgba(255,255,255,0.1); border-radius: 2px; overflow: hidden; }
    .jf-progress-fill { height: 100%; background: var(--gold); border-radius: 2px; transition: width 0.35s ease; width: 0%; }
    .jf-main { padding: 48px 5% 80px; max-width: 760px; margin: 0 auto; width: 100%; }
    .jf-panel { display: none; }
    .jf-panel.active { display: block; animation: fadeIn 0.22s ease; }
    .jf-panel-header { margin-bottom: 32px; padding-bottom: 24px; border-bottom: 1px solid var(--border); }
    .jf-panel-step-tag { font-size: 0.65rem; font-weight: 700; letter-spacing: 0.2em; text-transform: uppercase; color: var(--gold); margin-bottom: 8px; display: block; }
    .jf-panel-title { font-family: 'Playfair Display', serif; font-size: 1.7rem; font-weight: 900; color: var(--ink); margin-bottom: 6px; }
    .jf-panel-subtitle { font-size: 0.9rem; color: var(--muted); line-height: 1.6; }
    .jf-field-card { background: var(--white); border-radius: 10px; border: 1px solid var(--border); padding: 24px 28px; margin-bottom: 16px; box-shadow: var(--shadow-sm); transition: box-shadow 0.18s, border-color 0.18s; }
    .jf-field-card:focus-within { border-color: var(--gold); box-shadow: 0 0 0 3px rgba(184,149,90,0.10), var(--shadow-sm); }
    .jf-field-label { font-size: 0.8rem; font-weight: 700; letter-spacing: 0.07em; text-transform: uppercase; color: var(--ink); margin-bottom: 10px; display: flex; align-items: center; gap: 6px; }
    .jf-req { color: var(--rust); font-size: 0.9rem; }
    .jf-field-hint { font-size: 0.76rem; color: var(--muted); font-weight: 400; text-transform: none; letter-spacing: 0; margin-top: 2px; display: block; }
    .jf-input, .jf-select, .jf-textarea { font-family: 'DM Sans', sans-serif; font-size: 0.96rem; color: var(--ink); background: transparent; border: none; border-bottom: 1.5px solid var(--border); padding: 8px 0; outline: none; width: 100%; transition: border-color 0.18s; }
    .jf-input:focus, .jf-select:focus, .jf-textarea:focus { border-color: var(--gold); }
    .jf-textarea { resize: vertical; min-height: 220px; line-height: 1.75; }
    .jf-select { background: transparent; cursor: pointer; }
    .jf-cat-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
    .jf-cat-card { border: 1.5px solid var(--border); border-radius: 8px; padding: 16px 14px; cursor: pointer; transition: all 0.18s; text-align: center; background: var(--white); }
    .jf-cat-card:hover { border-color: var(--gold); background: #fef9f2; }
    .jf-cat-card.selected { border-color: var(--gold); background: #fef9f2; box-shadow: 0 0 0 2px rgba(184,149,90,0.25); }
    .jf-cat-card .cat-emoji { font-size: 1.6rem; margin-bottom: 6px; display: block; }
    .jf-cat-card .cat-name { font-size: 0.78rem; font-weight: 700; color: var(--ink); }
    .jf-cat-card .cat-sub { font-size: 0.68rem; color: var(--muted); margin-top: 3px; }
    .jf-radio-group { display: flex; flex-direction: column; gap: 10px; }
    .jf-radio-option { display: flex; align-items: center; gap: 12px; padding: 12px 16px; border: 1.5px solid var(--border); border-radius: 8px; cursor: pointer; transition: all 0.18s; background: var(--white); }
    .jf-radio-option:hover { border-color: var(--gold); background: #fef9f2; }
    .jf-radio-option.selected { border-color: var(--gold); background: #fef9f2; }
    .jf-radio-option input { accent-color: var(--gold); width: 16px; height: 16px; }
    .jf-radio-label { font-size: 0.9rem; font-weight: 500; }
    .jf-nav { display: flex; justify-content: space-between; align-items: center; margin-top: 32px; padding-top: 24px; border-top: 1px solid var(--border); }
    .jf-btn-next { background: var(--gold); color: white; border: none; padding: 13px 36px; border-radius: var(--radius); font-family: 'DM Sans', sans-serif; font-size: 0.9rem; font-weight: 700; cursor: pointer; transition: all 0.18s; display: flex; align-items: center; gap: 8px; }
    .jf-btn-next:hover { background: var(--rust); transform: translateY(-1px); box-shadow: var(--shadow-md); }
    .jf-btn-back { background: none; border: 1.5px solid var(--border); color: var(--muted); padding: 12px 24px; border-radius: var(--radius); font-family: 'DM Sans', sans-serif; font-size: 0.86rem; font-weight: 600; cursor: pointer; transition: all 0.18s; }
    .jf-btn-back:hover { border-color: var(--ink); color: var(--ink); }
    .jf-btn-submit { background: var(--ink); color: var(--ivory); border: none; padding: 15px 44px; border-radius: var(--radius); font-family: 'DM Sans', sans-serif; font-size: 0.96rem; font-weight: 700; cursor: pointer; transition: all 0.2s; display: flex; align-items: center; gap: 10px; letter-spacing: 0.02em; }
    .jf-btn-submit:hover { background: var(--gold); transform: translateY(-2px); box-shadow: var(--shadow-lg); }
    .jf-success { text-align: center; padding: 60px 24px; }
    .jf-success-icon { width: 80px; height: 80px; border-radius: 50%; background: linear-gradient(135deg, var(--gold), var(--rust)); display: flex; align-items: center; justify-content: center; font-size: 2.2rem; margin: 0 auto 24px; animation: popIn 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
    @keyframes popIn { from { transform: scale(0); opacity: 0; } to { transform: scale(1); opacity: 1; } }
    .jf-upload { border: 2px dashed var(--border); border-radius: 8px; padding: 32px; text-align: center; cursor: pointer; transition: all 0.2s; background: #fafaf8; }
    .jf-upload:hover, .jf-upload.dragging { border-color: var(--gold); background: #fef9f2; }
    .jf-count { font-size: 0.72rem; color: var(--muted); margin-top: 6px; text-align: right; }
    .jf-count.warn { color: var(--gold); }
    .jf-count.over { color: var(--rust); }

    /* ===== FORM ===== */
    .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
    .form-full { grid-column: 1 / -1; }
    .form-group { display: flex; flex-direction: column; gap: 7px; }
    .form-label { font-size: 0.72rem; font-weight: 700; letter-spacing: 0.09em; text-transform: uppercase; color: var(--muted); }
    .form-input, .form-select, .form-textarea { font-family: 'DM Sans', sans-serif; font-size: 0.94rem; color: var(--ink); background: var(--white); border: 1.5px solid var(--border); border-radius: var(--radius); padding: 11px 15px; outline: none; transition: border-color 0.2s, box-shadow 0.2s; width: 100%; }
    .form-input:focus, .form-select:focus, .form-textarea:focus { border-color: var(--gold); box-shadow: 0 0 0 3px rgba(184,149,90,0.13); }
    .form-textarea { min-height: 260px; resize: vertical; line-height: 1.72; }
    .char-count { font-size: 0.72rem; color: var(--muted); text-align: right; margin-top: 4px; }

    /* ===== BUTTONS ===== */
    .btn { display: inline-flex; align-items: center; gap: 8px; padding: 13px 30px; border-radius: var(--radius); border: none; font-family: 'DM Sans', sans-serif; font-size: 0.86rem; font-weight: 600; letter-spacing: 0.04em; cursor: pointer; transition: all 0.2s; text-decoration: none; }
    .btn-primary { background: var(--ink); color: var(--ivory); }
    .btn-primary:hover { background: var(--gold); transform: translateY(-1px); box-shadow: var(--shadow-md); }
    .btn-gold { background: var(--gold); color: var(--white); }
    .btn-gold:hover { background: var(--rust); transform: translateY(-1px); }
    .btn-outline { background: transparent; color: var(--ink); border: 1.5px solid var(--border); }
    .btn-outline:hover { border-color: var(--ink); }
    .btn-sm { padding: 8px 18px; font-size: 0.78rem; }

    /* ===== KARYA TULISAN ===== */
    .works-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 2px; background: var(--border); }
    .work-item { background: var(--ivory); padding: 36px 40px; cursor: pointer; transition: background 0.2s; }
    .work-item:hover { background: var(--cream); }
    .work-item:hover .art-title { color: var(--gold); }

    /* ===== EMPTY STATE ===== */
    .empty-state { text-align: center; padding: 80px 24px; color: var(--muted); }
    .empty-state .empty-icon { font-size: 3.5rem; margin-bottom: 20px; opacity: 0.5; }
    .empty-state h3 { font-family: 'Playfair Display', serif; font-size: 1.6rem; color: var(--ink); margin-bottom: 12px; }
    .empty-state p { font-size: 0.95rem; line-height: 1.7; max-width: 400px; margin: 0 auto 28px; }

    /* ===== ARTICLE VIEW ===== */
    .article-view-hero { background: var(--ink); color: var(--ivory); padding: 110px 5% 60px; position: relative; overflow: hidden; }
    .article-view-hero::before { content: ''; position: absolute; inset: 0; background: radial-gradient(ellipse 70% 60% at 20% 80%, rgba(184,149,90,0.12) 0%, transparent 60%); }
    .article-view-title { font-family: 'Playfair Display', serif; font-size: clamp(2.2rem, 5vw, 3.6rem); font-weight: 900; line-height: 1.1; max-width: 780px; margin-bottom: 24px; position: relative; }
    .article-body { max-width: 700px; margin: 0 auto; padding: 60px 5%; font-size: 1.04rem; line-height: 1.88; color: #1a1a1a; }
    .article-body p { margin-bottom: 24px; }
    .article-body h2 { font-family: 'Playfair Display', serif; font-size: 1.55rem; margin: 44px 0 16px; color: var(--ink); }
    .article-body blockquote { border-left: 3px solid var(--gold); padding-left: 24px; color: var(--muted); font-style: italic; margin: 36px 0; font-family: 'DM Serif Display', serif; font-size: 1.18rem; line-height: 1.65; }

    /* ===== PAGE HEADER ===== */
    .page-header { background: var(--ink); color: var(--ivory); padding: 100px 5% 52px; text-align: center; position: relative; overflow: hidden; }
    .page-header::before { content: ''; position: absolute; inset: 0; background: radial-gradient(ellipse 80% 60% at 50% 120%, rgba(184,149,90,0.14) 0%, transparent 65%); }
    .page-header h1 { font-family: 'Playfair Display', serif; font-size: clamp(2.8rem, 7vw, 4.5rem); font-weight: 900; position: relative; }
    .page-header p { color: rgba(248,244,238,0.6); margin-top: 10px; font-size: 0.98rem; position: relative; }
    .main-wrap { max-width: 1440px; margin: 0 auto; padding: 60px 5%; }

    /* ===== GUIDELINES BOX ===== */
    .guidelines-box { background: var(--cream); border-left: 3px solid var(--gold); padding: 24px 28px; border-radius: var(--radius); margin-bottom: 30px; }
    .guidelines-box h3 { font-family: 'Playfair Display', serif; margin-bottom: 12px; font-size: 1.1rem; }
    .guidelines-box ul { padding-left: 18px; }
    .guidelines-box ul li { font-size: 0.88rem; color: var(--muted); margin-bottom: 7px; line-height: 1.65; }

    /* ===== TOAST ===== */
    .toast { position: fixed; bottom: 28px; right: 28px; z-index: 9999; background: var(--forest); color: var(--white); padding: 14px 22px; border-radius: var(--radius); display: none; align-items: center; gap: 10px; font-size: 0.88rem; font-weight: 500; box-shadow: var(--shadow-lg); max-width: 360px; }
    .toast.show { display: flex; animation: slideUp 0.28s ease; }
    @keyframes slideUp { from { transform: translateY(16px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }

    /* ===== CTA BANNER ===== */
    .cta-banner { background: var(--gold); padding: 64px 5%; text-align: center; position: relative; overflow: hidden; }
    .cta-banner::before { content: ''; position: absolute; inset: 0; background: repeating-linear-gradient(45deg, transparent, transparent 40px, rgba(255,255,255,0.04) 40px, rgba(255,255,255,0.04) 80px); }

    .chip { display: inline-block; font-size: 0.7rem; font-weight: 600; letter-spacing: 0.08em; text-transform: uppercase; padding: 5px 14px; border-radius: 20px; background: var(--cream); color: var(--muted); cursor: pointer; transition: all 0.18s; }
    .chip:hover { background: var(--ink); color: var(--ivory); }

    /* ===== FOOTER ===== */
    footer { background: var(--ink); color: var(--ivory); padding: 64px 5% 32px; }
    .footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; gap: 48px; max-width: 1440px; margin: 0 auto; padding-bottom: 48px; border-bottom: 1px solid rgba(255,255,255,0.09); }
    .footer-brand .logo { font-size: 1.3rem; display: block; margin-bottom: 14px; color: var(--ivory); }
    .footer-brand p { font-size: 0.86rem; color: rgba(248,244,238,0.45); line-height: 1.75; }
    .footer-col h4 { font-size: 0.66rem; letter-spacing: 0.17em; text-transform: uppercase; font-weight: 700; color: var(--gold); margin-bottom: 18px; }
    .footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 9px; }
    .footer-col ul li a { font-size: 0.86rem; color: rgba(248,244,238,0.55); text-decoration: none; cursor: pointer; transition: color 0.18s; }
    .footer-col ul li a:hover { color: var(--ivory); }
    .footer-bottom { max-width: 1440px; margin: 0 auto; padding-top: 22px; display: flex; justify-content: space-between; font-size: 0.76rem; color: rgba(248,244,238,0.3); flex-wrap: wrap; gap: 8px; }

    .input-file-hidden { display: none; }
    .mt-8 { margin-top: 8px; }
    .mt-16 { margin-top: 16px; }
    .mt-24 { margin-top: 24px; }
    .divider { height: 1px; background: var(--border); }

    /* ===== RESPONSIVE ===== */
    @media (max-width: 1024px) {
      .featured-grid { grid-template-columns: 1fr; }
      .featured-main { border-right: none; border-bottom: 1px solid var(--border); }
      .articles-row { grid-template-columns: 1fr 1fr; }
      .two-col { grid-template-columns: 1fr; gap: 40px; }
      .footer-grid { grid-template-columns: 1fr 1fr; }
      .works-grid { grid-template-columns: 1fr 1fr; }
    }
    @media (max-width: 768px) {
      .nav-links { display: none; }
      .nav-hamburger { display: block; }
      .nav-search-trigger .kbd { display: none; }
      .articles-row { grid-template-columns: 1fr; }
      .footer-grid { grid-template-columns: 1fr 1fr; }
      .profile-stats { flex-direction: column; gap: 0; }
      .stat { border-right: none; border-bottom: 1px solid var(--border); }
      .form-grid { grid-template-columns: 1fr; }
      .works-grid { grid-template-columns: 1fr; }
      .work-item { padding: 28px 24px; }
      .search-palette { border-radius: 10px; }
      .search-overlay { padding-top: 56px; }
      .jf-wrap { grid-template-columns: 1fr; }
      .jf-sidebar { position: static; height: auto; }
      .jf-steps { display: flex; overflow-x: auto; padding: 0; }
      .jf-step-item { flex-direction: column; align-items: center; text-align: center; padding: 14px 16px; min-width: 90px; }
      .jf-step-desc { display: none; }
      .jf-sidebar-header { display: none; }
      .jf-progress-wrap { display: none; }
      .jf-cat-grid { grid-template-columns: repeat(2, 1fr); }
    }
    @media (max-width: 480px) {
      .footer-grid { grid-template-columns: 1fr; }
      .masthead-title { font-size: 3.2rem; }
      .featured-main { padding: 36px 5%; }
      .cat-section { padding: 48px 5%; }
    }
    @media (min-width: 1100px) {
      .nav-search-trigger .search-label { display: inline; }
      .nav-search-trigger { padding: 6px 14px 6px 12px; }
    }
  </style>
</head>
<body>

<!-- ======================== SPLASH SCREEN ======================== -->
<div id="splashScreen">
  <div class="splash-logo">OV</div>
  <div class="splash-brand">Orvexa</div>
  <div class="splash-sub">Foundation</div>
  <div class="splash-tagline">Ideas. Empowered. Impact. Sustainability.</div>
  <div class="splash-divider"></div>
  <button class="splash-enter" onclick="enterApp()">Masuk ke Platform →</button>
</div>

<!-- ======================== MAIN APP ======================== -->
<div id="mainApp">

<!-- SEARCH OVERLAY -->
<div class="search-overlay" id="searchOverlay" onclick="handleOverlayClick(event)">
  <div class="search-palette" id="searchPalette">
    <div class="search-input-row">
      <span class="search-icon-big">🔍</span>
      <input type="text" id="searchInput" class="search-input-main" placeholder="Cari artikel, topik, penulis…" oninput="doSearch(this.value)" onkeydown="handleSearchKey(event)" autocomplete="off" spellcheck="false"/>
      <button class="search-esc-badge" onclick="closeSearch()">ESC</button>
    </div>
    <div class="search-section" id="searchQuickNav">
      <div class="search-section-label">Navigasi Cepat</div>
      <div class="search-nav-items">
        <a class="search-nav-chip" onclick="closeSearch();showPage('home')"><span class="chip-emoji">🏠</span>Beranda</a>
        <a class="search-nav-chip" onclick="closeSearch();showPage('ekonomi')"><span class="chip-emoji">📊</span>Ekonomi</a>
        <a class="search-nav-chip" onclick="closeSearch();showPage('politik')"><span class="chip-emoji">🗳️</span>Politik</a>
        <a class="search-nav-chip" onclick="closeSearch();showPage('sosial')"><span class="chip-emoji">👥</span>Sosial</a>
        <a class="search-nav-chip" onclick="closeSearch();showPage('lingkungan')"><span class="chip-emoji">🌿</span>Lingkungan</a>
        <a class="search-nav-chip" onclick="closeSearch();showPage('pendidikan')"><span class="chip-emoji">📚</span>Pendidikan</a>
        <a class="search-nav-chip" onclick="closeSearch();showPage('karya')"><span class="chip-emoji">✍️</span>Karya Tulisan</a>
        <a class="search-nav-chip" onclick="closeSearch();showPage('kirim')"><span class="chip-emoji">📮</span>Kirim Tulisan</a>
      </div>
    </div>
    <div id="searchResultsArea"></div>
    <div class="search-footer">
      <div class="search-footer-hint">
        <span><kbd>↑↓</kbd> navigasi</span>
        <span><kbd>↵</kbd> pilih</span>
        <span><kbd>ESC</kbd> tutup</span>
      </div>
      <div class="search-result-count" id="searchCount"></div>
    </div>
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast">✓ <span id="toastMsg">Berhasil!</span></div>

<!-- NAVBAR -->
<nav>
  <div class="nav-inner">
    <a class="logo" onclick="showPage('home')">Orvexa <span>Foundations</span></a>
    <ul class="nav-links">
      <li><a onclick="showPage('home')" id="nav-home" class="active">Beranda</a></li>
      <li><a onclick="showPage('ekonomi')" id="nav-ekonomi">Ekonomi</a></li>
      <li><a onclick="showPage('politik')" id="nav-politik">Politik</a></li>
      <li><a onclick="showPage('sosial')" id="nav-sosial">Sosial</a></li>
      <li><a onclick="showPage('lingkungan')" id="nav-lingkungan">Lingkungan</a></li>
      <li><a onclick="showPage('pendidikan')" id="nav-pendidikan">Pendidikan</a></li>
      <li><a onclick="showPage('karya')" id="nav-karya">Karya Tulisan</a></li>
      <li><a onclick="showPage('profil')" id="nav-profil">Profil</a></li>
      <li><a onclick="showPage('pedoman')" id="nav-pedoman">Pedoman</a></li>
      <li><a onclick="showPage('kirim')" id="nav-kirim" class="nav-cta">Kirim Tulisan</a></li>
    </ul>
    <div class="nav-right">
      <button class="nav-search-trigger" onclick="openSearch()" title="Cari (Ctrl+K)">
        <span class="search-icon">🔍</span>
        <span class="search-label" style="font-size:0.8rem;color:var(--muted);">Cari…</span>
        <span class="kbd">⌘K</span>
      </button>
      <button class="nav-hamburger" onclick="toggleDrawer()" id="hamburgerBtn">☰</button>
    </div>
  </div>
</nav>

<!-- MOBILE DRAWER -->
<div class="mobile-drawer" id="mobileDrawer">
  <a onclick="showPage('home');closeDrawer()">Beranda</a>
  <a onclick="showPage('ekonomi');closeDrawer()">Ekonomi</a>
  <a onclick="showPage('politik');closeDrawer()">Politik</a>
  <a onclick="showPage('sosial');closeDrawer()">Sosial</a>
  <a onclick="showPage('lingkungan');closeDrawer()">Lingkungan</a>
  <a onclick="showPage('pendidikan');closeDrawer()">Pendidikan</a>
  <a onclick="showPage('karya');closeDrawer()">Karya Tulisan</a>
  <a onclick="showPage('profil');closeDrawer()">Profil</a>
  <a onclick="showPage('pedoman');closeDrawer()">Pedoman Penulisan</a>
  <a onclick="showPage('kirim');closeDrawer()" class="mob-cta">Kirim Tulisan →</a>
</div>

<!-- ==================== HOME PAGE ==================== -->
<div class="page active" id="page-home">
  <div class="hero-masthead" style="padding-top:110px;">
    <p class="masthead-eyebrow">Media Pemikiran & Analisis Indonesia</p>
    <h1 class="masthead-title">Orvexa<br><em>Foundations</em></h1>
    <p class="masthead-sub">Platform editorial terbuka untuk pemikiran, analisis, dan gagasan yang membentuk Indonesia masa depan.</p>
    <div class="masthead-actions">
      <button class="btn btn-gold" onclick="showPage('kirim')">Kirim Tulisan →</button>
      <button class="btn btn-outline" style="color:var(--ivory);border-color:rgba(255,255,255,0.25);" onclick="showPage('karya')">Baca Karya Tulisan</button>
    </div>
  </div>
  <div class="date-strip" id="dateBar"></div>
  <div id="homeFeatured"></div>
  <div class="cat-section" id="homeUserArticles" style="display:none;">
    <div class="section-header">
      <h2 class="section-title">Tulisan Terbaru</h2>
      <div class="section-line"></div>
      <a class="section-more" onclick="showPage('karya')">Lihat Semua →</a>
    </div>
    <div class="articles-row" id="homeUserGrid"></div>
  </div>
  <div class="cta-banner">
    <div style="position:relative;">
      <p style="font-size:0.72rem;letter-spacing:0.16em;text-transform:uppercase;color:rgba(255,255,255,0.75);margin-bottom:12px;">Kontribusi Pemikiran Anda</p>
      <h2 style="font-family:'Playfair Display',serif;font-size:clamp(1.8rem,4vw,2.6rem);font-weight:900;color:white;margin-bottom:14px;">Jadilah Suara Perubahan</h2>
      <p style="color:rgba(255,255,255,0.8);margin-bottom:28px;max-width:460px;margin-left:auto;margin-right:auto;font-size:0.95rem;">Orvexa Foundations membuka ruang bagi penulis, akademisi, dan praktisi untuk berbagi analisis dan gagasan secara langsung.</p>
      <button class="btn btn-primary" style="font-size:0.9rem;" onclick="showPage('kirim')">Kirim Tulisan Anda →</button>
    </div>
  </div>
</div>

<!-- ==================== CATEGORY PAGES ==================== -->
<div class="page" id="page-ekonomi">
  <div class="page-header"><p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;position:relative;">Rubrik</p><h1>Ekonomi</h1><p>Analisis mendalam tentang dinamika ekonomi Indonesia dan global</p></div>
  <div class="main-wrap"><div class="articles-row" id="grid-ekonomi"><div class="empty-state"><div class="empty-icon">📊</div><h3>Belum ada tulisan</h3><p>Jadilah yang pertama mengirim tulisan di kategori Ekonomi.</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan →</button></div></div></div>
</div>
<div class="page" id="page-politik">
  <div class="page-header"><p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;position:relative;">Rubrik</p><h1>Politik</h1><p>Kajian kritis tentang demokrasi, kebijakan publik, dan tata kelola negara</p></div>
  <div class="main-wrap"><div class="articles-row" id="grid-politik"><div class="empty-state"><div class="empty-icon">🗳️</div><h3>Belum ada tulisan</h3><p>Jadilah yang pertama mengirim tulisan di kategori Politik.</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan →</button></div></div></div>
</div>
<div class="page" id="page-sosial">
  <div class="page-header"><p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;position:relative;">Rubrik</p><h1>Sosial</h1><p>Mengurai dinamika masyarakat dan transformasi budaya Indonesia</p></div>
  <div class="main-wrap"><div class="articles-row" id="grid-sosial"><div class="empty-state"><div class="empty-icon">👥</div><h3>Belum ada tulisan</h3><p>Jadilah yang pertama mengirim tulisan di kategori Sosial.</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan →</button></div></div></div>
</div>
<div class="page" id="page-lingkungan">
  <div class="page-header"><p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;position:relative;">Rubrik</p><h1>Lingkungan</h1><p>Isu iklim, keberlanjutan, dan keadilan lingkungan hidup</p></div>
  <div class="main-wrap"><div class="articles-row" id="grid-lingkungan"><div class="empty-state"><div class="empty-icon">🌿</div><h3>Belum ada tulisan</h3><p>Jadilah yang pertama mengirim tulisan di kategori Lingkungan.</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan →</button></div></div></div>
</div>
<div class="page" id="page-pendidikan">
  <div class="page-header"><p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;position:relative;">Rubrik</p><h1>Pendidikan</h1><p>Refleksi dan gagasan untuk memajukan pendidikan Indonesia</p></div>
  <div class="main-wrap"><div class="articles-row" id="grid-pendidikan"><div class="empty-state"><div class="empty-icon">📚</div><h3>Belum ada tulisan</h3><p>Jadilah yang pertama mengirim tulisan di kategori Pendidikan.</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan →</button></div></div></div>
</div>

<!-- ==================== KARYA TULISAN ==================== -->
<div class="page" id="page-karya">
  <div class="page-header"><p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;position:relative;">Arsip</p><h1>Karya Tulisan</h1><p>Koleksi seluruh tulisan yang telah dikirimkan</p></div>
  <div style="background:var(--cream);padding:20px 5%;border-bottom:1px solid var(--border);">
    <div style="max-width:1440px;margin:0 auto;display:flex;gap:10px;align-items:center;flex-wrap:wrap;">
      <span style="font-size:0.74rem;font-weight:700;color:var(--muted);letter-spacing:0.08em;text-transform:uppercase;">Filter:</span>
      <button class="btn btn-primary btn-sm" onclick="filterWorks('semua')" id="filter-semua">Semua</button>
      <button class="btn btn-outline btn-sm" onclick="filterWorks('ekonomi')" id="filter-ekonomi">Ekonomi</button>
      <button class="btn btn-outline btn-sm" onclick="filterWorks('politik')" id="filter-politik">Politik</button>
      <button class="btn btn-outline btn-sm" onclick="filterWorks('sosial')" id="filter-sosial">Sosial</button>
      <button class="btn btn-outline btn-sm" onclick="filterWorks('lingkungan')" id="filter-lingkungan">Lingkungan</button>
      <button class="btn btn-outline btn-sm" onclick="filterWorks('pendidikan')" id="filter-pendidikan">Pendidikan</button>
      <button class="btn btn-outline btn-sm" onclick="filterWorks('opini')" id="filter-opini">Opini Umum</button>
    </div>
  </div>
  <div class="main-wrap" style="padding-top:40px;">
    <div id="worksContainer">
      <div class="empty-state"><div class="empty-icon">✍️</div><h3>Belum Ada Tulisan</h3><p>Platform ini siap menampung karya Anda. Kirimkan tulisan pertama dan langsung tampil di sini!</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan Sekarang →</button></div>
    </div>
  </div>
</div>

<!-- ==================== PROFIL ==================== -->
<div class="page" id="page-profil">
  <div class="profile-hero">
    <div class="profile-avatar">OF</div>
    <h1 class="profile-name">Orvexa Foundations</h1>
    <p class="profile-role">Platform Publikasi Terbuka</p>
    <p class="profile-bio">Orvexa Foundations adalah platform editorial independen yang berkomitmen menyajikan pemikiran kritis, analisis mendalam, dan gagasan segar tentang Indonesia.</p>
  </div>
  <div class="profile-stats">
    <div class="stat"><div class="stat-num" id="statArticles">0</div><div class="stat-label">Tulisan Terbit</div></div>
    <div class="stat"><div class="stat-num" id="statAuthors">0</div><div class="stat-label">Penulis Berkontribusi</div></div>
    <div class="stat"><div class="stat-num">∞</div><div class="stat-label">Topik Terbuka</div></div>
    <div class="stat"><div class="stat-num">0</div><div class="stat-label">Hari Review</div></div>
  </div>
  <div class="profile-content">
    <div class="guidelines-box"><h3>Tentang Orvexa Foundations</h3><p style="font-size:0.92rem;color:var(--muted);line-height:1.75;">Platform publikasi terbuka di mana setiap tulisan yang dikirim langsung terbit tanpa proses review atau moderasi.</p></div>
    <h2 style="font-family:'Playfair Display',serif;font-size:1.8rem;margin-bottom:24px;">Visi & Misi</h2>
    <p style="color:var(--muted);line-height:1.8;margin-bottom:20px;"><strong style="color:var(--ink);">Visi:</strong> Menjadi platform referensi pemikiran terdepan di Indonesia.</p>
    <p style="color:var(--muted);line-height:1.8;margin-bottom:40px;"><strong style="color:var(--ink);">Misi:</strong> Menyediakan ruang publikasi terbuka bagi siapa saja.</p>
    <div style="text-align:center;padding:40px;background:var(--cream);border-radius:var(--radius);">
      <h3 style="font-family:'Playfair Display',serif;font-size:1.5rem;margin-bottom:12px;">Siap Berkontribusi?</h3>
      <p style="color:var(--muted);margin-bottom:24px;font-size:0.95rem;">Tulisan Anda akan langsung terbit begitu dikirim.</p>
      <button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan →</button>
    </div>
  </div>
</div>

<!-- ==================== KIRIM TULISAN ==================== -->
<div class="page" id="page-kirim">
<div class="jf-wrap">
  <aside class="jf-sidebar">
    <div class="jf-sidebar-header">
      <div class="jf-sidebar-logo">Orvexa <span>Foundations</span></div>
      <div class="jf-sidebar-tagline">Platform publikasi terbuka · Tulisan langsung terbit</div>
    </div>
    <div class="jf-steps" id="jfSteps">
      <div class="jf-step-item active" onclick="goStep(1)" id="jf-step-nav-1"><div class="jf-step-num" id="jf-stepnum-1">1</div><div class="jf-step-info"><span class="jf-step-label">Identitas Penulis</span><span class="jf-step-desc">Nama, email & institusi</span></div></div>
      <div class="jf-step-item" onclick="goStep(2)" id="jf-step-nav-2"><div class="jf-step-num" id="jf-stepnum-2">2</div><div class="jf-step-info"><span class="jf-step-label">Kategori Tulisan</span><span class="jf-step-desc">Pilih rubrik yang sesuai</span></div></div>
      <div class="jf-step-item" onclick="goStep(3)" id="jf-step-nav-3"><div class="jf-step-num" id="jf-stepnum-3">3</div><div class="jf-step-info"><span class="jf-step-label">Judul & Ringkasan</span><span class="jf-step-desc">Headline & abstrak</span></div></div>
      <div class="jf-step-item" onclick="goStep(4)" id="jf-step-nav-4"><div class="jf-step-num" id="jf-stepnum-4">4</div><div class="jf-step-info"><span class="jf-step-label">Isi Tulisan</span><span class="jf-step-desc">Konten artikel lengkap</span></div></div>
      <div class="jf-step-item" onclick="goStep(5)" id="jf-step-nav-5"><div class="jf-step-num" id="jf-stepnum-5">5</div><div class="jf-step-info"><span class="jf-step-label">Upload & Kirim</span><span class="jf-step-desc">Lampiran & terbitkan</span></div></div>
    </div>
    <div class="jf-progress-wrap">
      <div class="jf-progress-label"><span>Progres pengisian</span><span id="jfProgressPct">0%</span></div>
      <div class="jf-progress-track"><div class="jf-progress-fill" id="jfProgressFill"></div></div>
    </div>
  </aside>

  <main class="jf-main" style="padding-top:48px;">
    <div class="jf-panel active" id="jf-panel-1">
      <div class="jf-panel-header"><span class="jf-panel-step-tag">Langkah 1 dari 5</span><h2 class="jf-panel-title">Identitas Penulis</h2><p class="jf-panel-subtitle">Isi informasi dasar tentang diri Anda sebagai penulis.</p></div>
      <div class="jf-field-card"><div class="jf-field-label">Nama Lengkap <span class="jf-req">*</span></div><input class="jf-input" type="text" id="f-nama" placeholder="Contoh: Ahmad Fauzi Rahman"/></div>
      <div class="jf-field-card"><div class="jf-field-label">Alamat Email <span class="jf-req">*</span><span class="jf-field-hint">Untuk konfirmasi penerbitan tulisan Anda</span></div><input class="jf-input" type="email" id="f-email" placeholder="email@anda.com"/></div>
      <div class="jf-field-card"><div class="jf-field-label">Nomor WhatsApp<span class="jf-field-hint">Opsional</span></div><input class="jf-input" type="tel" id="f-wa" placeholder="+62 812 3456 7890"/></div>
      <div class="jf-field-card"><div class="jf-field-label">Afiliasi / Institusi<span class="jf-field-hint">Universitas, lembaga, atau "Independen"</span></div><input class="jf-input" type="text" id="f-afiliasi" placeholder="Contoh: Universitas Indonesia / Independen"/></div>
      <div class="jf-field-card"><div class="jf-field-label">Biografi Singkat<span class="jf-field-hint">Akan ditampilkan di bawah artikel Anda (maks. 150 kata)</span></div><textarea class="jf-textarea" id="f-bio" style="min-height:100px;" placeholder="Ceritakan latar belakang, keahlian, dan fokus penulisan Anda…" oninput="jfCount(this,'bioCount',150,'kata')"></textarea><div class="jf-count" id="bioCount">0 / 150 kata</div></div>
      <div class="jf-nav"><span></span><button class="jf-btn-next" onclick="nextStep(1)">Lanjutkan <span>→</span></button></div>
    </div>

    <div class="jf-panel" id="jf-panel-2">
      <div class="jf-panel-header"><span class="jf-panel-step-tag">Langkah 2 dari 5</span><h2 class="jf-panel-title">Pilih Kategori Rubrik</h2><p class="jf-panel-subtitle">Tentukan rubrik yang paling sesuai dengan topik tulisan Anda.</p></div>
      <div class="jf-field-card"><div class="jf-field-label">Kategori <span class="jf-req">*</span></div><div class="jf-cat-grid" id="catGrid"><div class="jf-cat-card" onclick="selectCat('ekonomi',this)"><span class="cat-emoji">📊</span><div class="cat-name">Ekonomi</div><div class="cat-sub">Bisnis, keuangan, pasar</div></div><div class="jf-cat-card" onclick="selectCat('politik',this)"><span class="cat-emoji">🗳️</span><div class="cat-name">Politik</div><div class="cat-sub">Demokrasi, kebijakan publik</div></div><div class="jf-cat-card" onclick="selectCat('sosial',this)"><span class="cat-emoji">👥</span><div class="cat-name">Sosial</div><div class="cat-sub">Masyarakat, budaya</div></div><div class="jf-cat-card" onclick="selectCat('lingkungan',this)"><span class="cat-emoji">🌿</span><div class="cat-name">Lingkungan</div><div class="cat-sub">Iklim, keberlanjutan</div></div><div class="jf-cat-card" onclick="selectCat('pendidikan',this)"><span class="cat-emoji">📚</span><div class="cat-name">Pendidikan</div><div class="cat-sub">Kurikulum, riset, inovasi</div></div><div class="jf-cat-card" onclick="selectCat('opini',this)"><span class="cat-emoji">✍️</span><div class="cat-name">Opini Umum</div><div class="cat-sub">Essay, kolom, gagasan</div></div></div><input type="hidden" id="f-kategori" value=""/></div>
      <div class="jf-field-card"><div class="jf-field-label">Jenis Tulisan <span class="jf-req">*</span></div><div class="jf-radio-group"><label class="jf-radio-option" onclick="this.classList.add('selected');this.parentElement.querySelectorAll('.jf-radio-option').forEach(o=>o!==this&&o.classList.remove('selected'))"><input type="radio" name="jenisTulisan" value="analisis"/> <span class="jf-radio-label">📐 Analisis — tulisan berbasis data dan penelitian</span></label><label class="jf-radio-option" onclick="this.classList.add('selected');this.parentElement.querySelectorAll('.jf-radio-option').forEach(o=>o!==this&&o.classList.remove('selected'))"><input type="radio" name="jenisTulisan" value="opini"/><span class="jf-radio-label">💬 Opini / Kolom — pandangan dan argumentasi pribadi</span></label><label class="jf-radio-option" onclick="this.classList.add('selected');this.parentElement.querySelectorAll('.jf-radio-option').forEach(o=>o!==this&&o.classList.remove('selected'))"><input type="radio" name="jenisTulisan" value="esai"/><span class="jf-radio-label">📝 Esai — refleksi mendalam dan naratif</span></label><label class="jf-radio-option" onclick="this.classList.add('selected');this.parentElement.querySelectorAll('.jf-radio-option').forEach(o=>o!==this&&o.classList.remove('selected'))"><input type="radio" name="jenisTulisan" value="reportase"/><span class="jf-radio-label">🔎 Reportase — liputan dan investigasi</span></label></div></div>
      <div class="jf-nav"><button class="jf-btn-back" onclick="goStep(1)">← Kembali</button><button class="jf-btn-next" onclick="nextStep(2)">Lanjutkan <span>→</span></button></div>
    </div>

    <div class="jf-panel" id="jf-panel-3">
      <div class="jf-panel-header"><span class="jf-panel-step-tag">Langkah 3 dari 5</span><h2 class="jf-panel-title">Judul & Ringkasan</h2><p class="jf-panel-subtitle">Judul yang kuat dan ringkasan yang menarik akan membantu pembaca menemukan tulisan Anda.</p></div>
      <div class="jf-field-card"><div class="jf-field-label">Judul Tulisan <span class="jf-req">*</span><span class="jf-field-hint">Ringkas, deskriptif, dan tidak clickbait</span></div><input class="jf-input" type="text" id="f-judul" placeholder="Contoh: Ketimpangan Digital dan Masa Depan Ekonomi Indonesia" maxlength="120" oninput="jfCount(this,'judulCount',120,'karakter')"/><div class="jf-count" id="judulCount">0 / 120 karakter</div></div>
      <div class="jf-field-card"><div class="jf-field-label">Ringkasan / Abstrak <span class="jf-req">*</span><span class="jf-field-hint">1–2 kalimat yang menggambarkan isi dan argumen utama tulisan</span></div><textarea class="jf-textarea" id="f-ringkasan" style="min-height:100px;" placeholder="Tulisan ini menganalisis…" maxlength="300" oninput="jfCount(this,'ringkasanCount',300,'karakter')"></textarea><div class="jf-count" id="ringkasanCount">0 / 300 karakter</div></div>
      <div class="jf-field-card"><div class="jf-field-label">Kata Kunci<span class="jf-field-hint">Pisahkan dengan koma (maks. 5 kata kunci)</span></div><input class="jf-input" type="text" id="f-keywords" placeholder="Contoh: ekonomi digital, ketimpangan, UMKM, teknologi"/></div>
      <div class="jf-nav"><button class="jf-btn-back" onclick="goStep(2)">← Kembali</button><button class="jf-btn-next" onclick="nextStep(3)">Lanjutkan <span>→</span></button></div>
    </div>

    <div class="jf-panel" id="jf-panel-4">
      <div class="jf-panel-header"><span class="jf-panel-step-tag">Langkah 4 dari 5</span><h2 class="jf-panel-title">Isi Tulisan</h2><p class="jf-panel-subtitle">Tulis atau tempel isi artikel Anda. Minimal 100 kata untuk dapat diterbitkan.</p></div>
      <div class="jf-field-card"><div class="jf-field-label">Konten Artikel <span class="jf-req">*</span><span class="jf-field-hint">Gunakan paragraf terpisah untuk memudahkan pembacaan</span></div><textarea class="jf-textarea" id="f-isi" style="min-height:320px;" placeholder="Mulai tulis artikel Anda di sini…&#10;&#10;Pisahkan setiap paragraf dengan baris kosong." oninput="updateWordCount(this)"></textarea><div style="display:flex;justify-content:space-between;align-items:center;margin-top:8px;"><span class="jf-count" id="wordCount" style="text-align:left;">0 kata · estimasi 0 menit baca</span><span class="jf-count" id="warnText" style="color:var(--rust);"></span></div></div>
      <div class="jf-nav"><button class="jf-btn-back" onclick="goStep(3)">← Kembali</button><button class="jf-btn-next" onclick="nextStep(4)">Lanjutkan <span>→</span></button></div>
    </div>

    <div class="jf-panel" id="jf-panel-5">
      <div class="jf-panel-header"><span class="jf-panel-step-tag">Langkah 5 dari 5</span><h2 class="jf-panel-title">Upload & Terbitkan</h2><p class="jf-panel-subtitle">Langkah terakhir — lampirkan dokumen (opsional) lalu terbitkan tulisan Anda.</p></div>
      <div class="jf-field-card" style="background:var(--cream);border-color:var(--border);"><div class="jf-field-label">📋 Ringkasan Pengiriman</div><div id="jf-summary" style="margin-top:8px;display:grid;gap:10px;"></div></div>
      <div class="jf-field-card"><div class="jf-field-label">Upload Dokumen Pendukung<span class="jf-field-hint">Opsional — .doc, .docx, .pdf, .txt · Maks. 10 MB</span></div><div class="jf-upload" id="uploadZone" onclick="document.getElementById('fileInput').click()" ondragover="event.preventDefault();this.classList.add('dragging')" ondragleave="this.classList.remove('dragging')" ondrop="handleDrop(event)"><div style="font-size:2rem;margin-bottom:10px;">📎</div><p style="font-size:0.88rem;color:var(--ink);font-weight:600;">Klik untuk pilih file</p><p style="font-size:0.78rem;color:var(--muted);margin-top:4px;">atau seret & lepas ke sini</p><p id="uploadedFileName" style="margin-top:12px;font-size:0.84rem;color:var(--gold);font-weight:700;"></p></div><input type="file" id="fileInput" class="input-file-hidden" accept=".doc,.docx,.pdf,.txt" onchange="handleFileSelect(this)"/></div>
      <div class="jf-field-card" style="background:#e8f4ec;border-color:#b8ddc4;"><div style="display:flex;gap:14px;align-items:flex-start;"><span style="font-size:1.4rem;margin-top:2px;">⚡</span><div><div style="font-weight:700;color:var(--forest);margin-bottom:4px;font-size:0.9rem;">Auto-Publish Aktif</div><p style="font-size:0.84rem;color:#2a5a3a;line-height:1.65;">Tulisan Anda akan <strong>langsung diterbitkan</strong> begitu Anda menekan tombol di bawah.</p></div></div></div>
      <div class="jf-nav"><button class="jf-btn-back" onclick="goStep(4)">← Kembali</button><button class="jf-btn-submit" onclick="submitForm()">⚡ Terbitkan Tulisan Sekarang</button></div>
    </div>

    <div class="jf-panel" id="jf-panel-success">
      <div class="jf-success">
        <div class="jf-success-icon">✓</div>
        <h2 style="font-family:'Playfair Display',serif;font-size:2rem;font-weight:900;margin-bottom:12px;">Tulisan Berhasil Diterbitkan!</h2>
        <p style="font-size:0.96rem;color:var(--muted);max-width:440px;margin:0 auto 32px;line-height:1.7;">Tulisan Anda kini sudah tampil di Beranda, halaman Kategori, dan Karya Tulisan.</p>
        <div style="display:flex;gap:12px;justify-content:center;flex-wrap:wrap;">
          <button class="btn btn-primary" onclick="showPage('home')">Lihat di Beranda →</button>
          <button class="btn btn-outline" onclick="showPage('karya')">Karya Tulisan</button>
          <button class="btn btn-outline" onclick="resetJFForm()">Kirim Tulisan Lain</button>
        </div>
      </div>
    </div>
  </main>
</div>
</div>

<!-- ==================== ARTICLE VIEW ==================== -->
<div class="page" id="page-article">
  <div class="article-view-hero">
    <div style="max-width:840px;margin:0 auto;position:relative;">
      <span class="category-tag" id="art-cat-tag"></span>
      <h1 class="article-view-title" id="art-title"></h1>
      <div class="art-meta" style="margin-top:20px;">
        <span class="author" id="art-author"></span>
        <span class="dot">·</span>
        <span id="art-date"></span>
        <span class="dot">·</span>
        <span id="art-readtime">5 menit baca</span>
      </div>
    </div>
  </div>
  <div class="article-body" id="articleBodyContent"></div>
</div>

<!-- ==================== PEDOMAN PENULISAN ==================== -->
<div class="page" id="page-pedoman">
  <div class="page-header"><p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;position:relative;">Panduan</p><h1>Pedoman Penulisan</h1><p>Standar editorial Orvexa Foundations untuk tulisan yang informatif, etis, dan profesional</p></div>
  <div style="max-width:860px;margin:0 auto;padding:64px 5%;">
    <div style="background:var(--ink);color:var(--ivory);padding:36px 40px;border-radius:var(--radius);margin-bottom:48px;position:relative;overflow:hidden;">
      <div style="position:absolute;inset:0;background:radial-gradient(ellipse 70% 60% at 80% 50%,rgba(184,149,90,0.18) 0%,transparent 70%);pointer-events:none;"></div>
      <p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:12px;position:relative;">Tentang Pedoman Ini</p>
      <p style="font-family:'DM Serif Display',serif;font-size:1.25rem;line-height:1.7;color:rgba(248,244,238,0.9);position:relative;">Pedoman ini bertujuan memastikan bahwa setiap tulisan yang diterbitkan di Orvexa Foundations tidak hanya informatif, tetapi juga <em>etis, akurat, dan profesional</em>.</p>
    </div>
    <div style="text-align:center;padding:48px 32px;background:var(--ink);border-radius:var(--radius);">
      <div style="position:relative;"><p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:12px;">Siap Menulis?</p><h3 style="font-family:'Playfair Display',serif;font-size:1.8rem;font-weight:900;color:var(--ivory);margin-bottom:12px;">Terapkan Pedoman Ini</h3><button class="btn btn-gold" onclick="showPage('kirim')">Kirim Tulisan Sekarang →</button></div>
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-grid">
    <div class="footer-brand">
      <a class="logo" onclick="showPage('home')">Orvexa <span>Foundations</span></a>
      <p>Platform publikasi terbuka untuk pemikiran, analisis, dan gagasan.</p>
    </div>
    <div class="footer-col"><h4>Rubrik</h4><ul><li><a onclick="showPage('ekonomi')">Ekonomi</a></li><li><a onclick="showPage('politik')">Politik</a></li><li><a onclick="showPage('sosial')">Sosial</a></li><li><a onclick="showPage('lingkungan')">Lingkungan</a></li><li><a onclick="showPage('pendidikan')">Pendidikan</a></li></ul></div>
    <div class="footer-col"><h4>Media</h4><ul><li><a onclick="showPage('karya')">Karya Tulisan</a></li><li><a onclick="showPage('kirim')">Kirim Tulisan</a></li><li><a onclick="showPage('profil')">Profil</a></li></ul></div>
    <div class="footer-col"><h4>Lainnya</h4><ul><li><a onclick="showPage('pedoman')">Pedoman Penulisan</a></li><li><a>Kebijakan Privasi</a></li><li><a>Kontak</a></li></ul></div>
  </div>
  <div class="footer-bottom">
    <span>© 2025 Orvexa Foundations. Hak cipta dilindungi undang-undang.</span>
    <span>redaksi@orvexafoundations.id</span>
  </div>
</footer>

</div><!-- end #mainApp -->

<script>
// ================================================================
// SPLASH → APP
// ================================================================
function enterApp() {
  document.getElementById('splashScreen').classList.add('hidden');
  const app = document.getElementById('mainApp');
  app.classList.add('visible');
  renderHome();
  updateStats();
}

// Auto-dismiss splash after 6 seconds if user doesn't click
setTimeout(() => {
  const splash = document.getElementById('splashScreen');
  if (!splash.classList.contains('hidden')) enterApp();
}, 6000);

// ================================================================
// DATA STORE
// ================================================================
let publishedArticles = [];

// ================================================================
// NAVIGATION
// ================================================================
function showPage(pageId) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.nav-links a').forEach(a => a.classList.remove('active'));
  const page = document.getElementById('page-' + pageId);
  if (page) page.classList.add('active');
  const navEl = document.getElementById('nav-' + pageId);
  if (navEl) navEl.classList.add('active');
  window.scrollTo({ top: 0, behavior: 'smooth' });
  closeSearch();
  closeDrawer();
  if (pageId === 'home') renderHome();
  if (pageId === 'karya') renderWorks('semua');
  if (['ekonomi','politik','sosial','lingkungan','pendidikan'].includes(pageId)) renderCategoryPage(pageId);
}

function toggleDrawer() { document.getElementById('mobileDrawer').classList.toggle('open'); }
function closeDrawer() { document.getElementById('mobileDrawer').classList.remove('open'); }

// ================================================================
// ARTICLE VIEW
// ================================================================
function showArticle(article) {
  const catLabels = {ekonomi:'Ekonomi',politik:'Politik',sosial:'Sosial',lingkungan:'Lingkungan',pendidikan:'Pendidikan',opini:'Opini Umum'};
  const catClasses = {ekonomi:'cat-ekonomi',politik:'cat-politik',sosial:'cat-sosial',lingkungan:'cat-lingkungan',pendidikan:'cat-pendidikan',opini:'cat-opini'};
  document.getElementById('art-title').textContent = article.judul;
  document.getElementById('art-author').textContent = article.nama;
  document.getElementById('art-date').textContent = article.tanggal;
  const tag = document.getElementById('art-cat-tag');
  tag.textContent = catLabels[article.kategori] || article.kategori;
  tag.className = 'category-tag ' + (catClasses[article.kategori] || 'cat-opini');
  const words = article.isi.split(/\s+/).length;
  const mins = Math.max(1, Math.round(words / 200));
  document.getElementById('art-readtime').textContent = mins + ' menit baca';
  const body = document.getElementById('articleBodyContent');
  const ringkasan = article.ringkasan || '';
  const paragraphs = article.isi.split(/\n\n+/).filter(p => p.trim());
  let html = '';
  if (ringkasan) html += `<blockquote>${ringkasan}</blockquote>`;
  paragraphs.forEach(p => { html += `<p>${p.trim()}</p>`; });
  html += `<div style="border-top:1px solid var(--border);padding-top:32px;margin-top:44px;"><button class="btn btn-outline" onclick="history.back();window.scrollTo(0,0);" style="margin-bottom:24px;">← Kembali</button><div style="background:var(--cream);padding:24px;border-radius:var(--radius);display:flex;gap:16px;align-items:center;"><div style="width:48px;height:48px;border-radius:50%;background:linear-gradient(135deg,var(--gold),var(--rust));display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1rem;flex-shrink:0;">${article.nama.split(' ').slice(0,2).map(n=>n[0]).join('')}</div><div><p style="font-size:0.72rem;color:var(--muted);margin-bottom:3px;letter-spacing:0.06em;text-transform:uppercase;">Tentang Penulis</p><p style="font-weight:600;">${article.nama}</p>${article.afiliasi ? `<p style="font-size:0.83rem;color:var(--muted);">${article.afiliasi}</p>` : ''}</div></div></div>`;
  body.innerHTML = html;
  showPage('article');
}

// ================================================================
// RENDER
// ================================================================
const catLabels = {ekonomi:'Ekonomi',politik:'Politik',sosial:'Sosial',lingkungan:'Lingkungan',pendidikan:'Pendidikan',opini:'Opini Umum'};
const catClasses = {ekonomi:'cat-ekonomi',politik:'cat-politik',sosial:'cat-sosial',lingkungan:'cat-lingkungan',pendidikan:'cat-pendidikan',opini:'cat-opini'};
const catEmojis = {ekonomi:'📊',politik:'🗳️',sosial:'👥',lingkungan:'🌿',pendidikan:'📚',opini:'✍️'};

function makeCardHTML(article, idx) {
  return `<div class="article-card" onclick="showArticle(publishedArticles[${idx}])"><div class="card-img-placeholder">${catEmojis[article.kategori] || '📝'}</div><span class="category-tag ${catClasses[article.kategori] || 'cat-opini'}">${catLabels[article.kategori] || article.kategori}</span><h3 class="art-title md mt-8">${escHtml(article.judul)}</h3>${article.ringkasan ? `<p class="art-excerpt mt-8" style="font-size:0.85rem;">${escHtml(article.ringkasan.substring(0,120))}${article.ringkasan.length>120?'…':''}</p>` : ''}<div class="art-meta mt-16"><span class="author">${escHtml(article.nama)}</span><span class="dot">·</span><span>${article.tanggal}</span></div></div>`;
}

function makeWorkItemHTML(article, idx) {
  return `<div class="work-item" data-cat="${article.kategori}" onclick="showArticle(publishedArticles[${idx}])"><span class="category-tag ${catClasses[article.kategori] || 'cat-opini'}">${catLabels[article.kategori] || article.kategori}</span><h3 class="art-title lg mt-8">${escHtml(article.judul)}</h3>${article.ringkasan ? `<p class="art-excerpt mt-8" style="font-size:0.88rem;">${escHtml(article.ringkasan)}</p>` : ''}<div class="art-meta mt-16"><span class="author">${escHtml(article.nama)}</span><span class="dot">·</span><span>${article.tanggal}</span>${article.afiliasi ? `<span class="dot">·</span><span>${escHtml(article.afiliasi)}</span>` : ''}</div></div>`;
}

function renderHome() {
  const featuredEl = document.getElementById('homeFeatured');
  const userSectionEl = document.getElementById('homeUserArticles');
  const userGridEl = document.getElementById('homeUserGrid');
  if (!featuredEl) return;
  if (publishedArticles.length === 0) {
    featuredEl.innerHTML = `<div style="max-width:1440px;margin:0 auto;padding:80px 5%;text-align:center;"><div class="empty-state"><div class="empty-icon">🌟</div><h3>Platform Siap Digunakan</h3><p>Belum ada tulisan yang diterbitkan. Kirim tulisan pertama Anda dan langsung tampil di sini!</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan Pertama →</button></div></div>`;
    userSectionEl.style.display = 'none';
    return;
  }
  const recent = publishedArticles.slice().reverse();
  const main = recent[0];
  const mainIdx = publishedArticles.indexOf(main);
  let sidebarHTML = '';
  for (let i = 1; i < Math.min(4, recent.length); i++) {
    const a = recent[i];
    const idx = publishedArticles.indexOf(a);
    sidebarHTML += `<div class="featured-sidebar-item" onclick="showArticle(publishedArticles[${idx}])"><span class="category-tag ${catClasses[a.kategori]||'cat-opini'}">${catLabels[a.kategori]||a.kategori}</span><h3 class="art-title lg">${escHtml(a.judul)}</h3>${a.ringkasan ? `<p class="art-excerpt" style="font-size:0.85rem;">${escHtml(a.ringkasan.substring(0,100))}…</p>` : ''}<div class="art-meta mt-16"><span class="author">${escHtml(a.nama)}</span><span class="dot">·</span><span>${a.tanggal}</span></div></div>`;
  }
  featuredEl.innerHTML = `<div class="featured-grid"><div class="featured-main" onclick="showArticle(publishedArticles[${mainIdx}])"><span class="category-tag ${catClasses[main.kategori]||'cat-opini'}">${catLabels[main.kategori]||main.kategori}</span><h2 class="art-title xl">${escHtml(main.judul)}</h2>${main.ringkasan ? `<p class="art-excerpt">${escHtml(main.ringkasan)}</p>` : ''}<div class="art-meta"><span class="author">${escHtml(main.nama)}</span><span class="dot">·</span><span>${main.tanggal}</span></div></div><div class="featured-sidebar">${sidebarHTML || '<div class="featured-sidebar-item" style="display:flex;align-items:center;justify-content:center;flex:1;color:var(--muted);font-size:0.9rem;">Kirim lebih banyak tulisan untuk ditampilkan</div>'}</div></div>`;
  if (recent.length > 4) {
    const moreArticles = recent.slice(4, 10);
    userGridEl.innerHTML = moreArticles.map(a => makeCardHTML(a, publishedArticles.indexOf(a))).join('');
    userSectionEl.style.display = 'block';
  } else {
    userSectionEl.style.display = 'none';
  }
}

function renderCategoryPage(cat) {
  const grid = document.getElementById('grid-' + cat);
  if (!grid) return;
  const filtered = publishedArticles.filter(a => a.kategori === cat);
  if (filtered.length === 0) {
    const emptyIcons = {ekonomi:'📊',politik:'🗳️',sosial:'👥',lingkungan:'🌿',pendidikan:'📚'};
    const catName = catLabels[cat] || cat;
    grid.innerHTML = `<div class="empty-state"><div class="empty-icon">${emptyIcons[cat]||'📝'}</div><h3>Belum ada tulisan</h3><p>Jadilah yang pertama mengirim tulisan di kategori ${catName}.</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan →</button></div>`;
  } else {
    grid.innerHTML = filtered.slice().reverse().map(a => makeCardHTML(a, publishedArticles.indexOf(a))).join('');
  }
}

let currentFilter = 'semua';
function renderWorks(cat) {
  currentFilter = cat;
  ['semua','ekonomi','politik','sosial','lingkungan','pendidikan','opini'].forEach(c => {
    const btn = document.getElementById('filter-' + c);
    if (!btn) return;
    btn.className = c === cat ? 'btn btn-primary btn-sm' : 'btn btn-outline btn-sm';
  });
  const container = document.getElementById('worksContainer');
  const filtered = cat === 'semua' ? publishedArticles : publishedArticles.filter(a => a.kategori === cat);
  if (filtered.length === 0) {
    const catName = cat === 'semua' ? '' : ' di kategori ' + (catLabels[cat]||cat);
    container.innerHTML = `<div class="empty-state"><div class="empty-icon">✍️</div><h3>Belum Ada Tulisan${cat!=='semua'?' di Kategori Ini':''}</h3><p>Platform ini siap menampung karya Anda${catName}.</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan Sekarang →</button></div>`;
  } else {
    const reversed = filtered.slice().reverse();
    container.innerHTML = `<div class="works-grid">${reversed.map(a => makeWorkItemHTML(a, publishedArticles.indexOf(a))).join('')}</div>`;
  }
}

function filterWorks(cat) { renderWorks(cat); }
function updateStats() {
  const el1 = document.getElementById('statArticles');
  const el2 = document.getElementById('statAuthors');
  if (el1) el1.textContent = publishedArticles.length;
  if (el2) { const authors = new Set(publishedArticles.map(a => a.nama.toLowerCase().trim())); el2.textContent = authors.size; }
}

// ================================================================
// FORM SUBMISSION
// ================================================================
function submitForm() {
  const nama = document.getElementById('f-nama').value.trim();
  const email = document.getElementById('f-email').value.trim();
  const judul = document.getElementById('f-judul').value.trim();
  const isi = document.getElementById('f-isi').value.trim();
  const kategori = document.getElementById('f-kategori').value;
  const ringkasan = document.getElementById('f-ringkasan').value.trim();
  const afiliasi = (document.getElementById('f-afiliasi')||{}).value?.trim() || '';
  if (!nama || !email || !judul || !isi || !kategori || !ringkasan) { showToast('Mohon lengkapi semua field yang wajib diisi.'); return; }
  const wordCount = isi.split(/\s+/).filter(Boolean).length;
  if (wordCount < 100) { showToast('Isi tulisan minimal 100 kata.'); return; }
  const now = new Date();
  const monthsArr = ['Januari','Februari','Maret','April','Mei','Juni','Juli','Agustus','September','Oktober','November','Desember'];
  const tanggal = `${now.getDate()} ${monthsArr[now.getMonth()]} ${now.getFullYear()}`;
  const newArticle = { nama, email, afiliasi, judul, ringkasan, isi, kategori, tanggal, id: Date.now() };
  publishedArticles.push(newArticle);
  renderHome(); renderCategoryPage(kategori); renderWorks(currentFilter); updateStats();
  const fill = document.getElementById('jfProgressFill');
  const pctEl = document.getElementById('jfProgressPct');
  if (fill) fill.style.width = '100%';
  if (pctEl) pctEl.textContent = '100%';
  for (let i = 1; i <= JF_TOTAL; i++) {
    const p = document.getElementById('jf-panel-' + i);
    if (p) p.classList.remove('active');
    const nav = document.getElementById('jf-step-nav-' + i);
    if (nav) { nav.classList.remove('active'); nav.classList.add('done'); }
    const numEl = document.getElementById('jf-stepnum-' + i);
    if (numEl) numEl.textContent = '✓';
  }
  document.getElementById('jf-panel-success').classList.add('active');
  showToast('✅ Tulisan berhasil diterbitkan!');
  window.scrollTo({ top: 66, behavior: 'smooth' });
}

// ================================================================
// SEARCH
// ================================================================
let searchFocusIdx = -1;
let searchResultsCache = [];

function openSearch() {
  document.getElementById('searchOverlay').classList.add('open');
  document.getElementById('searchQuickNav').style.display = 'block';
  document.getElementById('searchResultsArea').innerHTML = '';
  document.getElementById('searchCount').textContent = '';
  searchFocusIdx = -1;
  setTimeout(() => document.getElementById('searchInput').focus(), 80);
}
function closeSearch() {
  document.getElementById('searchOverlay').classList.remove('open');
  document.getElementById('searchInput').value = '';
  document.getElementById('searchResultsArea').innerHTML = '';
  document.getElementById('searchCount').textContent = '';
  searchFocusIdx = -1;
}
function handleOverlayClick(e) { if (e.target === document.getElementById('searchOverlay')) closeSearch(); }
function highlightMatch(text, query) {
  if (!query) return escHtml(text);
  const escaped = query.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
  const re = new RegExp('(' + escaped + ')', 'gi');
  return escHtml(text).replace(re, '<span class="search-highlight">$1</span>');
}
function doSearch(q) {
  const quickNav = document.getElementById('searchQuickNav');
  const resultsArea = document.getElementById('searchResultsArea');
  const countEl = document.getElementById('searchCount');
  searchFocusIdx = -1;
  if (!q.trim()) { quickNav.style.display = 'block'; resultsArea.innerHTML = ''; countEl.textContent = ''; searchResultsCache = []; return; }
  quickNav.style.display = 'none';
  const ql = q.toLowerCase();
  searchResultsCache = publishedArticles.filter(a => a.judul.toLowerCase().includes(ql) || a.nama.toLowerCase().includes(ql) || (a.ringkasan||'').toLowerCase().includes(ql) || a.kategori.toLowerCase().includes(ql));
  if (searchResultsCache.length === 0) { resultsArea.innerHTML = `<div class="search-section"><div class="search-empty"><div class="search-empty-icon">🔍</div><div class="search-empty-text">Tidak ada hasil untuk "<strong>${escHtml(q)}</strong>"</div></div></div>`; countEl.textContent = ''; return; }
  countEl.textContent = searchResultsCache.length + ' hasil';
  const iconClass = {ekonomi:'icon-ekonomi',politik:'icon-politik',sosial:'icon-sosial',lingkungan:'icon-lingkungan',pendidikan:'icon-pendidikan',opini:'icon-opini'};
  const catTextClass = {ekonomi:'cat-text-ekonomi',politik:'cat-text-politik',sosial:'cat-text-sosial',lingkungan:'cat-text-lingkungan',pendidikan:'cat-text-pendidikan',opini:'cat-text-opini'};
  const rows = searchResultsCache.slice(0,8).map((a,i) => {
    const idx = publishedArticles.indexOf(a);
    const ic = iconClass[a.kategori] || 'icon-opini';
    const cc = catTextClass[a.kategori] || 'cat-text-opini';
    return `<div class="search-result-row" data-idx="${i}" onclick="selectSearchResult(${idx})"><div class="search-result-icon ${ic}">${catEmojis[a.kategori]||'📝'}</div><div class="search-result-body"><div class="search-result-cat ${cc}">${(catLabels[a.kategori]||a.kategori).toUpperCase()}</div><div class="search-result-title">${highlightMatch(a.judul,q)}</div><div class="search-result-meta">${escHtml(a.nama)}${a.afiliasi?' · '+escHtml(a.afiliasi):''} · ${a.tanggal}</div></div><span class="search-result-arrow">→</span></div>`;
  }).join('');
  resultsArea.innerHTML = `<div class="search-section"><div class="search-results-list" id="searchList">${rows}</div></div>`;
}
function selectSearchResult(idx) { closeSearch(); showArticle(publishedArticles[idx]); }
function handleSearchKey(e) {
  const rows = document.querySelectorAll('.search-result-row');
  if (!rows.length) return;
  if (e.key === 'ArrowDown') { e.preventDefault(); searchFocusIdx = Math.min(searchFocusIdx+1,rows.length-1); rows.forEach((r,i)=>r.classList.toggle('focused',i===searchFocusIdx)); rows[searchFocusIdx]?.scrollIntoView({block:'nearest'}); }
  else if (e.key === 'ArrowUp') { e.preventDefault(); searchFocusIdx = Math.max(searchFocusIdx-1,0); rows.forEach((r,i)=>r.classList.toggle('focused',i===searchFocusIdx)); rows[searchFocusIdx]?.scrollIntoView({block:'nearest'}); }
  else if (e.key === 'Enter' && searchFocusIdx >= 0) { rows[searchFocusIdx]?.click(); }
  else if (e.key === 'Escape') { closeSearch(); }
}
document.addEventListener('keydown', e => {
  if ((e.metaKey||e.ctrlKey) && e.key==='k') { e.preventDefault(); openSearch(); }
  if (e.key==='Escape') closeSearch();
});

// ================================================================
// TOAST
// ================================================================
function showToast(msg) {
  const t = document.getElementById('toast');
  document.getElementById('toastMsg').textContent = msg;
  t.classList.add('show');
  setTimeout(() => t.classList.remove('show'), 4500);
}

// ================================================================
// UTILS
// ================================================================
function escHtml(str) { return String(str).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;'); }
function updateWordCount(el) {
  const words = el.value.trim()==='' ? 0 : el.value.trim().split(/\s+/).length;
  const wc = document.getElementById('wordCount');
  const mins = Math.max(1, Math.round(words/200));
  if (wc) wc.textContent = words+' kata · estimasi '+mins+' menit baca';
}
function handleFileSelect(input) {
  if (input.files && input.files[0]) {
    document.getElementById('uploadedFileName').textContent = '✓ '+input.files[0].name;
    const f = input.files[0];
    if (f.name.endsWith('.txt')) { const reader = new FileReader(); reader.onload = e => { document.getElementById('f-isi').value = e.target.result; updateWordCount(document.getElementById('f-isi')); }; reader.readAsText(f); }
  }
}
function handleDrop(event) { event.preventDefault(); document.getElementById('uploadZone').classList.remove('dragging'); const file = event.dataTransfer.files[0]; if (file) document.getElementById('uploadedFileName').textContent = '✓ '+file.name; }

// ================================================================
// DATE BAR
// ================================================================
const days = ['Minggu','Senin','Selasa','Rabu','Kamis','Jumat','Sabtu'];
const months2 = ['Januari','Februari','Maret','April','Mei','Juni','Juli','Agustus','September','Oktober','November','Desember'];
const now2 = new Date();
const dateBarEl = document.getElementById('dateBar');
if (dateBarEl) dateBarEl.textContent = `${days[now2.getDay()]}, ${now2.getDate()} ${months2[now2.getMonth()]} ${now2.getFullYear()}`;

// ================================================================
// JF MULTI-STEP
// ================================================================
let jfCurrentStep = 1;
const JF_TOTAL = 5;

function goStep(n) {
  for (let i=1;i<=JF_TOTAL;i++) {
    const p=document.getElementById('jf-panel-'+i); if(p)p.classList.remove('active');
    const nav=document.getElementById('jf-step-nav-'+i); if(nav){nav.classList.remove('active');if(i<n)nav.classList.add('done');else nav.classList.remove('done');}
  }
  const panel=document.getElementById('jf-panel-'+n); if(panel)panel.classList.add('active');
  const navItem=document.getElementById('jf-step-nav-'+n); if(navItem){navItem.classList.add('active');navItem.classList.remove('done');}
  jfCurrentStep=n;
  for(let i=1;i<=JF_TOTAL;i++){const numEl=document.getElementById('jf-stepnum-'+i);if(!numEl)continue;if(i<n)numEl.textContent='✓';else numEl.textContent=i;}
  const pct=Math.round(((n-1)/JF_TOTAL)*100);
  const fill=document.getElementById('jfProgressFill'); const pctEl=document.getElementById('jfProgressPct');
  if(fill)fill.style.width=pct+'%'; if(pctEl)pctEl.textContent=pct+'%';
  if(n===5)buildSummary();
  window.scrollTo({top:66,behavior:'smooth'});
}

function nextStep(from) {
  if(from===1){const nama=document.getElementById('f-nama').value.trim();const email=document.getElementById('f-email').value.trim();if(!nama){showToast('Mohon isi nama lengkap Anda.');document.getElementById('f-nama').focus();return;}if(!email||!email.includes('@')){showToast('Mohon isi email yang valid.');document.getElementById('f-email').focus();return;}}
  if(from===2&&!document.getElementById('f-kategori').value){showToast('Mohon pilih kategori tulisan.');return;}
  if(from===3){if(!document.getElementById('f-judul').value.trim()){showToast('Mohon isi judul tulisan.');return;}if(!document.getElementById('f-ringkasan').value.trim()){showToast('Mohon isi ringkasan tulisan.');return;}}
  if(from===4){const isi=document.getElementById('f-isi').value.trim();const words=isi===''?0:isi.split(/\s+/).length;if(words<100){showToast('Isi tulisan minimal 100 kata. Saat ini: '+words+' kata.');return;}}
  goStep(from+1);
}

function selectCat(cat,el){document.querySelectorAll('.jf-cat-card').forEach(c=>c.classList.remove('selected'));el.classList.add('selected');document.getElementById('f-kategori').value=cat;}

function buildSummary(){
  const catLabelsLocal={ekonomi:'Ekonomi',politik:'Politik',sosial:'Sosial',lingkungan:'Lingkungan',pendidikan:'Pendidikan',opini:'Opini Umum'};
  const cat=document.getElementById('f-kategori').value;
  const jenis=document.querySelector('input[name="jenisTulisan"]:checked');
  const words=(document.getElementById('f-isi').value.trim()||'').split(/\s+/).filter(Boolean).length;
  const rows=[['✍️ Penulis',document.getElementById('f-nama').value||'—'],['📧 Email',document.getElementById('f-email').value||'—'],['🏛️ Afiliasi',document.getElementById('f-afiliasi').value||'Independen'],['📂 Kategori',catLabelsLocal[cat]||'—'],['📐 Jenis',jenis?jenis.value.charAt(0).toUpperCase()+jenis.value.slice(1):'—'],['📰 Judul',(document.getElementById('f-judul').value||'—').substring(0,60)+(document.getElementById('f-judul').value.length>60?'…':'')],['📊 Panjang',words+' kata · ~'+Math.max(1,Math.round(words/200))+' menit baca']];
  document.getElementById('jf-summary').innerHTML=rows.map(([label,val])=>`<div style="display:flex;gap:12px;align-items:baseline;font-size:0.86rem;"><span style="min-width:110px;color:var(--muted);font-size:0.75rem;font-weight:600;text-transform:uppercase;letter-spacing:0.06em;">${label}</span><span style="color:var(--ink);font-weight:500;">${escHtml(val)}</span></div>`).join('');
}

function jfCount(el,countId,max,unit){
  const countEl=document.getElementById(countId); if(!countEl)return;
  let val=unit==='kata'?(el.value.trim()===''?0:el.value.trim().split(/\s+/).length):el.value.length;
  countEl.textContent=val+' / '+max+' '+unit;
  countEl.className='jf-count'+(val>max*0.85?' warn':'')+(val>=max?' over':'');
}

function resetJFForm(){
  ['f-nama','f-email','f-wa','f-afiliasi','f-bio','f-judul','f-ringkasan','f-keywords','f-isi'].forEach(id=>{const el=document.getElementById(id);if(el)el.value='';});
  document.getElementById('f-kategori').value='';
  document.querySelectorAll('.jf-cat-card').forEach(c=>c.classList.remove('selected'));
  document.querySelectorAll('.jf-radio-option').forEach(o=>o.classList.remove('selected'));
  document.querySelectorAll('input[name="jenisTulisan"]').forEach(r=>r.checked=false);
  document.getElementById('uploadedFileName').textContent='';
  document.getElementById('jf-panel-success').classList.remove('active');
  goStep(1);
}
</script>
</body>
</html>
