<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>С Днём Рождения! 🎉</title>
<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    font-family: 'Segoe UI', 'Arial', sans-serif;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 40%, #a18cd1 100%);
    background-size: 400% 400%;
    animation: gradientShift 12s ease infinite;
    overflow-x: hidden;
    padding: 20px;
  }

  @keyframes gradientShift {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  /* Плавающие шарики на фоне */
  .balloon {
    position: fixed;
    bottom: -150px;
    width: 60px;
    height: 75px;
    border-radius: 50% 50% 50% 50% / 55% 55% 45% 45%;
    opacity: 0.55;
    animation: floatUp linear infinite;
    z-index: 0;
    pointer-events: none;
  }
  .balloon::after {
    content: '';
    position: absolute;
    bottom: -28px;
    left: 50%;
    width: 2px;
    height: 30px;
    background: rgba(255,255,255,0.7);
    transform: translateX(-50%);
  }
  @keyframes floatUp {
    0% { transform: translateY(0) rotate(-4deg); }
    50% { transform: translateY(-55vh) rotate(4deg); }
    100% { transform: translateY(-125vh) rotate(-4deg); }
  }

  .card {
    position: relative;
    z-index: 2;
    background: rgba(255, 255, 255, 0.82);
    backdrop-filter: blur(14px);
    -webkit-backdrop-filter: blur(14px);
    border-radius: 32px;
    padding: 50px 40px 45px;
    max-width: 560px;
    width: 100%;
    text-align: center;
    box-shadow: 0 25px 60px rgba(120, 40, 120, 0.35),
                0 0 0 1px rgba(255,255,255,0.6) inset;
    animation: cardIn 1s cubic-bezier(.2,.8,.3,1.1);
  }

  @keyframes cardIn {
    from { opacity: 0; transform: translateY(40px) scale(0.94); }
    to { opacity: 1; transform: translateY(0) scale(1); }
  }

  .cake {
    font-size: 78px;
    line-height: 1;
    display: inline-block;
    animation: bounce 2.2s ease-in-out infinite;
    filter: drop-shadow(0 8px 12px rgba(200, 80, 120, 0.35));
  }
  @keyframes bounce {
    0%, 100% { transform: translateY(0) rotate(-3deg); }
    50% { transform: translateY(-16px) rotate(3deg); }
  }

  h1 {
    font-size: clamp(1.9rem, 6vw, 2.9rem);
    margin: 18px 0 6px;
    background: linear-gradient(90deg, #e91e63, #9c27b0, #ff5722);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    font-weight: 800;
    letter-spacing: 0.5px;
  }

  .name {
    font-size: clamp(1.4rem, 4.5vw, 2rem);
    color: #6a1b9a;
    font-weight: 700;
    margin-bottom: 22px;
  }
  .name span {
    border-bottom: 3px dashed #f06292;
    padding-bottom: 2px;
  }

  .message {
    font-size: clamp(1rem, 2.6vw, 1.15rem);
    line-height: 1.75;
    color: #4a2c5a;
    margin-bottom: 30px;
    white-space: pre-line;
  }

  .btn {
    position: relative;
    display: inline-block;
    padding: 16px 42px;
    font-size: 1.1rem;
    font-weight: 700;
    color: #fff;
    background: linear-gradient(135deg, #ff4081, #ab47bc);
    border: none;
    border-radius: 50px;
    cursor: pointer;
    box-shadow: 0 10px 25px rgba(233, 30, 99, 0.45);
    transition: transform 0.18s ease, box-shadow 0.18s ease;
    overflow: hidden;
    font-family: inherit;
  }
  .btn:hover {
    transform: translateY(-3px) scale(1.04);
    box-shadow: 0 16px 34px rgba(233, 30, 99, 0.55);
  }
  .btn:active {
    transform: translateY(1px) scale(0.98);
  }
  .btn::before {
    content: '';
    position: absolute;
    top: 0; left: -80%;
    width: 50%;
    height: 100%;
    background: linear-gradient(100deg, transparent, rgba(255,255,255,0.55), transparent);
    transform: skewX(-20deg);
    animation: shine 3.2s infinite;
  }
  @keyframes shine {
    0% { left: -80%; }
    55%, 100% { left: 130%; }
  }

  .surprise {
    max-height: 0;
    overflow: hidden;
    opacity: 0;
    transition: max-height 0.7s ease, opacity 0.6s ease, margin 0.6s ease;
    font-size: 1.05rem;
    color: #7b1fa2;
    font-weight: 600;
    line-height: 1.7;
  }
  .surprise.show {
    max-height: 300px;
    opacity: 1;
    margin-top: 26px;
  }

  /* Конфетти */
  .confetti-piece {
    position: fixed;
    top: -20px;
    z-index: 999;
    pointer-events: none;
    border-radius: 2px;
  }
  @keyframes fall {
    to {
      transform: translateY(110vh) rotate(720deg);
      opacity: 0;
    }
  }

  @media (max-width: 480px) {
    .card { padding: 38px 22px 34px; border-radius: 26px; }
    .cake { font-size: 62px; }
    .btn { padding: 14px 32px; font-size: 1rem; }
  }
</style>
</head>
<body>

<div class="card">
  <div class="cake">🎂</div>
  <h1>С Днём Рождения!</h1>
  <div class="name">Дорогой(ая) <span>Имя</span> 💖</div>

  <p class="message">
    Пусть этот день будет наполнен улыбками, тёплыми словами и приятными сюрпризами.
    Желаю крепкого здоровья, огромного счастья, исполнения самых заветных желаний
    и чтобы каждый новый день приносил только радость!
  </p>

  <button class="btn" id="celebrateBtn">Нажми меня 🎁</button>

  <div class="surprise" id="surprise">
    🎉 Ура! Ты лучший(ая)!<br>
    Пусть сбудется всё, о чём мечтаешь! ✨<br>
    <span style="font-size:1.6rem;">🥳🎈🎊</span>
  </div>
</div>

<script>
  // ====== Настройки ======
  const BALLOON_COUNT = 14;

  // Плавающие шарики
  const colors = ['#ff4081', '#ffd54f', '#4fc3f7', '#ba68c8', '#81c784', '#ff8a65', '#f06292'];
  for (let i = 0; i < BALLOON_COUNT; i++) {
    const b = document.createElement('div');
    b.className = 'balloon';
    const size = 40 + Math.random() * 45;
    b.style.width = size + 'px';
    b.style.height = size * 1.25 + 'px';
    b.style.left = Math.random() * 100 + 'vw';
    b.style.background = colors[Math.floor(Math.random() * colors.length)];
    b.style.animationDuration = (9 + Math.random() * 9) + 's';
    b.style.animationDelay = (-Math.random() * 15) + 's';
    document.body.appendChild(b);
  }

  // Конфетти
  function launchConfetti(amount = 120) {
    const colorsC = ['#e91e63', '#ffd54f', '#4fc3f7', '#ba68c8', '#81c784', '#ff7043', '#fff176', '#f06292'];
    for (let i = 0; i < amount; i++) {
      const p = document.createElement('div');
      p.className = 'confetti-piece';
      const w = 6 + Math.random() * 8;
      const h = 8 + Math.random() * 10;
      p.style.width = w + 'px';
      p.style.height = h + 'px';
      p.style.left = Math.random() * 100 + 'vw';
      p.style.background = colorsC[Math.floor(Math.random() * colorsC.length)];
      p.style.borderRadius = Math.random() > 0.5 ? '50%' : '2px';
      const dur = 2.5 + Math.random() * 2.5;
      p.style.animation = `fall ${dur}s linear forwards`;
      p.style.animationDelay = (Math.random() * 0.6) + 's';
      document.body.appendChild(p);
      setTimeout(() => p.remove(), (dur + 1) * 1000);
    }
  }

  // Кнопка
  const btn = document.getElementById('celebrateBtn');
  const surprise = document.getElementById('surprise');
  let clickCount = 0;

  btn.addEventListener('click', () => {
    launchConfetti(140);
    surprise.classList.add('show');
    clickCount++;

    // Меняем текст кнопки после первого нажатия
    if (clickCount === 1) {
      btn.textContent = 'Ещё конфетти! 🎊';
    } else if (clickCount === 3) {
      btn.textContent = 'Ты супер! 🥳';
    }
  });

  // Автоматическое конфетти при загрузке
  window.addEventListener('load', () => {
    setTimeout(() => launchConfetti(90), 600);
  });
</script>
</body>
</html>
