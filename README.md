at > /mnt/user-data/outputs/orvexa-foundations.html << 'HTMLEOF'
<!DOCTYPE html>
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

    /* ===== PAGE SYSTEM ===== */
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

    .nav-search-btn {
      background: none; border: none; cursor: pointer;
      color: var(--muted); padding: 8px; border-radius: 5px;
      transition: all 0.18s; font-size: 1rem; line-height: 1;
    }
    .nav-search-btn:hover { color: var(--ink); background: var(--cream); }

    /* Mobile hamburger */
    .nav-hamburger {
      display: none; background: none; border: none; cursor: pointer;
      padding: 8px; color: var(--ink); font-size: 1.2rem;
    }

    /* ===== MOBILE DRAWER ===== */
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
      background: rgba(13,13,13,0.88); backdrop-filter: blur(10px);
      display: none; align-items: flex-start; justify-content: center;
      padding-top: 110px;
    }
    .search-overlay.open { display: flex; }

    .search-box { width: 100%; max-width: 680px; padding: 0 24px; }
    .search-box input {
      width: 100%; font-family: 'Playfair Display', serif;
      font-size: 2rem; font-weight: 400; color: var(--white);
      background: transparent; border: none;
      border-bottom: 2px solid var(--gold);
      padding: 14px 0; outline: none;
    }
    .search-box input::placeholder { color: rgba(255,255,255,0.3); }
    .search-hint { margin-top: 14px; color: rgba(255,255,255,0.4); font-size: 0.82rem; }

    .search-results { margin-top: 28px; display: flex; flex-direction: column; gap: 10px; }
    .search-result-item {
      background: rgba(255,255,255,0.07); border-radius: 8px;
      padding: 14px 18px; cursor: pointer; transition: background 0.18s;
    }
    .search-result-item:hover { background: rgba(255,255,255,0.13); }
    .search-result-item .cat { font-size: 0.68rem; letter-spacing: 0.12em;
      text-transform: uppercase; color: var(--gold); margin-bottom: 5px; }
    .search-result-item h4 { color: var(--white); font-family: 'Playfair Display', serif; font-size: 1rem; }

    .close-search {
      position: absolute; top: 20px; right: 28px;
      background: none; border: none; color: rgba(255,255,255,0.5);
      font-size: 1.8rem; cursor: pointer; transition: color 0.18s; line-height: 1;
    }
    .close-search:hover { color: var(--white); }

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

    .masthead-eyebrow {
      font-size: 0.68rem; letter-spacing: 0.22em; text-transform: uppercase;
      color: var(--gold); margin-bottom: 22px; opacity: 0.9;
    }

    .masthead-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3.5rem, 10vw, 8rem);
      font-weight: 900; line-height: 0.88;
      letter-spacing: -0.04em; margin-bottom: 24px;
    }
    .masthead-title em { color: var(--gold); font-style: italic; }

    .masthead-sub {
      font-size: 1.02rem; color: rgba(248,244,238,0.58);
      max-width: 460px; margin: 0 auto; line-height: 1.75;
    }

    .masthead-actions {
      margin-top: 36px; display: flex; gap: 12px; justify-content: center; flex-wrap: wrap;
    }

    .date-strip {
      background: var(--gold); color: var(--ink);
      text-align: center; padding: 9px;
      font-size: 0.68rem; letter-spacing: 0.14em; text-transform: uppercase; font-weight: 700;
    }

    /* ===== FEATURED GRID ===== */
    .featured-grid {
      display: grid; grid-template-columns: 1.65fr 1fr;
      border-bottom: 1px solid var(--border);
    }

    .featured-main {
      padding: 52px 5%; border-right: 1px solid var(--border);
      cursor: pointer; transition: background 0.2s;
    }
    .featured-main:hover { background: rgba(248,244,238,0.5); }
    .featured-main:hover .art-title { color: var(--gold); }

    .featured-sidebar { display: flex; flex-direction: column; }
    .featured-sidebar-item {
      padding: 30px 5% 30px 4%; border-bottom: 1px solid var(--border);
      cursor: pointer; transition: background 0.2s; flex: 1;
    }
    .featured-sidebar-item:last-child { border-bottom: none; }
    .featured-sidebar-item:hover { background: var(--cream); }
    .featured-sidebar-item:hover .art-title { color: var(--gold); }

    /* ===== TAGS ===== */
    .category-tag {
      display: inline-block;
      font-size: 0.62rem; font-weight: 700; letter-spacing: 0.14em;
      text-transform: uppercase; padding: 4px 10px;
      border-radius: 3px; margin-bottom: 14px;
    }
    .cat-ekonomi { background: #fef3e2; color: #92650a; }
    .cat-politik { background: #fce8e8; color: var(--rust); }
    .cat-sosial { background: #e8f4ec; color: var(--forest); }
    .cat-lingkungan { background: #e4f0e8; color: #2d6a4f; }
    .cat-pendidikan { background: #eaeeff; color: #3a3a8b; }
    .cat-opini { background: #f5e8f5; color: #6a3a6a; }

    /* ===== TYPOGRAPHY ===== */
    .art-title { font-family: 'Playfair Display', serif; line-height: 1.15; transition: color 0.2s; }
    .art-title.xl { font-size: clamp(1.9rem, 3.2vw, 2.9rem); font-weight: 700; margin-bottom: 16px; }
    .art-title.lg { font-size: 1.3rem; font-weight: 700; margin-bottom: 10px; }
    .art-title.md { font-size: 1.05rem; font-weight: 700; margin-bottom: 8px; }

    .art-excerpt { color: var(--muted); font-size: 0.92rem; line-height: 1.72; margin-bottom: 20px; }

    .art-meta {
      display: flex; align-items: center; gap: 10px;
      font-size: 0.74rem; color: var(--muted); flex-wrap: wrap;
    }
    .art-meta .author { font-weight: 600; color: var(--ink); }
    .art-meta .dot { color: var(--border); }

    /* ===== SECTION HEADERS ===== */
    .section-header {
      display: flex; align-items: center; gap: 16px; margin-bottom: 32px;
    }
    .section-title { font-family: 'Playfair Display', serif; font-size: 1.45rem; font-weight: 700; }
    .section-line { flex: 1; height: 1px; background: var(--border); }
    .section-more {
      font-size: 0.7rem; letter-spacing: 0.1em; text-transform: uppercase;
      font-weight: 700; color: var(--gold); text-decoration: none; cursor: pointer;
      white-space: nowrap;
    }
    .section-more:hover { color: var(--rust); }

    /* ===== CATEGORY SECTIONS ===== */
    .cat-section {
      max-width: 1440px; margin: 0 auto;
      padding: 70px 5%; border-bottom: 1px solid var(--border);
    }

    .articles-row { display: grid; grid-template-columns: repeat(3, 1fr); gap: 32px; }

    .article-card { cursor: pointer; }
    .article-card:hover .art-title { color: var(--gold); }

    .card-img-placeholder {
      width: 100%; aspect-ratio: 16/9;
      border-radius: var(--radius); margin-bottom: 16px;
      background: linear-gradient(135deg, var(--cream), var(--border));
      display: flex; align-items: center; justify-content: center;
      font-size: 2.2rem; overflow: hidden;
    }

    /* ===== TWO COLUMN ===== */
    .two-col { display: grid; grid-template-columns: 1fr 360px; gap: 56px; }

    .latest-list { display: flex; flex-direction: column; }
    .latest-item {
      display: flex; gap: 16px; padding: 20px 0;
      border-bottom: 1px solid var(--border); cursor: pointer;
      transition: all 0.18s; border-radius: 4px;
    }
    .latest-item:hover { background: var(--cream); padding-left: 10px; padding-right: 10px; }
    .latest-item:hover .art-title { color: var(--gold); }
    .latest-num {
      font-family: 'Playfair Display', serif; font-size: 1.7rem;
      font-weight: 900; color: var(--border); line-height: 1; min-width: 38px;
    }

    /* ===== SIDEBAR ===== */
    .sidebar-widget { margin-bottom: 36px; }
    .sidebar-widget-title {
      font-size: 0.66rem; letter-spacing: 0.2em; text-transform: uppercase;
      font-weight: 700; color: var(--muted); margin-bottom: 14px;
      padding-bottom: 10px; border-bottom: 2px solid var(--ink);
    }

    .trending-list { list-style: none; }
    .trending-list li {
      display: flex; gap: 12px; align-items: flex-start;
      padding: 11px 0; border-bottom: 1px solid var(--border);
      cursor: pointer; font-size: 0.86rem; font-weight: 500;
      transition: color 0.18s;
    }
    .trending-list li:hover { color: var(--gold); }
    .trending-num {
      font-family: 'Playfair Display', serif; font-size: 1rem;
      font-weight: 900; color: var(--border); min-width: 22px; line-height: 1.4;
    }

    /* ===== PROFILE PAGE ===== */
    .profile-hero {
      background: var(--ink); color: var(--ivory);
      padding: 120px 5% 80px; text-align: center; position: relative; overflow: hidden;
    }
    .profile-hero::before {
      content: ''; position: absolute; inset: 0;
      background: radial-gradient(ellipse 60% 50% at 50% 100%, rgba(184,149,90,0.15) 0%, transparent 70%);
    }

    .profile-avatar {
      width: 130px; height: 130px; border-radius: 50%;
      background: linear-gradient(135deg, var(--gold), var(--rust));
      margin: 0 auto 24px;
      display: flex; align-items: center; justify-content: center;
      font-size: 3rem; font-family: 'Playfair Display', serif;
      font-weight: 900; color: white; border: 3px solid rgba(184,149,90,0.6);
      position: relative;
    }

    .profile-name { font-family: 'Playfair Display', serif; font-size: 2.6rem; font-weight: 900; margin-bottom: 8px; }
    .profile-role { color: var(--gold); font-size: 0.82rem; letter-spacing: 0.16em; text-transform: uppercase; margin-bottom: 20px; }
    .profile-bio { max-width: 620px; margin: 0 auto; color: rgba(248,244,238,0.65); line-height: 1.8; }

    .profile-stats {
      display: flex; justify-content: center; gap: 0;
      border-bottom: 1px solid var(--border); background: var(--cream);
    }
    .stat {
      text-align: center; padding: 36px 48px;
      border-right: 1px solid var(--border);
    }
    .stat:last-child { border-right: none; }
    .stat-num { font-family: 'Playfair Display', serif; font-size: 2.4rem; font-weight: 900; color: var(--ink); line-height: 1; }
    .stat-label { font-size: 0.72rem; color: var(--muted); text-transform: uppercase; letter-spacing: 0.1em; margin-top: 6px; }

    .profile-content { max-width: 880px; margin: 0 auto; padding: 60px 5%; }

    /* ===== SUBMIT PAGE ===== */
    .submit-hero {
      background: var(--ink); color: var(--ivory);
      padding: 110px 5% 60px; text-align: center; position: relative; overflow: hidden;
    }
    .submit-hero::before {
      content: ''; position: absolute; inset: 0;
      background: radial-gradient(ellipse 70% 50% at 50% 110%, rgba(184,149,90,0.15) 0%, transparent 70%);
    }
    .submit-hero h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2.2rem, 5vw, 3.8rem); font-weight: 900; margin-bottom: 14px;
      position: relative;
    }
    .submit-hero p { color: rgba(248,244,238,0.6); font-size: 1rem; max-width: 460px; margin: 0 auto; position: relative; }

    .submit-form-wrap { max-width: 820px; margin: 0 auto; padding: 56px 5%; }

    /* ===== FORM ===== */
    .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
    .form-full { grid-column: 1 / -1; }
    .form-group { display: flex; flex-direction: column; gap: 7px; }

    .form-label {
      font-size: 0.72rem; font-weight: 700; letter-spacing: 0.09em;
      text-transform: uppercase; color: var(--muted);
    }

    .form-input, .form-select, .form-textarea {
      font-family: 'DM Sans', sans-serif; font-size: 0.94rem;
      color: var(--ink); background: var(--white);
      border: 1.5px solid var(--border); border-radius: var(--radius);
      padding: 11px 15px; outline: none;
      transition: border-color 0.2s, box-shadow 0.2s; width: 100%;
    }
    .form-input:focus, .form-select:focus, .form-textarea:focus {
      border-color: var(--gold); box-shadow: 0 0 0 3px rgba(184,149,90,0.13);
    }
    .form-textarea { min-height: 260px; resize: vertical; line-height: 1.72; }

    .char-count {
      font-size: 0.72rem; color: var(--muted); text-align: right; margin-top: 4px;
    }
    .char-count.warn { color: var(--gold); }
    .char-count.error { color: var(--rust); }

    .upload-zone {
      border: 2px dashed var(--border); border-radius: var(--radius);
      padding: 36px; text-align: center; cursor: pointer;
      transition: all 0.2s; background: var(--white);
    }
    .upload-zone:hover, .upload-zone.dragging { border-color: var(--gold); background: #fef9f2; }
    .upload-icon { font-size: 2.2rem; margin-bottom: 10px; }
    .upload-text { font-size: 0.88rem; color: var(--muted); }
    .upload-text strong { color: var(--ink); }

    /* ===== BUTTONS ===== */
    .btn {
      display: inline-flex; align-items: center; gap: 8px;
      padding: 13px 30px; border-radius: var(--radius); border: none;
      font-family: 'DM Sans', sans-serif; font-size: 0.86rem;
      font-weight: 600; letter-spacing: 0.04em; cursor: pointer;
      transition: all 0.2s; text-decoration: none;
    }
    .btn-primary { background: var(--ink); color: var(--ivory); }
    .btn-primary:hover { background: var(--gold); transform: translateY(-1px); box-shadow: var(--shadow-md); }
    .btn-gold { background: var(--gold); color: var(--white); }
    .btn-gold:hover { background: var(--rust); transform: translateY(-1px); }
    .btn-outline { background: transparent; color: var(--ink); border: 1.5px solid var(--border); }
    .btn-outline:hover { border-color: var(--ink); }
    .btn-sm { padding: 8px 18px; font-size: 0.78rem; }

    /* ===== KARYA TULISAN ===== */
    .works-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 2px; background: var(--border); }
    .work-item {
      background: var(--ivory); padding: 36px 40px;
      cursor: pointer; transition: background 0.2s;
    }
    .work-item:hover { background: var(--cream); }
    .work-item:hover .art-title { color: var(--gold); }

    /* ===== EMPTY STATE ===== */
    .empty-state {
      text-align: center; padding: 80px 24px; color: var(--muted);
    }
    .empty-state .empty-icon { font-size: 3.5rem; margin-bottom: 20px; opacity: 0.5; }
    .empty-state h3 { font-family: 'Playfair Display', serif; font-size: 1.6rem; color: var(--ink); margin-bottom: 12px; }
    .empty-state p { font-size: 0.95rem; line-height: 1.7; max-width: 400px; margin: 0 auto 28px; }

    /* ===== ARTICLE VIEW ===== */
    .article-view-hero {
      background: var(--ink); color: var(--ivory);
      padding: 110px 5% 60px; position: relative; overflow: hidden;
    }
    .article-view-hero::before {
      content: ''; position: absolute; inset: 0;
      background: radial-gradient(ellipse 70% 60% at 20% 80%, rgba(184,149,90,0.12) 0%, transparent 60%);
    }
    .article-view-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2.2rem, 5vw, 3.6rem); font-weight: 900;
      line-height: 1.1; max-width: 780px; margin-bottom: 24px; position: relative;
    }

    .article-body {
      max-width: 700px; margin: 0 auto; padding: 60px 5%;
      font-size: 1.04rem; line-height: 1.88; color: #1a1a1a;
    }
    .article-body p { margin-bottom: 24px; }
    .article-body h2 {
      font-family: 'Playfair Display', serif; font-size: 1.55rem;
      margin: 44px 0 16px; color: var(--ink);
    }
    .article-body blockquote {
      border-left: 3px solid var(--gold); padding-left: 24px;
      color: var(--muted); font-style: italic; margin: 36px 0;
      font-family: 'DM Serif Display', serif; font-size: 1.18rem; line-height: 1.65;
    }

    /* ===== PAGE HEADER ===== */
    .page-header {
      background: var(--ink); color: var(--ivory);
      padding: 100px 5% 52px; text-align: center; position: relative; overflow: hidden;
    }
    .page-header::before {
      content: ''; position: absolute; inset: 0;
      background: radial-gradient(ellipse 80% 60% at 50% 120%, rgba(184,149,90,0.14) 0%, transparent 65%);
    }
    .page-header h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2.8rem, 7vw, 4.5rem); font-weight: 900; position: relative;
    }
    .page-header p { color: rgba(248,244,238,0.6); margin-top: 10px; font-size: 0.98rem; position: relative; }

    .main-wrap { max-width: 1440px; margin: 0 auto; padding: 60px 5%; }

    /* ===== GUIDELINES BOX ===== */
    .guidelines-box {
      background: var(--cream); border-left: 3px solid var(--gold);
      padding: 24px 28px; border-radius: var(--radius); margin-bottom: 30px;
    }
    .guidelines-box h3 { font-family: 'Playfair Display', serif; margin-bottom: 12px; font-size: 1.1rem; }
    .guidelines-box ul { padding-left: 18px; }
    .guidelines-box ul li { font-size: 0.88rem; color: var(--muted); margin-bottom: 7px; line-height: 1.65; }

    /* ===== TOAST ===== */
    .toast {
      position: fixed; bottom: 28px; right: 28px; z-index: 9999;
      background: var(--forest); color: var(--white);
      padding: 14px 22px; border-radius: var(--radius);
      display: none; align-items: center; gap: 10px;
      font-size: 0.88rem; font-weight: 500;
      box-shadow: var(--shadow-lg); max-width: 360px;
    }
    .toast.show { display: flex; animation: slideUp 0.28s ease; }
    @keyframes slideUp {
      from { transform: translateY(16px); opacity: 0; }
      to { transform: translateY(0); opacity: 1; }
    }

    /* ===== CTA BANNER ===== */
    .cta-banner {
      background: var(--gold); padding: 64px 5%; text-align: center;
      position: relative; overflow: hidden;
    }
    .cta-banner::before {
      content: ''; position: absolute; inset: 0;
      background: repeating-linear-gradient(45deg, transparent, transparent 40px, rgba(255,255,255,0.04) 40px, rgba(255,255,255,0.04) 80px);
    }

    /* ===== CHIPS ===== */
    .chip {
      display: inline-block; font-size: 0.7rem; font-weight: 600;
      letter-spacing: 0.08em; text-transform: uppercase;
      padding: 5px 14px; border-radius: 20px;
      background: var(--cream); color: var(--muted); cursor: pointer;
      transition: all 0.18s;
    }
    .chip:hover { background: var(--ink); color: var(--ivory); }

    /* ===== FOOTER ===== */
    footer {
      background: var(--ink); color: var(--ivory);
      padding: 64px 5% 32px;
    }
    .footer-grid {
      display: grid; grid-template-columns: 2fr 1fr 1fr 1fr;
      gap: 48px; max-width: 1440px; margin: 0 auto;
      padding-bottom: 48px; border-bottom: 1px solid rgba(255,255,255,0.09);
    }
    .footer-brand .logo { font-size: 1.3rem; display: block; margin-bottom: 14px; color: var(--ivory); }
    .footer-brand p { font-size: 0.86rem; color: rgba(248,244,238,0.45); line-height: 1.75; }

    .footer-col h4 {
      font-size: 0.66rem; letter-spacing: 0.17em; text-transform: uppercase;
      font-weight: 700; color: var(--gold); margin-bottom: 18px;
    }
    .footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 9px; }
    .footer-col ul li a {
      font-size: 0.86rem; color: rgba(248,244,238,0.55);
      text-decoration: none; cursor: pointer; transition: color 0.18s;
    }
    .footer-col ul li a:hover { color: var(--ivory); }

    .footer-bottom {
      max-width: 1440px; margin: 0 auto;
      padding-top: 22px; display: flex; justify-content: space-between;
      font-size: 0.76rem; color: rgba(248,244,238,0.3); flex-wrap: wrap; gap: 8px;
    }

    /* ===== NOTIFICATION DOT ===== */
    .new-badge {
      display: inline-block; background: var(--rust); color: white;
      font-size: 0.6rem; font-weight: 700; padding: 2px 7px;
      border-radius: 10px; margin-left: 6px; vertical-align: middle;
      text-transform: uppercase; letter-spacing: 0.06em;
    }

    /* ===== MISC ===== */
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
      .articles-row { grid-template-columns: 1fr; }
      .footer-grid { grid-template-columns: 1fr 1fr; }
      .profile-stats { flex-direction: column; gap: 0; }
      .stat { border-right: none; border-bottom: 1px solid var(--border); }
      .form-grid { grid-template-columns: 1fr; }
      .works-grid { grid-template-columns: 1fr; }
      .work-item { padding: 28px 24px; }
    }

    @media (max-width: 480px) {
      .footer-grid { grid-template-columns: 1fr; }
      .masthead-title { font-size: 3.2rem; }
      .featured-main { padding: 36px 5%; }
      .cat-section { padding: 48px 5%; }
    }
  </style>
