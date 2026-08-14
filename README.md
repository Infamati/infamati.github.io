<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, viewport-fit=cover">
<title>دعوة زفاف — دكتور مصطفى و صيدلانية تبارك</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Aref+Ruqaa:wght@400;700&family=Tajawal:wght@300;400;500;700&display=swap" rel="stylesheet">
<style>
  :root{
    --sage-deep: #5f6f52;
    --sage: #92a17f;
    --sage-light: #c7d1b8;
    --ivory: #f7f2e7;
    --ivory-warm: #efe6d3;
    --gold: #b6924f;
    --gold-light: #d8bd85;
    --pearl: #fdfbf7;
    --ink: #3c4230;
    --paper: #faf7ef;
  }
 
  *{ margin:0; padding:0; box-sizing:border-box; -webkit-tap-highlight-color: transparent; }
 
  @media (prefers-reduced-motion: reduce){
    *{ animation-duration: 0.01ms !important; animation-iteration-count: 1 !important; transition-duration: 0.01ms !important; }
  }
 
  html, body{
    background: var(--sage-deep);
    color: var(--ink);
    font-family: 'Tajawal', sans-serif;
    overflow-x: hidden;
    width: 100%;
  }
 
  body{
    min-height: 100vh;
    min-height: 100dvh;
    background:
      radial-gradient(ellipse at top, rgba(255,255,255,0.06), transparent 60%),
      linear-gradient(180deg, #6b7a5c 0%, #55634a 40%, #47543d 100%);
  }
 
  /* ============ Petals ============ */
  #petals{
    position: fixed; inset: 0; pointer-events: none; z-index: 40; overflow: hidden;
  }
  .petal{
    position: absolute; top: -5%;
    width: 14px; height: 14px;
    background: radial-gradient(circle at 30% 30%, #ffffff, #eee2c8 70%);
    border-radius: 0 70% 0 70%;
    opacity: 0.85;
    filter: drop-shadow(0 1px 1px rgba(0,0,0,0.15));
    animation: fall linear infinite;
  }
  @keyframes fall{
    0%{ transform: translateY(-10vh) translateX(0) rotate(0deg); }
    100%{ transform: translateY(110vh) translateX(var(--drift, 40px)) rotate(360deg); }
  }
 
  /* ============ Gate / Arch Reveal ============ */
  #gate{
    position: fixed; inset: 0; z-index: 100;
    display: flex;
    background: var(--sage-deep);
    height: 100vh;
    height: 100dvh;
    cursor: pointer;
  }
  #gate .leaf{
    flex: 1;
    background:
      radial-gradient(ellipse at 50% 0%, rgba(255,255,255,0.08), transparent 55%),
      linear-gradient(180deg, #7a8a68, #4c5a41);
    position: relative;
    transition: transform 1.9s cubic-bezier(.76,0,.24,1), opacity 1.9s ease;
  }
  #gate .leaf.left{ transform-origin: left center; border-left: 2px solid rgba(214,189,133,0.4); }
  #gate .leaf.right{ transform-origin: right center; border-right: 2px solid rgba(214,189,133,0.4);}
  #gate.open .leaf.left{ transform: translateX(-102%); }
  #gate.open .leaf.right{ transform: translateX(102%); }
  #gate.open{ pointer-events: none; }
 
  #gate .center-text{
    position:absolute; top:50%; left:50%; transform:translate(-50%,-50%);
    text-align:center; width: 100%; max-width: 320px; padding: 0 24px;
    display:flex; flex-direction:column; align-items:center;
    transition: opacity 0.6s ease;
  }
  #gate.open .center-text{ opacity: 0; }
  #gate .center-text .mono-line{
    font-family:'Aref Ruqaa', serif;
    font-size: clamp(26px, 8vw, 42px);
    letter-spacing: 0.5px;
    opacity: 0;
    animation: gentleIn 1.4s ease forwards 0.3s;
  }
  #gate .center-text .sub{
    margin-top: 14px;
    font-size: clamp(11px, 3.4vw, 14px);
    letter-spacing: 1px;
    line-height: 2;
    color: var(--gold-light);
    opacity: 0;
    max-width: 280px;
    animation: gentleIn 1.4s ease forwards 0.8s;
  }
  #gate .tap-hint{
    position:absolute; bottom: 9%; left:0; right:0;
    text-align: center;
    color: var(--gold-light); font-size: 13px; letter-spacing: 2px;
    opacity: 0; animation: gentleIn 1.2s ease forwards 1.6s, pulse 2s ease-in-out infinite 1.6s;
    transition: opacity 0.4s ease;
  }
  #gate.open .tap-hint{ opacity: 0 !important; animation: none; }
  @keyframes gentleIn{
    from{ opacity:0; transform: translateY(10px); }
    to{ opacity:1; transform: translateY(0); }
  }
  @keyframes pulse{
    0%,100%{ opacity: 0.55; } 50%{ opacity: 1; }
  }
  #gate.hidden{ display:none; }
 
  /* ============ Layout shell ============ */
  .page{
    max-width: 480px;
    margin: 0 auto;
    padding: 0 0 50px;
    position: relative;
    z-index: 1;
  }
 
  section{
    padding: 44px 22px;
    position: relative;
  }
 
  /* ============ Hero ============ */
  .hero{
    padding-top: 56px;
    text-align: center;
    color: var(--ivory);
  }
  .hero .frame-wrap{
    position: relative;
    max-width: 320px;
    margin: 0 auto;
    padding: 66px 26px 54px;
    min-height: 460px;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .arch-svg{
    position:absolute; inset:0; width:100%; height:100%;
    z-index: 0;
  }
  .hero .content{ position: relative; z-index: 1; }
 
  .reveal{
    opacity: 0;
    transform: translateY(16px);
    transition: opacity 0.9s ease, transform 0.9s ease;
  }
  .revealed .reveal{ opacity: 1; transform: translateY(0); }
  .revealed .reveal.d1{ transition-delay: 0.05s; }
  .revealed .reveal.d2{ transition-delay: 0.25s; }
  .revealed .reveal.d3{ transition-delay: 0.4s; }
  .revealed .reveal.d4{ transition-delay: 0.6s; }
  .revealed .reveal.d5{ transition-delay: 0.8s; }
 
  .eyebrow{
    font-size: 12px;
    letter-spacing: 4px;
    color: var(--gold-light);
    text-transform: uppercase;
  }
  .hero h1{
    font-family:'Aref Ruqaa', serif;
    font-weight: 700;
    font-size: clamp(28px, 8.5vw, 38px);
    line-height: 1.5;
    margin-top: 16px;
    color: #fffdf7;
    text-shadow: 0 2px 18px rgba(0,0,0,0.25);
  }
  .hero .amp{
    display:block;
    font-size: 20px;
    color: var(--gold-light);
    margin: 4px 0;
  }
  .hero .tagline{
    margin-top: 20px;
    font-size: 14px;
    line-height: 2;
    color: var(--sage-light);
    font-weight: 300;
    padding: 0 6px;
  }
 
  .divider{
    display:flex; align-items:center; justify-content:center; gap: 14px;
    margin: 26px auto 0; width: 200px;
    color: var(--gold-light);
  }
  .divider .line{ flex:1; height:1px; background: linear-gradient(90deg, transparent, var(--gold-light), transparent); }
  .divider .diamond{ width:7px; height:7px; background: var(--gold-light); transform: rotate(45deg); flex-shrink:0; }
 
  /* ============ Info panel ============ */
  .info{
    background: var(--paper);
    border-radius: 26px 26px 0 0;
    margin-top: 26px;
    box-shadow: 0 -20px 60px rgba(0,0,0,0.25);
    position: relative;
    overflow: hidden;
  }
 
  .rose{
    position: absolute;
    width: 118px;
    height: auto;
    opacity: 0.92;
    z-index: 0;
    pointer-events: none;
  }
  .rose.top-left{ top: -14px; left: -20px; transform: rotate(-14deg); }
  .rose.top-right{ top: -14px; right: -20px; transform: rotate(14deg) scaleX(-1); }
  .rose .petal{ fill: #fffdf9; stroke: #e4d9c4; stroke-width: 0.6; }
  .rose .petal-inner{ fill: #f1e8d4; }
  .rose .leaf{ fill: var(--sage-light); }
  .rose .stem{ stroke: var(--sage); stroke-width: 2.4; fill: none; }
 
  .info-inner{
    position: relative;
    z-index: 1;
    padding-bottom: 6px;
  }
 
  .quote{
    text-align:center;
    font-family:'Aref Ruqaa', serif;
    font-size: 19px;
    line-height: 2.1;
    color: var(--sage-deep);
    padding-bottom: 6px;
    margin-top: 6px;
  }
  .quote .src{
    display:block; margin-top: 10px; font-family:'Tajawal',sans-serif; font-size: 12px; letter-spacing:2px; color: var(--gold);
  }
 
  .cards{
    display: grid;
    gap: 18px;
    margin-top: 28px;
  }
  .card{
    background: linear-gradient(180deg, #ffffff, var(--ivory));
    border: 1px solid var(--sage-light);
    border-radius: 18px;
    padding: 24px 20px;
    text-align: center;
    position: relative;
    overflow: hidden;
    opacity: 0;
    transform: translateY(18px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .card.in-view{ opacity: 1; transform: translateY(0); }
  .card::before{
    content:"";
    position:absolute; top:-30%; right:-20%;
    width: 140px; height:140px;
    background: radial-gradient(circle, rgba(182,146,79,0.12), transparent 70%);
  }
  .card .icon{
    width: 36px; height: 36px; margin: 0 auto 10px;
    color: var(--gold);
  }
  .card .label{
    font-size: 11px; letter-spacing: 3px; color: var(--sage);
    text-transform: uppercase; margin-bottom: 8px;
  }
  .card .value{
    font-family:'Aref Ruqaa', serif;
    font-size: 21px;
    color: var(--sage-deep);
    line-height: 1.6;
  }
  .card .sub-value{
    margin-top: 3px;
    font-size: 13px;
    color: #8a8470;
  }
  .card .mini-divider{
    width: 46px; height: 1px;
    background: var(--sage-light);
    margin: 16px auto;
  }
  .card .dl-row{
    display: flex;
    align-items: stretch;
    gap: 14px;
  }
  .card .dl-col{
    flex: 1;
    min-width: 0;
  }
  .card .dl-sep{
    width: 1px;
    background: var(--sage-light);
    margin: 4px 0;
    flex-shrink: 0;
  }
  .card .dl-col .value{
    font-size: 18px;
    line-height: 1.5;
  }
  .map-btn{
    display: block;
    margin: 18px auto 0;
    width: fit-content;
    padding: 12px 28px;
    border-radius: 40px;
    border: 1px solid var(--gold);
    color: var(--gold);
    background: transparent;
    font-family: 'Tajawal', sans-serif;
    font-size: 13px;
    letter-spacing: 1px;
    text-decoration: none;
    transition: background 0.3s ease, color 0.3s ease;
  }
  .map-btn:active{ background: var(--gold); color: #fff; }
 
  .guest-note{
    margin-top: 16px;
    font-size: 12.5px;
    line-height: 2;
    color: #8a8470;
  }
 
  /* ============ Countdown ============ */
  .countdown-wrap{
    margin-top: 32px;
    text-align: center;
  }
  .countdown-wrap .label{
    font-size: 11px; letter-spacing: 3px; color: var(--sage);
    text-transform: uppercase; margin-bottom: 14px;
  }
  .countdown{
    display: flex; justify-content: center; gap: 8px;
  }
  .countdown .unit{
    background: var(--sage-deep);
    color: var(--ivory);
    border-radius: 14px;
    padding: 12px 4px;
    width: 64px;
    box-shadow: 0 8px 18px rgba(95,111,82,0.35);
  }
  .countdown .unit .num{
    font-family: 'Aref Ruqaa', serif;
    font-size: 24px;
    color: var(--gold-light);
  }
  .countdown .unit .unit-label{
    font-size: 10px;
    margin-top: 3px;
    letter-spacing: 1px;
    color: var(--sage-light);
  }
 
  /* ============ Personal note ============ */
  .personal-note{
    text-align: center;
    margin-top: 44px;
    padding-top: 30px;
    border-top: 1px dashed var(--sage-light);
  }
  .personal-note p{
    font-size: 13px;
    letter-spacing: 1px;
    color: var(--sage-deep);
    line-height: 2.2;
  }
  .personal-note .no-kids{
    color: #a06a5b;
    font-weight: 500;
  }
 
  footer{
    text-align: center;
    margin-top: 36px;
    font-size: 12px;
    letter-spacing: 2px;
    color: var(--sage);
  }
  footer .heart{ color: var(--gold); }
</style>
</head>
<body>
 
<div id="petals"></div>
 
<!-- Gate reveal -->
<div id="gate">
  <div class="leaf left"></div>
  <div class="leaf right"></div>
  <div class="center-text">
    <div class="mono-line">بِسْمِ اللَّهِ</div>
    <div class="sub">وَمِنْ آيَاتِهِ أَنْ خَلَقَ لَكُم مِّنْ أَنفُسِكُمْ<br>أَزْوَاجًا لِّتَسْكُنُوا إِلَيْهَا</div>
  </div>
  <div class="tap-hint">اضغط لفتح الدعوة</div>
</div>
 
<div class="page" id="page">
 
  <!-- HERO -->
  <section class="hero">
    <div class="frame-wrap">
      <svg class="arch-svg" viewBox="0 0 360 520" preserveAspectRatio="none" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path id="archPath" d="M25 520 V236 C25 118 92 34 180 34 C268 34 335 118 335 236 V520"
              stroke="#b6924f" stroke-width="1.4" opacity="0.55" fill="none"/>
        <path d="M25 520 V236 C25 118 92 34 180 34 C268 34 335 118 335 236 V520"
              stroke="#fdfbf7" stroke-width="6" stroke-linecap="round" stroke-dasharray="0.1 17" fill="none" opacity="0.9"/>
        <path d="M40 520 V238 C40 128 100 52 180 52 C260 52 320 128 320 238 V520"
              stroke="#d8bd85" stroke-width="1" opacity="0.4" fill="none"/>
      </svg>
      <div class="content">
        <div class="eyebrow reveal d1">دعوة زفاف</div>
        <h1 class="reveal d2">دكتور مصطفى</h1>
        <span class="amp reveal d2">و</span>
        <h1 class="reveal d3">صيدلانية تبارك</h1>
        <p class="tagline reveal d4">بمشيئة الله تعالى، يسرّنا دعوتكم<br>لمشاركتنا فرحة عقد قراننا</p>
      </div>
    </div>
    <div class="divider reveal d5"><span class="line"></span><span class="diamond"></span><span class="line"></span></div>
  </section>
 
  <!-- INFO -->
  <div class="info">
 
    <svg class="rose top-left" viewBox="0 0 140 170" xmlns="http://www.w3.org/2000/svg">
      <path class="stem" d="M70 170 C60 130 78 108 66 78" />
      <path class="leaf" d="M64 108 C48 100 34 108 26 122 C42 128 58 122 64 108 Z"/>
      <path class="leaf" d="M72 96 C88 90 100 98 106 112 C90 116 76 110 72 96 Z"/>
      <g transform="translate(60,50)">
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(0)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(60)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(120)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(180)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(240)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(300)"/>
        <circle class="petal-inner" cx="0" cy="0" r="8"/>
      </g>
      <g transform="translate(104,132) scale(0.7)">
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(10)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(70)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(130)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(190)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(250)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(310)"/>
        <circle class="petal-inner" cx="0" cy="0" r="8"/>
      </g>
    </svg>
 
    <svg class="rose top-right" viewBox="0 0 140 170" xmlns="http://www.w3.org/2000/svg">
      <path class="stem" d="M70 170 C60 130 78 108 66 78" />
      <path class="leaf" d="M64 108 C48 100 34 108 26 122 C42 128 58 122 64 108 Z"/>
      <path class="leaf" d="M72 96 C88 90 100 98 106 112 C90 116 76 110 72 96 Z"/>
      <g transform="translate(60,50)">
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(0)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(60)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(120)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(180)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(240)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(300)"/>
        <circle class="petal-inner" cx="0" cy="0" r="8"/>
      </g>
      <g transform="translate(104,132) scale(0.7)">
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(10)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(70)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(130)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(190)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(250)"/>
        <path class="petal" d="M0,0 C-14,-6 -16,-22 -2,-30 C10,-24 14,-8 0,0 Z" transform="rotate(310)"/>
        <circle class="petal-inner" cx="0" cy="0" r="8"/>
      </g>
    </svg>
 
    <div class="info-inner">
      <section style="padding-bottom: 10px;">
        <p class="quote">
          « وَمِنْ آيَاتِهِ أَنْ خَلَقَ لَكُم مِّنْ أَنفُسِكُمْ أَزْوَاجًا لِّتَسْكُنُوا إِلَيْهَا
          وَجَعَلَ بَيْنَكُم مَّوَدَّةً وَرَحْمَةً »
          <span class="src">سورة الروم — آية 21</span>
        </p>
 
        <div class="cards">
          <!-- Merged date + location card -->
          <div class="card">
            <div class="dl-row">
              <div class="dl-col">
                <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><rect x="3" y="5" width="18" height="16" rx="3"/><path d="M3 10h18M8 3v4M16 3v4"/></svg>
                <div class="label">التاريخ</div>
                <div class="value">الثلاثاء<br>١ سبتمبر</div>
                <div class="sub-value">٥:٠٠ مساءً</div>
              </div>
 
              <div class="dl-sep"></div>
 
              <div class="dl-col">
                <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><path d="M12 21s7-6.2 7-12a7 7 0 10-14 0c0 5.8 7 12 7 12z"/><circle cx="12" cy="9" r="2.5"/></svg>
                <div class="label">المكان</div>
                <div class="value">قاعة زمزم<br>الملكية</div>
                <div class="sub-value">كورنيش الأعظمية</div>
              </div>
            </div>
 
            <div class="mini-divider"></div>
 
            <a class="map-btn" href="https://www.google.com/maps/search/?api=1&query=%D9%82%D8%A7%D8%B9%D8%A9%20%D8%B2%D9%85%D8%B2%D9%85%20%D8%A7%D9%84%D9%85%D9%84%D9%83%D9%8A%D8%A9%20%D9%83%D9%88%D8%B1%D9%86%D9%8A%D8%B4%20%D8%A7%D9%84%D8%A7%D8%B9%D8%B8%D9%85%D9%8A%D8%A9" target="_blank" rel="noopener">فتح الموقع على الخريطة</a>
          </div>
 
          <!-- Guest count + entry reminder card -->
          <div class="card">
            <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><circle cx="9" cy="8" r="3.2"/><path d="M3 20c0-3.5 2.7-6 6-6s6 2.5 6 6"/><circle cx="17.5" cy="9" r="2.4"/><path d="M15.7 14.2c2.6.3 4.3 2.5 4.3 5.8"/></svg>
            <div class="label">عدد المرافقين المسموح</div>
            <div class="value" id="guest-count">٠</div>
            <div class="mini-divider"></div>
            <p class="guest-note">يُرجى الاحتفاظ بهذه الدعوة معكم،<br>فستحتاجون لإبرازها عند الدخول</p>
          </div>
        </div>
 
        <div class="countdown-wrap">
          <div class="label">الوقت المتبقي للفرحة</div>
          <div class="countdown">
            <div class="unit"><div class="num" id="cd-days">--</div><div class="unit-label">يوم</div></div>
            <div class="unit"><div class="num" id="cd-hours">--</div><div class="unit-label">ساعة</div></div>
            <div class="unit"><div class="num" id="cd-mins">--</div><div class="unit-label">دقيقة</div></div>
            <div class="unit"><div class="num" id="cd-secs">--</div><div class="unit-label">ثانية</div></div>
          </div>
        </div>
 
        <div class="personal-note">
          <p>الدعوة شخصية<br><span class="no-kids">يُرجى العلم أنه ممنوع اصطحاب الأطفال</span></p>
        </div>
 
        <footer>
          بِحُبٍّ <span class="heart">♥</span> مصطفى و تبارك
        </footer>
      </section>
    </div>
  </div>
</div>
 
<script>
  // ---------- Petals ----------
  const petalContainer = document.getElementById('petals');
  const PETAL_COUNT = 16;
  for(let i=0;i<PETAL_COUNT;i++){
    const p = document.createElement('div');
    p.className = 'petal';
    const left = Math.random()*100;
    const duration = 9 + Math.random()*8;
    const delay = Math.random()*10;
    const drift = (Math.random()*80-40)+'px';
    const size = 8 + Math.random()*8;
    p.style.left = left+'vw';
    p.style.width = size+'px';
    p.style.height = size+'px';
    p.style.animationDuration = duration+'s';
    p.style.animationDelay = delay+'s';
    p.style.setProperty('--drift', drift);
    petalContainer.appendChild(p);
  }
 
  // ---------- Gate open (fixed: smoother, reveals hero only after doors clear) ----------
  const gate = document.getElementById('gate');
  const page = document.getElementById('page');
  let opened = false;
  function openGate(){
    if(opened) return;
    opened = true;
    gate.classList.add('open');
    setTimeout(()=>{ page.classList.add('revealed'); }, 500);
    setTimeout(()=> gate.classList.add('hidden'), 2000);
  }
  gate.addEventListener('click', openGate);
  setTimeout(openGate, 6000); // gentle auto-open fallback
 
  // ---------- Reveal cards on scroll ----------
  const cards = document.querySelectorAll('.card');
  const obs = new IntersectionObserver((entries)=>{
    entries.forEach(e=>{ if(e.isIntersecting) e.target.classList.add('in-view'); });
  }, {threshold: 0.2});
  cards.forEach(c=>obs.observe(c));
 
  // ---------- Countdown ----------
  const weddingDate = new Date("2026-09-01T17:00:00+03:00");
  const arDigits = ['٠','١','٢','٣','٤','٥','٦','٧','٨','٩'];
  function toArabicDigits(n){
    return String(n).split('').map(ch => (ch>='0'&&ch<='9') ? arDigits[ch] : ch).join('');
  }
  function updateCountdown(){
    const now = new Date();
    let diff = weddingDate - now;
    if(diff < 0) diff = 0;
    const days = Math.floor(diff/(1000*60*60*24));
    const hours = Math.floor((diff/(1000*60*60))%24);
    const mins = Math.floor((diff/(1000*60))%60);
    const secs = Math.floor((diff/1000)%60);
    document.getElementById('cd-days').textContent = toArabicDigits(days);
    document.getElementById('cd-hours').textContent = toArabicDigits(String(hours).padStart(2,'0'));
    document.getElementById('cd-mins').textContent = toArabicDigits(String(mins).padStart(2,'0'));
    document.getElementById('cd-secs').textContent = toArabicDigits(String(secs).padStart(2,'0'));
  }
  updateCountdown();
  setInterval(updateCountdown, 1000);
 
  // ---------- Guest count ----------
  // HOW TO CHANGE THE GUEST COUNT PER PERSON:
  // Easiest: add ?guests=N to the end of the link you send, e.g.
  //   yoursite.com/invite.html?guests=2
  // If no ?guests= is in the link, it falls back to GUEST_COUNT_DEFAULT below.
  const GUEST_COUNT_DEFAULT = 0; // <-- change this number to set the fallback default
  const urlParams = new URLSearchParams(window.location.search);
  const guestCount = urlParams.has('guests') && !isNaN(parseInt(urlParams.get('guests')))
    ? Math.max(0, parseInt(urlParams.get('guests')))
    : GUEST_COUNT_DEFAULT;
  document.getElementById('guest-count').textContent = toArabicDigits(guestCount);
</script>
 
</body>
</html>
