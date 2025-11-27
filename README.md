<!doctype html>
<html lang="ru">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Анимация — GitHub Pages</title>
<style>
  :root{
    --bg: #0f1724;
    --accent: #39b3a6;
    --muted: #9aa4b2;
  }
  html,body{height:100%;margin:0;font-family:Inter,system-ui,Arial;background:var(--bg);color:#eef;}
  .wrap{
    min-height:100%;
    display:flex;
    align-items:center;
    justify-content:center;
    gap:40px;
    flex-direction:column;
    padding:40px;
    box-sizing:border-box;
  }

  /* Карточка с анимацией логотипа */
  .card{
    width:320px;
    height:320px;
    border-radius:24px;
    background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    box-shadow: 0 8px 30px rgba(0,0,0,0.6);
    display:flex;
    align-items:center;
    justify-content:center;
    position:relative;
    overflow:hidden;
  }

  /* Элемент — «логотип» из трёх кругов */
  .logo{
    position:relative;
    width:160px;
    height:160px;
  }
  .dot{
    position:absolute;
    width:56px;
    height:56px;
    border-radius:50%;
    background:var(--accent);
    transform-origin:center;
    filter:drop-shadow(0 8px 18px rgba(0,0,0,0.5));
    animation: float 3s ease-in-out infinite;
  }
  .dot:nth-child(1){ left:0; top:50%; transform:translateY(-50%); animation-delay:0s; background:linear-gradient(135deg,#39b3a6,#2ea39b);}
  .dot:nth-child(2){ left:50%; top:0; transform:translateX(-50%); animation-delay:.2s; background:linear-gradient(135deg,#6f87ff,#5f76f0);}
  .dot:nth-child(3){ right:0; top:50%; transform:translateY(-50%); animation-delay:.4s; background:linear-gradient(135deg,#ff7a6b,#ff6a5a);}

  /* вращающиеся кольца */
  .ring{
    position:absolute;
    width:240px;
    height:240px;
    border-radius:50%;
    border:2px solid rgba(255,255,255,0.03);
    left:50%; top:50%; transform:translate(-50%,-50%);
    animation: spin 10s linear infinite;
    pointer-events:none;
  }
  .ring.r2{ width:280px; height:280px; border-style:dashed; animation-duration:14s; opacity:.6;}
  .ring.r3{ width:200px; height:200px; border-style:solid; animation-duration:7s; opacity:.35;}

  @keyframes float{
    0%   { transform: translateY(-6px) scale(1); }
    50%  { transform: translateY(6px)  scale(1.05); }
    100% { transform: translateY(-6px) scale(1); }
  }
  @keyframes spin{
    from{ transform: translate(-50%,-50%) rotate(0deg); }
    to  { transform: translate(-50%,-50%) rotate(360deg); }
  }

  /* подпись */
  .caption{
    color:var(--muted);
    font-size:14px;
    text-align:center;
    max-width:420px;
  }

  /* адаптив */
  @media (max-width:420px){
    .card{ width:260px; height:260px; }
    .logo{ width:120px; height:120px; }
    .dot{ width:44px; height:44px; }
  }
</style>
</head>
<body>
  <div class="wrap">
    <div class="card" role="img" aria-label="Анимированное лого">
      <div class="ring r1"></div>
      <div class="ring r2"></div>
      <div class="ring r3"></div>

      <div class="logo" aria-hidden="true">
        <div class="dot"></div>
        <div class="dot"></div>
        <div class="dot"></div>
      </div>
    </div>

    <div class="caption">
      Простая CSS-анимация — можно менять цвета, размер и скорость. <br>
      Чтобы опубликовать: положи этот файл как <code>index.html</code> в репозиторий и включи GitHub Pages.
    </div>
  </div>
</body>
</html>