</head>
<body>

<!-- SEARCH OVERLAY -->
<div class="search-overlay" id="searchOverlay">
  <button class="close-search" onclick="closeSearch()">×</button>
  <div class="search-box">
    <input type="text" id="searchInput" placeholder="Cari artikel, topik, penulis…" oninput="doSearch(this.value)" onkeydown="if(event.key==='Escape')closeSearch()"/>
    <p class="search-hint">Tekan ESC untuk menutup</p>
    <div class="search-results" id="searchResults"></div>
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
      <li><a onclick="showPage('kirim')" id="nav-kirim" class="nav-cta">Kirim Tulisan</a></li>
    </ul>
    <div class="nav-right">
      <button class="nav-search-btn" onclick="openSearch()" title="Cari">🔍</button>
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

  <!-- Featured / Empty Check -->
  <div id="homeFeatured"></div>

  <!-- Tulisan Terbaru dari Pengguna -->
  <div class="cat-section" id="homeUserArticles" style="display:none;">
    <div class="section-header">
      <h2 class="section-title">Tulisan Terbaru</h2>
      <div class="section-line"></div>
      <a class="section-more" onclick="showPage('karya')">Lihat Semua →</a>
    </div>
    <div class="articles-row" id="homeUserGrid"></div>
  </div>

  <!-- CTA Banner -->
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
  <div class="page-header">
    <p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;position:relative;">Rubrik</p>
    <h1>Ekonomi</h1>
    <p>Analisis mendalam tentang dinamika ekonomi Indonesia dan global</p>
  </div>
  <div class="main-wrap"><div class="articles-row" id="grid-ekonomi"><div class="empty-state"><div class="empty-icon">📊</div><h3>Belum ada tulisan</h3><p>Jadilah yang pertama mengirim tulisan di kategori Ekonomi.</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan →</button></div></div></div>
