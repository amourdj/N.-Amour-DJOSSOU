# N.-Amour-DJOSSOU
PORTFOLIO COMMUNITY MANAGMENT &amp; DIGITAL STRATEGIST
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>N. Amour Djossou — Community Manager</title>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Syne:wght@400;600;700;800&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,600;1,9..40,300&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --black: #090909;
      --white: #f4f1ed;
      --accent: #ff4500;
      --accent2: #ffba08;
      --mid: #131313;
      --card: #181818;
      --gray: #666;
      --gray-light: rgba(244,241,237,0.55);
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--black);
      color: var(--white);
      font-family: 'DM Sans', sans-serif;
      overflow-x: hidden;
      cursor: none;
    }

    /* ── CURSOR ── */
    #cur { position:fixed;width:10px;height:10px;background:var(--accent);border-radius:50%;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);transition:transform .1s; }
    #cur-ring { position:fixed;width:38px;height:38px;border:1.5px solid rgba(255,69,0,.5);border-radius:50%;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);transition:left .35s ease,top .35s ease; }

    /* ── NAV ── */
    nav {
      position: fixed; top:0; left:0; right:0; z-index:100;
      display: flex; justify-content: space-between; align-items: center;
      padding: 1.4rem 5rem;
      background: rgba(9,9,9,.9);
      backdrop-filter: blur(14px);
      border-bottom: 1px solid rgba(255,255,255,.05);
    }
    .nav-logo { font-family:'Bebas Neue',sans-serif; font-size:1.3rem; letter-spacing:.12em; }
    .nav-logo em { color:var(--accent); font-style:normal; }
    nav ul { list-style:none; display:flex; gap:2.5rem; }
    nav a { font-family:'Syne',sans-serif; font-size:.72rem; font-weight:700; letter-spacing:.18em; text-transform:uppercase; color:var(--gray); text-decoration:none; transition:color .2s; }
    nav a:hover { color:var(--accent); }
    .nav-cta {
      font-family:'Syne',sans-serif; font-size:.72rem; font-weight:700; letter-spacing:.12em; text-transform:uppercase;
      background:var(--accent); color:var(--black); padding:.55rem 1.3rem; text-decoration:none;
      transition:background .2s,transform .2s;
    }
    .nav-cta:hover { background:var(--accent2); transform:translateY(-1px); }

    /* ── HERO ── */
    #hero {
      min-height:100vh; display:flex; align-items:center;
      padding: 9rem 5rem 5rem;
      position: relative; overflow:hidden;
    }
    .hero-bg {
      position:absolute; inset:0;
      background:
        radial-gradient(ellipse 55% 65% at 75% 35%, rgba(255,69,0,.13) 0%, transparent 65%),
        radial-gradient(ellipse 35% 40% at 15% 85%, rgba(255,186,8,.06) 0%, transparent 55%);
    }
    .hero-grid {
      position:absolute; inset:0;
      background-image: linear-gradient(rgba(255,255,255,.025) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,.025) 1px, transparent 1px);
      background-size: 70px 70px;
    }
    .hero-noise {
      position:absolute; inset:0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
      opacity:.4;
    }

    .hero-content { position:relative; z-index:2; max-width:860px; }

    .hero-badge {
      display:inline-flex; align-items:center; gap:.6rem;
      font-family:'Syne',sans-serif; font-size:.7rem; font-weight:700; letter-spacing:.22em; text-transform:uppercase;
      color:var(--accent); margin-bottom:1.8rem;
      opacity:0; animation: fadeUp .8s .15s ease forwards;
    }
    .hero-badge::before { content:''; width:28px; height:2px; background:var(--accent); }

    .hero-name {
      font-family:'Bebas Neue',sans-serif;
      font-size: clamp(4.5rem, 11vw, 10rem);
      line-height:.92; letter-spacing:.02em;
      margin-bottom:1.6rem;
      opacity:0; animation: fadeUp .8s .3s ease forwards;
    }
    .hero-name .or { color:var(--accent); }

    .hero-tagline {
      font-size:1.1rem; font-weight:300; color:var(--gray-light);
      max-width:500px; line-height:1.75; margin-bottom:2.8rem;
      opacity:0; animation: fadeUp .8s .5s ease forwards;
    }
    .hero-tagline strong { color:var(--white); font-weight:600; }

    .hero-cta {
      display:flex; gap:1rem; flex-wrap:wrap;
      opacity:0; animation: fadeUp .8s .7s ease forwards;
    }
    .btn {
      display:inline-flex; align-items:center; gap:.5rem;
      padding:.9rem 2rem; font-family:'Syne',sans-serif;
      font-size:.82rem; font-weight:700; letter-spacing:.1em; text-transform:uppercase;
      text-decoration:none; border:none; cursor:none; transition:all .25s;
    }
    .btn-primary { background:var(--accent); color:var(--black); }
    .btn-primary:hover { background:var(--accent2); transform:translateY(-2px); }
    .btn-ghost { background:transparent; color:var(--white); border:1px solid rgba(255,255,255,.18); }
    .btn-ghost:hover { border-color:var(--accent); color:var(--accent); transform:translateY(-2px); }

    .hero-kpis {
      position:absolute; right:5rem; bottom:4rem; z-index:2;
      display:flex; flex-direction:column; gap:1.8rem; text-align:right;
      opacity:0; animation: fadeUp .8s .9s ease forwards;
    }
    .kpi-num { font-family:'Bebas Neue',sans-serif; font-size:2.8rem; line-height:1; color:var(--accent); }
    .kpi-label { font-size:.65rem; font-weight:300; letter-spacing:.12em; text-transform:uppercase; color:var(--gray); }

    /* ── MARQUEE ── */
    .marquee-wrap {
      overflow:hidden; border-top:1px solid rgba(255,255,255,.06);
      border-bottom:1px solid rgba(255,255,255,.06);
      padding:.9rem 0; background:var(--mid);
    }
    .marquee-track { display:flex; gap:2.5rem; animation:marquee 22s linear infinite; white-space:nowrap; }
    .m-item { font-family:'Bebas Neue',sans-serif; font-size:1rem; letter-spacing:.15em; color:var(--gray); flex-shrink:0; }
    .m-item span { color:var(--accent); margin:0 .4rem; }
    @keyframes marquee { 0%{transform:translateX(0)} 100%{transform:translateX(-50%)} }

    /* ── SECTIONS ── */
    section { padding: 7rem 5rem; }

    .s-label {
      font-family:'Syne',sans-serif; font-size:.67rem; font-weight:700;
      letter-spacing:.28em; text-transform:uppercase; color:var(--accent);
      display:flex; align-items:center; gap:.75rem; margin-bottom:.9rem;
    }
    .s-label::after { content:''; flex:1; max-width:36px; height:1px; background:var(--accent); }

    .s-title {
      font-family:'Bebas Neue',sans-serif;
      font-size: clamp(2.6rem, 5vw, 4.5rem);
      line-height:1; margin-bottom:3rem;
    }

    /* ── ABOUT ── */
    #about { background:var(--black); }
    .about-grid { display:grid; grid-template-columns:1fr 1fr; gap:6rem; align-items:start; }

    .about-text p { font-size:1rem; font-weight:300; color:var(--gray-light); line-height:1.85; margin-bottom:1.4rem; }
    .about-text strong { color:var(--white); font-weight:600; }

    .about-card {
      background:var(--card); border:1px solid rgba(255,255,255,.07);
      padding:2.5rem; position:relative;
    }
    .about-card::before { content:''; position:absolute; top:0; left:0; width:50px; height:3px; background:var(--accent); }
    .about-card-title { font-family:'Syne',sans-serif; font-size:.67rem; font-weight:700; letter-spacing:.22em; text-transform:uppercase; color:var(--gray); margin-bottom:1.8rem; }

    .skill { margin-bottom:1.3rem; }
    .skill-head { display:flex; justify-content:space-between; font-family:'Syne',sans-serif; font-size:.82rem; font-weight:600; margin-bottom:.4rem; }
    .skill-head span:last-child { color:var(--accent); }
    .skill-track { height:2px; background:rgba(255,255,255,.08); overflow:hidden; }
    .skill-fill { height:100%; background:linear-gradient(90deg,var(--accent),var(--accent2)); transform:scaleX(0); transform-origin:left; transition:transform 1.2s ease; }
    .skill-fill.run { transform:scaleX(1); }

    /* ── SERVICES ── */
    #services { background:var(--mid); }
    .services-grid { display:grid; grid-template-columns:repeat(3,1fr); gap:1px; background:rgba(255,255,255,.05); }
    .svc {
      background:var(--mid); padding:2.5rem; position:relative; overflow:hidden;
      transition:background .3s;
    }
    .svc:hover { background:var(--card); }
    .svc::after {
      content:''; position:absolute; bottom:0; left:0; right:0; height:2px;
      background:var(--accent); transform:scaleX(0); transform-origin:left; transition:transform .4s;
    }
    .svc:hover::after { transform:scaleX(1); }
    .svc-num { font-family:'Bebas Neue',sans-serif; font-size:3.5rem; color:rgba(255,69,0,.12); line-height:1; margin-bottom:.8rem; transition:color .3s; }
    .svc:hover .svc-num { color:rgba(255,69,0,.25); }
    .svc-icon { font-size:1.7rem; margin-bottom:.8rem; }
    .svc-title { font-family:'Syne',sans-serif; font-size:1rem; font-weight:700; margin-bottom:.65rem; }
    .svc-desc { font-size:.87rem; font-weight:300; color:var(--gray); line-height:1.7; }

    /* ── PROJETS ── */
    #projects { background:var(--black); }
    .projects-grid { display:grid; grid-template-columns:repeat(2,1fr); gap:1.5rem; }
    .proj {
      background:var(--card); border:1px solid rgba(255,255,255,.06);
      padding:2.5rem; position:relative; overflow:hidden;
      transition:transform .3s, border-color .3s;
    }
    .proj:hover { transform:translateY(-5px); border-color:var(--accent); }
    .proj-plat {
      display:inline-flex; align-items:center; gap:.4rem;
      font-family:'Syne',sans-serif; font-size:.67rem; font-weight:700; letter-spacing:.15em; text-transform:uppercase;
      color:var(--accent); background:rgba(255,69,0,.1); padding:.28rem .7rem; margin-bottom:1.2rem;
    }
    .proj-title { font-family:'Syne',sans-serif; font-size:1.05rem; font-weight:700; margin-bottom:.6rem; }
    .proj-desc { font-size:.87rem; font-weight:300; color:var(--gray); line-height:1.72; margin-bottom:1.4rem; }
    .proj-result { font-family:'Syne',sans-serif; font-size:.78rem; font-weight:700; color:var(--accent2); margin-bottom:1.2rem; }
    .tags { display:flex; flex-wrap:wrap; gap:.4rem; }
    .tag {
      font-family:'Syne',sans-serif; font-size:.62rem; font-weight:600; letter-spacing:.1em; text-transform:uppercase;
      color:var(--gray); border:1px solid rgba(255,255,255,.1); padding:.22rem .55rem;
    }

    /* ── TOOLS ── */
    #tools { background:var(--mid); }
    .tools-grid { display:grid; grid-template-columns:repeat(4,1fr); gap:1rem; }
    .tool {
      background:rgba(255,255,255,.03); border:1px solid rgba(255,255,255,.06);
      padding:1.6rem; text-align:center; transition:all .3s;
    }
    .tool:hover { border-color:var(--accent); background:rgba(255,69,0,.05); transform:translateY(-3px); }
    .tool-ico { font-size:1.8rem; margin-bottom:.5rem; }
    .tool-name { font-family:'Syne',sans-serif; font-size:.78rem; font-weight:600; }

    /* ── PROCESS ── */
    #process { background:var(--black); }
    .process-grid { display:grid; grid-template-columns:repeat(4,1fr); gap:2rem; position:relative; }
    .process-grid::before {
      content:''; position:absolute; top:2.4rem; left:12%; right:12%; height:1px;
      background:linear-gradient(90deg, var(--accent), rgba(255,69,0,.15));
    }
    .step {}
    .step-num {
      width:4.8rem; height:4.8rem; background:var(--card); border:1px solid rgba(255,255,255,.09);
      display:flex; align-items:center; justify-content:center;
      font-family:'Bebas Neue',sans-serif; font-size:1.8rem; color:var(--accent);
      margin-bottom:1.5rem; position:relative; z-index:1;
    }
    .step-title { font-family:'Syne',sans-serif; font-size:.93rem; font-weight:700; margin-bottom:.5rem; }
    .step-desc { font-size:.85rem; font-weight:300; color:var(--gray); line-height:1.7; }

    /* ── CONTACT ── */
    #contact { background:var(--mid); }
    .contact-inner { max-width:700px; margin:0 auto; text-align:center; }
    .contact-title { font-family:'Bebas Neue',sans-serif; font-size:clamp(3rem,8vw,6.5rem); line-height:.9; margin-bottom:1.4rem; }
    .contact-title em { color:var(--accent); font-style:normal; }
    .contact-sub { font-size:1rem; font-weight:300; color:var(--gray-light); margin-bottom:3rem; line-height:1.7; }

    .contact-cards { display:grid; grid-template-columns:repeat(2,1fr); gap:1rem; text-align:left; }
    .contact-card {
      display:flex; align-items:center; gap:1rem;
      background:var(--card); border:1px solid rgba(255,255,255,.07);
      padding:1.4rem 1.6rem; text-decoration:none; color:var(--white);
      transition:border-color .25s, transform .25s;
    }
    .contact-card:hover { border-color:var(--accent); transform:translateY(-3px); }
    .contact-card-ico { font-size:1.5rem; flex-shrink:0; }
    .contact-card-label { font-family:'Syne',sans-serif; font-size:.62rem; font-weight:700; letter-spacing:.15em; text-transform:uppercase; color:var(--gray); margin-bottom:.2rem; }
    .contact-card-val { font-size:.88rem; font-weight:400; }

    .contact-note { margin-top:2rem; font-size:.82rem; font-weight:300; color:var(--gray); font-style:italic; }

    /* ── FOOTER ── */
    footer {
      padding:1.8rem 5rem; background:var(--black);
      border-top:1px solid rgba(255,255,255,.06);
      display:flex; justify-content:space-between; align-items:center;
    }
    .f-logo { font-family:'Bebas Neue',sans-serif; font-size:1.1rem; letter-spacing:.1em; }
    .f-logo em { color:var(--accent); font-style:normal; }
    .f-copy { font-size:.73rem; font-weight:300; color:var(--gray); }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity:0; transform:translateY(28px); }
      to   { opacity:1; transform:translateY(0); }
    }
    .reveal { opacity:0; transform:translateY(28px); transition:opacity .75s ease, transform .75s ease; }
    .reveal.on { opacity:1; transform:translateY(0); }

    /* ── RESPONSIVE ── */
    @media(max-width:960px){
      nav { padding:1.2rem 2rem; }
      nav ul { display:none; }
      section { padding:5rem 2rem; }
      #hero { padding:8rem 2rem 4rem; }
      .about-grid { grid-template-columns:1fr; gap:3rem; }
      .services-grid { grid-template-columns:1fr; }
      .projects-grid { grid-template-columns:1fr; }
      .tools-grid { grid-template-columns:repeat(2,1fr); }
      .process-grid { grid-template-columns:1fr 1fr; }
      .process-grid::before { display:none; }
      .contact-cards { grid-template-columns:1fr; }
      .hero-kpis { position:static; margin-top:3rem; flex-direction:row; gap:2.5rem; text-align:left; }
      footer { flex-direction:column; gap:.8rem; text-align:center; padding:1.5rem 2rem; }
    }
  </style>
