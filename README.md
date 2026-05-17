<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Respect Presentation - Gopi Vivaan</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      margin: 0;
      overflow: hidden;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background: linear-gradient(135deg, #ffe6f7, #dff6ff);
    }

    .slide {
      position: absolute;
      width: 100%;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      opacity: 0;
      transform: scale(0.95);
      transition: all 1s ease;
      padding: 40px;
      text-align: center;
    }

    .active {
      opacity: 1;
      transform: scale(1);
      z-index: 10;
    }

    h1 {
      font-size: 4rem;
      color: #ff1493;
      text-shadow: 0 0 15px rgba(255, 20, 147, 0.4);
      animation: glow 2s infinite alternate;
    }

    h2 {
      font-size: 3rem;
      color: #7c3aed;
    }

    p {
      font-size: 1.8rem;
      max-width: 900px;
      color: #333;
      line-height: 1.7;
    }

    .emoji {
      position: absolute;
      font-size: 2rem;
      animation: float 6s linear infinite;
      opacity: 0.8;
    }

    .heart {
      color: #ff1493;
    }

    .sparkle {
      color: gold;
    }

    .confetti {
      position: absolute;
      width: 10px;
      height: 10px;
      background: red;
      animation: confettiFall linear infinite;
      opacity: 0.8;
    }

    @keyframes confettiFall {
      0% {
        transform: translateY(-100vh) rotate(0deg);
      }
      100% {
        transform: translateY(100vh) rotate(720deg);
      }
    }

    @keyframes glow {
      from {
        text-shadow: 0 0 10px #ff69b4;
      }
      to {
        text-shadow: 0 0 25px #ff1493;
      }
    }

    @keyframes float {
      0% {
        transform: translateY(100vh) scale(0.5);
      }
      100% {
        transform: translateY(-120vh) scale(1.2);
      }
    }

    .next-btn {
      position: fixed;
      bottom: 25px;
      right: 25px;
      background: #ff1493;
      color: white;
      border: none;
      padding: 14px 24px;
      border-radius: 999px;
      font-size: 1.2rem;
      cursor: pointer;
      z-index: 100;
      box-shadow: 0 5px 20px rgba(0,0,0,0.2);
      transition: transform 0.3s ease;
    }

    .next-btn:hover {
      transform: scale(1.08);
    }

    .badge {
      margin-top: 20px;
      background: white;
      padding: 12px 22px;
      border-radius: 999px;
      font-size: 1.2rem;
      color: #7c3aed;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    }

    .gif {
      width: 240px;
      border-radius: 25px;
      margin-top: 20px;
      box-shadow: 0 8px 25px rgba(0,0,0,0.2);
    }
  </style>
</head>
<body>

  <div class="slide active">
    <h1>Welcome To My Presentation ✨</h1>
    <p>Today I want to talk about the importance of Respect 💖</p>
    <div class="badge">Presented by Gopi Vivaan | 1B | Institute of Thomas Jefferson</div>
    <img class="gif" src="https://media.giphy.com/media/26ufdipQqU2lhNA4g/giphy.gif" />
  </div>

  <div class="slide">
    <h2>What is Respect? 🌟</h2>
    <p>
      Respect means being kind, polite, and caring toward others.
      It helps people feel happy, safe, and important.
    </p>
    <img class="gif" src="https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif" />
  </div>

  <div class="slide">
    <h2>How Can We Show Respect? 💕</h2>
    <p>
      We can show respect by listening carefully, helping others,
      using kind words, and sharing with friends.
    </p>
    <img class="gif" src="https://media.giphy.com/media/5GoVLqeAOo6PK/giphy.gif" />
  </div>

  <div class="slide">
    <h2>Respect at School 🏫</h2>
    <p>
      Respecting teachers, classmates, and school rules creates
      a happy classroom for everyone.
    </p>
    <img class="gif" src="https://media.giphy.com/media/3oriO0OEd9QIDdllqo/giphy.gif" />
  </div>

  <div class="slide">
    <h2>Respect at Home 🏡</h2>
    <p>
      Respecting parents and family members shows love and care.
      Helping at home is also a sign of respect.
    </p>
    <img class="gif" src="https://media.giphy.com/media/xT0xeJpnrWC4XWblEk/giphy.gif" />
  </div>

  <div class="slide">
    <h1>Respect Makes The World Better 💖</h1>
    <p>
      When we respect others, we spread kindness, happiness, and friendship everywhere.
    </p>
    <img class="gif" src="https://media.giphy.com/media/3o6fJ1BM7R2EBRDnxK/giphy.gif" />
  </div>

  <button class="next-btn" onclick="nextSlide()">Next ➜</button>

  <script>
    const slides = document.querySelectorAll('.slide');
    let current = 0;

    function nextSlide() {
      slides[current].classList.remove('active');
      current = (current + 1) % slides.length;
      slides[current].classList.add('active');
    }

    document.addEventListener('keydown', (e) => {
      if (e.key === 'ArrowRight' || e.key === ' ') {
        nextSlide();
      }
    });

    // Floating emojis
    const emojis = ['💖', '✨', '🎉', '🌟'];

    for (let i = 0; i < 30; i++) {
      const span = document.createElement('span');
      span.className = 'emoji';
      span.innerHTML = emojis[Math.floor(Math.random() * emojis.length)];
      span.style.left = Math.random() * 100 + 'vw';
      span.style.animationDuration = (5 + Math.random() * 8) + 's';
      span.style.fontSize = (20 + Math.random() * 30) + 'px';
      document.body.appendChild(span);
    }

    // Confetti
    const colors = ['#ff1493', '#ffd700', '#7c3aed', '#00bfff', '#ff4500'];

    for (let i = 0; i < 120; i++) {
      const conf = document.createElement('div');
      conf.className = 'confetti';
      conf.style.left = Math.random() * 100 + 'vw';
      conf.style.background = colors[Math.floor(Math.random() * colors.length)];
      conf.style.animationDuration = (4 + Math.random() * 5) + 's';
      conf.style.animationDelay = Math.random() * 5 + 's';
      document.body.appendChild(conf);
    }
  </script>
</body>
</html>