</div>

<div class="page" id="page-politik">
  <div class="page-header">
    <p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;position:relative;">Rubrik</p>
    <h1>Politik</h1>
    <p>Kajian kritis tentang demokrasi, kebijakan publik, dan tata kelola negara</p>
  </div>
  <div class="main-wrap"><div class="articles-row" id="grid-politik"><div class="empty-state"><div class="empty-icon">🗳️</div><h3>Belum ada tulisan</h3><p>Jadilah yang pertama mengirim tulisan di kategori Politik.</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan →</button></div></div></div>
</div>

<div class="page" id="page-sosial">
  <div class="page-header">
    <p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;position:relative;">Rubrik</p>
    <h1>Sosial</h1>
    <p>Mengurai dinamika masyarakat dan transformasi budaya Indonesia</p>
  </div>
  <div class="main-wrap"><div class="articles-row" id="grid-sosial"><div class="empty-state"><div class="empty-icon">👥</div><h3>Belum ada tulisan</h3><p>Jadilah yang pertama mengirim tulisan di kategori Sosial.</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan →</button></div></div></div>
</div>

<div class="page" id="page-lingkungan">
  <div class="page-header">
    <p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;position:relative;">Rubrik</p>
    <h1>Lingkungan</h1>
    <p>Isu iklim, keberlanjutan, dan keadilan lingkungan hidup</p>
  </div>
  <div class="main-wrap"><div class="articles-row" id="grid-lingkungan"><div class="empty-state"><div class="empty-icon">🌿</div><h3>Belum ada tulisan</h3><p>Jadilah yang pertama mengirim tulisan di kategori Lingkungan.</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan →</button></div></div></div>
