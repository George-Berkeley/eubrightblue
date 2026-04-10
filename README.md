<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bright Blue Europe</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,400;0,9..144,500;1,9..144,300;1,9..144,400;1,9..144,500&family=Outfit:wght@300;400;500&display=swap" rel="stylesheet">

<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}

:root{
  --navy:#002366;
  --navy-dark:#001540;
  --blue:#1a4fc4;
  --cream:#FAF8F2;
  --cream-dark:#F0EDE3;
  --gold:#C9A84C;
  --ink:#111217;
  --muted:#6b7280;
  --border:#e2ddd4;
  --serif:'Fraunces',Georgia,serif;
  --sans:'Outfit',system-ui,sans-serif;
}

body{margin: 0;
  padding: 0;
  width: 100vw;       /* Force body to browser width */
  overflow-x: hidden; /* Prevents unwanted horizontal scrolling */
  background: var(--cream);
     font-family:var(--sans);background:var(--cream);color:var(--ink);overflow-x:hidden;font-size:17px;line-height:1.7}

/* NAV */
#nav{
  position:fixed;top:0;left:0;right:0;z-index:200;
  display:flex;align-items:center;justify-content:space-between;
  padding:0 4rem;height:72px;
  transition:background 0.4s,border-color 0.4s;
}
#nav.solid{background:rgba(0,20,64,0.97);border-bottom:1px solid rgba(255,255,255,0.08)}
#nav.light{background:rgba(250,248,242,0.96);border-bottom:1px solid var(--border)}

.nav-brand{text-decoration:none;display:flex;flex-direction:column;line-height:1.15}
.nav-brand-name{font-family:var(--serif);font-size:18px;font-weight:400;letter-spacing:0.01em;transition:color 0.3s}
.nav-brand-sub{font-family:var(--sans);font-size:10px;font-weight:300;letter-spacing:0.22em;text-transform:uppercase;transition:color 0.3s}
#nav.solid .nav-brand-name{color:#fff}
#nav.solid .nav-brand-sub{color:rgba(255,255,255,0.4)}
#nav.light .nav-brand-name{color:var(--navy)}
#nav.light .nav-brand-sub{color:var(--gold)}

.nav-links{display:flex;gap:2.5rem;list-style:none}
.nav-links a{font-size:12px;font-weight:400;letter-spacing:0.08em;text-transform:uppercase;text-decoration:none;transition:color 0.2s}
#nav.solid .nav-links a{color:rgba(255,255,255,0.55)}
#nav.solid .nav-links a:hover{color:#fff}
#nav.light .nav-links a{color:var(--muted)}
#nav.light .nav-links a:hover{color:var(--navy)}

.nav-btn{
  font-family:var(--sans);font-size:11px;font-weight:500;letter-spacing:0.1em;
  text-transform:uppercase;text-decoration:none;padding:10px 22px;border-radius:1px;transition:all 0.2s;
}
#nav.solid .nav-btn{background:transparent;border:1px solid rgba(255,255,255,0.28);color:#fff}
#nav.solid .nav-btn:hover{background:rgba(255,255,255,0.1);border-color:rgba(255,255,255,0.55)}
#nav.light .nav-btn{background:var(--navy);border:1px solid var(--navy);color:#fff}
#nav.light .nav-btn:hover{background:var(--blue)}

