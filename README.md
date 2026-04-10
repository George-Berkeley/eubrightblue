<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bright Blue Europe</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --navy: #4073af;
    --blue: #6db2e3;
    --blue-mid: #64c7ea;
    --blue-light: #9cd6ea;
    --gold: #eab51f;
    --gold-light: #f1e3a4;
    --cream: #f5efe7;
    --ink: #111827;
    --muted: #5a6478;
    --border: #dde3ef;
    --white: #ffffff;
    --serif: 'Cormorant Garamond', Georgia, serif;
    --sans: 'DM Sans', system-ui, sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: var(--sans);
    font-size: 16px;
    color: var(--ink);
    background: var(--white);
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 3rem;
    height: 68px;
    background: rgba(255,255,255,0.96);
    border-bottom: 1px solid var(--border);
    backdrop-filter: blur(8px);
    transition: box-shadow 0.3s;
  }
  nav.scrolled { box-shadow: 0 2px 24px rgba(0,35,102,0.09); }

  .nav-logo {
    display: flex;
    flex-direction: column;
    line-height: 1.1;
    text-decoration: none;
  }
  .nav-logo .logo-top {
    font-family: var(--serif);
    font-size: 20px;
    font-weight: 500;
    color: var(--navy);
    letter-spacing: 0.01em;
  }
  .nav-logo .logo-sub {
    font-size: 10px;
    font-weight: 300;
    letter-spacing: 0.22em;
    text-transform: uppercase;
    color: var(--gold);
  }

  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }
  .nav-links a {
    font-size: 13px;
    font-weight: 400;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: var(--muted);
    text-decoration: none;
    transition: color 0.2s;
    position: relative;
  }
  .nav-links a::after {
    content: '';
    position: absolute;
    bottom: -3px; left: 0;
    width: 0; height: 1px;
    background: var(--gold);
    transition: width 0.25s;
  }
  .nav-links a:hover { color: var(--navy); }
  .nav-links a:hover::after { width: 100%; }

  .nav-cta {
    font-size: 12px;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--white);
    background: var(--navy);
    padding: 9px 20px;
    text-decoration: none;
    border-radius: 2px;
    transition: background 0.2s;
  }
  .nav-cta:hover { background: var(--blue); }

  /* ── HERO ── */
  #home {
    min-height: 100vh;
    background: var(--navy);
    display: flex;
    align-items: center;
    position: relative;
    overflow: hidden;
    padding-top: 68px;
  }

  .hero-bg {
    position: absolute;
    inset: 0;
    overflow: hidden;
  }

  /* EU-inspired star ring */
  .star-ring {
    position: absolute;
    right: -80px;
    top: 50%;
    transform: translateY(-50%);
    width: 700px;
    height: 700px;
    opacity: 0.07;
  }

  .diagonal-stripe {
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      -55deg,
      transparent,
      transparent 80px,
      rgba(201,168,76,0.04) 80px,
      rgba(201,168,76,0.04) 81px
    );
  }

  .hero-content {
    position: relative;
    z-index: 2;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 3rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
    width: 100%;
  }

  .hero-eyebrow {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1.5rem;
  }
  .hero-eyebrow::before {
    content: '';
    display: block;
    width: 28px;
    height: 1px;
    background: var(--gold);
  }

  .hero-title {
    font-family: var(--serif);
    font-size: clamp(42px, 5vw, 72px);
    font-weight: 300;
    line-height: 1.1;
    color: var(--white);
    margin-bottom: 1.5rem;
    letter-spacing: -0.01em;
  }
  .hero-title em {
    font-style: italic;
    color: var(--gold);
  }

  .hero-body {
    font-size: 17px;
    color: rgba(255,255,255,0.7);
    line-height: 1.75;
    margin-bottom: 2.5rem;
    font-weight: 300;
    max-width: 520px;
  }

  .hero-actions {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
  }
  .btn-primary {
    font-size: 13px;
    font-weight: 500;
    letter-spacing: 0.07em;
    text-transform: uppercase;
    color: var(--navy);
    background: var(--gold);
    padding: 14px 28px;
    text-decoration: none;
    border-radius: 2px;
    transition: background 0.2s, transform 0.15s;
  }
  .btn-primary:hover { background: #d4b05e; transform: translateY(-1px); }

  .btn-secondary {
    font-size: 13px;
    font-weight: 400;
    letter-spacing: 0.07em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.85);
    padding: 14px 28px;
    text-decoration: none;
    border: 1px solid rgba(255,255,255,0.25);
    border-radius: 2px;
    transition: border-color 0.2s, color 0.2s;
  }
  .btn-secondary:hover { border-color: rgba(255,255,255,0.6); color: var(--white); }

  .hero-right {
    display: flex;
    flex-direction: column;
    gap: 1.5px;
  }
  .hero-stat-block {
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    border-left: 3px solid var(--gold);
    padding: 1.5rem 1.75rem;
    transition: background 0.2s;
  }
  .hero-stat-block:hover { background: rgba(255,255,255,0.07); }
  .hero-stat-number {
    font-family: var(--serif);
    font-size: 40px;
    font-weight: 300;
    color: var(--white);
    line-height: 1;
    margin-bottom: 4px;
  }
  .hero-stat-label {
    font-size: 12px;
    font-weight: 300;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.5);
  }

  .scroll-indicator {
    position: absolute;
    bottom: 2.5rem;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    color: rgba(255,255,255,0.35);
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    animation: bob 2.4s ease-in-out infinite;
  }
  .scroll-indicator::after {
    content: '';
    width: 1px;
    height: 40px;
    background: linear-gradient(to bottom, rgba(255,255,255,0.3), transparent);
  }
  @keyframes bob {
    0%,100% { transform: translateX(-50%) translateY(0); }
    50% { transform: translateX(-50%) translateY(6px); }
  }

  /* ── SECTIONS COMMON ── */
  section { scroll-margin-top: 68px; }

  .section-inner {
    max-width: 1200px;
    margin: 0 auto;
    padding: 6rem 3rem;
  }

  .section-label {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 1rem;
  }
  .section-label::before {
    content: '';
    display: block;
    width: 24px;
    height: 1px;
    background: var(--gold);
  }

  .section-heading {
    font-family: var(--serif);
    font-size: clamp(32px, 4vw, 52px);
    font-weight: 300;
    line-height: 1.15;
    color: var(--navy);
    margin-bottom: 1.5rem;
  }

  /* ── ABOUT ── */
  #about { background: var(--cream); }

  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5rem;
    align-items: start;
  }

  .about-lead {
    font-family: var(--serif);
    font-size: 22px;
    font-weight: 300;
    line-height: 1.6;
    color: var(--navy);
    margin-bottom: 1.5rem;
  }

  .about-body {
    font-size: 16px;
    color: var(--muted);
    line-height: 1.8;
    margin-bottom: 1rem;
  }

  .about-pillars {
    display: flex;
    flex-direction: column;
    gap: 0;
  }

  .pillar {
    display: flex;
    gap: 1.25rem;
    padding: 1.5rem 0;
    border-bottom: 1px solid var(--border);
    align-items: flex-start;
    transition: padding-left 0.2s;
  }
  .pillar:first-child { border-top: 1px solid var(--border); }
  .pillar:hover { padding-left: 0.5rem; }

  .pillar-icon {
    width: 36px;
    height: 36px;
    min-width: 36px;
    border-radius: 50%;
    background: var(--blue-light);
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 2px;
  }
  .pillar-icon svg { width: 16px; height: 16px; stroke: var(--blue); fill: none; stroke-width: 1.5; stroke-linecap: round; stroke-linejoin: round; }

  .pillar-title {
    font-family: var(--serif);
    font-size: 18px;
    font-weight: 500;
    color: var(--navy);
    margin-bottom: 4px;
  }
  .pillar-text {
    font-size: 14px;
    color: var(--muted);
    line-height: 1.65;
  }

  .about-parent-note {
    margin-top: 2rem;
    padding: 1.25rem 1.5rem;
    border-left: 3px solid var(--gold);
    background: var(--gold-light);
    border-radius: 0 4px 4px 0;
  }
  .about-parent-note p {
    font-size: 14px;
    color: #7a5c1a;
    line-height: 1.6;
  }
  .about-parent-note a {
    color: #5a4010;
    font-weight: 500;
  }

  /* ── PUBLICATIONS ── */
  #publications { background: var(--white); }

  .pub-filter {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    margin-bottom: 3rem;
  }
  .filter-btn {
    font-size: 12px;
    font-weight: 400;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    padding: 7px 16px;
    border: 1px solid var(--border);
    background: transparent;
    color: var(--muted);
    cursor: pointer;
    border-radius: 2px;
    transition: all 0.18s;
  }
  .filter-btn:hover, .filter-btn.active {
    background: var(--navy);
    border-color: var(--navy);
    color: var(--white);
  }

  .pub-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }

  .pub-card {
    background: var(--white);
    border: 1px solid var(--border);
    border-radius: 3px;
    overflow: hidden;
    transition: transform 0.2s, box-shadow 0.2s;
    cursor: pointer;
    display: flex;
    flex-direction: column;
  }
  .pub-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 12px 40px rgba(0,35,102,0.1);
  }
  .pub-card.featured {
    grid-column: span 2;
    flex-direction: row;
  }

  .pub-thumb {
    height: 200px;
    background: var(--blue-light);
    position: relative;
    overflow: hidden;
    display: flex;
    align-items: flex-end;
  }
  .pub-card.featured .pub-thumb {
    height: auto;
    min-height: 260px;
    width: 45%;
    min-width: 45%;
    flex-shrink: 0;
  }

  .pub-thumb-pattern {
    position: absolute;
    inset: 0;
    overflow: hidden;
  }

  .pub-tag {
    position: absolute;
    top: 1rem;
    left: 1rem;
    font-size: 10px;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 4px 10px;
    border-radius: 2px;
  }
  .tag-economy { background: #e8eef8; color: var(--blue); }
  .tag-climate { background: #e4f0e8; color: #1a6b35; }
  .tag-democracy { background: #f5eed8; color: #7a5c1a; }
  .tag-migration { background: #f0e8f5; color: #6b1a6b; }
  .tag-security { background: #f5e8e8; color: #8b2020; }

  .pub-body {
    padding: 1.5rem;
    flex: 1;
    display: flex;
    flex-direction: column;
  }
  .pub-date {
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 0.04em;
    margin-bottom: 0.6rem;
  }
  .pub-title {
    font-family: var(--serif);
    font-size: 20px;
    font-weight: 400;
    line-height: 1.3;
    color: var(--navy);
    margin-bottom: 0.75rem;
    flex: 1;
  }
  .pub-card.featured .pub-title { font-size: 26px; }
  .pub-excerpt {
    font-size: 14px;
    color: var(--muted);
    line-height: 1.65;
    margin-bottom: 1.25rem;
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }
  .pub-link {
    font-size: 12px;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--blue);
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    gap: 6px;
    margin-top: auto;
  }
  .pub-link svg { width: 14px; height: 14px; transition: transform 0.2s; }
  .pub-card:hover .pub-link svg { transform: translateX(3px); }

  /* SVG patterns for pub thumbs */
  .pattern-dots { background: radial-gradient(circle, #b8cae8 1px, transparent 1px) center/20px 20px var(--blue-light); }
  .pattern-lines {
    background: repeating-linear-gradient(-45deg, transparent, transparent 8px, #c5d5ea 8px, #c5d5ea 9px);
    background-color: var(--blue-light);
  }
  .pattern-grid { background: linear-gradient(var(--border) 1px,transparent 1px) 0 0/30px 30px, linear-gradient(90deg, var(--border) 1px,transparent 1px) 0 0/30px 30px var(--blue-light); }
  .pattern-cross {
    background: radial-gradient(circle at 50% 50%, #c5d5ea 2px, transparent 2px) 0 0/16px 16px,
                radial-gradient(circle at 0% 50%, #c5d5ea 2px, transparent 2px) 0 0/16px 16px var(--blue-light);
  }
  .pattern-wave { background: repeating-linear-gradient(90deg, transparent, transparent 20px, #c5d5ea 20px, #c5d5ea 21px) var(--blue-light); }

  /* ── CONTACT ── */
  #contact { background: var(--navy); }
  #contact .section-heading { color: var(--white); }

  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5rem;
  }

  .contact-intro {
    font-family: var(--serif);
    font-size: 21px;
    font-weight: 300;
    color: rgba(255,255,255,0.85);
    line-height: 1.6;
    margin-bottom: 2rem;
  }

  .contact-details {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    margin-top: 2rem;
  }
  .contact-item {
    display: flex;
    gap: 1rem;
    align-items: flex-start;
  }
  .contact-item-icon {
    width: 36px;
    height: 36px;
    min-width: 36px;
    border-radius: 50%;
    border: 1px solid rgba(255,255,255,0.12);
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 2px;
  }
  .contact-item-icon svg { width: 15px; height: 15px; stroke: var(--gold); fill: none; stroke-width: 1.5; stroke-linecap: round; stroke-linejoin: round; }
  .contact-item-label {
    font-size: 10px;
    font-weight: 500;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 3px;
  }
  .contact-item-value {
    font-size: 15px;
    color: rgba(255,255,255,0.75);
    line-height: 1.5;
  }
  .contact-item-value a { color: rgba(255,255,255,0.75); text-decoration: none; }
  .contact-item-value a:hover { color: var(--gold); }

  .contact-form {
    display: flex;
    flex-direction: column;
    gap: 1.25rem;
  }

  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }

  .form-group { display: flex; flex-direction: column; gap: 6px; }
  .form-label {
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.5);
  }
  .form-input, .form-textarea, .form-select {
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(255,255,255,0.12);
    border-radius: 2px;
    padding: 12px 14px;
    color: var(--white);
    font-family: var(--sans);
    font-size: 15px;
    outline: none;
    transition: border-color 0.2s, background 0.2s;
    width: 100%;
  }
  .form-input::placeholder, .form-textarea::placeholder { color: rgba(255,255,255,0.25); }
  .form-input:focus, .form-textarea:focus, .form-select:focus {
    border-color: var(--gold);
    background: rgba(255,255,255,0.09);
  }
  .form-textarea { resize: vertical; min-height: 130px; line-height: 1.6; }
  .form-select { appearance: none; cursor: pointer; }
  .form-select option { background: var(--navy); }

  .form-submit {
    font-family: var(--sans);
    font-size: 13px;
    font-weight: 500;
    letter-spacing: 0.09em;
    text-transform: uppercase;
    background: var(--gold);
    color: var(--navy);
    border: none;
    padding: 15px 32px;
    cursor: pointer;
    border-radius: 2px;
    transition: background 0.2s, transform 0.15s;
    align-self: flex-start;
  }
  .form-submit:hover { background: #d4b05e; transform: translateY(-1px); }

  .form-success {
    display: none;
    padding: 1.25rem;
    border: 1px solid rgba(201,168,76,0.3);
    border-radius: 2px;
    background: rgba(201,168,76,0.08);
    color: var(--gold);
    font-size: 14px;
    text-align: center;
  }

  /* ── FOOTER ── */
  footer {
    background: #001540;
    padding: 2.5rem 3rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 2rem;
    flex-wrap: wrap;
  }
  .footer-logo {
    font-family: var(--serif);
    font-size: 16px;
    font-weight: 300;
    color: rgba(255,255,255,0.4);
    letter-spacing: 0.02em;
  }
  .footer-logo strong { color: rgba(255,255,255,0.65); font-weight: 400; }
  .footer-links {
    display: flex;
    gap: 2rem;
    list-style: none;
  }
  .footer-links a {
    font-size: 11px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.35);
    text-decoration: none;
    transition: color 0.2s;
  }
  .footer-links a:hover { color: rgba(255,255,255,0.7); }
  .footer-copy {
    font-size: 12px;
    color: rgba(255,255,255,0.25);
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }
  .fade-up { opacity: 0; animation: fadeUp 0.7s ease forwards; }
  .delay-1 { animation-delay: 0.1s; }
  .delay-2 { animation-delay: 0.22s; }
  .delay-3 { animation-delay: 0.34s; }
  .delay-4 { animation-delay: 0.46s; }
  .delay-5 { animation-delay: 0.58s; }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    nav { padding: 0 1.5rem; }
    .nav-links { display: none; }
    .section-inner { padding: 4rem 1.5rem; }
    .hero-content { grid-template-columns: 1fr; gap: 3rem; padding: 0 1.5rem; }
    .hero-right { display: none; }
    .about-grid, .contact-grid { grid-template-columns: 1fr; gap: 2.5rem; }
    .pub-grid { grid-template-columns: 1fr; }
    .pub-card.featured { flex-direction: column; }
    .pub-card.featured .pub-thumb { width: 100%; min-height: 200px; }
    footer { flex-direction: column; align-items: flex-start; text-align: left; padding: 2rem 1.5rem; }
    .form-row { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav id="navbar">
  <a class="nav-logo" href="#home">
    <span class="logo-top">Bright Blue Europe</span>
    <span class="logo-sub">Centre-Right Think Tank</span>
  </a>
  <ul class="nav-links">
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#publications">Publications</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a class="nav-cta" href="#contact">Get in touch</a>
</nav>

<!-- HERO -->
<section id="home">
  <div class="hero-bg">
    <div class="diagonal-stripe"></div>
    <!-- EU star ring SVG -->
    <svg class="star-ring" viewBox="0 0 700 700" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
      <g fill="white">
        <!-- 12 stars arranged in a circle -->
        <polygon points="350,30 355,44 370,44 358,53 363,67 350,58 337,67 342,53 330,44 345,44" transform="rotate(0,350,350)"/>
        <polygon points="350,30 355,44 370,44 358,53 363,67 350,58 337,67 342,53 330,44 345,44" transform="rotate(30,350,350)"/>
        <polygon points="350,30 355,44 370,44 358,53 363,67 350,58 337,67 342,53 330,44 345,44" transform="rotate(60,350,350)"/>
        <polygon points="350,30 355,44 370,44 358,53 363,67 350,58 337,67 342,53 330,44 345,44" transform="rotate(90,350,350)"/>
        <polygon points="350,30 355,44 370,44 358,53 363,67 350,58 337,67 342,53 330,44 345,44" transform="rotate(120,350,350)"/>
        <polygon points="350,30 355,44 370,44 358,53 363,67 350,58 337,67 342,53 330,44 345,44" transform="rotate(150,350,350)"/>
        <polygon points="350,30 355,44 370,44 358,53 363,67 350,58 337,67 342,53 330,44 345,44" transform="rotate(180,350,350)"/>
        <polygon points="350,30 355,44 370,44 358,53 363,67 350,58 337,67 342,53 330,44 345,44" transform="rotate(210,350,350)"/>
        <polygon points="350,30 355,44 370,44 358,53 363,67 350,58 337,67 342,53 330,44 345,44" transform="rotate(240,350,350)"/>
        <polygon points="350,30 355,44 370,44 358,53 363,67 350,58 337,67 342,53 330,44 345,44" transform="rotate(270,350,350)"/>
        <polygon points="350,30 355,44 370,44 358,53 363,67 350,58 337,67 342,53 330,44 345,44" transform="rotate(300,350,350)"/>
        <polygon points="350,30 355,44 370,44 358,53 363,67 350,58 337,67 342,53 330,44 345,44" transform="rotate(330,350,350)"/>
      </g>
    </svg>
  </div>

  <div class="hero-content">
    <div>
      <div class="hero-eyebrow fade-up">European Think Tank</div>
      <h1 class="hero-title fade-up delay-1">
        Defending<br><em>liberal society</em><br>across Europe
      </h1>
      <p class="hero-body fade-up delay-2">
        Bright Blue Europe is an independent, non-partisan centre-right think tank dedicated to promoting liberal, progressive conservatism across the European continent.
      </p>
      <div class="hero-actions fade-up delay-3">
        <a href="#publications" class="btn-primary">Read our research</a>
        <a href="#about" class="btn-secondary">Who we are</a>
      </div>
    </div>

    <div class="hero-right fade-up delay-4">
      <div class="hero-stat-block">
        <div class="hero-stat-number">27</div>
        <div class="hero-stat-label">EU member states engaged</div>
      </div>
      <div class="hero-stat-block">
        <div class="hero-stat-number">40+</div>
        <div class="hero-stat-label">Publications to date</div>
      </div>
      <div class="hero-stat-block">
        <div class="hero-stat-number">5</div>
        <div class="hero-stat-label">Core research themes</div>
      </div>
      <div class="hero-stat-block">
        <div class="hero-stat-number">2019</div>
        <div class="hero-stat-label">Year established</div>
      </div>
    </div>
  </div>
  <div class="scroll-indicator">Scroll</div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="section-inner">
    <div class="about-grid">
      <div>
        <div class="section-label">About us</div>
        <h2 class="section-heading">A liberal, centre-right voice for Europe</h2>
        <p class="about-lead">We produce rigorous, independent research to shape the future of centre-right politics across European democracies.</p>
        <p class="about-body">Bright Blue Europe was established as an offshoot of Bright Blue UK, bringing the same commitment to evidence-based, liberal conservative policy to the broader European stage. We believe in open societies, free markets, strong institutions, and the defence of individual rights.</p>
        <p class="about-body">Our fellows, researchers and associates span the continent — from Stockholm to Lisbon, Warsaw to Lisbon — united by a commitment to practical, humane policy-making that works for ordinary citizens.</p>
        <div class="about-parent-note">
          <p>Bright Blue Europe is an affiliate of <a href="https://www.brightblue.org.uk" target="_blank">Bright Blue UK</a>, the leading centre-right think tank in Britain, which has shaped Conservative Party policy since 2011.</p>
        </div>
      </div>

      <div class="about-pillars">
        <div class="pillar">
          <div class="pillar-icon">
            <svg viewBox="0 0 24 24"><path d="M12 2L2 7l10 5 10-5-10-5z"/><path d="M2 17l10 5 10-5"/><path d="M2 12l10 5 10-5"/></svg>
          </div>
          <div>
            <div class="pillar-title">Rigorous research</div>
            <p class="pillar-text">Independent, evidence-based analysis that transcends party political lines and speaks to the genuine challenges facing European democracies.</p>
          </div>
        </div>
        <div class="pillar">
          <div class="pillar-icon">
            <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M2 12h20M12 2a15.3 15.3 0 010 20M12 2a15.3 15.3 0 000 20"/></svg>
          </div>
          <div>
            <div class="pillar-title">Pan-European perspective</div>
            <p class="pillar-text">We engage policymakers, academics and civil society leaders across the continent to produce research grounded in diverse national contexts.</p>
          </div>
        </div>
        <div class="pillar">
          <div class="pillar-icon">
            <svg viewBox="0 0 24 24"><path d="M17 21v-2a4 4 0 00-4-4H5a4 4 0 00-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 00-3-3.87M16 3.13a4 4 0 010 7.75"/></svg>
          </div>
          <div>
            <div class="pillar-title">Policy influence</div>
            <p class="pillar-text">Our work reaches the offices of European Commissioners, national ministers and Members of the European Parliament who share our values.</p>
          </div>
        </div>
        <div class="pillar">
          <div class="pillar-icon">
            <svg viewBox="0 0 24 24"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
          </div>
          <div>
            <div class="pillar-title">Liberal values</div>
            <p class="pillar-text">We champion individual liberty, open economies and the rule of law — a principled alternative to both populist nationalism and statist progressivism.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PUBLICATIONS -->
<section id="publications">
  <div class="section-inner">
    <div class="section-label">Research & publications</div>
    <h2 class="section-heading">Our latest thinking</h2>

    <div class="pub-filter">
      <button class="filter-btn active" onclick="filterPubs('all', this)">All</button>
      <button class="filter-btn" onclick="filterPubs('economy', this)">Economy</button>
      <button class="filter-btn" onclick="filterPubs('climate', this)">Climate</button>
      <button class="filter-btn" onclick="filterPubs('democracy', this)">Democracy</button>
      <button class="filter-btn" onclick="filterPubs('migration', this)">Migration</button>
      <button class="filter-btn" onclick="filterPubs('security', this)">Security</button>
    </div>

    <div class="pub-grid" id="pub-grid">

      <!-- Featured -->
      <div class="pub-card featured" data-tag="democracy">
        <div class="pub-thumb pattern-dots">
          <span class="pub-tag tag-democracy">Democracy</span>
        </div>
        <div class="pub-body">
          <div class="pub-date">March 2026</div>
          <div class="pub-title">Renewing the centre: how European centre-right parties can rebuild democratic legitimacy</div>
          <p class="pub-excerpt">Across Europe, centre-right parties face an existential challenge from populist movements. This report examines how liberal conservative parties can reconnect with alienated voters through credible, humane policy reform — drawing on case studies from Germany, Sweden and the Netherlands.</p>
          <a href="#" class="pub-link">
            Read report
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </a>
        </div>
      </div>

      <div class="pub-card" data-tag="climate">
        <div class="pub-thumb pattern-lines">
          <span class="pub-tag tag-climate">Climate</span>
        </div>
        <div class="pub-body">
          <div class="pub-date">February 2026</div>
          <div class="pub-title">Green growth: a market-led European climate agenda</div>
          <p class="pub-excerpt">A pro-competition framework for achieving net zero without stifling the enterprise needed to get us there.</p>
          <a href="#" class="pub-link">
            Read report
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </a>
        </div>
      </div>

      <div class="pub-card" data-tag="migration">
        <div class="pub-thumb pattern-grid">
          <span class="pub-tag tag-migration">Migration</span>
        </div>
        <div class="pub-body">
          <div class="pub-date">January 2026</div>
          <div class="pub-title">A fair and managed approach to European migration</div>
          <p class="pub-excerpt">Humane, ordered migration policy that builds public confidence and respects the rule of law.</p>
          <a href="#" class="pub-link">
            Read report
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </a>
        </div>
      </div>

      <div class="pub-card" data-tag="economy">
        <div class="pub-thumb pattern-cross">
          <span class="pub-tag tag-economy">Economy</span>
        </div>
        <div class="pub-body">
          <div class="pub-date">November 2025</div>
          <div class="pub-title">Single market, shared prosperity: deepening European economic integration</div>
          <p class="pub-excerpt">How completing the single market in services could unlock €1.2 trillion in economic value for European citizens.</p>
          <a href="#" class="pub-link">
            Read report
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </a>
        </div>
      </div>

      <div class="pub-card" data-tag="security">
        <div class="pub-thumb pattern-wave">
          <span class="pub-tag tag-security">Security</span>
        </div>
        <div class="pub-body">
          <div class="pub-date">October 2025</div>
          <div class="pub-title">European defence cooperation after Ukraine: a new strategic compact</div>
          <p class="pub-excerpt">The war in Ukraine has transformed the strategic landscape. We propose a framework for deeper European defence industrial collaboration.</p>
          <a href="#" class="pub-link">
            Read report
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </a>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="section-inner">
    <div class="section-label">Contact us</div>
    <h2 class="section-heading">Get in touch</h2>

    <div class="contact-grid">
      <div>
        <p class="contact-intro">We welcome enquiries from researchers, policymakers, journalists and partner organisations across Europe.</p>

        <div class="contact-details">
          <div class="contact-item">
            <div class="contact-item-icon">
              <svg viewBox="0 0 24 24"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
            </div>
            <div>
              <div class="contact-item-label">Address</div>
              <div class="contact-item-value">Rue de la Loi 81, 1040 Brussels, Belgium</div>
            </div>
          </div>
          <div class="contact-item">
            <div class="contact-item-icon">
              <svg viewBox="0 0 24 24"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
            </div>
            <div>
              <div class="contact-item-label">Email</div>
              <div class="contact-item-value"><a href="mailto:info@brightblueeurope.eu">info@brightblueeurope.eu</a></div>
            </div>
          </div>
          <div class="contact-item">
            <div class="contact-item-icon">
              <svg viewBox="0 0 24 24"><path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07A19.5 19.5 0 013.07 9.81a19.79 19.79 0 01-3.07-8.67A2 2 0 012 .18h3a2 2 0 012 1.72c.127.96.361 1.903.7 2.81a2 2 0 01-.45 2.11L6.91 7.91a16 16 0 006.09 6.09l1.27-1.27a2 2 0 012.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0122 16.92z"/></svg>
            </div>
            <div>
              <div class="contact-item-label">Phone</div>
              <div class="contact-item-value"><a href="tel:+3227001234">+32 2 700 1234</a></div>
            </div>
          </div>
          <div class="contact-item">
            <div class="contact-item-icon">
              <svg viewBox="0 0 24 24"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1112.63 8 4 4 0 0116 11.37z"/><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/></svg>
            </div>
            <div>
              <div class="contact-item-label">Follow us</div>
              <div class="contact-item-value">@BrightBlueEurope</div>
            </div>
          </div>
        </div>
      </div>

      <form class="contact-form" onsubmit="handleSubmit(event)">
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">First name</label>
            <input class="form-input" type="text" placeholder="Anna" required>
          </div>
          <div class="form-group">
            <label class="form-label">Last name</label>
            <input class="form-input" type="text" placeholder="Müller" required>
          </div>
        </div>
        <div class="form-group">
          <label class="form-label">Email address</label>
          <input class="form-input" type="email" placeholder="anna@example.com" required>
        </div>
        <div class="form-group">
          <label class="form-label">Organisation</label>
          <input class="form-input" type="text" placeholder="Your institution or affiliation">
        </div>
        <div class="form-group">
          <label class="form-label">Enquiry type</label>
          <select class="form-select" style="background:#0c2d6e; color:white;">
            <option value="">Select a topic</option>
            <option>Research collaboration</option>
            <option>Media enquiry</option>
            <option>Events & speaking</option>
            <option>Partnership</option>
            <option>General enquiry</option>
          </select>
        </div>
        <div class="form-group">
          <label class="form-label">Message</label>
          <textarea class="form-textarea" placeholder="Tell us about your enquiry…" required></textarea>
        </div>
        <button type="submit" class="form-submit">Send message</button>
        <div class="form-success" id="form-success">
          Thank you — we'll be in touch shortly.
        </div>
      </form>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo"><strong>Bright Blue Europe</strong> &nbsp;·&nbsp; An affiliate of Bright Blue UK</div>
  <ul class="footer-links">
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#publications">Publications</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="https://www.brightblue.org.uk" target="_blank">Bright Blue UK</a></li>
  </ul>
  <div class="footer-copy">&copy; 2026 Bright Blue Europe. All rights reserved.</div>
</footer>

<script>
  const navbar = document.getElementById('navbar');
  window.addEventListener('scroll', () => {
    navbar.classList.toggle('scrolled', window.scrollY > 30);
  });

  function filterPubs(tag, btn) {
    document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
    document.querySelectorAll('.pub-card').forEach(card => {
      const show = tag === 'all' || card.dataset.tag === tag;
      card.style.display = show ? 'flex' : 'none';
    });
  }

  function handleSubmit(e) {
    e.preventDefault();
    const btn = e.target.querySelector('.form-submit');
    btn.textContent = 'Sending…';
    btn.disabled = true;
    setTimeout(() => {
      e.target.reset();
      btn.style.display = 'none';
      document.getElementById('form-success').style.display = 'block';
    }, 1000);
  }
</script>
</body>
</html>