</div>

<div class="page" id="page-pendidikan">
  <div class="page-header">
    <p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;position:relative;">Rubrik</p>
    <h1>Pendidikan</h1>
    <p>Refleksi dan gagasan untuk memajukan pendidikan Indonesia</p>
  </div>
  <div class="main-wrap"><div class="articles-row" id="grid-pendidikan"><div class="empty-state"><div class="empty-icon">📚</div><h3>Belum ada tulisan</h3><p>Jadilah yang pertama mengirim tulisan di kategori Pendidikan.</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan →</button></div></div></div>
</div>

<!-- ==================== KARYA TULISAN ==================== -->
<div class="page" id="page-karya">
  <div class="page-header">
    <p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:10px;position:relative;">Arsip</p>
    <h1>Karya Tulisan</h1>
    <p>Koleksi seluruh tulisan yang telah dikirimkan</p>
  </div>

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
      <div class="empty-state">
        <div class="empty-icon">✍️</div>
        <h3>Belum Ada Tulisan</h3>
        <p>Platform ini siap menampung karya Anda. Kirimkan tulisan pertama dan langsung tampil di sini!</p>
        <button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan Sekarang →</button>
      </div>
    </div>
  </div>
</div>

<!-- ==================== PROFIL ==================== -->
<div class="page" id="page-profil">
  <div class="profile-hero">
    <div class="profile-avatar">OF</div>
    <h1 class="profile-name">Orvexa Foundations</h1>
    <p class="profile-role">Platform Publikasi Terbuka</p>
    <p class="profile-bio">Orvexa Foundations adalah platform editorial independen yang berkomitmen menyajikan pemikiran kritis, analisis mendalam, dan gagasan segar tentang Indonesia. Kami percaya perubahan bermula dari ide yang ditulis dengan kejujuran dan keberanian intelektual.</p>
  </div>

  <div class="profile-stats">
    <div class="stat"><div class="stat-num" id="statArticles">0</div><div class="stat-label">Tulisan Terbit</div></div>
    <div class="stat"><div class="stat-num" id="statAuthors">0</div><div class="stat-label">Penulis Berkontribusi</div></div>
    <div class="stat"><div class="stat-num">∞</div><div class="stat-label">Topik Terbuka</div></div>
    <div class="stat"><div class="stat-num">0</div><div class="stat-label">Hari Review</div></div>
  </div>

  <div class="profile-content">
    <div class="guidelines-box">
      <h3>Tentang Orvexa Foundations</h3>
      <p style="font-size:0.92rem;color:var(--muted);line-height:1.75;">Platform publikasi terbuka di mana setiap tulisan yang dikirim langsung terbit tanpa proses review atau moderasi. Kami percaya pada kebebasan ekspresi dan transparansi intelektual.</p>
    </div>

    <h2 style="font-family:'Playfair Display',serif;font-size:1.8rem;margin-bottom:24px;">Visi & Misi</h2>
    <p style="color:var(--muted);line-height:1.8;margin-bottom:20px;"><strong style="color:var(--ink);">Visi:</strong> Menjadi platform referensi pemikiran terdepan di Indonesia yang mendorong kemajuan melalui gagasan dan analisis berbasis bukti.</p>
    <p style="color:var(--muted);line-height:1.8;margin-bottom:40px;"><strong style="color:var(--ink);">Misi:</strong> Menyediakan ruang publikasi terbuka bagi siapa saja — akademisi, praktisi, dan pemikir independen — untuk berbagi gagasan yang berkontribusi pada wacana publik Indonesia tanpa hambatan birokrasi editorial.</p>

    <div style="text-align:center;padding:40px;background:var(--cream);border-radius:var(--radius);">
      <h3 style="font-family:'Playfair Display',serif;font-size:1.5rem;margin-bottom:12px;">Siap Berkontribusi?</h3>
      <p style="color:var(--muted);margin-bottom:24px;font-size:0.95rem;">Tulisan Anda akan langsung terbit begitu dikirim.</p>
      <button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan →</button>
    </div>
  </div>
