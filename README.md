<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Oesa Tea — Oemah Sarangan | Segar di Setiap Tegukan</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=DM+Sans:wght@300;400;500&family=Cormorant+Garamond:ital,wght@0,300;0,400;1,400&display=swap" rel="stylesheet"/>
<style>
  :root {
    --green-deep: #1a3a2a;
    --green-mid: #2d6a4f;
    --green-light: #52b788;
    --green-pale: #d8f3dc;
    --cream: #f8f4ec;
    --gold: #c9a84c;
    --brown: #7c5c3a;
    --text-dark: #1a1a1a;
    --text-mid: #4a4a4a;
  }
  * { margin:0; padding:0; box-sizing:border-box; }
  html { scroll-behavior:smooth; }
  body { font-family:'DM Sans',sans-serif; background:var(--cream); color:var(--text-dark); overflow-x:hidden; }

  /* NAV */
  nav {
    position:fixed; top:0; left:0; right:0; z-index:100;
    display:flex; align-items:center; justify-content:space-between;
    padding:16px 60px;
    background:rgba(248,244,236,0.95);
    backdrop-filter:blur(14px);
    border-bottom:1px solid rgba(45,106,79,0.1);
    animation:fadeDown .6s ease both;
  }
  @keyframes fadeDown { from{opacity:0;transform:translateY(-20px)} to{opacity:1;transform:translateY(0)} }
  .nav-logo { display:flex; align-items:center; gap:12px; text-decoration:none; }
  .nav-brand-wrap { line-height:1.1; }
  .nav-brand { font-family:'Playfair Display',serif; font-size:20px; color:var(--green-deep); font-weight:700; display:block; }
  .nav-sub { font-size:9px; letter-spacing:2px; text-transform:uppercase; color:var(--brown); }
  .nav-links { display:flex; gap:32px; list-style:none; }
  .nav-links a { text-decoration:none; font-size:12px; font-weight:500; letter-spacing:1px; text-transform:uppercase; color:var(--text-mid); transition:color .3s; }
  .nav-links a:hover { color:var(--green-mid); }
  .btn-primary { background:var(--green-mid); color:#fff; padding:11px 28px; border-radius:4px; font-size:12px; font-weight:500; letter-spacing:.8px; text-transform:uppercase; text-decoration:none; border:none; cursor:pointer; transition:background .3s,transform .2s; display:inline-block; }
  .btn-primary:hover { background:var(--green-deep); transform:translateY(-2px); }
  .btn-outline { background:transparent; color:var(--green-mid); padding:11px 28px; border-radius:4px; font-size:12px; font-weight:500; letter-spacing:.8px; text-transform:uppercase; text-decoration:none; border:1.5px solid var(--green-mid); transition:all .3s; display:inline-block; }
  .btn-outline:hover { background:var(--green-pale); transform:translateY(-2px); }

  /* HERO */
  .hero {
    min-height:100vh; display:grid; grid-template-columns:1fr 1fr;
    align-items:center; padding:120px 60px 80px; position:relative; overflow:hidden;
  }
  .hero-bg {
    position:absolute; inset:0; z-index:0;
    background:
      radial-gradient(ellipse 70% 80% at 85% 50%, #d8f3dc66, transparent),
      radial-gradient(ellipse 50% 60% at 5% 80%, #b7e4c744, transparent),
      url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%232d6a4f' fill-opacity='0.03'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
  }
  .leaf { position:absolute; pointer-events:none; z-index:1; opacity:.1; animation:floatLeaf 9s ease-in-out infinite; font-size:52px; }
  .leaf:nth-child(2){top:12%;right:6%;font-size:72px;animation-delay:-2s;}
  .leaf:nth-child(3){bottom:18%;left:4%;font-size:40px;animation-delay:-5s;}
  .leaf:nth-child(4){top:55%;right:28%;font-size:30px;animation-delay:-3.5s;}
  @keyframes floatLeaf{0%,100%{transform:translateY(0) rotate(0deg)}33%{transform:translateY(-20px) rotate(9deg)}66%{transform:translateY(10px) rotate(-7deg)}}

  .hero-text { position:relative; z-index:2; }
  .hero-badge { display:inline-flex; align-items:center; gap:8px; background:var(--green-pale); color:var(--green-mid); font-size:11px; font-weight:500; letter-spacing:1.5px; text-transform:uppercase; padding:7px 18px; border-radius:20px; margin-bottom:24px; animation:fadeUp .8s .2s ease both; }
  .hero-title { font-family:'Playfair Display',serif; font-size:clamp(48px,6vw,84px); line-height:1.02; color:var(--green-deep); font-weight:900; animation:fadeUp .8s .3s ease both; }
  .hero-title em { color:var(--green-light); font-style:italic; }
  .hero-origin { font-family:'Cormorant Garamond',serif; font-size:17px; color:var(--brown); letter-spacing:1.5px; margin:14px 0 6px; animation:fadeUp .8s .35s ease both; }
  .hero-tagline { font-family:'Cormorant Garamond',serif; font-size:22px; color:var(--gold); letter-spacing:2px; margin-bottom:28px; font-style:italic; animation:fadeUp .8s .4s ease both; }
  .hero-desc { font-size:15px; color:var(--text-mid); line-height:1.85; max-width:440px; margin-bottom:40px; animation:fadeUp .8s .5s ease both; }
  .hero-cta { display:flex; gap:16px; flex-wrap:wrap; animation:fadeUp .8s .6s ease both; }

  .hero-visual { position:relative; z-index:2; display:flex; align-items:center; justify-content:center; }
  .hero-card {
    background:#fff; border-radius:28px; padding:44px 36px;
    box-shadow:0 32px 80px rgba(45,106,79,.12),0 2px 8px rgba(0,0,0,.04);
    text-align:center; animation:fadeUp .8s .4s ease both, floatCard 7s 1.2s ease-in-out infinite;
    max-width:340px; border:1px solid rgba(45,106,79,.08);
  }
  @keyframes floatCard{0%,100%{transform:translateY(0)}50%{transform:translateY(-12px)}}
  .hero-card-title { font-family:'Playfair Display',serif; font-size:26px; color:var(--green-deep); font-weight:700; margin:16px 0 6px; }
  .hero-card-origin { font-size:12px; color:var(--brown); letter-spacing:1.5px; text-transform:uppercase; margin-bottom:10px; }
  .hero-card-sub { font-size:13px; color:var(--text-mid); line-height:1.7; }
  .stats-row { display:flex; justify-content:center; gap:20px; margin-top:24px; padding-top:20px; border-top:1px solid var(--green-pale); }
  .stat-num { font-family:'Playfair Display',serif; font-size:22px; font-weight:700; color:var(--green-mid); }
  .stat-label { font-size:10px; color:var(--text-mid); letter-spacing:.5px; }

  @keyframes fadeUp{from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:translateY(0)}}

  /* SARANGAN BANNER */
  .sarangan-banner {
    background:var(--green-deep); color:#fff;
    padding:28px 60px; display:flex; align-items:center; justify-content:center;
    gap:60px; flex-wrap:wrap;
  }
  .banner-item { display:flex; align-items:center; gap:14px; }
  .banner-icon { font-size:28px; }
  .banner-label { font-size:10px; letter-spacing:2px; text-transform:uppercase; color:var(--green-light); margin-bottom:3px; }
  .banner-value { font-family:'Playfair Display',serif; font-size:17px; color:#fff; }

  /* SECTIONS */
  section { padding:100px 60px; }
  .section-label { font-size:10px; font-weight:500; letter-spacing:2.5px; text-transform:uppercase; color:var(--green-light); margin-bottom:10px; }
  .section-title { font-family:'Playfair Display',serif; font-size:clamp(30px,4vw,50px); color:var(--green-deep); font-weight:700; line-height:1.1; margin-bottom:18px; }
  .section-desc { font-size:15px; color:var(--text-mid); line-height:1.85; }

  /* ABOUT / ORIGIN */
  .about { background:var(--green-deep); color:#fff; display:grid; grid-template-columns:1fr 1fr; gap:80px; align-items:center; position:relative; overflow:hidden; }
  .about::before { content:''; position:absolute; top:-40%; right:-15%; width:600px; height:600px; border-radius:50%; background:radial-gradient(circle, rgba(82,183,136,.07), transparent 70%); }
  .about .section-label { color:var(--green-light); }
  .about .section-title { color:#fff; }
  .about .section-desc { color:rgba(255,255,255,.72); }
  .origin-name {
    display:inline-block; margin-top:20px;
    font-family:'Playfair Display',serif; font-size:15px; font-style:italic;
    color:var(--gold); border:1px solid rgba(201,168,76,.35);
    padding:10px 22px; border-radius:4px; letter-spacing:1px;
  }
  .about-quote { font-family:'Cormorant Garamond',serif; font-size:21px; font-style:italic; color:var(--gold); line-height:1.65; margin-top:32px; padding-left:20px; border-left:3px solid var(--gold); }
  .about-boxes { display:grid; grid-template-columns:1fr 1fr; gap:14px; }
  .about-box { background:rgba(255,255,255,.06); border:1px solid rgba(255,255,255,.1); border-radius:16px; padding:26px 22px; transition:background .3s; }
  .about-box:hover { background:rgba(255,255,255,.1); }
  .about-box-icon { font-size:26px; margin-bottom:10px; }
  .about-box-title { font-family:'Playfair Display',serif; font-size:15px; color:#fff; font-weight:700; margin-bottom:5px; }
  .about-box-text { font-size:12px; color:rgba(255,255,255,.58); line-height:1.65; }

  /* SINGKATAN SECTION */
  .akronim { background:#fff; text-align:center; padding:80px 60px; }
  .akronim-title { font-family:'Playfair Display',serif; font-size:clamp(28px,3.5vw,46px); color:var(--green-deep); margin-bottom:16px; }
  .akronim-sub { font-size:15px; color:var(--text-mid); max-width:520px; margin:0 auto 56px; line-height:1.8; }
  .akronim-grid { display:flex; justify-content:center; gap:0; max-width:700px; margin:0 auto; }
  .akronim-letter {
    flex:1; padding:36px 20px; position:relative;
    border-right:1px solid var(--green-pale);
  }
  .akronim-letter:last-child { border-right:none; }
  .letter-char { font-family:'Playfair Display',serif; font-size:56px; font-weight:900; color:var(--green-light); line-height:1; margin-bottom:10px; }
  .letter-word { font-family:'Playfair Display',serif; font-size:16px; color:var(--green-deep); font-weight:700; margin-bottom:6px; }
  .letter-desc { font-size:12px; color:var(--text-mid); line-height:1.6; }

  /* PRODUCTS */
  .products { background:var(--cream); }
  .products-header { text-align:center; margin-bottom:60px; }
  .products-header .section-desc { margin:0 auto; max-width:520px; }
  .products-grid { display:grid; grid-template-columns:repeat(3,1fr); gap:26px; }
  .product-card { background:#fff; border-radius:20px; overflow:hidden; border:1px solid rgba(45,106,79,.08); transition:transform .3s,box-shadow .3s; cursor:pointer; }
  .product-card:hover { transform:translateY(-8px); box-shadow:0 24px 60px rgba(45,106,79,.14); }
  .product-img { height:190px; display:flex; align-items:center; justify-content:center; font-size:76px; }
  .product-img-1 { background:linear-gradient(135deg,#d8f3dc,#b7e4c7); }
  .product-img-2 { background:linear-gradient(135deg,#e8f4f8,#c9e8f0); }
  .product-img-3 { background:linear-gradient(135deg,#fff3e0,#ffe0b2); }
  .product-body { padding:26px 22px; }
  .product-tag { display:inline-block; font-size:10px; font-weight:500; letter-spacing:1px; text-transform:uppercase; padding:4px 12px; border-radius:20px; background:var(--green-pale); color:var(--green-mid); margin-bottom:10px; }
  .product-name { font-family:'Playfair Display',serif; font-size:20px; color:var(--green-deep); font-weight:700; margin-bottom:7px; }
  .product-desc { font-size:13px; color:var(--text-mid); line-height:1.7; }

  /* VALUES */
  .values { background:var(--green-pale); display:grid; grid-template-columns:1fr 2fr; gap:80px; align-items:start; }
  .values-list { display:grid; grid-template-columns:1fr 1fr; gap:18px; }
  .value-item { padding:26px 22px; background:#fff; border-radius:14px; border-left:4px solid var(--green-light); transition:border-color .3s,transform .3s; }
  .value-item:hover { border-color:var(--green-mid); transform:translateX(4px); }
  .value-icon { font-size:26px; margin-bottom:10px; }
  .value-title { font-family:'Playfair Display',serif; font-size:15px; font-weight:700; color:var(--green-deep); margin-bottom:5px; }
  .value-text { font-size:12px; color:var(--text-mid); line-height:1.65; }

  /* TESTIMONY */
  .testimony { background:#fff; }
  .testimony-header { text-align:center; margin-bottom:52px; }
  .testimony-header .section-desc { margin:0 auto; max-width:500px; }
  .testimony-grid { display:grid; grid-template-columns:repeat(3,1fr); gap:22px; }
  .testi-card { background:var(--cream); border-radius:18px; padding:30px 26px; border:1px solid rgba(45,106,79,.07); }
  .testi-quote { font-size:38px; color:var(--green-light); font-family:Georgia,serif; line-height:1; margin-bottom:14px; }
  .stars { color:var(--gold); font-size:13px; margin-bottom:14px; }
  .testi-text { font-size:13px; color:var(--text-mid); line-height:1.8; font-style:italic; margin-bottom:22px; }
  .testi-author { display:flex; align-items:center; gap:11px; }
  .testi-avatar { width:42px; height:42px; border-radius:50%; background:var(--green-mid); display:flex; align-items:center; justify-content:center; font-family:'Playfair Display',serif; font-size:15px; color:#fff; font-weight:700; flex-shrink:0; }
  .testi-name { font-weight:600; font-size:13px; color:var(--green-deep); }
  .testi-loc { font-size:11px; color:var(--text-mid); }

  /* CONTACT */
  .contact { background:var(--green-deep); color:#fff; display:grid; grid-template-columns:1fr 1fr; gap:80px; align-items:center; }
  .contact .section-title { color:#fff; }
  .contact .section-desc { color:rgba(255,255,255,.7); }
  .contact-info { margin-top:36px; display:flex; flex-direction:column; gap:18px; }
  .contact-item { display:flex; align-items:flex-start; gap:14px; }
  .contact-icon { font-size:18px; margin-top:2px; }
  .contact-label { font-size:10px; letter-spacing:1px; text-transform:uppercase; color:var(--green-light); margin-bottom:3px; }
  .contact-value { font-size:14px; color:rgba(255,255,255,.82); }
  .contact-form { display:flex; flex-direction:column; gap:14px; }
  .form-row { display:grid; grid-template-columns:1fr 1fr; gap:14px; }
  .form-group { display:flex; flex-direction:column; gap:5px; }
  .form-group label { font-size:11px; letter-spacing:.8px; text-transform:uppercase; color:rgba(255,255,255,.55); }
  .form-group input,.form-group textarea { background:rgba(255,255,255,.07); border:1px solid rgba(255,255,255,.14); border-radius:8px; padding:12px 14px; color:#fff; font-family:'DM Sans',sans-serif; font-size:14px; outline:none; transition:border-color .3s; }
  .form-group input:focus,.form-group textarea:focus { border-color:var(--green-light); }
  .form-group textarea { resize:vertical; min-height:90px; }
  .form-group input::placeholder,.form-group textarea::placeholder { color:rgba(255,255,255,.28); }

  /* FOOTER */
  footer { background:#0f2419; color:rgba(255,255,255,.45); text-align:center; padding:28px 60px; font-size:12px; line-height:1.8; }
  footer span { color:var(--green-light); }

  /* REVEAL */
  .reveal { opacity:0; transform:translateY(36px); transition:opacity .8s ease,transform .8s ease; }
  .reveal.visible { opacity:1; transform:translateY(0); }

  @media(max-width:900px){
    nav{padding:14px 20px;} .nav-links{display:none;}
    .hero,.about,.values,.contact{grid-template-columns:1fr;gap:40px;padding:80px 22px 56px;}
    section{padding:64px 22px;}
    .products-grid,.testimony-grid{grid-template-columns:1fr;}
    .values-list,.about-boxes,.akronim-grid{grid-template-columns:1fr;}
    .akronim-grid{flex-direction:column;}
    .form-row{grid-template-columns:1fr;}
    .sarangan-banner{gap:28px;padding:22px;}
  }
</style>
</head>
<body>

<!-- NAVBAR -->
<nav>
  <a class="nav-logo" href="#">
    <img src="data:image/png;base64,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" style="width:46px;height:46px;border-radius:50%;object-fit:cover;border:2px solid var(--gold);" alt="Oesa Tea"/>
    <div class="nav-brand-wrap">
      <span class="nav-brand">Oesa Tea</span>
      <span class="nav-sub">Oemah Sarangan</span>
    </div>
  </a>
  <ul class="nav-links">
    <li><a href="#about">Asal Usul</a></li>
    <li><a href="#akronim">O·E·S·A</a></li>
    <li><a href="#products">Produk</a></li>
    <li><a href="#testimony">Testimoni</a></li>
    <li><a href="#contact">Kontak</a></li>
  </ul>
  <a href="#contact" class="btn-primary">Hubungi Kami</a>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg"></div>
  <div class="leaf">🍃</div>
  <div class="leaf">🌿</div>
  <div class="leaf">🍵</div>
  <div class="leaf">🍃</div>

  <div class="hero-text">
    <div class="hero-badge">🏔️ Terinspirasi dari Telaga Sarangan</div>
    <h1 class="hero-title">Teh<br><em>Oesa</em></h1>
    <p class="hero-origin">Oemah Sarangan · Magetan, Jawa Timur</p>
    <p class="hero-tagline">✦ Segar di Setiap Tegukan ✦</p>
    <p class="hero-desc">Lahir dari keindahan alam pegunungan Sarangan — udara sejuk, tanah subur, dan tradisi yang mengakar. Setiap tegukan Oesa Tea membawa kesegaran khas dataran tinggi Jawa Timur ke dalam cangkir Anda.</p>
    <div class="hero-cta">
      <a href="#products" class="btn-primary">Lihat Produk</a>
      <a href="#about" class="btn-outline">Cerita Kami</a>
    </div>
  </div>

  <div class="hero-visual">
    <div class="hero-card">
      <img src="data:image/png;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/4gHYSUNDX1BST0ZJTEUAAQEAAAHIAAAAAAQwAABtbnRyUkdCIFhZWiAH4AABAAEAAAAAAABhY3NwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAQAA9tYAAQAAAADTLQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAlkZXNjAAAA8AAAACRyWFlaAAABFAAAABRnWFlaAAABKAAAABRiWFlaAAABPAAAABR3dHB0AAABUAAAABRyVFJDAAABZAAAAChnVFJDAAABZAAAAChiVFJDAAABZAAAAChjcHJ0AAABjAAAADxtbHVjAAAAAAAAAAEAAAAMZW5VUwAAAAgAAAAcAHMAUgBHAEJYWVogAAAAAAAAb6IAADj1AAADkFhZWiAAAAAAAABimQAAt4UAABjaWFlaIAAAAAAAACSgAAAPhAAAts9YWVogAAAAAAAA9tYAAQAAAADTLXBhcmEAAAAAAAQAAAACZmYAAPKnAAANWQAAE9AAAApbAAAAAAAAAABtbHVjAAAAAAAAAAEAAAAMZW5VUwAAACAAAAAcAEcAbwBvAGcAbABlACAASQBuAGMALgAgADIAMAAxADb/2wBDAAUDBAQEAwUEBAQFBQUGBwwIBwcHBw8LCwkMEQ8SEhEPERETFhwXExQaFRERGCEYGh0dHx8fExciJCIeJBweHx7/2wBDAQUFBQcGBw4ICA4eFBEUHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh7/wAARCAC4AMIDASIAAhEBAxEB/8QAHQAAAAcBAQEAAAAAAAAAAAAAAAMEBQYHCAIBCf/EAEcQAAEDAwIEAwUGAwQIBQUAAAECAwQABREGIQcSMUETUWEUIjJxgQgVQmKRoSNSsTOCwfAWJCVDRFNyohcmNWPCktHS4fH/xAAZAQADAQEBAAAAAAAAAAAAAAACAwQAAQX/xAAwEQACAQMCBAQFBAMBAAAAAAABAgADESESMQRBUfATImGhMnGBkbEUI8HRBeHxUv/aAAwDAQACEQMRAD8AtcuOrXzrUVZ7UZkqHu70WUq8tq9UfDAFWMbyW0651/CoYAoxBASeYk53xRSVhWTmum1A0uxE7ie8nVTfuk0Y3KlMnbmIrw5r0r2GKIORNpBi2Pd1lQSsbd6d48hDjQIqNrUPDJSkZxRYmKBDLfOt49G2xk9cZPkPU7U1a4UXMUySUOvuIWSEpUjsRQEtB+JKh8t6a4Srh7Ph1xLHMOicKUOnc7Z6jofnVW3jjXBPOjTVin3TB/t3v4DXzycnH0FeZV451b9pr/T+YAW8ugS2s9FfpSebebfCSFSpLMdJ6F5xKAf1NZvu3E7XNyQ40J9htLZHRiOqScepPOn9hTzc3kWfhtCuV91ne27pd2CuG5CUEMJWNxgIQkbgjIVv1AxjNAf8jxPpCCJfJ79pcT+uNNNp5je7aU4/BJSv+lII2t9KT5qIsS9Q3JK1cqWkKJUo+gxk1UmhNL6imacevOrNXaltkZpxLypC57reWEhfMAlRzv7hCiOh270r1NxhsjNnXbtKzZSZAyiO8pYUvbPvLU8lQ5e4zlR9Knq8RWq+Vzfv5TuheRl5NPKT1JI8jRyX2++R9Ky0Nd6yfipbuFzst8bV+GVGUzj5LQG8fPNdR9TmKpL6X9VaaX+F2FOM+GT3Jbc3x9TTqHG16I03uPv/AEZzw1OxmpwUOJIBBzRLSy0otr6Z2NUvpjiVqBtrnkN2/V0FPxSbWfBltjzWwrqfkB86sXSer7Bqpom03FK30f2kV4eG+36FJ3+o2ql+LeqRUpjzDp06EHP5gNTK7yVggjIoUmjK5HClZ5R5GlR6V6nC8QK6arWPMQCLTyhQotlRWpZzsDgU5qoVlXrNDK8NdYoYpk05xQrrFCtNIgFhRwTXDhB2wT61wCEnOM0PE974dq8qWTxpGVEHIzSiMGUOht5zlGOtEqVzK2B2oY5k8xG9cIuLTWjqmKhYy0+lQ/WgICsnLgA+VMcuaxbYbkqU6GmmxlSielM1/v7tgs3+leo0zmmEK/2famchbiuVSgp4jocAnlOyQN8qICYqxqUh8ftAJK85I9RmJarUudcL03bITRy+8pIzy/ypJ6E/InyGagNi1fN1ZqBux6KhLtFpUouyro+nmkPtpI5igKyd/hClZIyNh0qrdWanu+rrszJu/wDrT5V/qVuZTzNx89AE/jWdsqVsP+0XbwB0xNhWeRcJQbfuNyd5QhpYXyIbykIKumQebOPdGMbYqOo7NhjcwDqIvH/iLcpFp0jL+72C9LebLLCSsJSnIwVqUo4SlIycnvgdTWf7NpybfZQZjPXG/wAhJ5THsUVTrTZ/NIWORPzAIrU8bhFbrzcxdtcSHbwUqCo9s5yIUcdvdGC6rzUrrnoBgVZNvhQ7dDbhwIjESM0nlbZZbCEIHkANhTafDEDzGPSljMypaeAur57aFO6dsVsQeqrpPclvJ9eVGEfSrU0nwt1bZLc3BXrC1uMNjDbaLPypaHknDg/erM1LfrRpu0u3S9TmocVsbrWdyfJI6knyG9UVrTiZq2+KKrI/J03BIzGQEI9qeH/MdK0qDaPygcx9OlMZKVMeadcIozJXetCS7qwnTEzVUuM+HPFM1uM1l8bkIKSOUAZGO/uDcnOVsnh7BtdhUzIZtr8ZKAh1tyOCXzsOYnABJ3JGKqVjWN7gzI6n7rNvch5sF1c13ZR3xyJAAQD6eYzXErjs+3coZmafdk27nCl/68VKUn8XKCkAKHcZ/Sp1CuSFH8Sc1UAtDLtwK1ClTk202PT8+G6S4ylmS7DkhB3A2ygnG2ehquL/AKQudgkE3GPetOODY/ecYuxVHyElnb9RW0NC6u0/rGyN3PT01t9jAC2xstk/yqT1SafXW23mlNOtpcbWMKSoZBHkRVJ4dbSoICL7z55T4z9uU3NnxC0lZyzcYbuWlH8ryNs+ihn5VLtGWPUOq5jT6oap0YKCU3nxPZpMcjuFpyHcenN23FaM1fwP01cFSJumHF6Znvg+ImKkKiPnycYPuEfLFURq6BrnQ0RvTj8tWnmkrUqO7F2t8kqJJAcA52VE5PLnlz2GanqUnXPvAKFdpcWj4l/tsBUS/wB6avPKcMu+zeE4E/mVzEKP0FPjbykHAyU+RNZVOstbw7h4a77c4lwZP9nId8RtYPTKVZSQey0gfTrU3sXGC9yorbxtTEpxgn22IAUPKSDhS2TnCgMHKSMjzrHiK1w2rPX+4gUybiX80tDiOYfUeVEwjnmHfrTZpi82zUdlYvNilB9hxO4/Ek90qHYjypdEJS+PXY16b8RUFal4gz7G9ou0XYoctdUK9mDOeWhXVCtNISBncV3yLcSEtpyc9q8yQcdKWNAx4RcQffcOAfIV49RyoxuZWcRK7EktJ8VSfng5olZcOSBgJBUo9gAMkn0A3p8sUJ+5LMWOS464Dzc2eVA8yaL165ZdPWCQiU+2LZFb8W6PK/4kj4Wh+Xmx7v4jypOdwU/qCgOv/swJtcxg0/blXaW3fLi2Qw0c2+Orpjs+ofzH8I/CN+p92AfaC1AuXOZ0Va2Q9NeYKnlHZLSVEbqPYBKST/1Jqx9Qak+4dHpvVxjKEtxCQ1DQMqW+v4WR5nOxPkCcCq74P8Pp3EK+3CZeJK3beZHNe5qdlTHRgiI0fwtJ/ER12Febdqz3O85TBZrxNwV4Ty9VLcmRZbsey55JV2A5HZyvxNx8j3Gx0K+prSfDizW61RnY9ujJjxomGI7YOQhI/qem/epRb4cW3wWYMGO3HjMIDbTTaeVKEjYACmbU2o9M6Ktpl3eaxAadWShHVbyz2SkbqPoKtFIKQY/RYg9JIKrniRxXtGmpLlltCUXnUAHvRWl/w4o/mfX0QPT4j2FVhxE4uX+/Nqg2kSNP29zIAbUPb30/Poyn13Pyqshdo9siYQ03GaKisNtq5itXdSlHdSvzHNcetyTJiavEhcCSrUd4m3K8ovWpbgm43FA5o7ajyRonclCPwgDqpWVH0qNXfUEqX4TSFE+3OYZJGFvDu4R2QADgeQ+tRiXPMh9yXOBWyDzBjJw53AJ8vOjLK6/IU7f7goF+WfAip6cqM4JA7A9B6A1OaR+J8yI1S0krai+86tOeYNksjPdABx+gqOanQGS3ObbSuFPOVozjw3sZ5kntkb+XWnJD5YRHXzcq1Or5T6gnH9KSQVMT7E/a5OcMrUwvzTg5bWPkDj6Vk8pvAJviMmlNRXjS19F10/cXoUxk++E9HE+S09Fp9P0rVPCHj7YtUqYtGpfCsl6XhLalKxGkn8ij8J/Kr6E1kN1CkTVQ5JDcpk8qHOzg9fQ0a7HUWiS3zp/EgjOP8+dX3mpV3pHG0+kAIO4pu1BZ4N6t7kK4RWJTDieVbTyApKh65BrH3C3jdqjR7bVvuDjl8sqMBLLzmH2B+Rz8Q9FegBFal4ecQ9K65hB2x3FCpCU5diO+6+180n+o2rT06dZKotM9caeEDmm4Sp8FmVO020SpYSSuTasn4kHA52fNJyR+9UvNeuNuYYtyXUCSiT7XAns/C4hQJJSfU4BB77Gvow6026kpcbStKhghQyCPKss/aB4VRdM815tSHGNPPv8AiLU1nmtD5OziMf7pR6jt2qWtSA8wH0hFLSBcPtY3LTdydvKILjC9l3q2hJSl1s/8S0PMd8bf4aVt86Hc7dGvNreQ/GkNhxC09FJIrI1l+/JWrYNsuV7ZiSosgI8WS2nw+VXUlQxzIUnfc71onhhp65aRlS4SJ8aXp6SfGjNgq54yz1CRuCg9eu3rnNFw1YW8KobDcHoZPV0nI3lgtqC0BQOxrqk0dSW3+QKBbXuk+VKsV7nD1vES53G8nnlCvcUKfeaQsox1pytMdye4i3oaU4tZynHbzz6U3lSlEAVPdPIi6btQkTQVTpQCvDA95Kew9PM//qvGradPmltgd4mkW6dZLGtJdZjoWrl5Gzlx5Z6BR8gMnbtnaqB4iXw6p4pWXRcZf+y4E1l+4Ebh50HIb+QH7kn8NW3xb1qmBpiTdnmwymK0oto588yz08v8/OstcPb1KtmtrTcn4pmS5EtbrqCvlypxCuZRO+yEKz/eNeW7BmJHKLYA7S1NaC46z4lwtMWhavFQpUdhQ+FjYe0ST6pB8NPqFY61oJh/RvDLSES3yLjCtNuhtciPGcAUsjqcdVKJ32GSTWQoer7k/qW8aktN3lW0T1qYbTGSgLLAUTstQJTkknYZpE7eOeauQAt+afjkuLVIf+ZcWTy/TFPoDQu2TOHiUp+UTQGteN0yU25F0dB9jaUMJulyaIUr1aj7KV6FfKPQ1T1xuzDtwful0ukiXcCMPT5S/Ed/6EDZKOvwpG3fNRG53CctKgJHgBXxK5srV8z2+lNtvhTZ6k+zhTyG8gOrGGkeeOxNGUZhdzYSZ+IZzaPlwviD7kdhzkcVhKN1PPntnvj02+lJng3HHtd2eQqQR7jKTlLQHYY+I/sO2etcIYYge8lwvyV7FfUn0SP8aU26zuSJQlz2cNJOUNOH4z5q9P8A+VyyqIm5MTw7dIupRKloVGt3xIbJwt8f4J9f0z1C+KozLh7cEpTChtkMoSMBSscqcDyAzj5Um1Xd+RtxlgmS6f7U5wCO6R/SjoMq4u2hl5q3NvsLa8RKYrwUoAj+Q4Jx0wM0DkgAmGqk7RBIvES4QEKjOEFCslKhhSfPb5c29J4s4M3Vb5yGn0gPJ9R0P+fWhiFcdER1ICUToTDq23MYV/DVlbavMFJyPIj1pvtcS53NBeixgWQceO6oIRn0J3O/lnrR02TSdWLYmek1xbN453SA1dWwULHtLKcpUP8AeN9j8x/WkMV96I57LOB2Huuenb5ikqHJcee80t9AXGcKEFvOM494f58qfI0yNdGPZZzZStO6XUjJHrTQLL1ESd7c40zWiZCnG1BKzgqT+FX07fMfvXEGXIhzWpUN9+FNaOW3WXChxJHdKh/n0pxuFolQ2EOOo9ohqHuPtHIH17fI01voSlJJcSpHXKtsfOmLYjEHIMvzhl9o28W7wrfraKq7RQQkT46QmQ2PNaB7rg9U4Pzq/wCwaw0Nry1PxrdeLfco77SkPxVq5V8pGCFtqwofUVgi2svz3lNQi04EJ5nHVKyhsepG5PkKfoths6QZlwmyJSmN1JQA0kK7JGMqOfn0pVSsqYMvo8RUt5siLuJdngWjUtwtFluke7N2dPiRn2HgtS4ZO7SiNudo/tR/DbWl10/eGWGZvPbrh/DDLpJaakdUqA/Cled8Y+LviohedRKi3WG8A0TFXlLLaeVCWyMKRj1GxoTojTUt+3MrV7O+2l6EvPVKvebPzBJT81elSML4OAe/9xocMNVtprHRGomdT2IXRhhyM406Y8phZyqO8nqgnv5g9x9QJe04FR/FI7ZP0qg/s36mDWu4zcsAwtTxzGlpOMJmsjZXpzD+tXvNZXBclwl9UHKT5g4/wxVXB1fABa+CD9xOVKdsjaEh6URkYwfShShlSPBRkJ+EUKpWmxAPin7xcj+n0IXcBIdSFMxx4ikn8Z/Cn6nr6A0/NR5d0dfmPKPhoBW66obDHYevpSTS9vMkRY5BT7UsuKP5E5H67L/WpbqtTcCxIhR08iXFBIA8huf8Kjr+cknYfmUEXuTsJmL7Tsp0ps1n8bDMxZWpOOiUHKyT65R+lVEw+uPAu92OEuFtNviZ6Jcf3WQexS2CPqKs77Syw5qq0tZGWoDh6/8AMcCf/jVUXJUd+zWeA654IlOSJqsfzKVyIz6e4fpUqKLAde/wIAewLdB3+Z1GlQUeHFaWZCwAlKArlR9SP8SKcmmLhIIbVIgwmwfdBdBHzAbBGfmRTPCi3OAVAW+PJaAJUG1oUFjzCc836UZEuMB55KSmOlsjZHh8rgPlzJUnPzIqwvfaQBese3bRCgQ1XCTfWH+X8DltWsA9gB4oSr65qb2ThvfZ2mHdUcQ9QL0vptlAcS22gCQ6g45TyZIbztgbnPbvSLgZp636r4pwmXUSVW+1smc6xIcDiVLBAQB6ZOd/KrB+2NdHFW/TenGggolyXJTiVOcgUGkgBO+25X38qSahLAXl1GgopGqw2lUJPC9uT4jenNbvQc/+om6tJkFP8wa5cfvUruPC2VN02zq7h5qOTq2zEFXsE1ZRIAGxAUMAqH8pSPrVaNuNqUtrxFR5CPiaeTt+o7eu4q5Psd3p1m9aj025zJYcSieygnZKs8i8fPKf0o3uq6hyg8OVrPocbyqI9xtlwR4T0CPDUCUEeGrmQe4JyMH6GiH1qtLBjRH0TYajzob8TkdYX5oUNsd8VPvtLWW36V4lpu6IjZhXqKp5bYJSA+g4URjuQQfmab43DBUHR69aa/ukmwWxQCo9uioC5TnN8CSVbBR8v1xW/bdQTsYAo1UqlV5SsZ1xU7MfcU4tlEhaW5XMnl3UCC5gZ6pznHen5m/pQ34kRsvvIHJFYR/Yx09BkkbkDyJzUx05wr0zxDsc6Xoq93SPdICkh6Bd0pUDkEp95PQHfffodqhtgsV8vuqGtJW6GGLv4qmn23dkxuT41K9B+9bw6T4PKEfFS1s3hEJVsRHDU6G646SVLdZeKVqUTkk5ynr8qEpuEyA9HnJKRv8AxCELT6eR+h+lSzVumuHuktQL05fbtqq53CMhBmPwkNIaaKkhQ5Uq3OxHekuudJwNF/c13sV9bvVtvbTjzD70ZPitpQAep77+QximeKALiIbhmySRiMcL71aaElqS3b4rieYOSVK/iDzDYBJHqQBS5pqzxJCZs9Ue5yijmbZSwWmG/wAykknJ+eAPLNSmx8On7loJ/iPrS9TLdZwz4zUeK0FyXW84SSVbDO2B5EHIo/R3CzSvEvT02ZpDUN5h3CGvkXGuYS4nJGUklPY+Y6eVIZy25sPSOXhmxYZlfzbv/Gda8VCG3nErfLSQ3hOOgx022HlnNN+Hbyt9yG4m2wWSAVoTypz2AA3Wo77k/Oh9ytW67T4Oo2pAuUOUtl6OhQCeZPbPUg+naj+d+alECJCcZYZSV+CwFL79TjOBud8+lY2XaKt1iaLFRbYsp4SBKfewlLyW1AoTjJGVDAUc74zXcd0P6birK8PW+SYaznfwncqbJP5VpV+1dB2TKQLfFhOqKUkoSB7qQTuoknYZJ3oq1REFV8tXtrb7jluW6AgHAcZUlzA/upV086Fsi53jaJ81usd7DdpEByW9FBS9EeYvEYJ25VIUA4P0JH0rat/faudvtd8jkKZmxUrCh3yAof1/asZaPsV2uzjV1i25963hDsaS8hOQ34rfNv3wCvfy71qDg/Leu/ATTshasrghcVzJ3HIstj+g/Wubqy/I9/aUb0+++cduZXmaFJ1SmEqKVLwQcHY0KX4VXoYixlh6agRW7XAkhoeN7Mn3/RQ5j+5NRnivd27aIi3cFAdZaOVYALzyGgfpnNSm3ymoel4cl44QiI2fn7owKo77SNwkSuHN0nlXhKD8Xl5T8GH0EY/SrK5Hw9ZVVI06RKn+0ygL1cmQOZD8W2tKbJ+FaPEd5v0JH1xVfLRIaucJphuM82m2R0uNPFGFhQ5yMK67ntVp/aLu2mbvp+K7GmRnryyHEFlCuZxpH4+YAEpwpIxnGc9+9T3mTHZv7XjxmZDCoMXmCxuB4Q+E9R8xUtO7Ad9IhhpQ99Z0xHmtuNptjwKmuqX3ktvNrHYZ60W/qFUjxYt7jJURlLrTiANx1IOMhXfP61wH7QZ7Spji5DT45UurWQ41y9ipJAPXrg0bcikMJalSZE5mYSGi2lCEHlPKMrOfewkdu9NABIBEm5Ylp/ZMlWy38RLnCiTVPiXbQtsuABXMlYJT67HNO/2wFMpvGlJctsLiluUyslOQCfDI+X032qpNKQr3YrvD1Bp23lmXDc8RPPIK/FT3QdgMEZFXjqyVZON3D9Vvs8hEXUMJYki3yvddadSCFIUDuUEEjmG3TODtQ1qbU6gc7bS3h6qVqDUlOZnNMiAmWk+PDkII5QJieblHUAEDoc9diKt77JCfE4i3qYwFiOxbvC5VK5vDJcT7ue/Q49KrlejtWMTDb3NFXATgrlDbdp50k+YXukp9c4q9OHsG38G9EuO391p7UV3cDpt0TCnXFdG2W0J+LGTlQ2yTucDJVjZCBkmBwdM+JqbAEHHdy33njNw5sMoNvJTL8Z9pW4UhS04SfQ8hH1p9+06dPSNHW8akuFzhRBPSpC4MdLqivlVgEEjA61RMl7UGo9fr1GiWDqpmX7RFtgjrJSpg8wYSrGCQBuAav6U7pvjFw7fhofLKlgF1oj+PAkDoFJO+xyPUZpNRGo6CdhK6VRa/iAbna8q7hNrTh7w+uU+fFnapuKpzKG1pet6UgcpyDsrfqaQ2riTYrf8AaBla2ZiyI9luLYjvqda5VoJQkFfKD0ykZ9M0UrgXq63lx246kskK0Me8/OU+5lDY6nlKQkH0KgPWveH2h7JeOIMu2uQpDdiulqe+5n7gQXXSkpT46AdwSrmUBjpTgKbXYG+JOprLpQi1jLo1roHQ3E9hF6bfSmaUAN3O3OjmIxsFjcKHz3xtkVnviZo3UehXINuv09dxsDZdTbX2xhtBXupKh1So9cZI8u9cQNPcR9Eal9ks9uv8e5tvcifZIq1x5SQfiyPdKSOuRt3q0PtP31hzRUHTbqGpN7eU3KfjM+8WEISStR8hkkDPUUtVem4UG4PtGVNFamzMulh7yJ6URxW1hwu/0ZRKt9v0c03y/eVwR4alMJOeUHclAx1Ce2M1Y32X4WmrOrUEWw6hevjyVM+0yBG8FjOFYDe5Ku+T06Yp61VbmtdcGl27SsphtidCb9jWDhvCCk+GcdPhKSOx61HPs8aee0fLvNqvcyC3e5KWnjb2Hg4tplOQFKI23J6eWPOlNV1U25ekelLRUTnjeVfxoajO8btVKfWhpvmYUokgEkst7DII3+R+RqHRlM+FK9rlyGYaHEhtDJSFOKx1UopxgD079ql32m9M3qLxDm6icS21a7k6yiM74qSpagylKvcB59uU747jzqEQUzUwW3GY7F0aaSsNIaJUPEJHvLQoA7DPbyqgC6Bgd7Tza4IqsCJ0mGVxXJAuhjxpBBaVIBW84B0wB23O/fypxscIQ9VWhpFtcZYdDkdb7oIW6pxpSTkE7DJ2GKa1T3GHxPukF2NKYSBFbdbKE5AO427DGKGm5zkrXNm8UnImNqKirJ3UM1nVip+RnKJAqL8xJPwf1rK0jJYcecU9DlyG4rsZKtuXOCsA/iGR9MDvWudLrtsPT863QmWWY8tSpSPDGElZwVbdBnGfmT3NYhgfdf3a2XgszVTE+ycoP/MGSTjGPr9O9aa4KXCVPsF3akK5kwbzIjNHyThC8fqtVKZiGJEeV0rcSwUwoK0hS28qIyenWhRYWoDGaFdHEuOcDXHOfcTKsdqhtZISwnnA7qHugfsf1qA8fbW8OEGqmFpHjRmGHyB2w82o/oKnuhYqX7gxz+8llBdAPnnb9zmhxBtJvcHVdlSAV3GzPNNA91lsBP7inW1Pr9bRltXmmH9WyP8AzFe2GASucttwL7BCmwr9yaInMC4TbepENElbltYKQtSgkcoKDkJ3O6fMVa1h0/oeLpGx6k1WzNffvDLUQOMqIbjltOOZWCN/cOevTYbGm+4aLGmdd2C1K5psV8vxojpIClJVlxrOCAVZ5k9gcZ2zQUCoZQfl7f6gViWDae8yKWrTN2kyW47L0SPznYRYqE4/vFJV+9WZp3hhasBV3kPXVexSmQ45yJPoAoCrM0np8REpSy28w70UtcSPk/MlRNWhZLCENIeedw51BDTW/wCia9EhF2ETS4dmyxlZaY4ZQpiUckOKhhJ7hf8A+VDUek+Bq78qyalkWyNeIoT8ch2M6kKAIIVz4Iq7m0JQkBIA+QAzVHfak0spbULWsO3+0mK2qJcghvnUI595LhHcIVnO3RR8qCo7BSRmVigiC4EdI3BDTcppDsLXWt3LcrdLDN/Upgp8hgdPrUUj2iLa9XXzSfDXTNptVwiOtxpeobjN8aUnxG0rJaSvKicK7EDIqueFGv52jtYW0eMlq2zJKGZLDSx7O+2tQSHUoBIQtJKT6jNXdxgs9ohcS9C3qLbYrNxmXZSZMpDYDjqQwrAUrqcYHXypK1A1MsBaELGM+oNM3HSF00I5piHHuDNjVLcfblz0R1PuOoCSsqV1USok4pBqO68NtUWleodU6ZdgaoNwdt0dqzSyZsh1sgEpW3gLG/xKyBTxxFhQL5xe4dW26RGJsJ1yd4jDyQpCsMgjIPXcA0m4O2SySNWas1ZGtcSJ4FzetltYabCUMNM+6opHYrVuTSqdXTR1NGtTvU0iRm2aRfZvkczdDx7zM/tY8DUOr/HkgdR/BI5SfQ5q0IcjRPEsL03rDSKIV3gNcyrfPaCXG0dOdlxOMo9UkdqpR62316DPDlm08vUsm8C5M39epoocj8rgKUBOSoJCAU8ue9Tn7Q12iXa2WWXpu92wahROTDbejyErUG3wW1pPKclO4P0p+sCw6xQGCZG71aNLPT5cXQEHWc+3QVKblPp1G5EtiCOo51klWO+Nqe9F3SPoe3ruCuFFvVZ3CVSbpabim5OY7qWVe8oDvg7VB9U66QeHbPCFvR15VqCEtiPNZhNodaUGnEqWpJQolRUE9CB8W5q2eC0SRGf1K8qyosVvmzEPxbWp5tTsdJbAPOhBIb5sZ5TSmqsgLWhIgdrCGucH9C6uYb1Jpa6z7NFuSQ+TZ5K2WngfNAOAfMADvTFqvgtw5sUVLky8Q7I8DzInKmuNSifPmUs5P0pVo3VP+g3C3iFKZSnwbJqGZHtzKvgb5ygoR6JC3CfqaodN3umobkmaEu3W7yl8kdxYDkia8TgBI6ttjyGAAP1N6oUAgXvFsqcxmWXauEWl79bn9QWa+ztSpadLCpbshbiuYAZAKkjIGR0qH6t4Tqb5lQrYVkHcKGT+prWHDDTCNIaEtdg5kreYZ5pLg/3j6jzOK+qifpSy9WJmaha21hpzG2Gm1D/uSapVyBE1OCVxfnMB3DTd506yuOtlLTDquYtvxkOIJ+o/xpNp0IRqy3OPwITPheK+pxhCkZDbSldMkdh0Fay1nphchtcWSXZOc8uIkYgHz+IGs0a2tbumb3em1sFK2LYWk82AoLfWEDYE4PJzHrSuICGkxAyf5k9GnUp1lBPlH8SK6bSt9+2291J/izGXWlDpurcfPG9a4+zRAYc4YaiuL7QUJd5lyGyfypCQf1Saqx/S1ju2kLRrXTkVuKu0tL9sjNjZam0FJOP5gUg+oPerz4KW1dm+z5aW3Rhx+MZC8jfLyyr/AOQqSmQzMfSXU8pn1nvMnzoUOUeQ/ShUuJND9MXRNuucVfN/DUPCe9Acb/Q4NSPVbi4V8hz29xyYxn4sE5H1BqAEHtUpiXRc6xNJcVzS7e4lQJ/E30z9DgGr3W1Ow+cpIstpmbiLPuWnoOo9Gxo7T1vau6JEdDjJUpER5fOkN/JRKTsepAp24oSHYMDSNrcX/tyFbkThzDmJdj+GQNxuSPH29KtfjtOOkU2a+QLdDet0172dx55BJirUAW1j8uQMjzA3rKeo71fZ9+cu9zf8S7xJJ5tsJCkfhA7JUgdO/L61MysGzvv39YJGlgxHf/JvvR/3JcrDAvdrjx1MTWEPtuBpIOFDONh1FPtUT9k7V0WVaJGkfGHKwPbbaCdzHcOVI+aF5H1FXtXoI2pQZSIK8UlK0lKkhSSMEEZBr2hRTsrLWXA7QGoUPPM2lNqnqUHEPw1qbSHAchRbB5Dv12pNx0Ba1Fw/fVshF5KCo9OZTKwB9TVrUxa70tbtYaeds9xU60CpLjL7KuVxh1JylxB7EGgZbqR1nLAZEp/iDdIun+IOh9U3XxkWy3vzEyHW2lLKCtnCBgb7nYU08B9VwZlw1ZYPDkRX03mRPYjymy06WHlcwyk7gjv/ANQqXK4e8WEr9jRr6xLi9BNcs5MkDz5OfwyfnTn/AOCGmUWNhqPOuLGoGXVSRf0uD2tb6viUvspJ6chGMbetSLw7+D4Zhl/3dayu9M23SWiLlc7VrTQLdztz8tyTbrszahKw2s58JzAKgUnIBPWovxX1ZAssP710rw/smnYbyvZocmbb0sz1uEbvtI6oCBjc9yKttehOLravAb1vpqQ109oetC0u48+RK+TNPeneElpa9tm6unv6qu86OqM/KlIDaG2iN0Mtp2bHy39afT8W1mtFOoPwyA6rgnSHB6QzpJtxh1YYMqZGRzSFoUtIee5hkqVylRz27YxXfBS32m3zNUTtNolCxSpbXsT0jn5n+VsBa/f945VnfzzUgVw14h2dIt+mtbWt+1NjkjIu9vU49HR2TzoUOfHmoVwOEmsYb331A4irfvzyQiWmbBSqE4gbpShpJBb5cncEk5PnU36eroZDz5xusawwG0jOimtMaqna54Y6jmuxZdy1M7OTHCShT7KQ0scqsY35fnjerj0Xw90do4len7FGivqGFSFZceI8udRJx6A4qNaN4a3lrVcPVOtdRs3edb0rTb4sKL4EaMVjCl7kqWojbc7VZ1W0wQoB3iwoveChQoUcKJLhGt7jK3pseOtCElSluNg8oHU71gjibdU3XUMyc2lKkXK4LnNpCAMMNZajpwMbEk/rWrPtL6r+5dE/cUSSGbheipgKzu1HAy858gnb5kViyZOQ/IfuKWjygJbht/ypHutJ+exV/dHnUtdrkKIqobCXT9mSYtTl9t6lhUQKb8HP4lIThw/XKa0LOuEZOmLfa4yUthtsBSE9EJR7oH16/Ss9/Z707Ibv0laHOWLYoPhyVA7Oy31JKk578oGPpVyyzyMrWPiI5anQm9v/AFEsNB0icGWASAnI+dCmsuHPShXofpaPSbQIpUoZo+EFF/KVFOBvjv6UkUCD50ot6h44Hcg0mpfQbRrfCZKbhZoOueHtw0pcCP4jRQlR3KD1QsfI/wBKxZq+2zrTPfXc0rRNhPCBdkgboWk/wnx6EAb98eta7YlyIsnxojnI+1hSfJQ7g+YqveP9gjXqKrXdrgB2azH8C+24f8VF/wCYnzUjrnqAPTdQu6DqPxBWzLYyjeHd+uGnNSQ34BS1Mivl+FvhDhP9owT/ACrT0+YrdehdT23WGmIl+tbgUy+nC0H4mnBspCh2UDtXzyl2x5uYmI3PbXEdQHYLy1cviJz7uFdAtJyCDjvVqcEOKE3RV6eXKZW7FeKTeIaCCV42EtoDqoDZYHUb/LtKoFO+DCpsR5TNq0KSWa5wLxa49ztkpuVEkIC2nWzkKBpXVkdBQoUK00FChQrTQUKFCtNBQoUK00FChQrTQUiv11t9js0u73WSiLCiNF151ZwEpH+Pp3pVIeZjMOPvuoaabSVLWs4CQOpJrI32g+LDOrJSLbbkuPWSO/iJH3AuT6T/AGi//ZQeg/Ef2CpUCC84TaGasDWuvb9e62ucqyWabiLAjtDLwj591A2OFLIyrY+WwBqH6h0bbLTDjau05cRe7O0opjNBOXPbCoIbSsAYwCR5fCPOpdq21/e0fQUO7PTzZlwT7U9DQFKEgtp95SsEDfm3A7nAqU6C0i7pa4XGxsrQ5YQw0uIhwBTingSVOLOMc2cdP5R0xXnDzHJ33+Um1HVq6bRw4d2denNJQrUpZXJUoyZjh6uyF7qJ88fCPQepqRz1k4bHzNJraCpanlnCEDqelHiTzoW8wgcgO6z3q57CoABtOE5iTwvShSj24/loU29Tp7zuYnDvw5G5oxjKJSVY2NI0uNlYUaOcc8PHIcg70DLcWjTtaLpDgZeU4T5UZ4LL6A4kqHMMhSTg01SXnH18ysdMbUot0hLY8FxXKk9DnoanamwUEbiKZSALSpNf8JJWJQtIEm1POF9LCE4ehOnqpsdFoPdIwfIGqhcjzbNLfgXJRj3OEEuxJIPxp5wDgn4gQokj8uPOteOypMV4ocwtPYkdRUB432TTV50dJuM+K8mXGKVIdjtczickAnbqANz6D5Uoq4zuD0mBPP7yH8FuK920jd3IiIpfhqWTMtIVgkg+87GztnuUd+3prnRmqrFq+zIu1guDUyOrZYScLaV3QtPVKh5GvnjPhPxnWnpj7b0Z4D2eayrCVKHQ83VC8dQfL61JNJ6zvemLv95xri9CnpACpzCOYPoHQSGujg/ON/U02nV043EYtQg2befQShVIcPvtA2a4xWW9WMotrigB7fHJdhrPqfibPoofWrmttwg3OIiXbpjEuOsZS4y4FpI+YqpXDC4MaDeKaFChRTsFChQrTQUKFFypEeKwp+S+2w0gZUtxQSkD1JrTQykGoLzatP2l+63qfHgQmE8zjzy+VI9PU+QG5qsNd8eNNWdp5jTqPv2U3kKeQsNxGj+d07H5JyazLrziHfdZXBM2dMTcZCFH2cFBTCin/wBlo7uLH86s0l6yrgZMEsBJ1x34zSNSoFuhMyYliX7zUP4ZFxA6Lcx/Zs+Q6q/pTchcydJDLDXtF8lP+ChCBhLDYTukD8IGevbloqLEnzLiv2Rz2mQlXizJT68pTjoXF9AB15Rnp3qa8P8ARr96bcZt7rrNueV/tG6lPK5L33bZzuEeZ7/tUpu7dT+O/eK1Fs8u+/SSvgjctSx0p0/bZzM+0wlqMudISpaPEJyWmCCNs5yTkbk43FXDB8dch51fvHkOPn2pss1rhWi1sW+3RW40VlPKhCew/wAT608NqESEV9Vq3ANUMgp07DJMW46CETfDajphBeNsrI70XFdZbY9mdQXG88ySDSN1aucqWMlRyTQLoTygEYx0qgUl0WPz+s6FxF/t0ZOwhpwNhnH/ANqFNpWMmhQeDT7M2gTwZB5VDAo8EqQQdvKjnYSlHINcFlaG8Hc5rao2FML5vc5t65WBznOcij22MKStI3wa8CErUpYO42Iruqcjshpt6C2FnI5QQo9RTXLiKQS2oApPn0IpfblBcZUcnfBx8jRLD5UDHlIJSDjm7pqamWRiN4pbgmVXrDhysF+bpdEZBeyZVtkJzGkeo/kV6j9qqebZXI0/2GMh23zQcm03FXJv5sPdFDy3GfWtXotoUoq8fKO2B1pq1DpG33uGYdziR5rJ3AWMKSfMHqD6g1xzSY3BsYWtTiZTUXbXcCgLk2mdnCkOANqPzzhDg/8Apz6086f1XerFOQ/FXJgSNj7RbHzGWserSv4bnySPrVn3vhJd2mCzZprU+GOkC64cQkfkWPeTUE1LoSdYABLtl0tSHBzFcRQnRdvNPxD6ilbH19O7/mYY+E/fu34k6sf2jNW2woZnXS23Dzbu1tdivY8udnmT9SKmtr+0w6+keNpCA9tuqLqJgk/3FhJFZgkW+U4Ci3320vb7oS8WCfQoXhNGQdPXMJW9LsC568YbLCm+T/sO9M8UqPi+/YhBnvt37zWI+0SxyZOhrpn0uEUj9eemy6/aUeZaJi6Phsn+aZqCMnH91OSazU1YZRsj5e0rOF058NBDB8PlPNv9Pd+fL6mk8vTt1djocZ0y7CkpOSpRR4frss9P85rg4hifiHf1hEv0Pf0l0Xr7SOrJ+WIdysFrKugt8J6Y/wDLK8Nn6VW2ptb3/UMvmuL1wurxOxuj5UlPyitbJ+oNRmPbLgxlM+82iKg/gXJCgP7jexqR2XS79zQERol7vSDuEsMiHEP95XUfIVxmLcye/pAu59O/rGGS+ufLQzMkvTpA2ajtNhYT6IaR7ifqT/00uYtDy5iYc8yEPuYCLXAHjTHfILUPdbHp+1WZpzhndFN8k+XGsEJWyotrGXljyW8rc/SrT0bpWw6djBqy29tjm/tHT7zjn/Uo7mtoYC5wJ3SBk5kHtnCiE1FgO3d3woSGkuKs7KeVsPYyfEXkl3HTJxnHltU7iezxm0NstttMoAShCRgJA7AU9TQFgIIzRTEBrGXEZGc4NHTZadMEzB/Ldp2hhDgQ6QSkDIT50W7GffX4jy0tgdB1wKUy5LUVkuOHAA2A6n5UxSp6pbfOSUo7JzXEapUbUMRa6nN4scbgfCuaCfy0xSFtolOeGpSkJOyjttR5RhHijeiHnEKRvg5GCBVSAjc3jAtp54wO4WKFEhTIAHIf1oUU1pLyDggminErDfu4NChUwMbaFocU0RzgYwaJdaAUH2c4V8QoUKMGCYmTLDL+UKAKd96cX1NyWkyWlhJOykk70KFZhkNAIzecMPuMnCPeHcGlhf8AFSAh0MueShnNChXKtNSNXOC6i14jkLnoWQ4pQH8yen7Un5lKOVkrPrvQoV2ibre0yZF4juVgsVzGbhZ4EvbGXWEqI/UVG5vCvQ8lWRYggnsy+6j9kqFChRnaGQJ6xwX0QoBS4VxA/l9ucA/rS1HB/QDCQWrJzKHUvS3lj9CrFChUJrNfEQXztHG3aW01bFYtlmtrSkdHW46Qf1xmnNKkZ5E4AHYUKFXrtKALCKWYbbie9ODLSWkcqaFCo+JY30xNYnaJpc1iPzEELcHbypqduDruHUulspz0PWhQo0UWjUQWiZSlvnnW444ogjfpRDDLjilJUAgDtQoUxYVodyKQnAOU0hkNJS6ooOCVb0KFNWcMQqRM5jhxOM+dChQo5rT/2Q==" style="width:110px;height:110px;border-radius:50%;object-fit:cover;border:3px solid var(--gold);box-shadow:0 8px 32px rgba(45,106,79,.2);" alt="Oesa Tea Logo"/>
      <div class="hero-card-title">Oesa Tea</div>
      <div class="hero-card-origin">Oemah Sarangan</div>
      <div class="hero-card-sub">Teh dengan aroma dan rasa klasik yang cocok diminum dingin atau hangat — dari bumi Sarangan untuk seluruh Indonesia.</div>
      <div class="stats-row">
        <div class="stat"><div class="stat-num">100%</div><div class="stat-label">Alami</div></div>
        <div class="stat"><div class="stat-num">5+</div><div class="stat-label">Varian</div></div>
        <div class="stat"><div class="stat-num">1000+</div><div class="stat-label">Pelanggan</div></div>
      </div>
    </div>
  </div>
</section>

<!-- SARANGAN BANNER -->
<div class="sarangan-banner">
  <div class="banner-item"><span class="banner-icon">🏔️</span><div><div class="banner-label">Lokasi Inspirasi</div><div class="banner-value">Telaga Sarangan, Magetan</div></div></div>
  <div class="banner-item"><span class="banner-icon">🌿</span><div><div class="banner-label">Bahan Baku</div><div class="banner-value">Teh Pilihan Dataran Tinggi</div></div></div>
  <div class="banner-item"><span class="banner-icon">☁️</span><div><div class="banner-label">Ketinggian</div><div class="banner-value">±1.000 mdpl</div></div></div>
  <div class="banner-item"><span class="banner-icon">🍵</span><div><div class="banner-label">Filosofi</div><div class="banner-value">Kesegaran Alam dalam Secangkir</div></div></div>
</div>

<!-- ABOUT / ASAL USUL -->
<section class="about" id="about">
  <div class="reveal">
    <div class="section-label">Asal Usul Kami</div>
    <h2 class="section-title">Dari Bumi<br>Sarangan<br>untuk Indonesia</h2>
    <p class="section-desc">Oesa Tea lahir dari kecintaan mendalam terhadap keindahan Telaga Sarangan — kawasan wisata alam di kaki Gunung Lawu, Magetan, Jawa Timur. Nama <strong style="color:#fff;">OESA</strong> merupakan singkatan dari <strong style="color:var(--gold);">Oemah Sarangan</strong>, sebuah penghormatan kepada tanah asal yang kaya akan alam hijau, udara segar, dan budaya lokal yang hangat.</p>
    <div class="origin-name">🏡 Oemah Sarangan · Magetan, Jawa Timur</div>
    <blockquote class="about-quote">"Seperti Sarangan yang menyejukkan jiwa, setiap tegukan Oesa membawa kesegaran yang tak terlupakan."</blockquote>
  </div>
  <div class="about-visual reveal">
    <div class="about-boxes">
      <div class="about-box">
        <div class="about-box-icon">🏔️</div>
        <div class="about-box-title">Gunung Lawu</div>
        <div class="about-box-text">Diinspirasi dari kemegahan Gunung Lawu yang menaungi Sarangan dengan udara pegunungan yang murni.</div>
      </div>
      <div class="about-box">
        <div class="about-box-icon">🌊</div>
        <div class="about-box-title">Telaga Sarangan</div>
        <div class="about-box-text">Danau vulkanik alami di ketinggian 1.000 mdpl, simbol kesegaran dan ketenangan alam Jawa Timur.</div>
      </div>
      <div class="about-box">
        <div class="about-box-icon">🌱</div>
        <div class="about-box-title">Tanah Subur</div>
        <div class="about-box-text">Tanah vulkanik Sarangan menghasilkan bahan teh berkualitas tinggi dengan cita rasa yang khas dan kaya.</div>
      </div>
      <div class="about-box">
        <div class="about-box-icon">🤝</div>
        <div class="about-box-title">Kearifan Lokal</div>
        <div class="about-box-text">Menggabungkan tradisi lokal Magetan dengan standar produksi modern yang higienis dan terpercaya.</div>
      </div>
    </div>
  </div>
</section>

<!-- AKRONIM O·E·S·A -->
<section class="akronim" id="akronim">
  <div class="reveal">
    <div class="section-label" style="text-align:center;">Makna di Balik Nama</div>
    <h2 class="akronim-title">O · E · S · A</h2>
    <p class="akronim-sub">Setiap huruf dalam nama <strong>OESA</strong> menyimpan makna dan identitas yang berakar dari tanah Sarangan.</p>
  </div>
  <div class="akronim-grid reveal">
    <div class="akronim-letter">
      <div class="letter-char">O</div>
      <div class="letter-word">Oemah</div>
      <div class="letter-desc">Rumah — tempat lahir, tempat kembali. Oemah adalah akar dari segalanya.</div>
    </div>
    <div class="akronim-letter">
      <div class="letter-char">E</div>
      <div class="letter-word">Eling</div>
      <div class="letter-desc">Ingat — selalu ingat asal-usul dan tanah yang melahirkan kami di Sarangan.</div>
    </div>
    <div class="akronim-letter">
      <div class="letter-char">S</div>
      <div class="letter-word">Sarangan</div>
      <div class="letter-desc">Telaga Sarangan — sumber inspirasi, keindahan, dan kesegaran alam kami.</div>
    </div>
    <div class="akronim-letter">
      <div class="letter-char">A</div>
      <div class="letter-word">Alam</div>
      <div class="letter-desc">Alam — jiwa dari produk kami, murni dan segar seperti udara pegunungan.</div>
    </div>
  </div>
</section>

<!-- PRODUCTS -->
<section class="products" id="products">
  <div class="products-header reveal">
    <div class="section-label">Produk Kami</div>
    <h2 class="section-title">Koleksi Teh Oesa</h2>
    <p class="section-desc">Setiap varian kami terinspirasi dari kekayaan alam dan budaya Sarangan — dari pagi yang tenang hingga sore yang menyegarkan.</p>
  </div>
  <div class="products-grid">
    <div class="product-card reveal">
      <div class="product-img product-img-1">🍵</div>
      <div class="product-body">
        <span class="product-tag">Terlaris</span>
        <div class="product-name">Oesa Klasik</div>
        <p class="product-desc">Rasa teh hitam otentik khas dataran tinggi — aroma harum alami yang menenangkan, sempurna hangat maupun dingin.</p>
      </div>
    </div>
    <div class="product-card reveal">
      <div class="product-img product-img-2">🫖</div>
      <div class="product-body">
        <span class="product-tag">Baru</span>
        <div class="product-name">Oesa Mint Segar</div>
        <p class="product-desc">Perpaduan teh premium dengan mint pilihan — sensasi dingin menyegarkan seperti angin sepoi Telaga Sarangan.</p>
      </div>
    </div>
    <div class="product-card reveal">
      <div class="product-img product-img-3">🌸</div>
      <div class="product-body">
        <span class="product-tag">Premium</span>
        <div class="product-name">Oesa Bunga Lawu</div>
        <p class="product-desc">Harmoni teh pilihan dengan bunga chamomile dan melati — terinspirasi dari keindahan flora lereng Gunung Lawu.</p>
      </div>
    </div>
  </div>
</section>

<!-- VALUES -->
<section class="values" id="values">
  <div class="reveal">
    <div class="section-label">Nilai Kami</div>
    <h2 class="section-title">Mengapa Memilih Oesa Tea?</h2>
    <p class="section-desc">Kami tidak sekadar menjual teh. Kami berbagi cinta pada alam Sarangan dan komitmen pada kualitas yang bisa Anda rasakan.</p>
  </div>
  <div class="values-list">
    <div class="value-item reveal"><div class="value-icon">✅</div><div class="value-title">Kualitas Terjamin</div><div class="value-text">Setiap produk melewati seleksi ketat sebelum sampai ke tangan Anda.</div></div>
    <div class="value-item reveal"><div class="value-icon">🌿</div><div class="value-title">100% Bahan Alami</div><div class="value-text">Murni dari alam — tanpa pewarna buatan, tanpa pengawet kimia.</div></div>
    <div class="value-item reveal"><div class="value-icon">🏔️</div><div class="value-title">Khas Sarangan</div><div class="value-text">Terinspirasi langsung dari kekayaan alam dan budaya Magetan, Jawa Timur.</div></div>
    <div class="value-item reveal"><div class="value-icon">💰</div><div class="value-title">Harga Terjangkau</div><div class="value-text">Kualitas premium yang bisa dinikmati semua kalangan masyarakat.</div></div>
    <div class="value-item reveal"><div class="value-icon">🚚</div><div class="value-title">Pengiriman Cepat</div><div class="value-text">Dikirim ke seluruh Indonesia dengan kemasan aman dan higienis.</div></div>
    <div class="value-item reveal"><div class="value-icon">♻️</div><div class="value-title">Eco-Friendly</div><div class="value-text">Kemasan ramah lingkungan — karena kami cinta alam Sarangan.</div></div>
  </div>
</section>

<!-- TESTIMONY -->
<section class="testimony" id="testimony">
  <div class="testimony-header reveal">
    <div class="section-label">Testimoni</div>
    <h2 class="section-title">Kata Mereka tentang Oesa Tea</h2>
    <p class="section-desc">Kepuasan pelanggan adalah kebanggaan kami. Inilah cerita mereka yang telah merasakan kesegaran khas Sarangan.</p>
  </div>
  <div class="testimony-grid">
    <div class="testi-card reveal">
      <div class="testi-quote">"</div>
      <div class="stars">★★★★★</div>
      <p class="testi-text">Baru tahu ternyata OESA itu singkatan dari Oemah Sarangan! Makin suka setelah tau ceritanya. Rasanya pun benar-benar beda, ada nuansa alami yang khas.</p>
      <div class="testi-author"><div class="testi-avatar">S</div><div><div class="testi-name">Sari Dewi</div><div class="testi-loc">📍 Surabaya</div></div></div>
    </div>
    <div class="testi-card reveal">
      <div class="testi-quote">"</div>
      <div class="stars">★★★★★</div>
      <p class="testi-text">Pernah wisata ke Sarangan dan beli teh ini di sana. Sekarang pesan online biar bisa nikmatin nuansa Sarangan dari rumah. Recommended banget!</p>
      <div class="testi-author"><div class="testi-avatar">B</div><div><div class="testi-name">Budi Santoso</div><div class="testi-loc">📍 Madiun</div></div></div>
    </div>
    <div class="testi-card reveal">
      <div class="testi-quote">"</div>
      <div class="stars">★★★★★</div>
      <p class="testi-text">Varian Mint Segar-nya juara! Rasanya kayak minum angin sejuk di pinggir Telaga Sarangan. Keluarga saya langsung ketagihan dan order lagi.</p>
      <div class="testi-author"><div class="testi-avatar">R</div><div><div class="testi-name">Rina Kusuma</div><div class="testi-loc">📍 Magetan</div></div></div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="reveal">
    <div class="section-label">Hubungi Kami</div>
    <h2 class="section-title">Mari Berkolaborasi<br>Bersama Kami</h2>
    <p class="section-desc">Ada pertanyaan, ingin menjadi reseller, atau ingin merasakan langsung kesegaran Oesa dari Sarangan? Kami siap melayani Anda.</p>
    <div class="contact-info">
      <div class="contact-item"><span class="contact-icon">📍</span><div><div class="contact-label">Lokasi</div><div class="contact-value">Sarangan, Plaosan, Magetan — Jawa Timur</div></div></div>
      <div class="contact-item"><span class="contact-icon">📱</span><div><div class="contact-label">WhatsApp</div><div class="contact-value">+62 xxx-xxxx-xxxx</div></div></div>
      <div class="contact-item"><span class="contact-icon">📧</span><div><div class="contact-label">Email</div><div class="contact-value">info@oesatea.com</div></div></div>
      <div class="contact-item"><span class="contact-icon">🕐</span><div><div class="contact-label">Jam Operasional</div><div class="contact-value">Senin – Sabtu, 08.00 – 17.00 WIB</div></div></div>
    </div>
  </div>
  <div class="reveal">
    <div class="contact-form">
      <div class="form-row">
        <div class="form-group"><label>Nama</label><input type="text" placeholder="Nama Anda"/></div>
        <div class="form-group"><label>Nomor HP</label><input type="text" placeholder="+62..."/></div>
      </div>
      <div class="form-group"><label>Email</label><input type="email" placeholder="email@contoh.com"/></div>
      <div class="form-group"><label>Pesan</label><textarea placeholder="Tulis pesan Anda..."></textarea></div>
      <button class="btn-primary" style="width:100%;padding:15px;font-size:13px;" onclick="alert('Pesan terkirim! Kami akan segera menghubungi Anda. 🍵')">Kirim Pesan</button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>© 2025 <span>Oesa Tea</span> — Oemah Sarangan &nbsp;|&nbsp; 🏔️ Sarangan, Magetan, Jawa Timur &nbsp;|&nbsp; <em>Segar di Setiap Tegukan</em></p>
</footer>

<script>
  const reveals = document.querySelectorAll('.reveal');
  const obs = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 80);
        obs.unobserve(e.target);
      }
    });
  }, { threshold: 0.1 });
  reveals.forEach(r => obs.observe(r));
</script>
</body>
</html>
