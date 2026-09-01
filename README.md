<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Studio Chuba — Funnels, landing pages &amp; websites built to convert</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@600;700;800&family=Manrope:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --cream:#FFF9EF;
    --cream-soft:#FFFDF9;
    --plum:#705575;
    --plum-deep:#4A3B4E;
    --plum-mid:#8B6E8F;
    --plum-tint:#EAE1E9;
    --plum-tint-2:#F3ECF2;
    --ink:#2B2230;
    --ink-soft:#5B4E60;
    --radius-lg:28px;
    --radius-md:18px;
    --radius-sm:10px;
    --maxw:1180px;
  }

  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    background:var(--cream);
    color:var(--ink);
    font-family:'Manrope',sans-serif;
    font-size:18px;
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }
  @media (prefers-reduced-motion: reduce){
    html{scroll-behavior:auto;}
    *{animation-duration:0.001ms !important; transition-duration:0.001ms !important;}
  }

  h1,h2,h3,.display{
    font-family:'Baloo 2',sans-serif;
    font-weight:700;
    color:var(--ink);
    margin:0;
    line-height:1.05;
    letter-spacing:-0.01em;
  }

  a{color:inherit;}
  img,svg{max-width:100%;display:block;}
  .wrap{max-width:var(--maxw); margin:0 auto; padding:0 32px;}
  section{scroll-margin-top:84px;}

  a:focus-visible, button:focus-visible, input:focus-visible, textarea:focus-visible, select:focus-visible{
    outline:3px solid var(--plum-deep);
    outline-offset:2px;
  }

  /* ---------- Buttons ---------- */
  .btn{
    display:inline-flex;
    align-items:center;
    gap:8px;
    padding:14px 26px;
    border-radius:999px;
    font-family:'Manrope',sans-serif;
    font-weight:700;
    font-size:16px;
    text-decoration:none;
    border:2px solid transparent;
    cursor:pointer;
    transition:transform .15s ease, background .15s ease, color .15s ease, border-color .15s ease;
  }
  .btn:hover{transform:translateY(-2px);}
  .btn-primary{background:var(--plum); color:var(--cream);}
  .btn-primary:hover{background:var(--plum-deep);}
  .btn-ghost{background:transparent; color:var(--plum-deep); border-color:var(--plum-deep);}
  .btn-ghost:hover{background:var(--plum-deep); color:var(--cream);}
  .btn-on-dark{background:var(--cream); color:var(--plum-deep);}
  .btn-on-dark:hover{background:var(--plum-tint-2);}
  .btn-ghost-on-dark{background:transparent; color:var(--cream); border-color:rgba(255,249,239,.5);}
  .btn-ghost-on-dark:hover{background:rgba(255,249,239,.12); border-color:var(--cream);}

  /* ---------- Nav ---------- */
  header{
    position:sticky; top:0; z-index:100;
    background:var(--plum);
  }
  .navbar{
    display:flex; align-items:center; justify-content:space-between;
    padding:16px 32px;
    max-width:var(--maxw); margin:0 auto;
  }
  .logo{
    font-family:'Baloo 2',sans-serif;
    font-weight:700;
    font-size:22px;
    color:var(--cream);
    text-decoration:none;
    display:flex;
    flex-direction:column;
    line-height:0.92;
    letter-spacing:-0.01em;
  }
  .logo .dot{color:var(--plum-tint);}

  nav.main-nav{display:flex; align-items:center; gap:4px;}
  .nav-item{position:relative;}
  .nav-link{
    display:inline-block;
    padding:10px 14px;
    color:var(--cream);
    text-decoration:none;
    font-weight:600;
    font-size:15.5px;
    border-radius:999px;
    transition:background .15s ease;
  }
  .nav-link:hover, .nav-item:hover > .nav-link{background:rgba(255,249,239,.14);}

  .dropdown{
    position:absolute; top:calc(100% + 8px); left:0;
    background:var(--cream-soft);
    border-radius:var(--radius-md);
    box-shadow:0 18px 40px rgba(43,34,48,.22);
    padding:10px;
    min-width:220px;
    opacity:0; visibility:hidden; transform:translateY(6px);
    transition:opacity .16s ease, transform .16s ease, visibility .16s ease;
  }
  .nav-item:hover .dropdown, .nav-item:focus-within .dropdown{
    opacity:1; visibility:visible; transform:translateY(0);
  }
  .dropdown a{
    display:block;
    padding:10px 14px;
    border-radius:var(--radius-sm);
    color:var(--ink);
    text-decoration:none;
    font-weight:600;
    font-size:15px;
  }
  .dropdown a:hover{background:var(--plum-tint-2); color:var(--plum-deep);}

  .nav-cta{margin-left:8px;}

  .hamburger{
    display:none;
    background:none; border:none; cursor:pointer;
    width:40px; height:40px;
    padding:0;
    flex-direction:column; justify-content:center; align-items:center; gap:5px;
  }
  .hamburger span{width:22px; height:2.5px; background:var(--cream); border-radius:2px; transition:transform .2s ease, opacity .2s ease;}
  .hamburger.open span:nth-child(1){transform:translateY(7.5px) rotate(45deg);}
  .hamburger.open span:nth-child(2){opacity:0;}
  .hamburger.open span:nth-child(3){transform:translateY(-7.5px) rotate(-45deg);}

  .mobile-panel{display:none;}

  @media (max-width: 940px){
    nav.main-nav, .nav-cta.desktop-only{display:none;}
    .hamburger{display:flex;}
    .mobile-panel{
      display:block;
      max-height:0;
      overflow:hidden;
      background:var(--plum-deep);
      transition:max-height .28s ease;
    }
    .mobile-panel.open{max-height:640px; overflow-y:auto;}
    .mobile-panel .inner{padding:8px 32px 26px;}
    .m-link{
      display:block; color:var(--cream); text-decoration:none;
      font-weight:700; font-size:17px; padding:14px 0;
      border-bottom:1px solid rgba(255,249,239,.14);
    }
    .m-sub{padding-left:14px; display:none;}
    .m-sub.open{display:block;}
    .m-sub a{
      display:block; color:var(--plum-tint); text-decoration:none;
      font-weight:600; font-size:15px; padding:10px 0;
    }
    .m-toggle{display:flex; align-items:center; justify-content:space-between; width:100%; background:none; border:none; cursor:pointer;}
    .m-caret{color:var(--cream); font-size:14px; transition:transform .2s ease;}
    .m-toggle[aria-expanded="true"] .m-caret{transform:rotate(180deg);}
    .m-cta{margin-top:18px;}
  }

  /* ---------- Hero ---------- */
  .hero{
    background:var(--cream);
    padding:88px 0 64px;
    overflow:hidden;
  }
  .hero .wrap{
    display:grid;
    grid-template-columns:1.05fr 0.85fr;
    gap:48px;
    align-items:center;
  }
  .hero h1{font-size:56px;}
  .hero p.lede{
    margin-top:22px;
    max-width:52ch;
    font-size:19px;
    color:var(--ink-soft);
  }
  .hero-ctas{display:flex; gap:14px; flex-wrap:wrap; margin-top:32px;}
  .stat-row{display:flex; gap:34px; margin-top:52px; flex-wrap:wrap;}
  .stat b{
    display:block; font-family:'Baloo 2',sans-serif; font-size:28px; color:var(--plum-deep);
  }
  .stat span{font-size:14.5px; color:var(--ink-soft);}

  .funnel-art{width:100%; height:auto;}

  /* ---------- Section shells ---------- */
  .section{padding:88px 0;}
  .section.tint{background:var(--plum-tint);}
  .section-head{max-width:56ch; margin-bottom:48px;}
  .section-head h2{font-size:38px;}
  .section-head p{margin-top:14px; color:var(--ink-soft); font-size:17.5px;}

  /* ---------- Cards: industries / templates / services ---------- */
  .grid-4{display:grid; grid-template-columns:repeat(4,1fr); gap:22px;}
  .grid-2{display:grid; grid-template-columns:repeat(2,1fr); gap:22px;}
  .grid-3{display:grid; grid-template-columns:repeat(3,1fr); gap:22px;}

  .card{
    background:var(--cream-soft);
    border:1.5px solid var(--plum-tint);
    border-radius:var(--radius-lg);
    padding:30px 26px;
  }
  .section.tint .card{background:var(--cream);}
  .card h3{font-size:22px; margin-bottom:10px;}
  .card p{color:var(--ink-soft); font-size:15.5px; margin:0;}
  .card .tag{
    display:inline-block;
    font-family:'Manrope',sans-serif;
    font-weight:700;
    font-size:13px;
    color:var(--plum-deep);
    background:var(--plum-tint-2);
    padding:5px 12px;
    border-radius:999px;
    margin-bottom:16px;
  }
  .section.tint .card .tag{background:var(--plum-tint);}

  .card-link{
    display:inline-flex; align-items:center; gap:6px;
    margin-top:18px; font-weight:700; font-size:14.5px; color:var(--plum-deep);
    text-decoration:none;
  }

  /* Templates */
  .tpl-card{position:relative; overflow:hidden;}
  .tpl-swatch{
    height:120px;
    border-radius:var(--radius-md);
    margin-bottom:18px;
    background:linear-gradient(135deg, var(--plum) 0%, var(--plum-mid) 100%);
  }
  .tpl-price{font-family:'Baloo 2',sans-serif; color:var(--plum-deep); font-size:20px; margin-top:14px;}

  /* Portfolio */
  .portfolio-card{
    border-radius:var(--radius-lg);
    padding:0;
    overflow:hidden;
    background:var(--cream);
    border:1.5px solid var(--plum-tint);
  }
  .portfolio-thumb{
    height:190px;
    display:flex; align-items:flex-end;
    padding:18px;
  }
  .portfolio-thumb span{
    background:rgba(255,249,239,.9);
    color:var(--plum-deep);
    font-weight:700; font-size:13px;
    padding:5px 12px; border-radius:999px;
  }
  .portfolio-body{padding:20px 22px 26px;}
  .portfolio-body h3{font-size:19px; margin-bottom:6px;}
  .portfolio-body p{color:var(--ink-soft); font-size:14.5px; margin:0;}

  /* Resources */
  .resource-card{
    display:flex; flex-direction:column; height:100%;
  }
  .resource-card .num{
    font-family:'Baloo 2',sans-serif; font-size:15px; color:var(--plum-mid); margin-bottom:14px;
  }

  /* ---------- Contact ---------- */
  .contact{
    background:var(--plum-deep);
    color:var(--cream);
  }
  .contact .section-head h2, .contact .section-head p{color:var(--cream);}
  .contact .section-head p{color:rgba(255,249,239,.8);}
  .contact-grid{
    display:grid;
    grid-template-columns:0.9fr 1.1fr;
    gap:56px;
    align-items:start;
  }
  .contact-info h3{color:var(--cream); font-size:20px; margin-bottom:14px;}
  .contact-info p{color:rgba(255,249,239,.78); font-size:15.5px;}
  .contact-info a{color:var(--cream); font-weight:700; text-decoration:none; border-bottom:2px solid rgba(255,249,239,.4);}
  .info-block{margin-bottom:28px;}

  form{
    background:var(--cream);
    border-radius:var(--radius-lg);
    padding:32px;
  }
  .field{margin-bottom:18px;}
  .field label{
    display:block; font-weight:700; font-size:14.5px; color:var(--ink); margin-bottom:7px;
  }
  .field input, .field select, .field textarea{
    width:100%;
    padding:13px 15px;
    border-radius:var(--radius-sm);
    border:1.5px solid var(--plum-tint);
    background:var(--cream-soft);
    font-family:'Manrope',sans-serif;
    font-size:15.5px;
    color:var(--ink);
  }
  .field textarea{resize:vertical; min-height:100px;}
  .field input:focus, .field select:focus, .field textarea:focus{border-color:var(--plum);}
  #formNote{margin-top:14px; font-size:14.5px; color:var(--plum-deep); display:none;}
  #formNote.show{display:block;}

  /* ---------- Footer ---------- */
  footer{background:var(--plum-deep); border-top:1px solid rgba(255,249,239,.14); padding:44px 0 30px;}
  .footer-top{display:flex; justify-content:space-between; flex-wrap:wrap; gap:30px; margin-bottom:34px;}
  .footer-nav{display:flex; gap:34px; flex-wrap:wrap;}
  .footer-nav a{color:rgba(255,249,239,.8); text-decoration:none; font-size:14.5px; font-weight:600;}
  .footer-nav a:hover{color:var(--cream);}
  .footer-logo{font-family:'Baloo 2',sans-serif; font-weight:700; font-size:22px; color:var(--cream);}
  .footer-bottom{color:rgba(255,249,239,.5); font-size:13.5px; border-top:1px solid rgba(255,249,239,.14); padding-top:22px;}

  /* ---------- Responsive ---------- */
  @media (max-width: 940px){
    .hero .wrap{grid-template-columns:1fr;}
    .hero{padding:56px 0 48px;}
    .hero h1{font-size:40px;}
    .funnel-art{order:-1; max-width:280px; margin:0 auto 8px;}
    .grid-4{grid-template-columns:repeat(2,1fr);}
    .grid-3{grid-template-columns:1fr;}
    .grid-2{grid-template-columns:1fr;}
    .contact-grid{grid-template-columns:1fr;}
    .section{padding:60px 0;}
    .section-head h2{font-size:30px;}
    .wrap{padding:0 22px;}
    .navbar{padding:14px 22px;}
    .stat-row{gap:24px;}
  }
  @media (max-width: 520px){
    .grid-4{grid-template-columns:1fr;}
  }