</div>

<!-- ==================== KIRIM TULISAN ==================== -->
<div class="page" id="page-kirim">
  <div class="submit-hero">
    <p style="font-size:0.68rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:12px;position:relative;">Kontribusi</p>
    <h1>Kirim Tulisan</h1>
    <p>Tulisan Anda langsung terbit begitu dikirim — tanpa proses review atau moderasi</p>
  </div>

  <div class="submit-form-wrap">
    <div class="guidelines-box">
      <h3>📢 Auto-Publish Aktif</h3>
      <ul>
        <li>Tulisan Anda <strong>langsung terbit</strong> setelah form dikirim — tidak ada proses review</li>
        <li>Tulisan otomatis muncul di <strong>Beranda, halaman Kategori, dan Karya Tulisan</strong></li>
        <li>Pastikan judul, nama penulis, dan isi tulisan sudah benar sebelum mengirim</li>
        <li>Gunakan ringkasan yang menarik agar pembaca tertarik membaca lebih lanjut</li>
      </ul>
    </div>

    <div class="form-grid">
      <div class="form-group">
        <label class="form-label">Nama Lengkap *</label>
        <input class="form-input" type="text" id="f-nama" placeholder="Nama Anda"/>
      </div>
      <div class="form-group">
        <label class="form-label">Email *</label>
        <input class="form-input" type="email" id="f-email" placeholder="email@anda.com"/>
      </div>
      <div class="form-group">
        <label class="form-label">Afiliasi / Institusi</label>
        <input class="form-input" type="text" id="f-afiliasi" placeholder="Universitas / Lembaga / Independen"/>
      </div>
      <div class="form-group">
        <label class="form-label">Kategori Rubrik *</label>
        <select class="form-select" id="f-kategori">
          <option value="">-- Pilih Kategori --</option>
          <option value="ekonomi">Ekonomi</option>
          <option value="politik">Politik</option>
          <option value="sosial">Sosial</option>
          <option value="lingkungan">Lingkungan</option>
          <option value="pendidikan">Pendidikan</option>
          <option value="opini">Opini Umum</option>
        </select>
      </div>
      <div class="form-group form-full">
        <label class="form-label">Judul Tulisan *</label>
        <input class="form-input" type="text" id="f-judul" placeholder="Judul yang ringkas dan deskriptif" maxlength="120"/>
        <div class="char-count" id="judulCount">0 / 120 karakter</div>
      </div>
      <div class="form-group form-full">
        <label class="form-label">Ringkasan / Abstrak *</label>
        <input class="form-input" type="text" id="f-ringkasan" placeholder="1–2 kalimat yang menggambarkan isi tulisan" maxlength="200"/>
        <div class="char-count" id="ringkasanCount">0 / 200 karakter</div>
      </div>
      <div class="form-group form-full">
        <label class="form-label">Isi Tulisan *</label>
        <textarea class="form-textarea" id="f-isi" placeholder="Tulis atau tempel isi artikel Anda di sini…" oninput="updateWordCount(this)"></textarea>
        <div class="char-count" id="wordCount">0 kata</div>
      </div>
      <div class="form-group form-full">
        <label class="form-label">Upload Dokumen (Opsional)</label>
        <div class="upload-zone" id="uploadZone" onclick="document.getElementById('fileInput').click()"
          ondragover="event.preventDefault();this.classList.add('dragging')"
          ondragleave="this.classList.remove('dragging')"
          ondrop="handleDrop(event)">
          <div class="upload-icon">📎</div>
          <p class="upload-text"><strong>Klik untuk upload</strong> atau seret file ke sini</p>
          <p class="upload-text" style="margin-top:6px;font-size:0.8rem;">Format: .doc, .docx, .pdf, .txt — Maks. 10 MB</p>
          <p id="uploadedFileName" style="margin-top:10px;font-size:0.84rem;color:var(--gold);font-weight:600;"></p>
        </div>
        <input type="file" id="fileInput" class="input-file-hidden" accept=".doc,.docx,.pdf,.txt" onchange="handleFileSelect(this)"/>
      </div>
    </div>

    <div style="margin-top:28px;display:flex;gap:14px;align-items:center;flex-wrap:wrap;">
      <button class="btn btn-gold" style="font-size:0.95rem;padding:15px 40px;" onclick="submitForm()">
        ⚡ Kirim & Terbitkan Sekarang
      </button>
      <button class="btn btn-outline" onclick="clearForm()">Bersihkan Form</button>
    </div>
    <p style="margin-top:14px;font-size:0.8rem;color:var(--muted);">Tulisan akan langsung muncul di website setelah dikirim.</p>
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
  <div class="article-body" id="articleBodyContent">
    <!-- filled dynamically -->
  </div>
