
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Something Special for Aradhya 🌺</title>
<link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Nunito:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --pink: #ff6b9d;
    --light-pink: #ffd6e7;
    --peach: #ffb347;
    --cream: #fff9f0;
    --red: #ff4466;
    --purple: #c084fc;
    --soft: #ffe4f0;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Nunito', sans-serif;
    background: var(--cream);
    overflow-x: hidden;
    cursor: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3Ctext y='20' font-size='20'%3E💕%3C/text%3E%3C/svg%3E"), auto;
  }

  /* ===== FLOATING HEARTS BG ===== */
  .hearts-bg { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 0; overflow: hidden; }
  .heart-float {
    position: absolute;
    font-size: 1.5rem;
    animation: floatUp linear infinite;
    opacity: 0.15;
  }
  @keyframes floatUp {
    0% { transform: translateY(100vh) rotate(0deg); opacity: 0.2; }
    100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
  }

  /* ===== PAGES ===== */
  .page {
    min-height: 100vh;
    display: none;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    position: relative;
    z-index: 1;
    padding: 30px 20px;
    text-align: center;
  }
  .page.active { display: flex; }

  /* ===== HERO PAGE ===== */
  #page-hero {
    background: linear-gradient(135deg, #ffe0ec 0%, #fff0fa 50%, #ffecd2 100%);
  }

  .title-main {
    font-family: 'Pacifico', cursive;
    font-size: clamp(2.5rem, 8vw, 5rem);
    color: var(--pink);
    text-shadow: 3px 3px 0 #fff, 6px 6px 0 rgba(255,107,157,0.2);
    animation: bounceIn 1s ease;
    line-height: 1.2;
  }
  .subtitle {
    font-size: 1.2rem;
    color: #b06090;
    margin: 12px 0 30px;
    font-weight: 600;
    animation: fadeUp 1s 0.3s ease both;
  }
  .big-heart {
    font-size: 5rem;
    animation: heartbeat 1.2s ease-in-out infinite;
    display: block;
    margin: 10px 0;
  }
  @keyframes heartbeat {
    0%, 100% { transform: scale(1); }
    14% { transform: scale(1.15); }
    28% { transform: scale(1); }
    42% { transform: scale(1.1); }
    70% { transform: scale(1); }
  }

  /* ===== BUTTONS ===== */
  .btn {
    background: linear-gradient(135deg, var(--pink), var(--purple));
    color: white;
    border: none;
    padding: 16px 40px;
    border-radius: 50px;
    font-size: 1.1rem;
    font-family: 'Nunito', sans-serif;
    font-weight: 800;
    cursor: pointer;
    box-shadow: 0 6px 20px rgba(255,107,157,0.4);
    transition: transform 0.2s, box-shadow 0.2s;
    animation: fadeUp 1s 0.6s ease both;
  }
  .btn:hover { transform: translateY(-3px) scale(1.05); box-shadow: 0 10px 30px rgba(255,107,157,0.5); }
  .btn:active { transform: scale(0.97); }

  /* ===== STARS CATCH GAME ===== */
  #page-game1 {
    background: linear-gradient(160deg, #1a0533 0%, #3d1060 100%);
    color: white;
  }
  #page-game1 .game-title {
    font-family: 'Pacifico', cursive;
    font-size: 2rem;
    color: #f9d5ff;
    margin-bottom: 8px;
  }
  #page-game1 .game-sub { color: #d8a8ff; margin-bottom: 20px; font-size: 1rem; }
  #game1-canvas {
    border: 3px solid rgba(255,255,255,0.2);
    border-radius: 20px;
    background: rgba(0,0,0,0.3);
    display: block;
    margin: 0 auto;
    touch-action: none;
  }
  .score-display {
    font-size: 1.3rem;
    margin: 10px 0;
    color: #f9c8ff;
    font-weight: 700;
  }

  /* ===== MEMORY GAME ===== */
  #page-game2 {
    background: linear-gradient(135deg, #fff0f5, #ffe8ff);
  }
  #page-game2 .game-title {
    font-family: 'Pacifico', cursive;
    font-size: 2rem;
    color: var(--pink);
    margin-bottom: 8px;
  }
  #page-game2 .game-sub { color: #b06090; margin-bottom: 20px; }
  .memory-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
    max-width: 360px;
    margin: 0 auto 20px;
  }
  .mem-card {
    width: 75px;
    height: 75px;
    border-radius: 14px;
    background: linear-gradient(135deg, var(--pink), var(--purple));
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.8rem;
    cursor: pointer;
    transition: transform 0.3s;
    box-shadow: 0 4px 12px rgba(255,107,157,0.3);
    perspective: 300px;
    position: relative;
    user-select: none;
  }
  .mem-card.flipped { animation: flipCard 0.3s ease; }
  .mem-card.matched { background: linear-gradient(135deg, #43e97b, #38f9d7); animation: matchPop 0.4s ease; }
  @keyframes flipCard { 0% { transform: rotateY(90deg); } 100% { transform: rotateY(0deg); } }
  @keyframes matchPop { 0%,100% { transform: scale(1); } 50% { transform: scale(1.2); } }
  .card-back { display: none; }
  .mem-card.show .card-back { display: block; }
  .mem-card.show .card-front { display: none; }
  .card-front { font-size: 1.8rem; }

  /* ===== LOVE LETTER ===== */
  #page-letter {
    background: linear-gradient(135deg, #fff5f8, #fef3e2);
  }
  .letter-card {
    background: white;
    border-radius: 24px;
    padding: 36px 30px;
    max-width: 520px;
    box-shadow: 0 10px 40px rgba(255,107,157,0.15), 0 2px 8px rgba(0,0,0,0.05);
    position: relative;
    overflow: hidden;
    border: 2px solid var(--light-pink);
    animation: fadeUp 0.8s ease;
  }
  .letter-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 8px;
    background: linear-gradient(90deg, var(--pink), var(--purple), var(--peach));
  }
  .letter-name {
    font-family: 'Pacifico', cursive;
    font-size: 2rem;
    color: var(--pink);
    margin-bottom: 16px;
  }
  .letter-body {
    font-size: 1.05rem;
    color: #555;
    line-height: 1.9;
    text-align: left;
  }
  .letter-body span.highlight {
    color: var(--pink);
    font-weight: 700;
  }
  .letter-sign {
    text-align: right;
    font-family: 'Pacifico', cursive;
    color: var(--purple);
    margin-top: 20px;
    font-size: 1.2rem;
  }
  .letter-hearts {
    position: absolute;
    top: 14px; right: 14px;
    font-size: 1.5rem;
    opacity: 0.3;
  }

  /* ===== CONFESSION PAGE ===== */
  #page-confession {
    background: linear-gradient(135deg, #1a0533 0%, #5c0a3e 50%, #1a0533 100%);
    color: white;
  }
  .confess-title {
    font-family: 'Pacifico', cursive;
    font-size: clamp(2rem, 7vw, 4rem);
    color: #ffb3d9;
    margin-bottom: 16px;
    animation: glow 2s ease-in-out infinite alternate;
  }
  @keyframes glow {
    from { text-shadow: 0 0 10px #ff6b9d; }
    to { text-shadow: 0 0 30px #ff6b9d, 0 0 60px #ff6b9d; }
  }
  .confess-text {
    font-size: 1.1rem;
    color: #f0c0d8;
    max-width: 480px;
    line-height: 1.8;
    margin-bottom: 40px;
  }
  .answer-btns {
    display: flex;
    gap: 20px;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
  }
  .btn-yes {
    background: linear-gradient(135deg, #ff6b9d, #ff4466);
    color: white;
    border: none;
    padding: 18px 50px;
    border-radius: 50px;
    font-size: 1.3rem;
    font-family: 'Nunito', sans-serif;
    font-weight: 800;
    cursor: pointer;
    box-shadow: 0 6px 25px rgba(255,68,102,0.5);
    transition: transform 0.2s, box-shadow 0.2s;
    animation: pulseYes 1.5s ease-in-out infinite;
  }
  @keyframes pulseYes {
    0%,100% { box-shadow: 0 6px 25px rgba(255,68,102,0.5); }
    50% { box-shadow: 0 6px 40px rgba(255,68,102,0.9), 0 0 20px rgba(255,107,157,0.6); }
  }
  .btn-yes:hover { transform: scale(1.1); }

  .btn-no {
    background: rgba(255,255,255,0.1);
    color: rgba(255,255,255,0.5);
    border: 2px solid rgba(255,255,255,0.2);
    padding: 18px 50px;
    border-radius: 50px;
    font-size: 1.3rem;
    font-family: 'Nunito', sans-serif;
    font-weight: 800;
    cursor: pointer;
    transition: transform 0.1s;
    position: relative;
  }

  /* ===== GIFT BOX PAGE ===== */
  #page-gift {
    background: linear-gradient(135deg, #ff9a9e, #fecfef, #ffecd2);
    animation: bgShift 4s ease-in-out infinite alternate;
  }
  @keyframes bgShift {
    from { background: linear-gradient(135deg, #ff9a9e, #fecfef, #ffecd2); }
    to { background: linear-gradient(135deg, #fecfef, #ffecd2, #a8edea); }
  }

  .gift-wrapper {
    position: relative;
    display: inline-block;
    cursor: pointer;
    transition: transform 0.2s;
  }
  .gift-wrapper:hover { transform: scale(1.05); }

  .gift-box {
    width: 160px;
    height: 140px;
    background: linear-gradient(135deg, #ff6b9d, #c084fc);
    border-radius: 10px;
    position: relative;
    box-shadow: 0 10px 30px rgba(255,107,157,0.4);
    animation: giftShake 0.5s ease infinite alternate;
  }
  @keyframes giftShake {
    from { transform: rotate(-3deg); }
    to { transform: rotate(3deg); }
  }
  .gift-lid {
    width: 180px;
    height: 40px;
    background: linear-gradient(135deg, #ff4466, #9333ea);
    border-radius: 10px;
    position: absolute;
    top: -20px;
    left: -10px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    transition: transform 0.6s ease;
  }
  .gift-ribbon-h {
    position: absolute;
    width: 100%;
    height: 18px;
    background: gold;
    top: 50%;
    transform: translateY(-50%);
    border-radius: 4px;
  }
  .gift-ribbon-v {
    position: absolute;
    width: 18px;
    height: 100%;
    background: gold;
    left: 50%;
    transform: translateX(-50%);
    border-radius: 4px;
  }
  .gift-ribbon-lid {
    position: absolute;
    width: 18px;
    height: 100%;
    background: gold;
    left: 50%;
    transform: translateX(-50%);
    border-radius: 4px;
  }
  .gift-bow {
    position: absolute;
    top: -50px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 2.5rem;
  }
  .gift-label {
    font-family: 'Nunito', sans-serif;
    font-size: 1rem;
    color: white;
    font-weight: 700;
    margin-top: 20px;
    animation: bounce 1s ease-in-out infinite;
  }
  @keyframes bounce {
    0%,100% { transform: translateY(0); }
    50% { transform: translateY(-8px); }
  }

  /* Open state */
  .gift-wrapper.opened .gift-lid {
    transform: translateY(-80px) rotate(-20deg);
    opacity: 0;
  }
  .gift-wrapper.opened .gift-box { animation: none; }

  /* ===== PUPPY ===== */
  .puppy-container {
    display: none;
    flex-direction: column;
    align-items: center;
    animation: popIn 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
    margin-top: 20px;
  }
  .puppy-container.show { display: flex; }
  @keyframes popIn {
    0% { transform: scale(0) rotate(-10deg); opacity: 0; }
    100% { transform: scale(1) rotate(0deg); opacity: 1; }
  }

  /* CSS Puppy */
  .puppy {
    position: relative;
    width: 130px;
    height: 130px;
    animation: puppyWiggle 0.8s ease-in-out infinite alternate;
  }
  @keyframes puppyWiggle {
    from { transform: rotate(-5deg); }
    to { transform: rotate(5deg); }
  }
  .puppy-body {
    width: 90px; height: 75px;
    background: #d4a574;
    border-radius: 50% 50% 50% 50% / 40% 40% 60% 60%;
    position: absolute;
    bottom: 0; left: 20px;
  }
  .puppy-head {
    width: 80px; height: 70px;
    background: #d4a574;
    border-radius: 50%;
    position: absolute;
    top: 5px; left: 25px;
    z-index: 2;
  }
  .puppy-ear-left {
    width: 30px; height: 38px;
    background: #b8865a;
    border-radius: 50% 50% 50% 50% / 40% 40% 60% 60%;
    position: absolute;
    top: 8px; left: 8px;
    transform: rotate(-20deg);
    z-index: 1;
    animation: earFlap 1s ease-in-out infinite alternate;
  }
  .puppy-ear-right {
    width: 30px; height: 38px;
    background: #b8865a;
    border-radius: 50% 50% 50% 50% / 40% 40% 60% 60%;
    position: absolute;
    top: 8px; right: 8px;
    transform: rotate(20deg);
    z-index: 1;
    animation: earFlap 1s 0.3s ease-in-out infinite alternate-reverse;
  }
  @keyframes earFlap {
    from { transform: rotate(-20deg); }
    to { transform: rotate(-35deg); }
  }
  .puppy-eye-left, .puppy-eye-right {
    width: 14px; height: 14px;
    background: #2c1810;
    border-radius: 50%;
    position: absolute;
    top: 22px;
    animation: blink 3s ease-in-out infinite;
  }
  .puppy-eye-left { left: 16px; }
  .puppy-eye-right { right: 16px; }
  .puppy-eye-left::after, .puppy-eye-right::after {
    content: '';
    width: 5px; height: 5px;
    background: white;
    border-radius: 50%;
    position: absolute;
    top: 2px; right: 2px;
  }
  @keyframes blink {
    0%,96%,100% { transform: scaleY(1); }
    98% { transform: scaleY(0.1); }
  }
  .puppy-nose {
    width: 20px; height: 14px;
    background: #8b5e3c;
    border-radius: 50%;
    position: absolute;
    top: 38px;
    left: 50%;
    transform: translateX(-50%);
  }
  .puppy-mouth {
    width: 24px; height: 12px;
    border-bottom: 3px solid #8b5e3c;
    border-radius: 0 0 50% 50%;
    position: absolute;
    top: 50px;
    left: 50%;
    transform: translateX(-50%);
  }
  .puppy-tail {
    width: 12px; height: 35px;
    background: #d4a574;
    border-radius: 50%;
    position: absolute;
    right: 8px; bottom: 10px;
    transform-origin: bottom center;
    animation: tailWag 0.4s ease-in-out infinite alternate;
  }
  @keyframes tailWag {
    from { transform: rotate(-30deg); }
    to { transform: rotate(30deg); }
  }
  .puppy-paw-left, .puppy-paw-right {
    width: 22px; height: 16px;
    background: #d4a574;
    border-radius: 50%;
    position: absolute;
    bottom: 0;
  }
  .puppy-paw-left { left: 20px; }
  .puppy-paw-right { left: 52px; }
  .puppy-cheek-left, .puppy-cheek-right {
    width: 16px; height: 10px;
    background: rgba(255,150,150,0.5);
    border-radius: 50%;
    position: absolute;
    top: 36px;
  }
  .puppy-cheek-left { left: 6px; }
  .puppy-cheek-right { right: 6px; }

  /* Puppy speech bubble */
  .speech-bubble {
    background: white;
    border-radius: 20px;
    padding: 14px 22px;
    max-width: 280px;
    position: relative;
    margin-bottom: 10px;
    box-shadow: 0 4px 20px rgba(255,107,157,0.2);
    border: 2px solid var(--light-pink);
    animation: fadeUp 0.6s 0.5s ease both;
  }
  .speech-bubble::after {
    content: '';
    position: absolute;
    bottom: -14px;
    left: 50%;
    transform: translateX(-50%);
    border: 8px solid transparent;
    border-top-color: white;
  }
  .speech-bubble p {
    color: #c0407a;
    font-weight: 700;
    font-size: 1rem;
    line-height: 1.5;
  }

  /* ===== CONFETTI ===== */
  .confetti-piece {
    position: fixed;
    width: 12px; height: 12px;
    top: -20px;
    animation: confettiFall linear forwards;
    border-radius: 2px;
    z-index: 100;
  }
  @keyframes confettiFall {
    0% { transform: translateY(0) rotate(0deg); opacity: 1; }
    100% { transform: translateY(100vh) rotate(720deg); opacity: 0; }
  }

  /* ===== CELEBRATION PAGE ===== */
  #page-celebrate {
    background: linear-gradient(135deg, #ff9a9e, #fad0c4, #ffecd2);
  }
  .celebrate-title {
    font-family: 'Pacifico', cursive;
    font-size: clamp(2.5rem, 8vw, 5rem);
    color: white;
    text-shadow: 3px 3px 0 rgba(255,68,102,0.3), 0 0 30px rgba(255,150,150,0.8);
    animation: celebrate 1s ease-in-out infinite alternate;
  }
  @keyframes celebrate {
    from { transform: scale(1) rotate(-1deg); }
    to { transform: scale(1.05) rotate(1deg); }
  }
  .celebrate-sub {
    font-size: 1.3rem;
    color: rgba(255,255,255,0.9);
    margin: 16px 0 30px;
    font-weight: 700;
  }

  /* ===== ANIMATIONS ===== */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes bounceIn {
    0% { transform: scale(0.3); opacity: 0; }
    50% { transform: scale(1.1); }
    70% { transform: scale(0.9); }
    100% { transform: scale(1); opacity: 1; }
  }

  /* ===== PROGRESS DOTS ===== */
  .progress {
    display: flex;
    gap: 8px;
    justify-content: center;
    margin-top: 24px;
  }
  .dot {
    width: 10px; height: 10px;
    border-radius: 50%;
    background: rgba(255,107,157,0.25);
    transition: background 0.3s;
  }
  .dot.active { background: var(--pink); }

  /* ===== UTILS ===== */
  .emoji-rain { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 50; }

  /* ===== RESPONSIVE ===== */
  @media (max-width: 400px) {
    .memory-grid { grid-template-columns: repeat(4, 1fr); gap: 6px; }
    .mem-card { width: 62px; height: 62px; font-size: 1.5rem; }
    .gift-box { width: 120px; height: 100px; }
    .gift-lid { width: 140px; }
  }

  /* Stars game canvas sizing */
  @media (max-width: 600px) {
    #game1-canvas { width: 300px !important; height: 260px !important; }
  }

  /* Next btn small text */
  .next-hint { color: #c095b0; font-size: 0.85rem; margin-top: 10px; }
</style>
</head>
<body>

<!-- Floating hearts background -->
<div class="hearts-bg" id="heartsBg"></div>

<!-- ========== PAGE 1: HERO ========== -->
<div class="page active" id="page-hero">
  <span class="big-heart">💝</span>
  <h1 class="title-main">Hey, Aradhya!</h1>
  <p class="subtitle">I made something special just for you 🌸</p>
  <p style="color:#b06090;max-width:360px;margin-bottom:24px;font-size:1rem;">Before I say what's on my mind… let's have a little fun first. Are you ready? 🎮</p>
  <button class="btn" onclick="goTo('page-game1')">Let's Go! ✨</button>
  <div class="progress">
    <div class="dot active"></div>
    <div class="dot"></div>
    <div class="dot"></div>
    <div class="dot"></div>
    <div class="dot"></div>
  </div>
</div>

<!-- ========== PAGE 2: STAR CATCH GAME ========== -->
<div class="page" id="page-game1">
  <h2 class="game-title">⭐ Catch the Stars!</h2>
  <p class="game-sub">Catch 10 stars with your basket 🧺</p>
  <div class="score-display">Stars: <span id="star-score">0</span> / 10</div>
  <canvas id="game1-canvas" width="360" height="300"></canvas>
  <p class="next-hint" style="color:#d8a8ff;margin-top:14px;">Catch 10 stars to continue 💫</p>
  <div class="progress">
    <div class="dot active"></div>
    <div class="dot active"></div>
    <div class="dot"></div>
    <div class="dot"></div>
    <div class="dot"></div>
  </div>
</div>

<!-- ========== PAGE 3: MEMORY GAME ========== -->
<div class="page" id="page-game2">
  <h2 class="game-title">💖 Match the Love!</h2>
  <p class="game-sub">Find all matching pairs to unlock my letter 💌</p>
  <div class="score-display">Pairs: <span id="mem-score">0</span> / 8</div>
  <div class="memory-grid" id="memoryGrid"></div>
  <div class="progress">
    <div class="dot active"></div>
    <div class="dot active"></div>
    <div class="dot active"></div>
    <div class="dot"></div>
    <div class="dot"></div>
  </div>
</div>

<!-- ========== PAGE 4: LOVE LETTER ========== -->
<div class="page" id="page-letter">
  <div class="letter-card">
    <div class="letter-hearts">💕💕</div>
    <h2 class="letter-name">Dear Aradhya,</h2>
    <div class="letter-body">
      <p>There are things I've been wanting to tell you, but words always felt <span class="highlight">too small</span> for what I feel.</p>
      <br>
      <p>You have this way of making everything around you feel <span class="highlight">brighter</span>. The way you smile, the way you talk, the way you just… <span class="highlight">exist</span> — it honestly makes my day better without you even trying.</p>
      <br>
      <p>I've been holding these feelings for a while now, and I thought — why not make it <span class="highlight">special</span>? Because you deserve special things.</p>
      <br>
      <p>So I'm going to ask you something on the next page. And I really, really hope the answer is <span class="highlight">yes</span> 💕</p>
    </div>
    <div class="letter-sign">— Someone who likes you a lot 🌸</div>
  </div>
  <button class="btn" style="margin-top:28px;" onclick="goTo('page-confession')">Continue 💌</button>
  <div class="progress" style="margin-top:18px;">
    <div class="dot active"></div>
    <div class="dot active"></div>
    <div class="dot active"></div>
    <div class="dot active"></div>
    <div class="dot"></div>
  </div>
</div>

<!-- ========== PAGE 5: CONFESSION ========== -->
<div class="page" id="page-confession">
  <div style="font-size:4rem;margin-bottom:16px;animation:heartbeat 1.2s ease-in-out infinite;">💗</div>
  <h1 class="confess-title">Aradhya…</h1>
  <p class="confess-text">
    Will you be <strong style="color:#ffb3d9;">my person?</strong> ✨<br><br>
    My smile-causer, my day-brightener,<br>
    the one I want to share silly memes with,<br>
    and hopefully — <strong style="color:#ffb3d9;">my girlfriend?</strong> 🌸
  </p>
  <div class="answer-btns">
    <button class="btn-yes" onclick="sayYes()">Yes! 💖</button>
    <button class="btn-no" id="noBtn" onmouseover="runAway(this)" ontouchstart="runAway(this)">No 🚫</button>
  </div>
  <p style="color:rgba(255,255,255,0.3);font-size:0.8rem;margin-top:20px;">(psst... the No button is a bit shy 🙈)</p>
  <div class="progress" style="margin-top:24px;">
    <div class="dot active"></div>
    <div class="dot active"></div>
    <div class="dot active"></div>
    <div class="dot active"></div>
    <div class="dot active"></div>
  </div>
</div>

<!-- ========== PAGE 6: GIFT ========== -->
<div class="page" id="page-gift">
  <h2 style="font-family:'Pacifico',cursive;font-size:2.2rem;color:#c0047a;margin-bottom:8px;">You said YES!! 🎉</h2>
  <p style="color:#b06090;margin-bottom:28px;font-size:1.05rem;">Now open your gift… 🎁</p>

  <div class="gift-wrapper" id="giftWrapper" onclick="openGift()">
    <div class="gift-box">
      <div class="gift-ribbon-h"></div>
      <div class="gift-ribbon-v"></div>
    </div>
    <div class="gift-lid">
      <div class="gift-ribbon-lid"></div>
    </div>
    <div class="gift-bow">🎀</div>
    <div class="gift-label">Tap to open! ✨</div>
  </div>

  <!-- Puppy -->
  <div class="puppy-container" id="puppyContainer">
    <div class="speech-bubble">
      <p>Woof woof! 🐾<br>She said YES!! I'm SO happy for you both! 🥹💕<br>You're gonna be the BEST couple ever!! 🎉</p>
    </div>
    <div class="puppy">
      <div class="puppy-ear-left"></div>
      <div class="puppy-ear-right"></div>
      <div class="puppy-head">
        <div class="puppy-eye-left"></div>
        <div class="puppy-eye-right"></div>
        <div class="puppy-cheek-left"></div>
        <div class="puppy-cheek-right"></div>
        <div class="puppy-nose"></div>
        <div class="puppy-mouth"></div>
      </div>
      <div class="puppy-body">
        <div class="puppy-tail"></div>
        <div class="puppy-paw-left"></div>
        <div class="puppy-paw-right"></div>
      </div>
    </div>
    <p style="font-size:1.3rem;margin-top:8px;animation:heartbeat 1s ease infinite;">🐾💕🐾</p>
    <button class="btn" style="margin-top:20px;" onclick="goTo('page-celebrate')">Continue 🎊</button>
  </div>
</div>

<!-- ========== PAGE 7: CELEBRATE ========== -->
<div class="page" id="page-celebrate">
  <div style="font-size:5rem;animation:heartbeat 1s ease infinite;margin-bottom:10px;">🥰</div>
  <h1 class="celebrate-title">We're a thing! 💕</h1>
  <p class="celebrate-sub">Aradhya & her person 🌸</p>
  <div style="background:rgba(255,255,255,0.6);border-radius:20px;padding:24px 30px;max-width:400px;box-shadow:0 8px 30px rgba(255,107,157,0.2);">
    <p style="color:#c0047a;font-size:1rem;font-weight:700;line-height:1.9;">
      💌 This moment is saved forever<br>
      🌸 I'll make every day count<br>
      🐾 That puppy is cheering for us<br>
      💖 Thank you for saying yes, Aradhya<br>
      ✨ This is just the beginning!
    </p>
  </div>
  <div style="margin-top:28px;font-size:2.5rem;animation:bounce 0.6s ease-in-out infinite alternate;">
    🎉💕🎉💕🎉
  </div>
</div>

<script>
// ===== FLOATING HEARTS =====
function spawnHearts() {
  const container = document.getElementById('heartsBg');
  const emojis = ['💕','💗','💖','🌸','✨','💝','🩷'];
  for (let i = 0; i < 18; i++) {
    const h = document.createElement('div');
    h.className = 'heart-float';
    h.textContent = emojis[Math.floor(Math.random() * emojis.length)];
    h.style.left = Math.random() * 100 + '%';
    h.style.animationDuration = (6 + Math.random() * 10) + 's';
    h.style.animationDelay = (Math.random() * 10) + 's';
    h.style.fontSize = (1 + Math.random() * 1.5) + 'rem';
    container.appendChild(h);
  }
}
spawnHearts();

// ===== PAGE NAVIGATION =====
function goTo(id) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  window.scrollTo(0,0);
  if (id === 'page-game1') startStarGame();
  if (id === 'page-game2') initMemoryGame();
}

// ===== STAR CATCH GAME =====
function startStarGame() {
  const canvas = document.getElementById('game1-canvas');
  const ctx = canvas.getContext('2d');
  let score = 0;
  let stars = [];
  let basket = { x: 160, y: 270, w: 70, h: 20 };
  let animId;
  let done = false;

  function createStar() {
    stars.push({
      x: Math.random() * (canvas.width - 30) + 15,
      y: -20,
      speed: 2.5 + Math.random() * 2,
      size: 22 + Math.random() * 12,
      rotation: 0,
      rotSpeed: (Math.random() - 0.5) * 0.1
    });
  }

  let starInterval = setInterval(() => {
    if (!done) createStar();
  }, 900);

  canvas.addEventListener('mousemove', e => {
    const rect = canvas.getBoundingClientRect();
    basket.x = (e.clientX - rect.left) * (canvas.width / rect.width) - basket.w / 2;
  });
  canvas.addEventListener('touchmove', e => {
    e.preventDefault();
    const rect = canvas.getBoundingClientRect();
    basket.x = (e.touches[0].clientX - rect.left) * (canvas.width / rect.width) - basket.w / 2;
  }, { passive: false });

  function draw() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);

    // stars
    stars.forEach((s, i) => {
      s.y += s.speed;
      s.rotation += s.rotSpeed;
      ctx.save();
      ctx.translate(s.x, s.y);
      ctx.rotate(s.rotation);
      ctx.font = s.size + 'px serif';
      ctx.textAlign = 'center';
      ctx.fillText('⭐', 0, 0);
      ctx.restore();

      // catch
      if (s.y > basket.y && s.y < basket.y + basket.h + 20 &&
          s.x > basket.x && s.x < basket.x + basket.w) {
        stars.splice(i, 1);
        score++;
        document.getElementById('star-score').textContent = score;
        spawnParticle(s.x, s.y);
        if (score >= 10 && !done) {
          done = true;
          clearInterval(starInterval);
          cancelAnimationFrame(animId);
          setTimeout(() => goTo('page-game2'), 700);
        }
      }
      if (s.y > canvas.height + 20) stars.splice(i, 1);
    });

    // basket
    const bx = Math.max(0, Math.min(canvas.width - basket.w, basket.x));
    const gradient = ctx.createLinearGradient(bx, basket.y, bx + basket.w, basket.y + basket.h);
    gradient.addColorStop(0, '#ff6b9d');
    gradient.addColorStop(1, '#c084fc');
    ctx.fillStyle = gradient;
    ctx.beginPath();
    ctx.roundRect(bx, basket.y, basket.w, basket.h, 10);
    ctx.fill();
    ctx.font = '1.2rem serif';
    ctx.fillText('🧺', bx + basket.w / 2 - 10, basket.y + 16);

    animId = requestAnimationFrame(draw);
  }
  draw();
}

function spawnParticle(x, y) {
  const canvas = document.getElementById('game1-canvas');
  const rect = canvas.getBoundingClientRect();
  const actualX = rect.left + x * (rect.width / canvas.width);
  const actualY = rect.top + y * (rect.height / canvas.height);
  for (let i = 0; i < 5; i++) {
    const p = document.createElement('div');
    p.style.cssText = `position:fixed;left:${actualX}px;top:${actualY}px;font-size:1.2rem;pointer-events:none;z-index:99;animation:confettiFall 0.8s ease forwards;`;
    p.textContent = ['💫','✨','🌟'][Math.floor(Math.random()*3)];
    document.body.appendChild(p);
    setTimeout(() => p.remove(), 900);
  }
}

// ===== MEMORY GAME =====
function initMemoryGame() {
  const emojis = ['💖','🌸','🐾','🎀','💌','🌷','🍓','✨'];
  const cards = [...emojis, ...emojis].sort(() => Math.random() - 0.5);
  const grid = document.getElementById('memoryGrid');
  grid.innerHTML = '';
  let flipped = [], matched = 0, locked = false;

  cards.forEach((em, i) => {
    const card = document.createElement('div');
    card.className = 'mem-card';
    card.innerHTML = `<span class="card-front">💝</span><span class="card-back">${em}</span>`;
    card.dataset.val = em;
    card.addEventListener('click', () => {
      if (locked || card.classList.contains('matched') || card.classList.contains('show')) return;
      card.classList.add('show', 'flipped');
      flipped.push(card);
      if (flipped.length === 2) {
        locked = true;
        setTimeout(() => {
          if (flipped[0].dataset.val === flipped[1].dataset.val) {
            flipped.forEach(c => c.classList.add('matched'));
            matched++;
            document.getElementById('mem-score').textContent = matched;
            if (matched === 8) setTimeout(() => goTo('page-letter'), 600);
          } else {
            flipped.forEach(c => c.classList.remove('show', 'flipped'));
          }
          flipped = [];
          locked = false;
        }, 800);
      }
    });
    grid.appendChild(card);
  });
}

// ===== NO BUTTON RUN =====
function runAway(btn) {
  const vw = window.innerWidth;
  const vh = window.innerHeight;
  const bw = 160, bh = 60;
  const x = Math.random() * (vw - bw);
  const y = Math.random() * (vh - bh);
  btn.style.position = 'fixed';
  btn.style.left = x + 'px';
  btn.style.top = y + 'px';
  btn.style.zIndex = '999';
  btn.style.transition = 'left 0.3s ease, top 0.3s ease';
}

// ===== YES BUTTON =====
function sayYes() {
  launchConfetti();
  setTimeout(() => goTo('page-gift'), 800);
}

// ===== CONFETTI =====
function launchConfetti() {
  const colors = ['#ff6b9d','#c084fc','#ffb347','#43e97b','#ff4466','#38f9d7','#ffd700'];
  for (let i = 0; i < 80; i++) {
    setTimeout(() => {
      const c = document.createElement('div');
      c.className = 'confetti-piece';
      c.style.left = Math.random() * 100 + 'vw';
      c.style.background = colors[Math.floor(Math.random() * colors.length)];
      c.style.animationDuration = (1.5 + Math.random() * 2) + 's';
      c.style.animationDelay = (Math.random() * 0.5) + 's';
      c.style.borderRadius = Math.random() > 0.5 ? '50%' : '2px';
      c.style.width = c.style.height = (8 + Math.random() * 12) + 'px';
      document.body.appendChild(c);
      setTimeout(() => c.remove(), 4000);
    }, i * 20);
  }
}

// ===== GIFT BOX =====
function openGift() {
  const wrapper = document.getElementById('giftWrapper');
  if (wrapper.classList.contains('opened')) return;
  wrapper.classList.add('opened');
  wrapper.querySelector('.gift-label').textContent = '🎊 ';
  launchConfetti();
  setTimeout(() => {
    document.getElementById('puppyContainer').classList.add('show');
    // emoji rain
    const emojis = ['💖','🌸','🎉','✨','💝','🐾'];
    for (let i = 0; i < 30; i++) {
      setTimeout(() => {
        const e = document.createElement('div');
        e.style.cssText = `position:fixed;left:${Math.random()*100}vw;top:-40px;font-size:1.6rem;pointer-events:none;z-index:99;animation:confettiFall ${2+Math.random()*2}s ease forwards;`;
        e.textContent = emojis[Math.floor(Math.random()*emojis.length)];
        document.body.appendChild(e);
        setTimeout(() => e.remove(), 4000);
      }, i * 120);
    }
  }, 700);
}
</script>
</body>
</html>