</style>
</head>
<body>

<header>
  <div class="navbar">
    <a href="#home" class="logo">studio<span class="dot">·</span>chuba</a>

    <nav class="main-nav" aria-label="Primary">
      <div class="nav-item"><a class="nav-link" href="#home">Home</a></div>
      <div class="nav-item">
        <a class="nav-link" href="#what-we-do">What We Do</a>
        <div class="dropdown">
          <a href="#wwd-beauty">Beauty</a>
          <a href="#wwd-realestate">Real Estate</a>
          <a href="#wwd-cars">Cars</a>
          <a href="#wwd-digital">Digital Products</a>
        </div>
      </div>
      <div class="nav-item">
        <a class="nav-link" href="#templates">Templates</a>
        <div class="dropdown">
          <a href="#tpl-beauty">Beauty</a>
          <a href="#tpl-realestate">Real Estate</a>
          <a href="#tpl-cars">Cars</a>
          <a href="#tpl-business">Business</a>
        </div>
      </div>
      <div class="nav-item">
        <a class="nav-link" href="#services">Services</a>
        <div class="dropdown">
          <a href="#svc-custom">Custom Funnels</a>
          <a href="#svc-landing">Landing Pages</a>
          <a href="#svc-website">Website Design</a>
          <a href="#svc-setup">Funnel Setup</a>
        </div>
      </div>
      <div class="nav-item"><a class="nav-link" href="#portfolio">Portfolio</a></div>
      <div class="nav-item"><a class="nav-link" href="#resources">Resources</a></div>
      <div class="nav-item"><a class="nav-link" href="#contact">Contact</a></div>
    </nav>

    <a href="#contact" class="btn btn-on-dark nav-cta desktop-only">Book a call</a>
    <button class="hamburger" id="hamburgerBtn" aria-label="Open menu" aria-expanded="false" aria-controls="mobilePanel">
      <span></span><span></span><span></span>
    </button>
  </div>

  <div class="mobile-panel" id="mobilePanel">
    <div class="inner">
      <a class="m-link" href="#home">Home</a>

      <button class="m-toggle" aria-expanded="false" data-target="m-wwd"><span class="m-link" style="border:none;padding:14px 0 0;">What We Do</span><span class="m-caret">▾</span></button>
      <div class="m-sub" id="m-wwd">
        <a href="#wwd-beauty">Beauty</a>
        <a href="#wwd-realestate">Real Estate</a>
        <a href="#wwd-cars">Cars</a>
        <a href="#wwd-digital">Digital Products</a>
      </div>

      <button class="m-toggle" aria-expanded="false" data-target="m-tpl"><span class="m-link" style="border:none;padding:14px 0 0;">Templates</span><span class="m-caret">▾</span></button>
      <div class="m-sub" id="m-tpl">
        <a href="#tpl-beauty">Beauty</a>
        <a href="#tpl-realestate">Real Estate</a>
        <a href="#tpl-cars">Cars</a>
        <a href="#tpl-business">Business</a>
      </div>

      <button class="m-toggle" aria-expanded="false" data-target="m-svc"><span class="m-link" style="border:none;padding:14px 0 0;">Services</span><span class="m-caret">▾</span></button>
      <div class="m-sub" id="m-svc">
        <a href="#svc-custom">Custom Funnels</a>
        <a href="#svc-landing">Landing Pages</a>
        <a href="#svc-website">Website Design</a>
        <a href="#svc-setup">Funnel Setup</a>
      </div>

      <a class="m-link" href="#portfolio">Portfolio</a>
      <a class="m-link" href="#resources">Resources</a>
      <a class="m-link" href="#contact" style="border-bottom:none;">Contact</a>

      <a href="#contact" class="btn btn-on-dark m-cta" style="width:100%; justify-content:center;">Book a call</a>
    </div>
  </div>