</div>

<!-- ==================== FOOTER ==================== -->
<footer>
  <div class="footer-grid">
    <div class="footer-brand">
      <a class="logo" onclick="showPage('home')">Orvexa <span>Foundations</span></a>
      <p>Platform publikasi terbuka untuk pemikiran, analisis, dan gagasan. Setiap tulisan yang dikirim langsung terbit dan tampil di seluruh bagian website.</p>
    </div>
    <div class="footer-col">
      <h4>Rubrik</h4>
      <ul>
        <li><a onclick="showPage('ekonomi')">Ekonomi</a></li>
        <li><a onclick="showPage('politik')">Politik</a></li>
        <li><a onclick="showPage('sosial')">Sosial</a></li>
        <li><a onclick="showPage('lingkungan')">Lingkungan</a></li>
        <li><a onclick="showPage('pendidikan')">Pendidikan</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Media</h4>
      <ul>
        <li><a onclick="showPage('karya')">Karya Tulisan</a></li>
        <li><a onclick="showPage('kirim')">Kirim Tulisan</a></li>
        <li><a onclick="showPage('profil')">Profil</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Lainnya</h4>
      <ul>
        <li><a>Pedoman Penulisan</a></li>
        <li><a>Kebijakan Privasi</a></li>
        <li><a>Syarat Penggunaan</a></li>
        <li><a>Kontak</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2025 Orvexa Foundations. Hak cipta dilindungi undang-undang.</span>
    <span>redaksi@orvexafoundations.id</span>
  </div>
</footer>

<script>
// ================================================================
// DATA STORE — semua artikel tersimpan di sini (mulai kosong)
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

  // Refresh grids when navigating
  if (pageId === 'home') renderHome();
  if (pageId === 'karya') renderWorks('semua');
  if (['ekonomi','politik','sosial','lingkungan','pendidikan'].includes(pageId)) renderCategoryPage(pageId);
}

// ================================================================
// MOBILE DRAWER
// ================================================================
function toggleDrawer() {
  const d = document.getElementById('mobileDrawer');
  d.classList.toggle('open');
}
function closeDrawer() {
  document.getElementById('mobileDrawer').classList.remove('open');
}

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

  // Build body
  const body = document.getElementById('articleBodyContent');
  const ringkasan = article.ringkasan || '';
  const paragraphs = article.isi.split(/\n\n+/).filter(p => p.trim());
  let html = '';
  if (ringkasan) html += `<blockquote>${ringkasan}</blockquote>`;
  paragraphs.forEach(p => { html += `<p>${p.trim()}</p>`; });
  html += `
    <div style="border-top:1px solid var(--border);padding-top:32px;margin-top:44px;">
      <button class="btn btn-outline" onclick="history.back();window.scrollTo(0,0);" style="margin-bottom:24px;">← Kembali</button>
      <div style="background:var(--cream);padding:24px;border-radius:var(--radius);display:flex;gap:16px;align-items:center;">
        <div style="width:48px;height:48px;border-radius:50%;background:linear-gradient(135deg,var(--gold),var(--rust));display:flex;align-items:center;justify-content:center;color:white;font-weight:700;font-size:1rem;flex-shrink:0;">${article.nama.split(' ').slice(0,2).map(n=>n[0]).join('')}</div>
        <div>
          <p style="font-size:0.72rem;color:var(--muted);margin-bottom:3px;letter-spacing:0.06em;text-transform:uppercase;">Tentang Penulis</p>
          <p style="font-weight:600;">${article.nama}</p>
          ${article.afiliasi ? `<p style="font-size:0.83rem;color:var(--muted);">${article.afiliasi}</p>` : ''}
        </div>
      </div>
    </div>`;
  body.innerHTML = html;

  showPage('article');
}

// ================================================================
// RENDER FUNCTIONS
// ================================================================
const catLabels = {ekonomi:'Ekonomi',politik:'Politik',sosial:'Sosial',lingkungan:'Lingkungan',pendidikan:'Pendidikan',opini:'Opini Umum'};
const catClasses = {ekonomi:'cat-ekonomi',politik:'cat-politik',sosial:'cat-sosial',lingkungan:'cat-lingkungan',pendidikan:'cat-pendidikan',opini:'cat-opini'};
const catEmojis = {ekonomi:'📊',politik:'🗳️',sosial:'👥',lingkungan:'🌿',pendidikan:'📚',opini:'✍️'};

function makeCardHTML(article, idx) {
  return `
    <div class="article-card" onclick="showArticle(publishedArticles[${idx}])">
      <div class="card-img-placeholder">${catEmojis[article.kategori] || '📝'}</div>
      <span class="category-tag ${catClasses[article.kategori] || 'cat-opini'}">${catLabels[article.kategori] || article.kategori}</span>
      <h3 class="art-title md mt-8">${escHtml(article.judul)}</h3>
      ${article.ringkasan ? `<p class="art-excerpt mt-8" style="font-size:0.85rem;">${escHtml(article.ringkasan.substring(0,120))}${article.ringkasan.length>120?'…':''}</p>` : ''}
      <div class="art-meta mt-16">
        <span class="author">${escHtml(article.nama)}</span>
        <span class="dot">·</span>
        <span>${article.tanggal}</span>
      </div>
    </div>`;
}