/* HERO */
#home {
  position: relative;
  width: 100vw;      /* Uses the full width of the browser window */
  margin-left: 0;    /* Ensures no left offset */
  margin-right: 0;
  height: 100vh;
  height: 100dvh; 
  min-height: 680px;
  display: flex;
  align-items: flex-end;
  overflow: hidden;
  left: 50%;         /* Centering hack to ensure it stays pinned if parented */
  transform: translateX(-50%); 
}
.hero-img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: url('https://images.unsplash.com/photo-1673295716958-b1dc96e5b24f?auto=format&fit=crop&w=960&q=80') center/cover no-repeat;
  z-index: 0;
}
.hero-img.loaded{transform:scale(1)}
.hero-overlay{
  position:absolute;inset:0;
  background:linear-gradient(to top,rgba(0,18,60,0.9) 0%,rgba(0,18,60,0.42) 52%,rgba(0,18,60,0.12) 100%);
}
.hero-content {
  position: relative;
  z-index: 2;
  padding: 0 4rem 5.5rem;
  max-width: 100%;    /* Allow content to use the full width of the hero */
  width: 100%;
}
.hero-eyebrow{
  font-family:var(--sans);font-size:11px;font-weight:400;letter-spacing:0.22em;text-transform:uppercase;
  color:var(--gold);margin-bottom:1.5rem;display:flex;align-items:center;gap:12px;
  opacity:0;transform:translateY(16px);animation:fadeUp 0.8s 0.2s forwards;
}
.hero-eyebrow::before{content:'';display:block;width:32px;height:1px;background:var(--gold)}
.hero-headline{
  font-family:var(--serif);font-size:clamp(50px,6.5vw,90px);
  font-weight:300;line-height:1.04;color:#fff;margin-bottom:2rem;
  opacity:0;transform:translateY(20px);animation:fadeUp 0.9s 0.35s forwards;
}
.hero-headline em{font-style:italic;color:var(--gold)}
.hero-sub{
  font-size:18px;font-weight:300;color:rgba(255,255,255,0.68);
  max-width:560px;line-height:1.78;margin-bottom:2.5rem;
  opacity:0;transform:translateY(16px);animation:fadeUp 0.8s 0.5s forwards;
}
.hero-actions{
  display:flex;gap:1rem;flex-wrap:wrap;
  opacity:0;animation:fadeUp 0.8s 0.65s forwards;
}
.btn-gold{
  font-family:var(--sans);font-size:12px;font-weight:500;letter-spacing:0.1em;text-transform:uppercase;
  text-decoration:none;padding:15px 32px;background:var(--gold);color:var(--navy-dark);
  border-radius:1px;transition:background 0.2s,transform 0.15s;
}
.btn-gold:hover{background:#d4b058;transform:translateY(-2px)}
.btn-ghost{
  font-family:var(--sans);font-size:12px;font-weight:400;letter-spacing:0.1em;text-transform:uppercase;
  text-decoration:none;padding:15px 32px;border:1px solid rgba(255,255,255,0.3);
  color:rgba(255,255,255,0.82);border-radius:1px;transition:border-color 0.2s,color 0.2s;
}
.btn-ghost:hover{border-color:#fff;color:#fff}
.hero-scroll-hint{
  position:absolute;bottom:2.5rem;right:4rem;z-index:2;
  display:flex;align-items:center;gap:10px;
  font-size:10px;font-weight:300;letter-spacing:0.18em;text-transform:uppercase;
  color:rgba(255,255,255,0.35);writing-mode:vertical-rl;
}
.hero-scroll-hint::after{
  content:'';display:block;width:1px;height:48px;
  background:linear-gradient(to bottom,rgba(255,255,255,0.3),transparent);
  animation:scrollLine 2.2s ease-in-out infinite;
}
@keyframes scrollLine{0%,100%{opacity:0.35;transform:scaleY(1)}50%{opacity:0.85;transform:scaleY(0.65)}}

/* ABOUT */
#about{background:var(--cream)}
.about-split{display:grid;grid-template-columns:1fr 1fr;min-height:90vh}
.about-photo-side{position:relative;overflow:hidden;min-height:500px}
.about-photo{
  position:absolute;inset:0;
  background:url('https://images.unsplash.com/photo-1673295716958-b1dc96e5b24f?auto=format&fit=crop&w=960&q=80') center/cover no-repeat;
  transform:scale(1.05);transition:transform 1.1s ease;
}
.about-photo.revealed{transform:scale(1)}
.about-text-side{
  background:var(--navy);padding:7rem 5rem;
  display:flex;flex-direction:column;justify-content:center;
}
.section-label{
  font-size:10px;font-weight:400;letter-spacing:0.24em;text-transform:uppercase;
  color:var(--gold);margin-bottom:1.5rem;display:flex;align-items:center;gap:10px;
}
.section-label::before{content:'';display:block;width:24px;height:1px;background:var(--gold)}
.section-heading{font-family:var(--serif);font-size:clamp(34px,3.5vw,54px);font-weight:300;line-height:1.12;margin-bottom:2rem}
.section-heading em{font-style:italic;color:var(--gold)}
.about-text-side .section-heading{color:#fff}
.about-lead{
  font-family:var(--serif);font-size:20px;font-weight:300;font-style:italic;
  color:rgba(255,255,255,0.72);line-height:1.65;margin-bottom:1.5rem;
}
.about-body{font-size:15px;font-weight:300;color:rgba(255,255,255,0.56);line-height:1.88;margin-bottom:1rem}
.about-cta-link{
  font-size:12px;font-weight:400;letter-spacing:0.1em;text-transform:uppercase;
  color:var(--gold);text-decoration:none;display:inline-flex;align-items:center;gap:8px;
  margin-top:1.5rem;transition:gap 0.22s;
}
.about-cta-link:hover{gap:14px}
.about-cta-link::after{content:'→';font-size:15px}

.pillars-band{background:var(--cream-dark);padding:5.5rem 4rem}
.pillars-inner{max-width:2715px;margin:0 auto}
.pillars-top{text-align:center;margin-bottom:3.5rem}
.pillars-top .section-label{justify-content:center}
.pillars-top .section-label::before{display:none}
.pillars-headline{
  font-family:var(--serif);font-size:clamp(28px,3vw,42px);font-weight:300;
  color:var(--navy);margin-top:0.5rem;
}
.pillars-headline em{font-style:italic;color:var(--gold)}
.pillars-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:0;border:1px solid var(--border)}
.pillar-item{
  padding:2.5rem 2rem;border-right:1px solid var(--border);
  transition:background 0.25s;
}
.pillar-item:last-child{border-right:none}
.pillar-item:hover{background:var(--cream)}
.pillar-num{
  font-family:var(--serif);font-size:44px;font-weight:300;
  color:var(--navy);opacity:0.13;line-height:1;margin-bottom:1rem;
}
.pillar-name{font-family:var(--serif);font-size:19px;font-weight:400;color:var(--navy);margin-bottom:0.75rem}
.pillar-desc{font-size:14px;font-weight:300;color:var(--muted);line-height:1.75}

/* STAFF */
#staff{background:var(--cream);padding:7rem 4rem}
.staff-inner{max-width:2715px;margin:0 auto}
.staff-header{display:flex;align-items:flex-end;justify-content:space-between;margin-bottom:4rem;gap:2rem;flex-wrap:wrap}
.staff-header .section-heading{color:var(--navy);margin-bottom:0}
.staff-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:2px}
.staff-card{position:relative;overflow:hidden;background:var(--navy-dark);cursor:pointer;aspect-ratio:3/4}
.staff-card-img{width:100%;height:100%;object-fit:cover;display:block;filter:grayscale(15%);transition:transform 0.65s ease,filter 0.4s}
.staff-card:hover .staff-card-img{transform:scale(1.05);filter:grayscale(0%)}
.staff-overlay{
  position:absolute;inset:0;
  background:linear-gradient(to top,rgba(0,15,50,0.94) 0%,rgba(0,15,50,0.28) 50%,transparent 100%);
}
.staff-body{
  position:absolute;bottom:0;left:0;right:0;padding:2rem 2.5rem;
  transform:translateY(6px);transition:transform 0.35s;
}
.staff-card:hover .staff-body{transform:none}
.staff-role{font-size:10px;font-weight:400;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold);margin-bottom:0.5rem}
.staff-name{font-family:var(--serif);font-size:34px;font-weight:300;color:#fff;line-height:1.12;margin-bottom:0.75rem}
.staff-bio{
  font-size:14px;font-weight:300;color:rgba(255,255,255,0.62);line-height:1.72;
  max-height:0;overflow:hidden;opacity:0;transition:max-height 0.45s ease,opacity 0.35s;
}
.staff-card:hover .staff-bio{max-height:130px;opacity:1}
.staff-tags{
  display:flex;flex-wrap:wrap;gap:6px;margin-top:1rem;
  max-height:0;overflow:hidden;opacity:0;transition:max-height 0.45s 0.05s ease,opacity 0.35s 0.05s;
}
.staff-card:hover .staff-tags{max-height:60px;opacity:1}
.staff-tag{
  font-size:10px;font-weight:300;letter-spacing:0.04em;
  background:rgba(255,255,255,0.09);border:1px solid rgba(255,255,255,0.18);
  color:rgba(255,255,255,0.72);padding:4px 10px;border-radius:100px;
}
.staff-socials{
  display:flex;gap:10px;margin-top:1.25rem;
  max-height:0;overflow:hidden;opacity:0;transition:max-height 0.45s 0.08s ease,opacity 0.35s 0.08s;
}
.staff-card:hover .staff-socials{max-height:40px;opacity:1}
.staff-social{
  width:32px;height:32px;border-radius:50%;border:1px solid rgba(255,255,255,0.22);
  display:flex;align-items:center;justify-content:center;text-decoration:none;
  color:rgba(255,255,255,0.55);transition:all 0.2s;
}
.staff-social:hover{background:var(--gold);border-color:var(--gold);color:var(--navy-dark)}
.staff-social svg{width:13px;height:13px;fill:none;stroke:currentColor;stroke-width:1.8;stroke-linecap:round;stroke-linejoin:round}

/* PUBLICATIONS */
#publications{background:var(--navy);padding:7rem 4rem}
.pub-inner{max-width:2715px;margin:0 auto}
.pub-header{display:flex;align-items:flex-end;justify-content:space-between;margin-bottom:1.5rem;gap:2rem;flex-wrap:wrap}
.pub-header .section-heading{color:#fff;margin-bottom:0}
.pub-header .section-label{color:var(--gold)}
.pub-all-link{
  font-size:12px;font-weight:300;letter-spacing:0.1em;text-transform:uppercase;
  color:rgba(255,255,255,0.45);text-decoration:none;white-space:nowrap;
  display:inline-flex;align-items:center;gap:8px;align-self:flex-end;
  transition:color 0.2s,gap 0.2s;
}
.pub-all-link:hover{color:#fff;gap:14px}
.pub-all-link::after{content:'→';font-size:14px}
.pub-filters{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:3rem}
.pub-filter-btn{
  font-size:11px;font-weight:300;letter-spacing:0.07em;text-transform:uppercase;
  padding:7px 18px;border:1px solid rgba(255,255,255,0.14);background:transparent;
  color:rgba(255,255,255,0.45);cursor:pointer;border-radius:100px;transition:all 0.2s;
}
.pub-filter-btn:hover{border-color:rgba(255,255,255,0.38);color:rgba(255,255,255,0.8)}
.pub-filter-btn.active{background:var(--gold);border-color:var(--gold);color:var(--navy-dark)}
.pub-grid{display:grid;grid-template-columns:2fr 1fr 1fr;gap:1px;background:rgba(255,255,255,0.07)}
.pub-card{
  background:var(--navy);padding:2.5rem;
  display:flex;flex-direction:column;
  border-bottom:2px solid transparent;transition:background 0.25s,border-color 0.25s;cursor:pointer;
}
.pub-card:hover{background:rgba(255,255,255,0.04);border-color:var(--gold)}
.pub-card.large{grid-row:span 2;padding:3rem}
.pub-cat{font-size:10px;font-weight:400;letter-spacing:0.18em;text-transform:uppercase;margin-bottom:1rem}
.cat-democracy{color:#93b4f0}.cat-economy{color:#86d9b0}.cat-climate{color:#7dd9c1}
.cat-migration{color:#c9a8f0}.cat-security{color:#f0b893}
.pub-title{font-family:var(--serif);font-weight:300;color:#fff;line-height:1.25;flex:1;margin-bottom:1.5rem}
.pub-card.large .pub-title{font-size:28px;margin-bottom:2rem}
.pub-card:not(.large) .pub-title{font-size:19px}
.pub-excerpt{font-size:14px;font-weight:300;color:rgba(255,255,255,0.48);line-height:1.78;margin-bottom:1.5rem;display:-webkit-box;-webkit-line-clamp:3;-webkit-box-orient:vertical;overflow:hidden}
.pub-meta{display:flex;align-items:center;justify-content:space-between;margin-top:auto;border-top:1px solid rgba(255,255,255,0.07);padding-top:1.25rem}
.pub-date{font-size:12px;font-weight:300;color:rgba(255,255,255,0.3);letter-spacing:0.04em}
.pub-arrow{font-size:18px;color:rgba(255,255,255,0.22);transition:color 0.2s,transform 0.2s}
.pub-card:hover .pub-arrow{color:var(--gold);transform:translateX(5px)}

/* CONTACT */
#contact{background:var(--cream)}
.contact-split{display:grid;grid-template-columns:1fr 1fr;min-height:80vh}
.contact-info{background:var(--cream-dark);padding:7rem 5rem;display:flex;flex-direction:column;justify-content:center}
.contact-info .section-heading{color:var(--navy)}
.contact-intro{
  font-family:var(--serif);font-size:19px;font-weight:300;font-style:italic;
  color:var(--muted);line-height:1.72;margin-bottom:3rem;
}
.contact-details{display:flex;flex-direction:column;gap:2rem}
.contact-item{display:flex;flex-direction:column;gap:5px}
.contact-item-label{font-size:10px;font-weight:500;letter-spacing:0.2em;text-transform:uppercase;color:var(--gold)}
.contact-item-val{font-size:16px;font-weight:300;color:var(--navy);line-height:1.5}
.contact-item-val a{color:var(--navy);text-decoration:none}
.contact-item-val a:hover{color:var(--blue)}
.contact-form-side{background:var(--navy);padding:7rem 5rem;display:flex;flex-direction:column;justify-content:center}
.contact-form-title{
  font-family:var(--serif);font-size:22px;font-weight:300;color:rgba(255,255,255,0.6);
  font-style:italic;margin-bottom:2.5rem;
}
.cform{display:flex;flex-direction:column;gap:2rem}
.cform-row{display:grid;grid-template-columns:1fr 1fr;gap:2rem}
.cfield{display:flex;flex-direction:column;gap:8px}
.clabel{font-size:10px;font-weight:400;letter-spacing:0.18em;text-transform:uppercase;color:rgba(255,255,255,0.38)}
.cinput,.ctextarea,.cselect{
  background:transparent;border:none;border-bottom:1px solid rgba(255,255,255,0.14);
  padding:11px 0;color:#fff;font-family:var(--sans);font-size:16px;font-weight:300;
  outline:none;width:100%;border-radius:0;transition:border-color 0.2s;
}
.cinput::placeholder,.ctextarea::placeholder{color:rgba(255,255,255,0.2)}
.cinput:focus,.ctextarea:focus,.cselect:focus{border-color:var(--gold)}
.ctextarea{resize:none;min-height:110px;line-height:1.65}
.cselect{appearance:none;cursor:pointer}
.cselect option{background:var(--navy-dark)}
.csubmit{
  font-family:var(--sans);font-size:12px;font-weight:500;letter-spacing:0.12em;text-transform:uppercase;
  background:transparent;border:1px solid rgba(255,255,255,0.24);color:#fff;
  padding:16px 36px;cursor:pointer;border-radius:1px;transition:all 0.22s;align-self:flex-start;
}
.csubmit:hover{background:var(--gold);border-color:var(--gold);color:var(--navy-dark)}
.csuccess{display:none;padding:1.25rem;border:1px solid rgba(201,168,76,0.3);background:rgba(201,168,76,0.06);border-radius:1px;font-size:15px;font-weight:300;color:var(--gold);text-align:center}

/* FOOTER */
footer{
  background:var(--navy-dark);padding:2.75rem 4rem;
  display:flex;align-items:center;justify-content:space-between;gap:2rem;flex-wrap:wrap;
  border-top:1px solid rgba(255,255,255,0.05);
}
.footer-brand{font-family:var(--serif);font-size:15px;font-weight:300;color:rgba(255,255,255,0.32)}
.footer-brand strong{color:rgba(255,255,255,0.58);font-weight:400}
.footer-nav{display:flex;gap:2rem;list-style:none}
.footer-nav a{font-size:11px;letter-spacing:0.07em;text-transform:uppercase;color:rgba(255,255,255,0.28);text-decoration:none;transition:color 0.2s}
.footer-nav a:hover{color:rgba(255,255,255,0.65)}
.footer-copy{font-size:12px;font-weight:300;color:rgba(255,255,255,0.18)}

/* REVEAL */
.reveal{opacity:0;transform:translateY(26px);transition:opacity 0.72s ease,transform 0.72s ease}
.reveal.in{opacity:1;transform:none}
.d1{transition-delay:0.1s}.d2{transition-delay:0.2s}.d3{transition-delay:0.32s}.d4{transition-delay:0.44s}

@keyframes fadeUp{to{opacity:1;transform:none}}

/* RESPONSIVE */
@media(max-width:1024px){
  .pub-grid{grid-template-columns:1fr 1fr}
  .pub-card.large{grid-row:span 1}
}
@media(max-width:900px){
  #nav{padding:0 1.5rem}
  .nav-links{display:none}
  .hero-content{padding:0 1.5rem 4rem}
  .about-split,.contact-split{grid-template-columns:1fr}
  .about-photo-side{min-height:320px}
  .about-text-side,.contact-info,.contact-form-side{padding:4rem 2rem}
  .pillars-band{padding:4rem 1.5rem}
  .pillars-grid{grid-template-columns:1fr 1fr}
  .pillar-item{border-bottom:1px solid var(--border);border-right:none!important}
  .pillar-item:nth-child(odd){border-right:1px solid var(--border)!important}
  #staff,#publications{padding:5rem 1.5rem}
  .staff-grid{grid-template-columns:1fr}
  .staff-card{aspect-ratio:4/3}
  .pub-grid{grid-template-columns:1fr}
  .pub-header{flex-direction:column;align-items:flex-start}
  footer{flex-direction:column;align-items:flex-start;padding:2rem 1.5rem}
  .cform-row{grid-template-columns:1fr}
  .staff-header{flex-direction:column;align-items:flex-start}
}
</style>
</head>
<body>

<!-- NAV -->
<nav id="nav" class="solid">
  <a class="nav-brand" href="#home">
    <span class="nav-brand-name">Bright Blue Europe</span>
    <span class="nav-brand-sub">Centre-Right Think Tank</span>
  </a>
  <ul class="nav-links">
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#staff">Our team</a></li>
    <li><a href="#publications">Publications</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a class="nav-btn" href="#contact">Get in touch</a>
</nav>

<!-- HERO -->
<section id="home">
  <div class="hero-img" id="heroImg"></div>
  <div class="hero-overlay"></div>
  <div class="hero-content">
    <div class="hero-eyebrow">Bright Blue Europe</div>
    <h1 class="hero-headline">The home of<br><em>liberal conservatism</em><br>across Europe</h1>
    <p class="hero-sub">An independent centre-right think tank solving public policy challenges across the European continent.</p>
    <div class="hero-actions">
      <a href="#publications" class="btn-gold">Read our research</a>
      <a href="#about" class="btn-ghost">Who we are</a>
    </div>
  </div>
  <div class="hero-scroll-hint">Scroll</div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-split">
    <div class="about-photo-side">
      <div class="about-photo" id="aboutPhoto"></div>
    </div>
    <div class="about-text-side">
      <div class="section-label reveal">About us</div>
      <h2 class="section-heading reveal d1">We champion <em>liberal<br>conservative</em><br>ideas in Europe</h2>
      <p class="about-body reveal d3">Bright Blue Europe was established in 2026 by Lukas Wick and Bartek Staniszewski as an affiliate of Bright Blue UK — Britain's leading centre-right think tank — bringing the same commitment to non-partisan, liberal conservative policy to the European stage.</p>
      <p class="about-body reveal d3">We have affiliates in Brussels, Berlin, Warsaw and Madrid working on challenges common to European governments across social, economic and security policy.</p>
      <a href="#staff" class="about-cta-link reveal d4">Meet our team</a>
    </div>
  </div>

  <div class="pillars-band">
    <div class="pillars-inner">
      <div class="pillars-top">
        <div class="section-label reveal">Our principles</div>
        <h3 class="pillars-headline reveal d1">What we <em>stand for</em></h3>
      </div>
      <div class="pillars-grid">
        <div class="pillar-item reveal d1">
          <div class="pillar-num">01</div>
          <div class="pillar-name">Conservatism</div>
          <p class="pillar-desc">It is easier to destroy than build. Cherished traditions and institutions must be protected against populist vandalism.</p>
        </div>
        <div class="pillar-item reveal d2">
          <div class="pillar-num">02</div>
          <div class="pillar-name">Liberty/div>
          <p class="pillar-desc">People generally know what is best for them better than the state. We champion free trade, competitive markets and enterprise as the surest route to broad-based prosperity.</p>
        </div>
        <div class="pillar-item reveal d3">
          <div class="pillar-num">03</div>
          <div class="pillar-name">Internationalism</div>
          <p class="pillar-desc">Most policy issues require international cooperation to be succesfully addressed. Strong countries are only possible with strong allies.</p>
        </div>
        <div class="pillar-item reveal d4">
          <div class="pillar-num">04</div>
          <div class="pillar-name">Neutrality</div>
          <p class="pillar-desc">The good of Europe, not party politics, guide our work. We retain full editorial control over all of our outputs.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- STAFF -->
<section id="staff">
  <div class="staff-inner">
    <div class="staff-header">
      <div>
        <div class="section-label reveal">Our team</div>
        <h2 class="section-heading reveal d1">The <em>people</em> behind the project</h2>
      </div>
    </div>

    <div class="staff-grid">

      <!-- Lukas Wick -->
      <div class="staff-card reveal">
        <img class="staff-card-img"
          src="https://images.unsplash.com/photo-1673295716958-b1dc96e5b24f?auto=format&fit=crop&w=900&q=80"
          alt="Lukas Wick"
          loading="lazy">
        <div class="staff-overlay"></div>
        <div class="staff-body">
          <div class="staff-role">Co-Founder</div>
          <div class="staff-name">Lukas Wick</div>
          <div class="staff-bio">Before  Bright Blue Europe, Lukas was a Project Manager and Research Associate at the Konrad-Adenauer-Stiftung in London (UK & Ireland office), specializing in German–British and German–Irish relations with a focus on foreign policy, security and the coordination of high-profile international conferences. He also worked at the Konrad-Adenauer-Stiftung in Brussels, advising on EU and NATO security and defence policy and supporting senior-level political engagement and events. Before that, he served as Head of Unit at the Representation of the State of Hesse to the EU, leading policy monitoring and speechwriting for the Hessian Minister for European Affairs, with a focus on Brexit, foreign policy and transatlantic relations. He holds a Master’s in International Security from the Institut Barcelona d’Estudis Internacionals (IBEI).</div>
          <div class="staff-tags">
            <span class="staff-tag">Communications</span>
            <span class="staff-tag">Engagement</span>
            <span class="staff-tag">Security</span>
            <span class="staff-tag">EU</span>
          </div>
          <div class="staff-socials">
            <a href="#" class="staff-social" aria-label="LinkedIn">
              <svg viewBox="0 0 24 24"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
            </a>
            <a href="#" class="staff-social" aria-label="X">
              <svg viewBox="0 0 24 24"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg>
            </a>
            <a href="mailto:lukas@eubrightblue.org" class="staff-social" aria-label="Email">
              <svg viewBox="0 0 24 24"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
            </a>
          </div>
        </div>
      </div>

      <!-- Bartek Staniszewski -->
      <div class="staff-card reveal d2">
        <img class="staff-card-img"
          src="https://images.unsplash.com/photo-1673295716958-b1dc96e5b24f?auto=format&fit=crop&w=900&q=80&sat=-30"
          alt="John Smith"
          loading="lazy">
        <div class="staff-overlay"></div>
        <div class="staff-body">
          <div class="staff-role">Co-Founder/div>
          <div class="staff-name">Bartek Staniszewski</div>
          <div class="staff-bio">Before Bright Blue Europe, Bartek was Bright Blue's Head of Research in London. He graduated with a BA in Philosophy and Theology from the University of Oxford in 2021 and with an MSt in Philosophical Theology in 2022. He has been featured, among others, in the Guardian, the Telegraph, the Critic, City A.M., the Spectator and on the BBC and GB News. He is the author of numerous think-tank reports, including on democratic business, planning policy, young people’s political priorities, affordable housing, social security and race inequality.</div>
          <div class="staff-tags">
            <span class="staff-tag">Social policy</span>
            <span class="staff-tag">Research</span>
            <span class="staff-tag">Poland</span>
            <span class="staff-tag">UK</span>
          </div>
          <div class="staff-socials">
            <a href="#" class="staff-social" aria-label="LinkedIn">
              <svg viewBox="0 0 24 24"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
            </a>
            <a href="#" class="staff-social" aria-label="X">
              <svg viewBox="0 0 24 24"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg>
            </a>
            <a href="mailto:bartek@eubrightblue.org" class="staff-social" aria-label="Email">
              <svg viewBox="0 0 24 24"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
            </a>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- PUBLICATIONS -->
<section id="publications">
  <div class="pub-inner">
    <div class="pub-header">
      <div>
        <div class="section-label reveal">Research &amp; publications</div>
        <h2 class="section-heading reveal d1">Our <em>latest</em> thinking</h2>
      </div>
      <a href="#" class="pub-all-link reveal">View all publications</a>
    </div>

    <div class="pub-filters reveal">
      <button class="pub-filter-btn active" onclick="filterPubs('all',this)">All</button>
      <button class="pub-filter-btn" onclick="filterPubs('social',this)">Social policy</button>
      <button class="pub-filter-btn" onclick="filterPubs('economy',this)">Economy</button>
      <button class="pub-filter-btn" onclick="filterPubs('security',this)">Security</button>
    </div>

    <div class="pub-grid reveal" id="pubGrid">

      <div class="pub-card large" data-tag="economy">
        <div class="pub-cat cat-economy">Economy</div>
        <div class="pub-title">The right road: The future of the European centre-right</div>
        <p class="pub-excerpt">It is time to reboot and reunify the centre-right across Europe to defeat both the populist right and the statist centre-left. This report seeks to better define and shape the centre-right across Europe. It details the philosophy, principles and history of the European centre-right before providing distinctive priorities — the ten Cs — and effective policies so the centre-right can return again to be the engine of peace and prosperity across Europe.</p>
        <div class="pub-meta"><span class="pub-date">June 2025</span><span class="pub-arrow">→</span></div>
      </div>

      <div class="pub-card" data-tag="economy">
        <div class="pub-cat cat-economy">Economy</div>
        <div class="pub-title">Made up title</div>
        <p class="pub-excerpt">Made up description</p>
        <div class="pub-meta"><span class="pub-date">November 2026</span><span class="pub-arrow">→</span></div>
      </div>

      <div class="pub-card" data-tag="social">
        <div class="pub-cat cat-climate">Social policy</div>
        <div class="pub-title">Another made up title</div>
        <p class="pub-excerpt">Another made up description.</p>
        <div class="pub-meta"><span class="pub-date">December 2026</span><span class="pub-arrow">→</span></div>
      </div>

      <div class="pub-card" data-tag="security">
        <div class="pub-cat cat-migration">Security</div>
        <div class="pub-title">Third made up title</div>
        <div class="pub-meta"><span class="pub-date">August 2027</span><span class="pub-arrow">→</span></div>
      </div>

      <div class="pub-card" data-tag="security">
        <div class="pub-cat cat-security">Security</div>
        <div class="pub-title">Fourth made up title</div>
        <div class="pub-meta"><span class="pub-date">October 2027</span><span class="pub-arrow">→</span></div>
      </div>

    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-split">
    <div class="contact-info">
      <div class="section-label reveal">Contact us</div>
      <h2 class="section-heading reveal d1">Work with <em>us</em></h2>
      <p class="contact-intro reveal d2">We welcome enquiries from policymakers, journalists and partner organisations across Europe.</p>
      <div class="contact-details">
        <div class="contact-item reveal d2">
          <span class="contact-item-label">Address</span>
          <span class="contact-item-val">Sokratesa 6/20<br>01-909 Warsaw, Poland</span>
        </div>
        <div class="contact-item reveal d3">
          <span class="contact-item-label">Email</span>
          <span class="contact-item-val"><a href="mailto:bartek@eubrightblue.org">mailto:bartek@eubrightblue.org</a><br><a href="mailto:lukas@eubrightblue.org">mailto:lukas@eubrightblue.org</a></span>
        </div>
        <div class="contact-item reveal d3">
          <span class="contact-item-label">Phone</span>
          <span class="contact-item-val"><a href="tel:+48732434093">+48 732 434 093</a><br><a href="tel:+491758370796">+49 175 8370796</a></span>
        </div>
        <div class="contact-item reveal d4">
          <span class="contact-item-label">Parent organisation</span>
          <span class="contact-item-val"><a href="https://www.brightblue.org.uk" target="_blank">Bright Blue UK ↗</a></span>
        </div>
      </div>
    </div>

    <div class="contact-form-side">
      <div class="contact-form-title">Send us a message</div>
      <form class="cform" onsubmit="sendForm(event)" novalidate>
        <div class="cform-row">
          <div class="cfield">
            <label class="clabel">First name</label>
            <input class="cinput" type="text" placeholder="Anna" required>
          </div>
          <div class="cfield">
            <label class="clabel">Last name</label>
            <input class="cinput" type="text" placeholder="Müller" required>
          </div>
        </div>
        <div class="cfield">
          <label class="clabel">Email address</label>
          <input class="cinput" type="email" placeholder="anna@example.com" required>
        </div>
        <div class="cfield">
          <label class="clabel">Organisation</label>
          <input class="cinput" type="text" placeholder="Your institution or affiliation">
        </div>
        <div class="cfield">
          <label class="clabel">Enquiry type</label>
          <select class="cselect">
            <option value="" disabled selected>Select a topic</option>
            <option>Research collaboration</option>
            <option>Media enquiry</option>
            <option>Events &amp; speaking</option>
            <option>Partnership</option>
            <option>General enquiry</option>
          </select>
        </div>
        <div class="cfield">
          <label class="clabel">Message</label>
          <textarea class="ctextarea" placeholder="Tell us about your enquiry…" required></textarea>
        </div>
        <button type="submit" class="csubmit">Send message</button>
        <div class="csuccess" id="csuccess">Thank you — we'll be in touch shortly.</div>
      </form>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-brand"><strong>Bright Blue Europe</strong> &nbsp;·&nbsp; The home of liberal conservatism across Europe</div>
  <ul class="footer-nav">
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#staff">Team</a></li>
    <li><a href="#publications">Publications</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="https://www.brightblue.org.uk" target="_blank">Bright Blue UK</a></li>
  </ul>
  <div class="footer-copy">&copy; 2026 Bright Blue Europe. All rights reserved.</div>
</footer>

<script>
const nav = document.getElementById('nav');
function updateNav(){
  const y = window.scrollY;
  nav.classList.toggle('solid', y < 80);
  nav.classList.toggle('light', y >= 80);
}
window.addEventListener('scroll', updateNav, {passive:true});
updateNav();

window.addEventListener('load', () => {
  document.getElementById('heroImg').classList.add('loaded');
  setTimeout(() => document.getElementById('aboutPhoto').classList.add('revealed'), 300);
});

const observer = new IntersectionObserver(entries => {
  entries.forEach(e => { if(e.isIntersecting){ e.target.classList.add('in'); observer.unobserve(e.target); }});
}, {threshold: 0.1});
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

function filterPubs(tag, btn){
  document.querySelectorAll('.pub-filter-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  document.querySelectorAll('#pubGrid .pub-card').forEach(c => {
    c.style.display = (tag==='all' || c.dataset.tag===tag) ? 'flex' : 'none';
  });
}

function sendForm(e){
  e.preventDefault();
  const btn = e.target.querySelector('.csubmit');
  btn.textContent = 'Sending…'; btn.disabled = true;
  setTimeout(() => {
    e.target.reset();
    btn.style.display = 'none';
    document.getElementById('csuccess').style.display = 'block';
  }, 900);
}
</script>
</body>
</html>