</header>

<main>

  <!-- HERO -->
  <section class="hero" id="home">
    <div class="wrap">
      <div>
        <h1>The page that turns a scroll into a sale.</h1>
        <p class="lede">Studio Chuba designs and builds funnels, landing pages, and websites for beauty brands, real estate agents, car dealers, and digital creators — built to convert, not just look good.</p>
        <div class="hero-ctas">
          <a href="#contact" class="btn btn-primary">Book a funnel audit</a>
          <a href="#templates" class="btn btn-ghost">Browse templates</a>
        </div>
        <div class="stat-row">
          <div class="stat"><b>40+</b><span>funnels launched</span></div>
          <div class="stat"><b>4</b><span>industries served</span></div>
          <div class="stat"><b>2 wks</b><span>average turnaround</span></div>
        </div>
      </div>

      <svg class="funnel-art" viewBox="0 0 420 420" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Illustration of a funnel made of layered rounded shapes">
        <circle cx="210" cy="120" r="150" fill="#EAE1E9"/>
        <circle cx="210" cy="170" r="120" fill="#C6ABC8"/>
        <circle cx="210" cy="220" r="90" fill="#8B6E8F"/>
        <circle cx="210" cy="270" r="60" fill="#705575"/>
        <circle cx="210" cy="320" r="30" fill="#4A3B4E"/>
        <circle cx="210" cy="320" r="9" fill="#FFF9EF"/>
      </svg>
    </div>
  </section>
   
  <!-- TEMPLATES -->
  <section class="section tint" id="templates">
    <div class="wrap">
      <div class="section-head">
        <h2>Templates</h2>
        <p>Not ready for a custom build? Start from a template made for your industry and launch in days, not weeks.</p>
      </div>
      <div class="grid-4">
        <div class="card tpl-card" id="tpl-beauty">
          <div class="tpl-swatch"></div>
          <h3>Beauty</h3>
          <p>Booking-first pages for salons, lash and brow bars, and product launches.</p>
          <a href="#contact" class="card-link">View templates</a>
        </div>
        <div class="card tpl-card" id="tpl-realestate">
          <div class="tpl-swatch"></div>
          <h3>Real Estate</h3>
          <p>Listing and open-house pages built to capture serious buyer leads.</p>
          <a href="#contact" class="card-link">View templates</a>
        </div>
        <div class="card tpl-card" id="tpl-cars">
          <div class="tpl-swatch"></div>
          <h3>Cars</h3>
          <p>Dealership and financing-offer pages built for test-drive bookings.</p>
          <a href="#contact" class="card-link">View templates</a>
        </div>
        <div class="card tpl-card" id="tpl-business">
          <div class="tpl-swatch"></div>
          <h3>Business</h3>
          <p>General service and consulting pages for any growing business.</p>
          <a href="#contact" class="card-link">View templates</a>
        </div>
      </div>
    </div>
  </section>

  <!-- SERVICES -->
  <section class="section" id="services">
    <div class="wrap">
      <div class="section-head">
        <h2>Services</h2>
        <p>Pick what your project needs — one page, a full funnel, or the tools that connect them.</p>
      </div>
      <div class="grid-4">
        <div class="card" id="svc-custom">
          <h3>Custom Funnels</h3>
          <p>A full multi-step funnel, designed and built around one offer, from first click to close.</p>
        </div>
        <div class="card" id="svc-landing">
          <h3>Landing Pages</h3>
          <p>One focused, high-converting page for a single launch, offer, or campaign.</p>
        </div>
        <div class="card" id="svc-website">
          <h3>Website Design</h3>
          <p>A complete site for your brand — built to represent you well beyond the funnel.</p>
        </div>
        <div class="card" id="svc-setup">
          <h3>Funnel Setup</h3>
          <p>The technical wiring — payments, email automation, and tools connected to a funnel you already have.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- PORTFOLIO -->
  <section class="section tint" id="portfolio">
    <div class="wrap">
      <div class="section-head">
        <h2>Portfolio</h2>
        <p>A few of the funnels and sites we've built recently.</p>
      </div>
      <div class="grid-3">
        <div class="portfolio-card">
          <div class="portfolio-thumb" style="background:linear-gradient(135deg,#705575,#8B6E8F);"><span>Beauty</span></div>
          <div class="portfolio-body">
            <h3>Glow Lab Skincare</h3>
            <p>Product-launch funnel that sold out three restocks in a week.</p>
          </div>
        </div>
        <div class="portfolio-card">
          <div class="portfolio-thumb" style="background:linear-gradient(135deg,#4A3B4E,#705575);"><span>Real Estate</span></div>
          <div class="portfolio-body">
            <h3>Harper &amp; Co. Realty</h3>
            <p>Listing funnel built around a single high-traffic open house.</p>
          </div>
        </div>
        <div class="portfolio-card">
          <div class="portfolio-thumb" style="background:linear-gradient(135deg,#8B6E8F,#C6ABC8);"><span>Digital Products</span></div>
          <div class="portfolio-body">
            <h3>The Creator Course</h3>
            <p>Evergreen course funnel with a self-liquidating lead offer.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- RESOURCES -->
  <section class="section" id="resources">
    <div class="wrap">
      <div class="section-head">
        <h2>Resources</h2>
        <p>Notes from what we've learned building funnels across four different industries.</p>
      </div>
      <div class="grid-3">
        <div class="card resource-card">
          <span class="num">Guide</span>
          <h3>The 5-page funnel, broken down</h3>
          <p>What each page needs to do, and why most funnels only need five.</p>
          <a href="#contact" class="card-link">Read the guide</a>
        </div>
        <div class="card resource-card">
          <span class="num">Guide</span>
          <h3>What actually makes a page convert</h3>
          <p>The handful of decisions that move a visitor toward "yes."</p>
          <a href="#contact" class="card-link">Read the guide</a>
        </div>
        <div class="card resource-card">
          <span class="num">Guide</span>
          <h3>Choosing between a template and a custom build</h3>
          <p>How to know which one your offer actually needs right now.</p>
          <a href="#contact" class="card-link">Read the guide</a>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section class="section contact" id="contact">
    <div class="wrap">
      <div class="section-head">
        <h2>Let's build your funnel</h2>
        <p>Tell us about your offer and your industry — we'll get back to you within a day with next steps.</p>
      </div>
      <div class="contact-grid">
        <div class="contact-info">
          <div class="info-block">
            <h3>Email</h3>
            <p><a href="mailto:hello@studiochuba.com">hello@studiochuba.com</a></p>
          </div>
          <div class="info-block">
            <h3>Based in</h3>
            <p>Lagos, Nigeria — working with clients everywhere.</p>
          </div>
          <div class="info-block">
            <h3>Response time</h3>
            <p>We reply to every project inquiry within one business day.</p>
          </div>
        </div>

        <form id="contactForm">
          <div class="field">
            <label for="name">Name</label>
            <input type="text" id="name" name="name" required>
          </div>
          <div class="field">
            <label for="email">Email</label>
            <input type="email" id="email" name="email" required>
          </div>
          <div class="field">
            <label for="project">Project type</label>
            <select id="project" name="project">
              <option>Custom Funnel</option>
              <option>Landing Page</option>
              <option>Website Design</option>
              <option>Funnel Setup</option>
              <option>Template</option>
              <option>Not sure yet</option>
            </select>
          </div>
          <div class="field">
            <label for="message">Tell us about your offer</label>
            <textarea id="message" name="message" required></textarea>
          </div>
          <button type="submit" class="btn btn-primary" style="width:100%; justify-content:center;">Send message</button>
          <p id="formNote">Thanks — your message is in. We'll reply within a business day.</p>
        </form>
      </div>
    </div>
  </section>