function makeWorkItemHTML(article, idx) {
  return `
    <div class="work-item" data-cat="${article.kategori}" onclick="showArticle(publishedArticles[${idx}])">
      <span class="category-tag ${catClasses[article.kategori] || 'cat-opini'}">${catLabels[article.kategori] || article.kategori}</span>
      <h3 class="art-title lg mt-8">${escHtml(article.judul)}</h3>
      ${article.ringkasan ? `<p class="art-excerpt mt-8" style="font-size:0.88rem;">${escHtml(article.ringkasan)}</p>` : ''}
      <div class="art-meta mt-16">
        <span class="author">${escHtml(article.nama)}</span>
        <span class="dot">·</span>
        <span>${article.tanggal}</span>
        ${article.afiliasi ? `<span class="dot">·</span><span>${escHtml(article.afiliasi)}</span>` : ''}
      </div>
    </div>`;
}

function renderHome() {
  const featuredEl = document.getElementById('homeFeatured');
  const userSectionEl = document.getElementById('homeUserArticles');
  const userGridEl = document.getElementById('homeUserGrid');

  if (publishedArticles.length === 0) {
    featuredEl.innerHTML = `
      <div style="max-width:1440px;margin:0 auto;padding:80px 5%;text-align:center;">
        <div class="empty-state">
          <div class="empty-icon">🌟</div>
          <h3>Platform Siap Digunakan</h3>
          <p>Belum ada tulisan yang diterbitkan. Kirim tulisan pertama Anda dan langsung tampil di sini!</p>
          <button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan Pertama →</button>
        </div>
      </div>`;
    userSectionEl.style.display = 'none';
    return;
  }

  // Featured: tampilkan 3 artikel terbaru dalam layout featured
  const recent = publishedArticles.slice().reverse();
  const main = recent[0];
  const mainIdx = publishedArticles.indexOf(main);

  let sidebarHTML = '';
  for (let i = 1; i < Math.min(4, recent.length); i++) {
    const a = recent[i];
    const idx = publishedArticles.indexOf(a);
    sidebarHTML += `
      <div class="featured-sidebar-item" onclick="showArticle(publishedArticles[${idx}])">
        <span class="category-tag ${catClasses[a.kategori]||'cat-opini'}">${catLabels[a.kategori]||a.kategori}</span>
        <h3 class="art-title lg">${escHtml(a.judul)}</h3>
        ${a.ringkasan ? `<p class="art-excerpt" style="font-size:0.85rem;">${escHtml(a.ringkasan.substring(0,100))}…</p>` : ''}
        <div class="art-meta mt-16"><span class="author">${escHtml(a.nama)}</span><span class="dot">·</span><span>${a.tanggal}</span></div>
      </div>`;
  }

  featuredEl.innerHTML = `
    <div class="featured-grid">
      <div class="featured-main" onclick="showArticle(publishedArticles[${mainIdx}])">
        <span class="category-tag ${catClasses[main.kategori]||'cat-opini'} ">${catLabels[main.kategori]||main.kategori}</span>
        <h2 class="art-title xl">${escHtml(main.judul)}</h2>
        ${main.ringkasan ? `<p class="art-excerpt">${escHtml(main.ringkasan)}</p>` : ''}
        <div class="art-meta"><span class="author">${escHtml(main.nama)}</span><span class="dot">·</span><span>${main.tanggal}</span></div>
      </div>
      <div class="featured-sidebar">${sidebarHTML || '<div class="featured-sidebar-item" style="display:flex;align-items:center;justify-content:center;flex:1;color:var(--muted);font-size:0.9rem;">Kirim lebih banyak tulisan untuk ditampilkan</div>'}</div>
    </div>`;

  // More articles section
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
  // Update filter buttons
  ['semua','ekonomi','politik','sosial','lingkungan','pendidikan','opini'].forEach(c => {
    const btn = document.getElementById('filter-' + c);
    if (!btn) return;
    btn.className = c === cat ? 'btn btn-primary btn-sm' : 'btn btn-outline btn-sm';
  });

  const container = document.getElementById('worksContainer');
  const filtered = cat === 'semua' ? publishedArticles : publishedArticles.filter(a => a.kategori === cat);

  if (filtered.length === 0) {
    const catName = cat === 'semua' ? '' : ' di kategori ' + (catLabels[cat]||cat);
    container.innerHTML = `<div class="empty-state"><div class="empty-icon">✍️</div><h3>Belum Ada Tulisan${cat!=='semua'?' di Kategori Ini':''}</h3><p>Platform ini siap menampung karya Anda${catName}. Kirimkan tulisan dan langsung tampil di sini!</p><button class="btn btn-primary" onclick="showPage('kirim')">Kirim Tulisan Sekarang →</button></div>`;
  } else {
    const reversed = filtered.slice().reverse();
    container.innerHTML = `<div class="works-grid">${reversed.map(a => makeWorkItemHTML(a, publishedArticles.indexOf(a))).join('')}</div>`;
  }
}

function filterWorks(cat) { renderWorks(cat); }

// ================================================================
// STATISTICS UPDATE
// ================================================================
function updateStats() {
  document.getElementById('statArticles').textContent = publishedArticles.length;
  const authors = new Set(publishedArticles.map(a => a.nama.toLowerCase().trim()));
  document.getElementById('statAuthors').textContent = authors.size;
}