</head>
<body>

<div id="cur"></div>
<div id="cur-ring"></div>

<!-- NAV -->
<nav>
  <div class="nav-logo">N.<em>A</em>D</div>
  <ul>
    <li><a href="#about">Profil</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#projects">Projets</a></li>
    <li><a href="#process">Méthode</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="mailto:nonhouegnonamourdjossou@gmail.com" class="nav-cta">Me contacter</a>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-noise"></div>
  <div class="hero-content">
    <div class="hero-badge">Community Manager · Présence Digitale · PME &amp; Entreprises</div>
    <h1 class="hero-name">N. AMOUR<br><span class="or">DJOSSOU</span></h1>
    <p class="hero-tagline">
      Je transforme la présence digitale des <strong>entreprises et PME</strong> en levier de croissance réel — stratégie, contenu, communauté et optimisation de profil, tout sous un même toit.
    </p>
    <div class="hero-cta">
      <a href="#services" class="btn btn-primary">Voir mes services →</a>
      <a href="#contact" class="btn btn-ghost">Discutons de votre projet</a>
    </div>
  </div>
  <div class="hero-kpis">
    <div>
      <div class="kpi-num">6+</div>
      <div class="kpi-label">Services proposés</div>
    </div>
    <div>
      <div class="kpi-num">5★</div>
      <div class="kpi-label">Qualité de service</div>
    </div>
    <div>
      <div class="kpi-num">100%</div>
      <div class="kpi-label">Orienté résultats</div>
    </div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-wrap">
  <div class="marquee-track">
    <span class="m-item">Community Management <span>✦</span></span>
    <span class="m-item">Stratégie Digitale <span>✦</span></span>
    <span class="m-item">Optimisation de Profil <span>✦</span></span>
    <span class="m-item">Création de Contenu <span>✦</span></span>
    <span class="m-item">Brand Identity <span>✦</span></span>
    <span class="m-item">Gestion de Communauté <span>✦</span></span>
    <span class="m-item">PME &amp; Entreprises <span>✦</span></span>
    <span class="m-item">Analytics &amp; Reporting <span>✦</span></span>
    <span class="m-item">Community Management <span>✦</span></span>
    <span class="m-item">Stratégie Digitale <span>✦</span></span>
    <span class="m-item">Optimisation de Profil <span>✦</span></span>
    <span class="m-item">Création de Contenu <span>✦</span></span>
    <span class="m-item">Brand Identity <span>✦</span></span>
    <span class="m-item">Gestion de Communauté <span>✦</span></span>
    <span class="m-item">PME &amp; Entreprises <span>✦</span></span>
    <span class="m-item">Analytics &amp; Reporting <span>✦</span></span>
  </div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="about-grid">
    <div class="about-text reveal">
      <div class="s-label">À propos</div>
      <h2 class="s-title">Votre présence digitale, enfin à votre hauteur.</h2>
      <p>
        Je suis <strong>N. Amour Djossou</strong>, community manager spécialisé·e dans la <strong>gestion de présence digitale</strong> et l'<strong>optimisation de profil</strong> pour les entreprises et PME qui veulent exister en ligne — vraiment.
      </p>
      <p>
        Mon approche est stratégique et orientée résultats : je ne publie pas pour publier. Chaque post, chaque profil, chaque interaction est pensé pour <strong>renforcer votre image, engager votre cible et générer des opportunités concrètes</strong>.
      </p>
      <p>
        Disponible pour des <strong>missions freelance</strong> — audit, gestion mensuelle ou accompagnement sur-mesure.
      </p>
      <a href="#contact" class="btn btn-primary" style="margin-top:1.2rem;display:inline-flex;">Démarrer un projet →</a>
    </div>
    <div class="reveal">
      <div class="about-card">
        <div class="about-card-title">Compétences clés</div>
        <div class="skill">
          <div class="skill-head"><span>Stratégie de contenu</span><span>95%</span></div>
          <div class="skill-track"><div class="skill-fill" style="width:95%"></div></div>
        </div>
        <div class="skill">
          <div class="skill-head"><span>Optimisation de profil</span><span>92%</span></div>
          <div class="skill-track"><div class="skill-fill" style="width:92%;transition-delay:.15s"></div></div>
        </div>
        <div class="skill">
          <div class="skill-head"><span>Gestion de communauté</span><span>90%</span></div>
          <div class="skill-track"><div class="skill-fill" style="width:90%;transition-delay:.3s"></div></div>
        </div>
        <div class="skill">
          <div class="skill-head"><span>Copywriting &amp; Storytelling</span><span>88%</span></div>
          <div class="skill-track"><div class="skill-fill" style="width:88%;transition-delay:.45s"></div></div>
        </div>
        <div class="skill">