</main>

<footer>
  <div class="wrap">
    <div class="footer-top">
      <span class="footer-logo">studio·chuba</span>
      <nav class="footer-nav" aria-label="Footer">
        <a href="#home">Home</a>
        <a href="#what-we-do">What We Do</a>
        <a href="#templates">Templates</a>
        <a href="#services">Services</a>
        <a href="#portfolio">Portfolio</a>
        <a href="#resources">Resources</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>
    <div class="footer-bottom">
      © 2026 Studio Chuba. Funnels, landing pages, and websites for brands that sell.
    </div>
  </div>
</footer>

<script>
  // Mobile menu toggle
  const hamburgerBtn = document.getElementById('hamburgerBtn');
  const mobilePanel = document.getElementById('mobilePanel');
  hamburgerBtn.addEventListener('click', () => {
    const isOpen = mobilePanel.classList.toggle('open');
    hamburgerBtn.classList.toggle('open', isOpen);
    hamburgerBtn.setAttribute('aria-expanded', isOpen);
  });

  // Mobile submenu accordions
  document.querySelectorAll('.m-toggle').forEach(btn => {
    btn.addEventListener('click', () => {
      const target = document.getElementById(btn.dataset.target);
      const isOpen = target.classList.toggle('open');
      btn.setAttribute('aria-expanded', isOpen);
    });
  });

  // Close mobile menu after tapping a link
  document.querySelectorAll('.mobile-panel a').forEach(link => {
    link.addEventListener('click', () => {
      mobilePanel.classList.remove('open');
      hamburgerBtn.classList.remove('open');
      hamburgerBtn.setAttribute('aria-expanded', 'false');
    });
  });

  // Contact form demo submission
  const contactForm = document.getElementById('contactForm');
  const formNote = document.getElementById('formNote');
  contactForm.addEventListener('submit', (e) => {
    e.preventDefault();
    formNote.classList.add('show');
    contactForm.querySelectorAll('input, select, textarea').forEach(el => el.disabled = true);
    contactForm.querySelector('button[type="submit"]').textContent = 'Sent';
  });
</script>

</body>
</html>
