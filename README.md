<!DOCTYPE html>
<html lang="bn" dir="ltr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>দারুল হুদা একাডেমি, লালমনিরহাট</title>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+Bengali:wght@300;400;500;600;700;900&family=Noto+Sans+Bengali:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --green-deep:   #0d4a24;
      --green-main:   #155c2e;
      --green-mid:    #1e7a3e;
      --green-light:  #2a9a50;
      --gold-deep:    #8a6200;
      --gold-main:    #b8860b;
      --gold-bright:  #d4a017;
      --gold-shine:   #f0c040;
      --gold-pale:    #fdf3d0;
      --cream:        #faf7ef;
      --text-dark:    #1a1008;
      --text-mid:     #3a2e10;
      --text-light:   #6b5c2e;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Noto Serif Bengali', serif;
      background: var(--cream);
      color: var(--text-dark);
      overflow-x: hidden;
    }

    /* ── GEOMETRIC PATTERN ── */
    .geo-bg {
      background-color: var(--green-deep);
      background-image:
        repeating-linear-gradient(45deg,  transparent, transparent 18px, rgba(212,160,23,.07) 18px, rgba(212,160,23,.07) 19px),
        repeating-linear-gradient(-45deg, transparent, transparent 18px, rgba(212,160,23,.07) 18px, rgba(212,160,23,.07) 19px),
        radial-gradient(circle at 50% 50%, rgba(212,160,23,.04) 0%, transparent 70%);
    }

    /* ── ARABIC ORNAMENT HELPER ── */
    .ornament { color: var(--gold-bright); font-size: 1.4em; line-height: 1; letter-spacing: .1em; }
    .divider {
      display: flex; align-items: center; justify-content: center; gap: 12px; margin: 12px 0 28px;
    }
    .divider::before, .divider::after {
      content: ''; flex: 1; max-width: 120px; height: 1px;
      background: linear-gradient(to right, transparent, var(--gold-main));
    }
    .divider::after { background: linear-gradient(to left, transparent, var(--gold-main)); }

    /* ── TOPBAR ── */
    .topbar {
      background: var(--green-deep);
      color: var(--gold-pale);
      text-align: center;
      padding: 7px 20px;
      font-size: .82rem;
      font-family: 'Noto Sans Bengali', sans-serif;
      letter-spacing: .03em;
      border-bottom: 1px solid rgba(212,160,23,.3);
    }

    /* ── NAVBAR ── */
    nav {
      position: sticky; top: 0; z-index: 100;
      background: var(--green-main);
      box-shadow: 0 3px 20px rgba(0,0,0,.35);
      border-bottom: 2px solid var(--gold-main);
    }
    .nav-inner {
      max-width: 1100px; margin: 0 auto;
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 24px;
    }
    .nav-brand {
      display: flex; align-items: center; gap: 12px;
      padding: 10px 0; text-decoration: none;
    }
    .nav-logo {
      width: 46px; height: 46px;
      border-radius: 50%;
      background: var(--gold-bright);
      display: flex; align-items: center; justify-content: center;
      font-size: 1.4rem; color: var(--green-deep);
      border: 2px solid var(--gold-shine);
      flex-shrink: 0;
    }

     .nav-logo img {
      width: 100%; height: 100%;
      object-fit: cover;
      border-radius: 50%;
    }
    .nav-title { color: #fff; line-height: 1.25; }
    .nav-title .main { font-size: 1.05rem; font-weight: 700; }
    .nav-title .sub  { font-size: .72rem; color: var(--gold-shine); font-family: 'Noto Sans Bengali', sans-serif; }
    .nav-links { display: flex; gap: 4px; list-style: none; }
    .nav-links a {
      color: rgba(255,255,255,.88);
      text-decoration: none;
      padding: 6px 13px;
      border-radius: 4px;
      font-family: 'Noto Sans Bengali', sans-serif;
      font-size: .88rem;
      font-weight: 500;
      transition: background .2s, color .2s;
    }
    .nav-links a:hover {
      background: rgba(212,160,23,.2);
      color: var(--gold-shine);
    }
    .hamburger { display: none; background: none; border: none; cursor: pointer; padding: 8px; }
    .hamburger span {
      display: block; width: 24px; height: 2px;
      background: #fff; margin: 5px 0;
      transition: .3s;
    }

    /* ── HERO ── */
    .hero {
      position: relative;
      min-height: 92vh;
      display: flex; align-items: center; justify-content: center;
      text-align: center;
      overflow: hidden;
    }
    .hero-bg {
      position: absolute; inset: 0;
      background: linear-gradient(160deg, var(--green-deep) 0%, #0a3318 45%, #06200f 100%);
    }
    /* Islamic star pattern overlay */
    .hero-pattern {
      position: absolute; inset: 0; opacity: .12;
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='80' height='80'%3E%3Cg fill='%23d4a017' fill-rule='evenodd'%3E%3Cpolygon points='40,5 47,28 70,28 52,42 59,65 40,51 21,65 28,42 10,28 33,28'/%3E%3C/g%3E%3C/svg%3E");
    }
    .hero-glow {
      position: absolute; inset: 0;
      background: radial-gradient(ellipse 60% 70% at 50% 40%, rgba(30,122,62,.35) 0%, transparent 70%);
    }
    .hero-content {
      position: relative; z-index: 2;
      padding: 60px 24px;
      animation: fadeUp .9s ease both;
    }
    .hero-bismillah {
      font-size: 2.8rem;
      color: var(--gold-shine);
      margin-bottom: 10px;
      text-shadow: 0 0 30px rgba(240,192,64,.4);
      letter-spacing: .08em;
      font-family: serif;
    }
    .hero-subtitle-top {
      color: rgba(255,255,255,.55);
      font-family: 'Noto Sans Bengali', sans-serif;
      font-size: .88rem;
      letter-spacing: .12em;
      text-transform: uppercase;
      margin-bottom: 18px;
    }
    .hero h1 {
      color: #fff;
      font-size: clamp(2.2rem, 6vw, 4rem);
      font-weight: 900;
      line-height: 1.2;
      text-shadow: 0 4px 24px rgba(0,0,0,.5);
      margin-bottom: 6px;
    }
    .hero h1 span { color: var(--gold-bright); }
    .hero-tagline {
      color: rgba(255,255,255,.7);
      font-size: 1.1rem;
      margin: 14px auto 36px;
      max-width: 560px;
      font-family: 'Noto Sans Bengali', sans-serif;
      line-height: 1.8;
    }
    .hero-btns { display: flex; gap: 14px; justify-content: center; flex-wrap: wrap; }
    .btn-gold {
      display: inline-block;
      padding: 13px 32px;
      background: linear-gradient(135deg, var(--gold-bright), var(--gold-main));
      color: var(--green-deep);
      font-family: 'Noto Sans Bengali', sans-serif;
      font-weight: 700;
      font-size: .95rem;
      border-radius: 4px;
      text-decoration: none;
      border: 1px solid var(--gold-shine);
      box-shadow: 0 4px 18px rgba(180,130,0,.35);
      transition: transform .2s, box-shadow .2s;
    }
    .btn-gold:hover { transform: translateY(-2px); box-shadow: 0 7px 24px rgba(180,130,0,.5); }
    .btn-outline {
      display: inline-block;
      padding: 13px 32px;
      background: transparent;
      color: #fff;
      font-family: 'Noto Sans Bengali', sans-serif;
      font-weight: 600;
      font-size: .95rem;
      border-radius: 4px;
      text-decoration: none;
      border: 1.5px solid rgba(255,255,255,.4);
      transition: border-color .2s, background .2s;
    }
    .btn-outline:hover { border-color: var(--gold-main); background: rgba(212,160,23,.1); }

    .hero-stats {
      display: flex; gap: 40px; justify-content: center; flex-wrap: wrap;
      margin-top: 52px;
      border-top: 1px solid rgba(212,160,23,.25);
      padding-top: 36px;
    }
    .stat { text-align: center; }
    .stat-num {
      font-size: 2.2rem; font-weight: 900;
      color: var(--gold-shine);
      line-height: 1;
    }
    .stat-label {
      color: rgba(255,255,255,.6);
      font-size: .8rem;
      font-family: 'Noto Sans Bengali', sans-serif;
      margin-top: 4px;
    }

    /* ── WAVE ── */
    .wave { display: block; width: 100%; margin-bottom: -2px; }

    /* ── SECTIONS ── */
    section { padding: 80px 24px; }
    .container { max-width: 1080px; margin: 0 auto; }

    .section-header { text-align: center; margin-bottom: 52px; }
    .section-label {
      display: inline-block;
      background: var(--green-main);
      color: var(--gold-shine);
      font-family: 'Noto Sans Bengali', sans-serif;
      font-size: .75rem;
      font-weight: 600;
      letter-spacing: .15em;
      padding: 5px 16px;
      border-radius: 20px;
      margin-bottom: 12px;
      border: 1px solid rgba(212,160,23,.3);
    }
    .section-title {
      font-size: clamp(1.7rem, 4vw, 2.5rem);
      font-weight: 800;
      color: var(--green-deep);
      line-height: 1.3;
    }
    .section-title span { color: var(--gold-main); }

    /* ── ABOUT ── */
    #about { background: var(--cream); }
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 60px;
      align-items: center;
    }
    .about-badge {
      display: inline-flex; align-items: center; gap: 8px;
      background: var(--gold-pale);
      color: var(--gold-deep);
      font-size: .8rem;
      font-family: 'Noto Sans Bengali', sans-serif;
      padding: 6px 14px; border-radius: 20px;
      border: 1px solid rgba(180,130,0,.25);
      margin-bottom: 20px;
    }
    .about-text h2 {
      font-size: 2rem; font-weight: 800;
      color: var(--green-deep);
      line-height: 1.35;
      margin-bottom: 16px;
    }
    .about-text p {
      color: var(--text-mid);
      line-height: 1.9;
      font-size: .97rem;
      margin-bottom: 14px;
      font-family: 'Noto Sans Bengali', sans-serif;
    }
    .about-features { list-style: none; margin-top: 20px; display: flex; flex-direction: column; gap: 10px; }
    .about-features li {
      display: flex; align-items: flex-start; gap: 10px;
      font-family: 'Noto Sans Bengali', sans-serif;
      font-size: .92rem; color: var(--text-mid);
    }
    .about-features li::before {
      content: '✦';
      color: var(--gold-main);
      flex-shrink: 0;
      margin-top: 2px;
    }
    .about-visual {
      position: relative;
    }
    .about-card {
      background: var(--green-main);
      border-radius: 12px;
      padding: 48px 36px;
      text-align: center;
      color: #fff;
      position: relative;
      overflow: hidden;
      box-shadow: 0 20px 60px rgba(13,74,36,.3);
    }
    .about-card::before {
      content: '';
      position: absolute; inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='60' height='60'%3E%3Cg fill='%23d4a017' fill-opacity='.06'%3E%3Cpolygon points='30,4 36,21 54,21 40,32 45,49 30,38 15,49 20,32 6,21 24,21'/%3E%3C/g%3E%3C/svg%3E");
      opacity: 1;
    }
    .about-card-icon { font-size: 4rem; margin-bottom: 16px; }
    .about-card h3 { font-size: 1.5rem; font-weight: 800; color: var(--gold-shine); margin-bottom: 10px; }
    .about-card p { font-family: 'Noto Sans Bengali', sans-serif; font-size: .9rem; color: rgba(255,255,255,.75); line-height: 1.8; position: relative; }
    .about-card-badge {
      position: absolute; top: 16px; right: 16px;
      background: var(--gold-bright);
      color: var(--green-deep);
      font-size: .72rem; font-weight: 700;
      font-family: 'Noto Sans Bengali', sans-serif;
      padding: 4px 10px; border-radius: 12px;
    }

    /* ── COURSES ── */
    #courses { background: #f0ede3; }
    .courses-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 24px;
    }
    .course-card {
      background: #fff;
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 4px 20px rgba(0,0,0,.07);
      border: 1px solid rgba(180,130,0,.12);
      transition: transform .25s, box-shadow .25s;
    }
    .course-card:hover { transform: translateY(-5px); box-shadow: 0 12px 36px rgba(13,74,36,.15); }
    .course-header {
      background: var(--green-main);
      padding: 22px 24px;
      display: flex; align-items: center; gap: 14px;
      position: relative;
      overflow: hidden;
    }
    .course-header::after {
      content: '';
      position: absolute; right: -10px; bottom: -10px;
      width: 80px; height: 80px;
      border-radius: 50%;
      background: rgba(212,160,23,.08);
    }
    .course-icon {
      width: 50px; height: 50px; flex-shrink: 0;
      background: var(--gold-bright);
      border-radius: 8px;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.6rem;
      color: var(--green-deep);
      border: 1px solid var(--gold-shine);
    }
    .course-header h3 { color: #fff; font-size: 1.05rem; font-weight: 700; line-height: 1.3; }
    .course-header span { color: var(--gold-shine); font-size: .78rem; font-family: 'Noto Sans Bengali', sans-serif; }
    .course-body { padding: 20px 24px; }
    .course-body p {
      color: var(--text-light);
      font-size: .88rem;
      line-height: 1.8;
      font-family: 'Noto Sans Bengali', sans-serif;
      margin-bottom: 14px;
    }
    .course-meta {
      display: flex; gap: 10px; flex-wrap: wrap;
    }
    .course-tag {
      background: var(--gold-pale);
      color: var(--gold-deep);
      font-size: .72rem;
      font-family: 'Noto Sans Bengali', sans-serif;
      padding: 3px 10px; border-radius: 12px;
      border: 1px solid rgba(180,130,0,.2);
    }

    /* ── ADMISSION ── */
    #admission { background: var(--cream); }
    .admission-wrap {
      display: grid; grid-template-columns: 1fr 1.2fr; gap: 48px; align-items: start;
    }
    .admission-info h3 {
      font-size: 1.3rem; font-weight: 800; color: var(--green-deep);
      margin: 28px 0 12px;
    }
    .admission-info h3:first-child { margin-top: 0; }
    .step-list { list-style: none; counter-reset: steps; display: flex; flex-direction: column; gap: 14px; }
    .step-list li {
      counter-increment: steps;
      display: flex; gap: 14px; align-items: flex-start;
      font-family: 'Noto Sans Bengali', sans-serif;
      font-size: .92rem; color: var(--text-mid); line-height: 1.6;
    }
    .step-list li::before {
      content: counter(steps);
      flex-shrink: 0;
      width: 28px; height: 28px;
      background: var(--green-main);
      color: #fff;
      border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      font-size: .8rem; font-weight: 700;
      font-family: 'Noto Sans Bengali', sans-serif;
    }
    .req-list { list-style: none; display: flex; flex-direction: column; gap: 10px; }
    .req-list li {
      display: flex; gap: 10px; align-items: flex-start;
      font-family: 'Noto Sans Bengali', sans-serif;
      font-size: .91rem; color: var(--text-mid); line-height: 1.6;
    }
    .req-list li::before { content: '◆'; color: var(--gold-main); flex-shrink: 0; margin-top: 2px; font-size: .65rem; }

    .admission-card {
      background: var(--green-deep);
      border-radius: 12px;
      padding: 36px 32px;
      color: #fff;
      position: relative; overflow: hidden;
    }
    .admission-card::before {
      content: '';
      position: absolute; inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='60' height='60'%3E%3Cg fill='%23d4a017' fill-opacity='.05'%3E%3Cpolygon points='30,4 36,21 54,21 40,32 45,49 30,38 15,49 20,32 6,21 24,21'/%3E%3C/g%3E%3C/svg%3E");
    }
    .admission-card > * { position: relative; }
    .admission-card h3 { font-size: 1.4rem; font-weight: 800; color: var(--gold-shine); margin-bottom: 6px; }
    .admission-card .notice {
      color: rgba(255,255,255,.65);
      font-size: .85rem;
      font-family: 'Noto Sans Bengali', sans-serif;
      margin-bottom: 28px; line-height: 1.7;
    }
    .info-row {
      display: flex; justify-content: space-between; align-items: center;
      border-bottom: 1px solid rgba(255,255,255,.1);
      padding: 11px 0;
      font-family: 'Noto Sans Bengali', sans-serif;
      font-size: .88rem;
    }
    .info-row:last-of-type { border-bottom: none; }
    .info-row .label { color: rgba(255,255,255,.55); }
    .info-row .value { color: var(--gold-shine); font-weight: 600; }
    .admission-cta {
      margin-top: 24px;
      display: block;
      text-align: center;
      padding: 13px;
      background: var(--gold-bright);
      color: var(--green-deep);
      font-family: 'Noto Sans Bengali', sans-serif;
      font-weight: 700; font-size: .95rem;
      border-radius: 6px;
      text-decoration: none;
      transition: background .2s;
    }
    .admission-cta:hover { background: var(--gold-shine); }

    /* ── GALLERY ── */
    #gallery { background: #f0ede3; }
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      grid-template-rows: auto;
      gap: 16px;
    }
    .gallery-item {
      border-radius: 8px;
      overflow: hidden;
      position: relative;
      cursor: pointer;
      aspect-ratio: 4/3;
      background: var(--green-main);
      display: flex; align-items: center; justify-content: center;
      box-shadow: 0 4px 16px rgba(0,0,0,.12);
      transition: transform .25s;
    }
    .gallery-item:hover { transform: scale(1.02); }
    .gallery-item:hover .gallery-overlay { opacity: 1; }
    .gallery-item.large { grid-column: span 2; aspect-ratio: 16/9; }
    .gallery-placeholder {
      position: absolute; inset: 0;
      display: flex; flex-direction: column;
      align-items: center; justify-content: center;
      gap: 10px;
      text-align: center;
      padding: 20px;
    }
    .gallery-placeholder .gp-icon { font-size: 2.8rem; opacity: .6; }
    .gallery-placeholder .gp-text {
      color: rgba(255,255,255,.7);
      font-size: .82rem;
      font-family: 'Noto Sans Bengali', sans-serif;
      line-height: 1.5;
    }
    .gallery-overlay {
      position: absolute; inset: 0;
      background: rgba(13,74,36,.7);
      opacity: 0;
      transition: opacity .25s;
      display: flex; align-items: center; justify-content: center;
    }
    .gallery-overlay span {
      color: var(--gold-shine);
      font-size: 2rem;
    }
    /* Different shades for variety */
    .gallery-item:nth-child(1) { background: #155c2e; }
    .gallery-item:nth-child(2) { background: #0d4a24; }
    .gallery-item:nth-child(3) { background: #1a6b3a; }
    .gallery-item:nth-child(4) { background: #1e7a3e; }
    .gallery-item:nth-child(5) { background: #124f27; }

    .gallery-note {
      text-align: center;
      margin-top: 24px;
      color: var(--text-light);
      font-size: .85rem;
      font-family: 'Noto Sans Bengali', sans-serif;
    }

    /* ── CONTACT ── */
    #contact { background: var(--green-deep); }
    #contact .section-title { color: #fff; }
    #contact .section-label { background: rgba(212,160,23,.15); border-color: rgba(212,160,23,.3); }

    .contact-grid {
      display: grid;
      grid-template-columns: 1.1fr 1fr;
      gap: 48px;
    }
    .contact-item {
      display: flex; gap: 16px; align-items: flex-start;
      margin-bottom: 28px;
    }
    .contact-icon-wrap {
      width: 46px; height: 46px; flex-shrink: 0;
      background: rgba(212,160,23,.12);
      border: 1px solid rgba(212,160,23,.25);
      border-radius: 8px;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.3rem;
    }
    .contact-item h4 {
      color: var(--gold-shine);
      font-size: .85rem;
      font-family: 'Noto Sans Bengali', sans-serif;
      font-weight: 600;
      margin-bottom: 4px;
    }
    .contact-item p {
      color: rgba(255,255,255,.7);
      font-family: 'Noto Sans Bengali', sans-serif;
      font-size: .9rem;
      line-height: 1.6;
    }
    .contact-map {
      background: rgba(255,255,255,.06);
      border: 1px solid rgba(212,160,23,.2);
      border-radius: 10px;
      overflow: hidden;
      min-height: 280px;
      display: flex; align-items: center; justify-content: center;
      flex-direction: column; gap: 12px;
      color: rgba(255,255,255,.4);
      font-family: 'Noto Sans Bengali', sans-serif;
      font-size: .88rem;
      text-align: center;
      padding: 24px;
    }
    .contact-map .map-icon { font-size: 3rem; opacity: .4; }
    .social-row {
      display: flex; gap: 12px; margin-top: 28px;
    }
    .social-btn {
      display: flex; align-items: center; gap: 8px;
      padding: 9px 18px;
      background: rgba(255,255,255,.07);
      color: rgba(255,255,255,.75);
      font-family: 'Noto Sans Bengali', sans-serif;
      font-size: .85rem;
      border-radius: 6px;
      text-decoration: none;
      border: 1px solid rgba(255,255,255,.12);
      transition: background .2s, color .2s;
    }
    .social-btn:hover { background: rgba(212,160,23,.15); color: var(--gold-shine); border-color: rgba(212,160,23,.3); }

    /* ── FOOTER ── */
    footer {
      background: #050f08;
      color: rgba(255,255,255,.45);
      text-align: center;
      padding: 28px 20px;
      font-family: 'Noto Sans Bengali', sans-serif;
      font-size: .82rem;
      border-top: 1px solid rgba(212,160,23,.15);
    }
    footer .gold { color: var(--gold-main); }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(28px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    .reveal {
      opacity: 0;
      transform: translateY(24px);
      transition: opacity .65s ease, transform .65s ease;
    }
    .reveal.visible { opacity: 1; transform: none; }

    /* ── RESPONSIVE ── */
    @media (max-width: 820px) {
      .about-grid, .admission-wrap, .contact-grid { grid-template-columns: 1fr; }
      .gallery-grid { grid-template-columns: 1fr 1fr; }
      .gallery-item.large { grid-column: span 2; }
      .nav-links { display: none; flex-direction: column; position: absolute; top: 100%; left: 0; right: 0; background: var(--green-deep); padding: 12px 16px; border-top: 1px solid rgba(212,160,23,.2); gap: 2px; }
      .nav-links.open { display: flex; }
      .hamburger { display: block; }
      .nav-inner { position: relative; }
      .hero-stats { gap: 24px; }
    }
    @media (max-width: 520px) {
      .gallery-grid { grid-template-columns: 1fr; }
      .gallery-item.large { grid-column: span 1; aspect-ratio: 4/3; }
      section { padding: 60px 18px; }
      .hero-bismillah { font-size: 2rem; }
    }
  </style>
</head>
<body>

<!-- TOP BAR -->
<div class="topbar">
  ☎ 01711-962740 &nbsp;|&nbsp; 📧 darulhudalalmoni@gmail.com &nbsp;|&nbsp; সকাল ৮টা – বিকাল ৫টা (শনি–বৃহস্পতি)
</div>

<!-- NAVBAR -->
<nav id="navbar">
  <div class="nav-inner">
      <a href="#" class="nav-brand">
      <div class="nav-logo"><img src="https://scontent.fdac31-1.fna.fbcdn.net/v/t39.30808-6/627001831_122169036650879554_5875217495032187453_n.jpg?_nc_cat=105&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=ZcfkCyP0MgcQ7kNvwHADYge&_nc_oc=Adk7ZaWCOp1Kg7naGq0ez8aSTYYWxNRj6-E6tD6QCRSP6SUG3t4uFj-mu5nPNPRwwvA&_nc_zt=23&_nc_ht=scontent.fdac31-1.fna&_nc_gid=XRJUD-riT5tiiNs6JYwHiQ&_nc_ss=8&oh=00_AfxTq0iaJ0n7V-nRrc_3PQ59Pxn5kPDDcxgeX5yreOwgqg&oe=69B624F4" alt="দারুল হুদা আলমনি লোগো"></div>
      <div class="nav-title">
        <div class="main">দারুল হুদা একাডেমি লালমনিরহাট</div>
        <div class="sub">ইসলামী শিক্ষা প্রতিষ্ঠান</div>
      </div>
    </a>
    <ul class="nav-links" id="navLinks">
      <li><a href="#about">পরিচিতি</a></li>
      <li><a href="#courses">বিভাগসমূহ</a></li>
      <li><a href="#admission">ভর্তি তথ্য</a></li>
      <li><a href="#gallery">গ্যালারি</a></li>
      <li><a href="#contact">যোগাযোগ</a></li>
    </ul>
    <button class="hamburger" id="hamburger" aria-label="মেনু">
      <span></span><span></span><span></span>
    </button>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-pattern"></div>
  <div class="hero-glow"></div>
  <div class="hero-content">
    <div class="hero-bismillah">بِسْمِ اللّٰهِ الرَّحْمٰنِ الرَّحِيْمِ</div>
    <p class="hero-subtitle-top">ইসলামী শিক্ষা ও আলোর পথে</p>
    <h1><span>দারুল হুদা একাডেমি লালমনিরহাট</span><br></h1>
    <p class="hero-tagline">কুরআন ও সুন্নাহর আলোকে দ্বীনি শিক্ষা, নৈতিক চরিত্র গঠন এবং সমাজের জন্য যোগ্য আলেম তৈরির অঙ্গীকার নিয়ে আমরা এগিয়ে চলেছি।</p>
    <div class="hero-btns">
      <a href="#admission" class="btn-gold">ভর্তি তথ্য জানুন</a>
      <a href="#about" class="btn-outline">আমাদের পরিচয়</a>
    </div>
    <div class="hero-stats">
      <div class="stat"><div class="stat-num">৫০০+</div><div class="stat-label">মোট শিক্ষার্থী</div></div>
      <div class="stat"><div class="stat-num">৩০+</div><div class="stat-label">অভিজ্ঞ শিক্ষক</div></div>
      <div class="stat"><div class="stat-num">১৫+</div><div class="stat-label">বছরের অভিজ্ঞতা</div></div>
      <div class="stat"><div class="stat-num">১০০%</div><div class="stat-label">নিষ্ঠার প্রতিশ্রুতি</div></div>
    </div>
  </div>
</section>

<!-- WAVE SVG -->
<svg class="wave" viewBox="0 0 1440 60" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="none">
  <path d="M0,30 C360,60 1080,0 1440,30 L1440,60 L0,60 Z" fill="#faf7ef"/>
</svg>

<!-- ABOUT -->
<section id="about">
  <div class="container">
    <div class="about-grid reveal">
      <div class="about-text">
        <div class="about-badge">✦ আমাদের পরিচয়</div>
        <h2>আলোর পথে পথচলা<br><span style="color:var(--gold-main)">দারুল হুদা লালমনিরহাট</span></h2>
        <div class="divider"><span class="ornament">❧</span></div>
        <p>দারুল হুদা লালমনিরহাট মাদরাসা একটি ঐতিহ্যবাহী ইসলামী শিক্ষা প্রতিষ্ঠান। এখানে পবিত্র কুরআন, হাদিস, ফিকহ ও আরবি সাহিত্যসহ সমন্বিত শিক্ষাক্রমে পাঠদান করা হয়।</p>
        <p>আমাদের লক্ষ্য হলো শিক্ষার্থীদের দ্বীনি ইলম অর্জনের পাশাপাশি আধুনিক জ্ঞান-বিজ্ঞানে সমৃদ্ধ করে তোলা এবং একজন পূর্ণাঙ্গ মানুষ হিসেবে গড়ে তোলা।</p>
        <ul class="about-features">
          <li>কুরআন মজিদ হিফজ ও তাজবিদ শিক্ষার বিশেষ ব্যবস্থা</li>
          <li>অভিজ্ঞ ও যোগ্য শিক্ষকমণ্ডলী দ্বারা পাঠদান</li>
          <li>আধুনিক সুবিধাসম্পন্ন আবাসিক সুবিধা (হোস্টেল)</li>
          <li>নিয়মিত বার্ষিক পরীক্ষা ও মূল্যায়ন ব্যবস্থা</li>
          <li>দরিদ্র ও মেধাবী শিক্ষার্থীদের জন্য বৃত্তির ব্যবস্থা</li>
        </ul>
      </div>
      <div class="about-visual">
        <div class="about-card">
          <div class="about-card-badge">প্রতিষ্ঠিত ২০০৮</div>
          <div class="about-card-icon">🕌</div>
          <h3>আমাদের মিশন</h3>
          <p>দ্বীনি শিক্ষার আলো ছড়িয়ে দেওয়া এবং সমাজের জন্য আদর্শ আলেম ও নাগরিক তৈরি করাই আমাদের মূল উদ্দেশ্য। কুরআন ও সুন্নাহর পথ অনুসরণ করে আমরা প্রজন্মকে গড়ে তুলছি।</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- COURSES -->
<section id="courses">
  <div class="container">
    <div class="section-header reveal">
      <div class="section-label">📚 আমাদের বিভাগসমূহ</div>
      <h2 class="section-title">কোন বিভাগে পড়বেন?</h2>
      <div class="divider"><span class="ornament">✦</span></div>
    </div>
    <div class="courses-grid reveal">

      <div class="course-card">
        <div class="course-header">
          <div class="course-icon">📖</div>
          <div>
            <h3>হিফজুল কুরআন বিভাগ</h3>
            <span>Hifzul Quran</span>
          </div>
        </div>
        <div class="course-body">
          <p>সহিহ তাজবিদসহ পবিত্র কুরআনুল কারিম মুখস্থ করার বিশেষ বিভাগ। অভিজ্ঞ হাফেজ উস্তাদদের তত্ত্বাবধানে পাঠ গ্রহণ করা হয়।</p>
          <div class="course-meta">
            <span class="course-tag">৩–৫ বছর</span>
            <span class="course-tag">আবাসিক</span>
            <span class="course-tag">বয়স: ৮–১৫</span>
          </div>
        </div>
      </div>

      <div class="course-card">
        <div class="course-header">
          <div class="course-icon">🕋</div>
          <div>
            <h3>নূরানী বিভাগ</h3>
            <span>Nurani Course</span>
          </div>
        </div>
        <div class="course-body">
          <p>শিশুদের জন্য কায়দা, আমপারা ও সূরা-কালামের প্রাথমিক শিক্ষার বিভাগ। নূরানী পদ্ধতিতে দ্রুত ও সহজে তাজবিদ শেখানো হয়।</p>
          <div class="course-meta">
            <span class="course-tag">১–২ বছর</span>
            <span class="course-tag">দৈনন্দিন</span>
            <span class="course-tag">বয়স: ৪–১০</span>
          </div>
        </div>
      </div>

      <div class="course-card">
        <div class="course-header">
          <div class="course-icon">📜</div>
          <div>
            <h3>কিতাব বিভাগ</h3>
            <span>Kitab / Dawra</span>
          </div>
        </div>
        <div class="course-body">
          <p>হাদিস, ফিকহ, আরবি সাহিত্য, উসুলুল ফিকহ ও তাফসিরসহ সম্পূর্ণ আলিয়া কারিকুলামে উচ্চতর দ্বীনি শিক্ষা প্রদান করা হয়।</p>
          <div class="course-meta">
            <span class="course-tag">৬–৮ বছর</span>
            <span class="course-tag">আবাসিক</span>
            <span class="course-tag">দাখিল–দাওরা</span>
          </div>
        </div>
      </div>

      <div class="course-card">
        <div class="course-header">
          <div class="course-icon">🌙</div>
          <div>
            <h3>তাহফিজুল হাদিস</h3>
            <span>Hadith Memorization</span>
          </div>
        </div>
        <div class="course-body">
          <p>আরবাঈন নববী, বুলুগুল মারামসহ গুরুত্বপূর্ণ হাদিস গ্রন্থের মূল মতন হিফজ করানোর বিশেষ কোর্স।</p>
          <div class="course-meta">
            <span class="course-tag">১–২ বছর</span>
            <span class="course-tag">নির্বাচিত</span>
          </div>
        </div>
      </div>

      <div class="course-card">
        <div class="course-header">
          <div class="course-icon">📝</div>
          <div>
            <h3>মহিলা বিভাগ</h3>
            <span>Women's Section</span>
          </div>
        </div>
        <div class="course-body">
          <p>নারীদের জন্য পৃথক পরিবেশে কুরআন, হাদিস ও ফিকহুন নিসা শিক্ষার বিশেষ ব্যবস্থা। মহিলা শিক্ষিকাদের তত্ত্বাবধানে পরিচালিত।</p>
          <div class="course-meta">
            <span class="course-tag">পৃথক ক্যাম্পাস</span>
            <span class="course-tag">সম্পূর্ণ পর্দা</span>
          </div>
        </div>
      </div>

      <div class="course-card">
        <div class="course-header">
          <div class="course-icon">🌙</div>
          <div>
            <h3>তাকমিল ফিল হাদিস</h3>
            <span>Takmiluddawra</span>
          </div>
        </div>
        <div class="course-body">
          <p>সর্বোচ্চ স্তরের হাদিস বিভাগ – সিহাহ সিত্তাহসহ প্রধান হাদিস গ্রন্থ পাঠ ও সনদ পর্যন্ত বিস্তারিত শিক্ষা।</p>
          <div class="course-meta">
            <span class="course-tag">১ বছর</span>
            <span class="course-tag">স্নাতক স্তর</span>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ADMISSION -->
<section id="admission">
  <div class="container">
    <div class="section-header reveal">
      <div class="section-label">📋 ভর্তি তথ্য</div>
      <h2 class="section-title">কিভাবে <span>ভর্তি হবেন?</span></h2>
      <div class="divider"><span class="ornament">✦</span></div>
    </div>
    <div class="admission-wrap reveal">
      <div class="admission-info">
        <h3>ভর্তির ধাপসমূহ</h3>
        <ol class="step-list">
          <li>মাদরাসা কার্যালয় থেকে ভর্তি ফর্ম সংগ্রহ করুন অথবা ফোনে যোগাযোগ করুন।</li>
          <li>নির্ধারিত তারিখে শিক্ষার্থীকে নিয়ে ভর্তি পরীক্ষায় অংশগ্রহণ করুন।</li>
          <li>উত্তীর্ণ শিক্ষার্থীদের তালিকা নোটিশ বোর্ডে প্রকাশ করা হবে।</li>
          <li>প্রয়োজনীয় কাগজপত্র ও ভর্তি ফি জমা দিয়ে ভর্তি নিশ্চিত করুন।</li>
          <li>ক্লাস শুরুর তারিখ ও সময়সূচি জেনে নিন।</li>
        </ol>

        <h3>প্রয়োজনীয় কাগজপত্র</h3>
        <ul class="req-list">
          <li>পূর্ববর্তী শ্রেণির সনদপত্র বা মার্কশিটের ফটোকপি</li>
          <li>জন্ম নিবন্ধন সনদের ফটোকপি</li>
          <li>পিতা-মাতার জাতীয় পরিচয়পত্রের ফটোকপি</li>
          <li>সাম্প্রতিক রঙিন পাসপোর্ট সাইজ ছবি (৪ কপি)</li>
          <li>স্থানীয় চেয়ারম্যান/কাউন্সিলরের প্রত্যয়নপত্র</li>
        </ul>
      </div>

      <div class="admission-card">
        <h3>ভর্তি সংক্রান্ত তথ্য</h3>
        <p class="notice">আগামী শিক্ষাবর্ষের ভর্তি প্রক্রিয়া শুরু হয়েছে। আসন সংখ্যা সীমিত, তাই দ্রুত যোগাযোগ করুন।</p>
        <div class="info-row"><span class="label">ভর্তি পরীক্ষার তারিখ</span><span class="value">পরবর্তী বিজ্ঞপ্তি অনুযায়ী</span></div>
        <div class="info-row"><span class="label">ক্লাস শুরু</span><span class="value">শাওয়াল মাস</span></div>
        <div class="info-row"><span class="label">ভর্তি ফর্মের মূল্য</span><span class="value">বিনামূল্যে</span></div>
        <div class="info-row"><span class="label">আবাসিক সুবিধা</span><span class="value">উপলব্ধ (সীমিত আসন)</span></div>
        <div class="info-row"><span class="label">বৃত্তির ব্যবস্থা</span><span class="value">মেধাবী ও গরিব শিক্ষার্থী</span></div>
        <div class="info-row"><span class="label">যোগাযোগের সময়</span><span class="value">শনি–বৃহস্পতি, সকাল ৯টা–৫টা</span></div>
        <a href="#contact" class="admission-cta">এখনই যোগাযোগ করুন →</a>
      </div>
    </div>
  </div>
</section>

<!-- GALLERY -->
<section id="gallery">
  <div class="container">
    <div class="section-header reveal">
      <div class="section-label">🖼️ গ্যালারি</div>
      <h2 class="section-title">আমাদের <span>প্রতিষ্ঠানের দৃশ্য</span></h2>
      <div class="divider"><span class="ornament">✦</span></div>
    </div>
    <div class="gallery-grid reveal">
      <div class="gallery-item large">
        <div class="gallery-placeholder">
          <div class="gp-icon">🕌</div>
          <div class="gp-text">মাদরাসা প্রাঙ্গণ<br><small>মূল ভবন</small></div>
        </div>
        <div class="gallery-overlay"><span>🔍</span></div>
      </div>
      <div class="gallery-item">
        <div class="gallery-placeholder">
          <div class="gp-icon">📚</div>
          <div class="gp-text">লাইব্রেরি কক্ষ</div>
        </div>
        <div class="gallery-overlay"><span>🔍</span></div>
      </div>
      <div class="gallery-item">
        <div class="gallery-placeholder">
          <div class="gp-icon">🎓</div>
          <div class="gp-text">বার্ষিক পুরস্কার বিতরণী</div>
        </div>
        <div class="gallery-overlay"><span>🔍</span></div>
      </div>
      <div class="gallery-item">
        <div class="gallery-placeholder">
          <div class="gp-icon">✏️</div>
          <div class="gp-text">শ্রেণিকক্ষ</div>
        </div>
        <div class="gallery-overlay"><span>🔍</span></div>
      </div>
      <div class="gallery-item">
        <div class="gallery-placeholder">
          <div class="gp-icon">🌙</div>
          <div class="gp-text">জামে মসজিদ</div>
        </div>
        <div class="gallery-overlay"><span>🔍</span></div>
      </div>
    </div>
    <p class="gallery-note">আরও ছবির জন্য আমাদের ফেসবুক পেজ ভিজিট করুন।</p>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="container">
    <div class="section-header reveal">
      <div class="section-label">📞 যোগাযোগ</div>
      <h2 class="section-title" style="color:#fff">আমাদের সাথে <span>যোগাযোগ করুন</span></h2>
      <div class="divider" style="--gold-main:#d4a017"><span class="ornament">✦</span></div>
    </div>
    <div class="contact-grid reveal">
      <div>
        <div class="contact-item">
          <div class="contact-icon-wrap">📍</div>
          <div>
            <h4>ঠিকানা</h4>
            <p>দারুল হুদা লালমনিরহাট মাদরাসা<br>এল.জিএ.ডি.রোড<br>লালমনিরহাট</p>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon-wrap">☎️</div>
          <div>
            <h4>মোবাইল / ফোন</h4>
            <p>01711-962740<br>01719154797</p>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon-wrap">📧</div>
          <div>
            <h4>@email</h4>
            <p>darulhudalalmoni@gmail.com</p>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon-wrap">🕐</div>
          <div>
            <h4>অফিস সময়</h4>
            <p>শনিবার – বৃহস্পতিবার<br>সকাল ৮:০০ – বিকাল ৫:০০</p>
          </div>
        </div>
        <div class="social-row">
          <a href="https://www.facebook.com/darulhudalalmoni" class="social-btn" target="_blank">
            📘 ফেসবুক পেজ
          </a>
        </div>
      </div>
      <div>
        <div class="contact-map">
          <span class="map-icon">🗺️</span>
          <p>Madrasa Darul Huda Al-Arabia, WC7H+QR7, LGED Rd 2, Lalmonirhat<br><small style="opacity:.6">Madrasa Darul Huda Al-Arabia, WC7H+QR7, LGED Rd 2, Lalmonirhat</small></p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>© ২০২৫ <span class="gold">দারুল হুদা একাডেমি লালমনিরহাট </span> — সর্বস্বত্ব সংরক্ষিত।</p>
  <p style="margin-top:6px">اَللّٰهُمَّ اَعِنَّا عَلَى طَلَبِ الْعِلْمِ</p>
</footer>

<script>
  // Hamburger menu
  const hamburger = document.getElementById('hamburger');
  const navLinks  = document.getElementById('navLinks');
  hamburger.addEventListener('click', () => navLinks.classList.toggle('open'));
  navLinks.querySelectorAll('a').forEach(a => a.addEventListener('click', () => navLinks.classList.remove('open')));

  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); } });
  }, { threshold: 0.12 });
  reveals.forEach(el => observer.observe(el));
</script>
</body>
</html>
