<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Gratitude 2025</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap" rel="stylesheet">

<style>
body {
  margin: 0;
  height: 100vh;
  background: radial-gradient(circle at top, #ffe4f2, #cdb4ff, #a2d2ff);
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Poppins', sans-serif;
  overflow: hidden;
}

/* Floating background flowers */
.bg-flower {
  position: absolute;
  font-size: 26px;
  opacity: 0.15;
  animation: drift 12s linear infinite;
}

@keyframes drift {
  from { transform: translateY(100vh) rotate(0deg); }
  to { transform: translateY(-120vh) rotate(360deg); }
}

/* Main glass card */
.card {
  width: 330px;
  height: 440px;
  background: rgba(255,255,255,0.18);
  backdrop-filter: blur(14px);
  border-radius: 28px;
  box-shadow:
    0 30px 80px rgba(0,0,0,0.25),
    inset 0 0 40px rgba(255,255,255,0.2);
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: white;
  cursor: pointer;
  position: relative;
  transition: transform 0.6s;
}

.card:hover {
  transform: scale(1.04);
}

/* Inner glow */
.card::before {
  content: "";
  position: absolute;
  inset: 0;
  border-radius: 28px;
  background: radial-gradient(circle at top, rgba(255,255,255,0.35), transparent);
}

/* Text */
.text {
  font-size: 23px;
  padding: 22px;
  z-index: 2;
  animation: fade 1.2s ease;
  line-height: 1.5;
}

@keyframes fade {
  from { opacity: 0; transform: translateY(12px); }
  to { opacity: 1; transform: translateY(0); }
}

/* Sparkle dots */
.sparkle {
  position: absolute;
  width: 4px;
  height: 4px;
  background: white;
  border-radius: 50%;
  opacity: 0.6;
  animation: sparkle 3s infinite ease-in-out;
}

@keyframes sparkle {
  0% { opacity: 0; transform: scale(0); }
  50% { opacity: 1; transform: scale(1); }
  100% { opacity: 0; transform: scale(0); }
}

/* Heart rays */
.hearts {
  position: absolute;
  inset: 0;
  pointer-events: none;
}

.heart {
  position: absolute;
  font-size: 22px;
  animation: rise 3.5s ease-in-out forwards;
  opacity: 0.85;
}

@keyframes rise {
  0% { transform: translateY(0) scale(0.8); opacity: 0; }
  40% { opacity: 1; }
  100% { transform: translateY(-220px) scale(1.6); opacity: 0; }
}

/* Small flower burst */
.flower {
  position: absolute;
  font-size: 18px;
  animation: bloom 3s ease forwards;
}

@keyframes bloom {
  from { transform: scale(0); opacity: 0; }
  to { transform: scale(1.4); opacity: 0; }
}
</style>
</head>

<body>

<!-- Background flowers -->
<script>
for (let i = 0; i < 18; i++) {
  let f = document.createElement("div");
  f.className = "bg-flower";
  f.innerHTML = ["🌸","🌼","🌷"][Math.floor(Math.random()*3)];
  f.style.left = Math.random()*100 + "%";
  f.style.animationDuration = 10 + Math.random()*10 + "s";
  document.body.appendChild(f);
}
</script>

<div class="card" onclick="nextScene()">
  <div class="text" id="text">Thank you ✨</div>
  <div class="hearts" id="effects"></div>
</div>

<script>
let step = 0;
const text = document.getElementById("text");
const effects = document.getElementById("effects");

createSparkles();

function nextScene() {
  step++;
  effects.innerHTML = "";

  if (step === 1) {
    text.innerHTML = "Thank you 🤍<br>for being here";
  }

  else if (step === 2) {
    text.innerHTML = "";
    heartRays();
    flowerBurst();
  }

  else if (step === 3) {
    text.innerHTML =
      "Grateful for every little moment,<br>every laugh,<br>every memory in 2025 🌿";
  }

  else if (step === 4) {
    text.innerHTML = "I love you 💖";
    step = 0;
  }
}

/* Heart rays */
function heartRays() {
  for (let i = 0; i < 28; i++) {
    let h = document.createElement("div");
    h.className = "heart";
    h.innerHTML = "💗";
    h.style.left = Math.random()*100 + "%";
    h.style.bottom = "0px";
    h.style.animationDelay = Math.random() + "s";
    effects.appendChild(h);
  }
}

/* Flower details */
function flowerBurst() {
  for (let i = 0; i < 16; i++) {
    let f = document.createElement("div");
    f.className = "flower";
    f.innerHTML = ["🌸","🌼","🌷"][Math.floor(Math.random()*3)];
    f.style.left = Math.random()*100 + "%";
    f.style.top = Math.random()*100 + "%";
    f.style.animationDelay = Math.random() + "s";
    effects.appendChild(f);
  }
}

/* Sparkles */
function createSparkles() {
  for (let i = 0; i < 20; i++) {
    let s = document.createElement("div");
    s.className = "sparkle";
    s.style.left = Math.random()*100 + "%";
    s.style.top = Math.random()*100 + "%";
    s.style.animationDelay = Math.random()*3 + "s";
    document.body.appendChild(s);
  }
}
</script>

</body>
</html>

