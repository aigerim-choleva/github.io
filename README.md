<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Aigerim Choleva · UGC Creator</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400&family=Jost:wght@200;300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #FAF7F2;
    --warm-white: #F5F0E8;
    --beige: #E8DDD0;
    --rose: #C9A99A;
    --terracotta: #B8876B;
    --brown: #6B4C3B;
    --dark: #2A2018;
    --mid: #7A6A5A;
    --light-text: #A89880;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--cream);
    color: var(--dark);
    font-family: 'Jost', sans-serif;
    font-weight: 300;
    overflow-x: hidden;
  }

  /* ── GRAIN OVERLAY ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 1000;
    opacity: 0.4;
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 24px 60px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: rgba(250, 247, 242, 0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(200, 185, 170, 0.3);
  }

  .nav-logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 18px;
    font-weight: 400;
    letter-spacing: 0.15em;
    color: var(--dark);
    text-decoration: none;
  }

  .nav-links {
    display: flex;
    gap: 40px;
    list-style: none;
  }

  .nav-links a {
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--mid);
    text-decoration: none;
    transition: color 0.3s;
  }

  .nav-links a:hover { color: var(--terracotta); }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    padding: 120px 60px 80px;
    gap: 60px;
    position: relative;
  }

  .hero::after {
    content: '';
    position: absolute;
    top: 0; right: 0;
    width: 45%;
    height: 100%;
    background: linear-gradient(135deg, var(--warm-white) 0%, var(--beige) 100%);
    z-index: -1;
  }

  .hero-text { animation: fadeUp 1s ease forwards; }

  .hero-eyebrow {
    font-size: 10px;
    letter-spacing: 0.35em;
    text-transform: uppercase;
    color: var(--terracotta);
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .hero-eyebrow::before {
    content: '';
    display: block;
    width: 40px;
    height: 1px;
    background: var(--terracotta);
  }

  .hero-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(52px, 7vw, 96px);
    font-weight: 300;
    line-height: 0.95;
    letter-spacing: -0.02em;
    color: var(--dark);
    margin-bottom: 8px;
  }

  .hero-name em {
    font-style: italic;
    color: var(--terracotta);
  }

  .hero-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(18px, 2.5vw, 28px);
    font-weight: 300;
    font-style: italic;
    color: var(--mid);
    margin-bottom: 40px;
    letter-spacing: 0.05em;
  }

  .hero-desc {
    font-size: 14px;
    line-height: 1.9;
    color: var(--mid);
    max-width: 420px;
    margin-bottom: 48px;
  }

  .hero-location {
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--light-text);
    margin-bottom: 48px;
  }

  .hero-cta {
    display: inline-flex;
    align-items: center;
    gap: 12px;
    padding: 14px 36px;
    border: 1px solid var(--terracotta);
    color: var(--terracotta);
    text-decoration: none;
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    transition: all 0.3s;
  }

  .hero-cta:hover {
    background: var(--terracotta);
    color: white;
  }

  .hero-image {
    position: relative;
    animation: fadeIn 1.2s ease forwards;
  }

  .hero-image img {
    width: 100%;
    max-width: 460px;
    aspect-ratio: 3/4;
    object-fit: cover;
    display: block;
    filter: sepia(8%) contrast(1.05);
  }

  .hero-image-placeholder {
    width: 100%;
    max-width: 460px;
    aspect-ratio: 3/4;
    background: linear-gradient(145deg, var(--beige) 0%, var(--rose) 60%, var(--terracotta) 100%);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: white;
    font-family: 'Cormorant Garamond', serif;
    font-size: 18px;
    font-style: italic;
    gap: 8px;
  }

  .hero-image-placeholder span {
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    opacity: 0.8;
    font-style: normal;
    font-family: 'Jost', sans-serif;
  }

  .hero-image::before {
    content: '';
    position: absolute;
    top: -20px; left: -20px;
    right: 20px; bottom: 20px;
    border: 1px solid var(--beige);
    z-index: -1;
  }

  .hero-floating-tag {
    position: absolute;
    bottom: 40px;
    left: -30px;
    background: white;
    padding: 16px 24px;
    box-shadow: 0 8px 40px rgba(0,0,0,0.08);
  }

  .hero-floating-tag .tag-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 32px;
    font-weight: 300;
    color: var(--terracotta);
    line-height: 1;
  }

  .hero-floating-tag .tag-label {
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--mid);
    margin-top: 4px;
  }

  /* ── MARQUEE ── */
  .marquee-wrap {
    background: var(--dark);
    padding: 18px 0;
    overflow: hidden;
    white-space: nowrap;
  }

  .marquee-track {
    display: inline-flex;
    animation: marquee 20s linear infinite;
  }

  .marquee-item {
    font-size: 10px;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--beige);
    padding: 0 48px;
  }

  .marquee-dot {
    color: var(--terracotta);
    padding: 0 4px;
  }

  /* ── SECTION COMMON ── */
  section { padding: 100px 60px; }

  .section-label {
    font-size: 10px;
    letter-spacing: 0.35em;
    text-transform: uppercase;
    color: var(--terracotta);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 16px;
  }

  .section-label::after {
    content: '';
    display: block;
    height: 1px;
    width: 60px;
    background: var(--terracotta);
    opacity: 0.5;
  }

  .section-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(36px, 5vw, 64px);
    font-weight: 300;
    line-height: 1.1;
    color: var(--dark);
    margin-bottom: 20px;
  }

  .section-title em { font-style: italic; color: var(--terracotta); }

  /* ── SERVICES ── */
  .services { background: var(--warm-white); }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
    margin-top: 60px;
  }

  .service-card {
    background: white;
    padding: 48px 40px;
    position: relative;
    overflow: hidden;
    transition: transform 0.3s;
  }

  .service-card:hover { transform: translateY(-4px); }

  .service-card::before {
    content: '';
    position: absolute;
    bottom: 0; left: 0;
    width: 100%; height: 3px;
    background: var(--terracotta);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s ease;
  }

  .service-card:hover::before { transform: scaleX(1); }

  .service-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 48px;
    font-weight: 300;
    color: var(--beige);
    line-height: 1;
    margin-bottom: 24px;
  }

  .service-icon { font-size: 28px; margin-bottom: 16px; }

  .service-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 22px;
    font-weight: 400;
    color: var(--dark);
    margin-bottom: 12px;
  }

  .service-desc {
    font-size: 13px;
    line-height: 1.8;
    color: var(--mid);
  }

  /* ── PORTFOLIO ── */
  .portfolio-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 60px;
  }

  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
  }

  .portfolio-item {
    position: relative;
    overflow: hidden;
    cursor: pointer;
  }

  .portfolio-thumb {
    aspect-ratio: 9/16;
    background: linear-gradient(145deg, var(--beige), var(--rose));
    position: relative;
    overflow: hidden;
    transition: transform 0.5s ease;
  }

  .portfolio-item:hover .portfolio-thumb { transform: scale(1.03); }

  .portfolio-thumb-inner {
    position: absolute;
    inset: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 24px;
    text-align: center;
  }

  .portfolio-play {
    width: 56px; height: 56px;
    border: 1.5px solid rgba(255,255,255,0.8);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 20px;
    transition: all 0.3s;
  }

  .portfolio-item:hover .portfolio-play {
    background: white;
    border-color: white;
  }

  .portfolio-play svg { fill: white; transition: fill 0.3s; }
  .portfolio-item:hover .portfolio-play svg { fill: var(--terracotta); }

  .portfolio-vid-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 16px;
    font-weight: 400;
    color: white;
    font-style: italic;
    margin-bottom: 6px;
  }

  .portfolio-vid-brand {
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.7);
  }

  .portfolio-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(to top, rgba(42,32,24,0.7) 0%, transparent 60%);
  }

  .portfolio-meta {
    padding: 16px 0;
  }

  .portfolio-cat {
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--terracotta);
    margin-bottom: 4px;
  }

  .portfolio-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 18px;
    color: var(--dark);
  }

  /* Portfolio color variants */
  .pt-1 { background: linear-gradient(145deg, #D4C4B8, #C9A99A); }
  .pt-2 { background: linear-gradient(145deg, #B8C4C8, #9AAAB4); }
  .pt-3 { background: linear-gradient(145deg, #C8C4B8, #B4A898); }
  .pt-4 { background: linear-gradient(145deg, #C4B8D4, #A89AC9); }
  .pt-5 { background: linear-gradient(145deg, #B8D4C4, #9AC9B4); }
  .pt-6 { background: linear-gradient(145deg, #D4B8C4, #C9A0B8); }

  /* ── BRANDS ── */
  .brands { background: var(--warm-white); }

  .brands-list {
    margin-top: 60px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2px;
  }

  .brand-item {
    background: white;
    padding: 32px 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    transition: background 0.3s;
  }

  .brand-item:hover { background: var(--cream); }

  .brand-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 24px;
    font-weight: 400;
    color: var(--dark);
  }

  .brand-detail {
    font-size: 12px;
    color: var(--mid);
    margin-top: 4px;
    letter-spacing: 0.05em;
  }

  .brand-tag {
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--terracotta);
    border: 1px solid var(--rose);
    padding: 6px 14px;
  }

  /* ── CONTACT ── */
  .contact {
    background: var(--dark);
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .contact::before {
    content: 'AC';
    position: absolute;
    font-family: 'Cormorant Garamond', serif;
    font-size: 400px;
    font-weight: 300;
    color: rgba(255,255,255,0.03);
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    pointer-events: none;
    letter-spacing: -0.05em;
  }

  .contact .section-label { justify-content: center; color: var(--rose); }
  .contact .section-label::after { background: var(--rose); }

  .contact .section-title { color: white; }
  .contact .section-title em { color: var(--rose); }

  .contact-subtitle {
    font-size: 14px;
    color: rgba(255,255,255,0.5);
    margin-bottom: 60px;
    line-height: 1.8;
  }

  .contact-links {
    display: flex;
    justify-content: center;
    gap: 48px;
    flex-wrap: wrap;
    margin-bottom: 60px;
  }

  .contact-link {
    text-decoration: none;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    transition: transform 0.3s;
  }

  .contact-link:hover { transform: translateY(-4px); }

  .contact-link-icon {
    width: 48px; height: 48px;
    border: 1px solid rgba(255,255,255,0.2);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
    transition: border-color 0.3s, background 0.3s;
  }

  .contact-link:hover .contact-link-icon {
    border-color: var(--rose);
    background: rgba(201, 169, 154, 0.15);
  }

  .contact-link-label {
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.4);
  }

  .contact-email {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(20px, 3vw, 36px);
    font-weight: 300;
    color: white;
    text-decoration: none;
    border-bottom: 1px solid rgba(255,255,255,0.2);
    padding-bottom: 4px;
    transition: border-color 0.3s, color 0.3s;
  }

  .contact-email:hover {
    color: var(--rose);
    border-color: var(--rose);
  }

  /* ── FOOTER ── */
  footer {
    background: var(--dark);
    border-top: 1px solid rgba(255,255,255,0.08);
    padding: 24px 60px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  footer .logo {
    font-family: 'Cormorant Garamond', serif;
    font-size: 14px;
    color: rgba(255,255,255,0.4);
    letter-spacing: 0.1em;
  }

  footer .copy {
    font-size: 11px;
    color: rgba(255,255,255,0.25);
    letter-spacing: 0.1em;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
  }

  @keyframes marquee {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }

  .reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }

  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* ── SCROLLBAR ── */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: var(--cream); }
  ::-webkit-scrollbar-thumb { background: var(--rose); }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">Aigerim Choleva</a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#portfolio">Portfolio</a></li>
    <li><a href="#brands">Brands</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="about">
  <div class="hero-text">
    <div class="hero-eyebrow">UGC Creator · Sofia, Bulgaria</div>
    <h1 class="hero-name">Aigerim<br><em>Choleva</em></h1>
    <p class="hero-title">Fashion · Beauty · Lifestyle</p>
    <p class="hero-desc">I create aesthetic, elegant UGC content for fashion, beauty and lifestyle brands — visuals that feel luxurious, feminine and editorial. Every frame is intentional.</p>
    <p class="hero-location">🇧🇬 Based in Sofia · Available for European & International Collaborations</p>
    <a href="#contact" class="hero-cta">Let's collaborate →</a>
  </div>

  <div class="hero-image">
    <div class="hero-image-placeholder">
      Your photo here
      <span>Upload your portrait</span>
    </div>
    <div class="hero-floating-tag">
      <div class="tag-num">3+</div>
      <div class="tag-label">Brand Collaborations</div>
    </div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-wrap">
  <div class="marquee-track">
    <span class="marquee-item">Fashion <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Beauty <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Lifestyle <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Skincare <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">UGC Creator <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Sofia, Bulgaria <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">European Market <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Aesthetic Content <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Fashion <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Beauty <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Lifestyle <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Skincare <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">UGC Creator <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Sofia, Bulgaria <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">European Market <span class="marquee-dot">✦</span></span>
    <span class="marquee-item">Aesthetic Content <span class="marquee-dot">✦</span></span>
  </div>
</div>

<!-- SERVICES -->
<section class="services" id="services">
  <div class="reveal">
    <div class="section-label">What I Create</div>
    <h2 class="section-title">Content that<br><em>converts</em></h2>
  </div>
  <div class="services-grid reveal">
    <div class="service-card">
      <div class="service-num">01</div>
      <div class="service-icon">🎬</div>
      <div class="service-name">Reels & Short Video</div>
      <p class="service-desc">Product demos, unboxing, lifestyle — vertical format optimised for Instagram & TikTok. Engaging, aesthetic, on-brand.</p>
    </div>
    <div class="service-card">
      <div class="service-num">02</div>
      <div class="service-icon">📸</div>
      <div class="service-name">Photo Content</div>
      <p class="service-desc">Flat lay, close-up, editorial — clean aesthetics that showcase your product beautifully and drive desire.</p>
    </div>
    <div class="service-card">
      <div class="service-num">03</div>
      <div class="service-icon">✨</div>
      <div class="service-name">Brand Storytelling</div>
      <p class="service-desc">Aesthetic narrative content that connects your product to a feeling and a lifestyle. Content with soul.</p>
    </div>
  </div>
</section>

<!-- PORTFOLIO -->
<section id="portfolio">
  <div class="portfolio-header reveal">
    <div>
      <div class="section-label">Selected Work</div>
      <h2 class="section-title">Portfolio</h2>
    </div>
  </div>

  <div class="portfolio-grid reveal">

    <div class="portfolio-item">
      <div class="portfolio-thumb pt-1">
        <div class="portfolio-overlay"></div>
        <div class="portfolio-thumb-inner">
          <div class="portfolio-play">
            <svg width="14" height="16" viewBox="0 0 14 16"><path d="M0 0l14 8-14 8z"/></svg>
          </div>
          <div class="portfolio-vid-title">White Truffle Mist</div>
          <div class="portfolio-vid-brand">D'alba × YesStyle</div>
        </div>
      </div>
      <div class="portfolio-meta">
        <div class="portfolio-cat">Beauty & Skincare</div>
        <div class="portfolio-name">D'alba White Truffle Mist × YesStyle</div>
      </div>
    </div>

    <div class="portfolio-item">
      <div class="portfolio-thumb pt-2">
        <div class="portfolio-overlay"></div>
        <div class="portfolio-thumb-inner">
          <div class="portfolio-play">
            <svg width="14" height="16" viewBox="0 0 14 16"><path d="M0 0l14 8-14 8z"/></svg>
          </div>
          <div class="portfolio-vid-title">TXA Niacinamide 99</div>
          <div class="portfolio-vid-brand">APRILSKIN × YesStyle</div>
        </div>
      </div>
      <div class="portfolio-meta">
        <div class="portfolio-cat">Beauty & Skincare</div>
        <div class="portfolio-name">APRILSKIN TXA Niacinamide × YesStyle</div>
      </div>
    </div>

    <div class="portfolio-item">
      <div class="portfolio-thumb pt-3">
        <div class="portfolio-overlay"></div>
        <div class="portfolio-thumb-inner">
          <div class="portfolio-play">
            <svg width="14" height="16" viewBox="0 0 14 16"><path d="M0 0l14 8-14 8z"/></svg>
          </div>
          <div class="portfolio-vid-title">Dior & Clarins Unboxing</div>
          <div class="portfolio-vid-brand">Douglas</div>
        </div>
      </div>
      <div class="portfolio-meta">
        <div class="portfolio-cat">Beauty & Skincare</div>
        <div class="portfolio-name">Douglas Unboxing — Dior & Clarins</div>
      </div>
    </div>

    <div class="portfolio-item">
      <div class="portfolio-thumb pt-4">
        <div class="portfolio-overlay"></div>
        <div class="portfolio-thumb-inner">
          <div class="portfolio-play">
            <svg width="14" height="16" viewBox="0 0 14 16"><path d="M0 0l14 8-14 8z"/></svg>
          </div>
          <div class="portfolio-vid-title">Zara Kimono</div>
          <div class="portfolio-vid-brand">Fashion Detail</div>
        </div>
      </div>
      <div class="portfolio-meta">
        <div class="portfolio-cat">Fashion & Accessories</div>
        <div class="portfolio-name">Zara Kimono — Fashion Detail</div>
      </div>
    </div>

    <div class="portfolio-item">
      <div class="portfolio-thumb pt-5">
        <div class="portfolio-overlay"></div>
        <div class="portfolio-thumb-inner">
          <div class="portfolio-play">
            <svg width="14" height="16" viewBox="0 0 14 16"><path d="M0 0l14 8-14 8z"/></svg>
          </div>
          <div class="portfolio-vid-title">Studio Bowling Bag</div>
          <div class="portfolio-vid-brand">COS / H&M Premium</div>
        </div>
      </div>
      <div class="portfolio-meta">
        <div class="portfolio-cat">Fashion & Accessories</div>
        <div class="portfolio-name">Studio Bowling Bag — COS/H&M Premium</div>
      </div>
    </div>

    <div class="portfolio-item">
      <div class="portfolio-thumb pt-6">
        <div class="portfolio-overlay"></div>
        <div class="portfolio-thumb-inner">
          <div class="portfolio-play">
            <svg width="14" height="16" viewBox="0 0 14 16"><path d="M0 0l14 8-14 8z"/></svg>
          </div>
          <div class="portfolio-vid-title">Coffee Ritual</div>
          <div class="portfolio-vid-brand">De'Longhi Rivelia</div>
        </div>
      </div>
      <div class="portfolio-meta">
        <div class="portfolio-cat">Lifestyle & Home</div>
        <div class="portfolio-name">De'Longhi Rivelia — Coffee Ritual</div>
      </div>
    </div>

  </div>
</section>

<!-- BRANDS -->
<section class="brands" id="brands">
  <div class="reveal">
    <div class="section-label">Collaborations</div>
    <h2 class="section-title">Brands I've<br><em>worked with</em></h2>
  </div>
  <div class="brands-list reveal">
    <div class="brand-item">
      <div>
        <div class="brand-name">YesStyle</div>
        <div class="brand-detail">D'alba White Truffle Mist · Skincare Reel</div>
      </div>
      <div class="brand-tag">Gifted</div>
    </div>
    <div class="brand-item">
      <div>
        <div class="brand-name">YesStyle</div>
        <div class="brand-detail">APRILSKIN TXA Niacinamide · Skincare Reel</div>
      </div>
      <div class="brand-tag">Gifted</div>
    </div>
    <div class="brand-item">
      <div>
        <div class="brand-name">Douglas</div>
        <div class="brand-detail">Dior & Clarins · Unboxing Reel</div>
      </div>
      <div class="brand-tag">Content</div>
    </div>
    <div class="brand-item">
      <div>
        <div class="brand-name">Kiehl's</div>
        <div class="brand-detail">Super Multi-Corrective Cream · Review</div>
      </div>
      <div class="brand-tag">Content</div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="reveal">
    <div class="section-label">Get in Touch</div>
    <h2 class="section-title">Let's create something<br><em>beautiful</em></h2>
    <p class="contact-subtitle">Open for gifted partnerships, paid collaborations<br>and long-term brand ambassadorships.</p>

    <div class="contact-links">
      <a href="mailto:aigerim11@gmail.com" class="contact-link">
        <div class="contact-link-icon">📩</div>
        <div class="contact-link-label">Email</div>
      </a>
      <a href="https://instagram.com/aigerim.choleva" target="_blank" class="contact-link">
        <div class="contact-link-icon">📱</div>
        <div class="contact-link-label">Instagram</div>
      </a>
      <a href="https://tiktok.com/@aigerim_choleva" target="_blank" class="contact-link">
        <div class="contact-link-icon">🎵</div>
        <div class="contact-link-label">TikTok</div>
      </a>
    </div>

    <a href="mailto:aigerim11@gmail.com" class="contact-email">aigerim11@gmail.com</a>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="logo">Aigerim Choleva · UGC Creator</div>
  <div class="copy">Sofia, Bulgaria 🇧🇬 · 2026</div>
</footer>

<script>
  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 100);
      }
    });
  }, { threshold: 0.1 });
  reveals.forEach(el => observer.observe(el));
</script>

</body>
</html># github.io