// ================================================================
// FORM SUBMISSION — AUTO PUBLISH
// ================================================================
function submitForm() {
  const nama = document.getElementById('f-nama').value.trim();
  const email = document.getElementById('f-email').value.trim();
  const judul = document.getElementById('f-judul').value.trim();
  const isi = document.getElementById('f-isi').value.trim();
  const kategori = document.getElementById('f-kategori').value;
  const ringkasan = document.getElementById('f-ringkasan').value.trim();
  const afiliasi = document.getElementById('f-afiliasi').value.trim();

  if (!nama) { showToast('Mohon isi nama lengkap Anda.'); document.getElementById('f-nama').focus(); return; }
  if (!email || !email.includes('@')) { showToast('Mohon isi email yang valid.'); document.getElementById('f-email').focus(); return; }
  if (!judul) { showToast('Mohon isi judul tulisan.'); document.getElementById('f-judul').focus(); return; }
  if (!isi || isi.split(/\s+/).length < 50) { showToast('Isi tulisan minimal 50 kata.'); document.getElementById('f-isi').focus(); return; }
  if (!kategori) { showToast('Mohon pilih kategori rubrik.'); document.getElementById('f-kategori').focus(); return; }
  if (!ringkasan) { showToast('Mohon isi ringkasan tulisan.'); document.getElementById('f-ringkasan').focus(); return; }

  // Auto publish — langsung masuk ke daftar
  const now = new Date();
  const months = ['Januari','Februari','Maret','April','Mei','Juni','Juli','Agustus','September','Oktober','November','Desember'];
  const tanggal = `${now.getDate()} ${months[now.getMonth()]} ${now.getFullYear()}`;

  const newArticle = { nama, email, afiliasi, judul, ringkasan, isi, kategori, tanggal, id: Date.now() };
  publishedArticles.push(newArticle);

  // Update all relevant sections
  renderHome();
  renderCategoryPage(kategori);
  renderWorks(currentFilter);
  updateStats();

  showToast('✅ Tulisan "' + judul.substring(0,40) + (judul.length>40?'…':'') + '" berhasil diterbitkan!');
  clearForm();

  // Optionally navigate to the article
  setTimeout(() => showArticle(newArticle), 1800);
}

function clearForm() {
  ['f-nama','f-email','f-afiliasi','f-judul','f-ringkasan','f-isi'].forEach(id => {
    document.getElementById(id).value = '';
  });
  document.getElementById('f-kategori').value = '';
  document.getElementById('uploadedFileName').textContent = '';
  document.getElementById('judulCount').textContent = '0 / 120 karakter';
  document.getElementById('ringkasanCount').textContent = '0 / 200 karakter';
  document.getElementById('wordCount').textContent = '0 kata';
}

// ================================================================
// CHAR / WORD COUNTERS
// ================================================================
document.getElementById('f-judul').addEventListener('input', function() {
  const el = document.getElementById('judulCount');
  el.textContent = this.value.length + ' / 120 karakter';
  el.className = 'char-count' + (this.value.length > 100 ? ' warn' : '') + (this.value.length >= 120 ? ' error' : '');
});

document.getElementById('f-ringkasan').addEventListener('input', function() {
  const el = document.getElementById('ringkasanCount');
  el.textContent = this.value.length + ' / 200 karakter';
  el.className = 'char-count' + (this.value.length > 170 ? ' warn' : '') + (this.value.length >= 200 ? ' error' : '');
});

function updateWordCount(el) {
  const words = el.value.trim() === '' ? 0 : el.value.trim().split(/\s+/).length;
  const wc = document.getElementById('wordCount');
  wc.textContent = words + ' kata';
  wc.className = 'char-count' + (words < 50 && words > 0 ? ' warn' : '') + (words >= 50 ? '' : '');
}

// ================================================================
// FILE UPLOAD
// ================================================================
function handleFileSelect(input) {
  if (input.files && input.files[0]) {
    document.getElementById('uploadedFileName').textContent = '✓ ' + input.files[0].name;
    // If text file, try to read and populate the textarea
    const f = input.files[0];
    if (f.name.endsWith('.txt')) {
      const reader = new FileReader();
      reader.onload = e => {
        document.getElementById('f-isi').value = e.target.result;
        updateWordCount(document.getElementById('f-isi'));
      };
      reader.readAsText(f);
    }
  }
}

function handleDrop(event) {
  event.preventDefault();
  document.getElementById('uploadZone').classList.remove('dragging');
  const file = event.dataTransfer.files[0];
  if (file) document.getElementById('uploadedFileName').textContent = '✓ ' + file.name;
}

// ================================================================
// SEARCH
// ================================================================
function openSearch() {
  document.getElementById('searchOverlay').classList.add('open');
  setTimeout(() => document.getElementById('searchInput').focus(), 80);
}
function closeSearch() {
  document.getElementById('searchOverlay').classList.remove('open');
  document.getElementById('searchInput').value = '';
  document.getElementById('searchResults').innerHTML = '';
}
document.addEventListener('keydown', e => { if(e.key === 'Escape') closeSearch(); });

function doSearch(q) {
  const container = document.getElementById('searchResults');
  if (!q.trim()) { container.innerHTML = ''; return; }
  const results = publishedArticles.filter(a =>
    a.judul.toLowerCase().includes(q.toLowerCase()) ||
    a.nama.toLowerCase().includes(q.toLowerCase()) ||
    (a.ringkasan||'').toLowerCase().includes(q.toLowerCase()) ||
    a.kategori.toLowerCase().includes(q.toLowerCase())
  );
  if (results.length === 0) {
    container.innerHTML = `<p style="color:rgba(255,255,255,0.45);font-size:0.88rem;">Tidak ada hasil untuk "<em>${escHtml(q)}</em>"</p>`;
    return;
  }
  container.innerHTML = results.slice(0, 6).map(a => {
    const idx = publishedArticles.indexOf(a);
    return `<div class="search-result-item" onclick="closeSearch();showArticle(publishedArticles[${idx}])">
      <div class="cat">${(catLabels[a.kategori]||a.kategori).toUpperCase()}</div>
      <h4>${escHtml(a.judul)}</h4>
      <p style="color:rgba(255,255,255,0.45);font-size:0.8rem;margin-top:4px;">${escHtml(a.nama)} · ${a.tanggal}</p>
    </div>`;
  }).join('');
}

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
function escHtml(str) {
  return String(str).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');
}

// ================================================================
// DATE BAR
// ================================================================
const days = ['Minggu','Senin','Selasa','Rabu','Kamis','Jumat','Sabtu'];
const months2 = ['Januari','Februari','Maret','April','Mei','Juni','Juli','Agustus','September','Oktober','November','Desember'];
const now2 = new Date();
document.getElementById('dateBar').textContent = `${days[now2.getDay()]}, ${now2.getDate()} ${months2[now2.getMonth()]} ${now2.getFullYear()}`;

// ================================================================
// INIT
// ================================================================
renderHome();
updateStats();
</script>
</body>
</html>
HTMLEOF
echo "Done. File size: $(wc -c < /mnt/user-data/outputs/orvexa-foundations.html) bytes"
