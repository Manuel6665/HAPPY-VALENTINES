<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Valentine Invitation 💖</title>
<style>
body {
  margin: 0;
  font-family: 'Segoe UI', sans-serif;
  background: linear-gradient(135deg, #ff758c, #ff7eb3);
  overflow: hidden;
  color: #fff;
  text-align: center;
}

.container {
  position: relative;
  top: 50%;
  transform: translateY(-50%);
  padding: 20px;
}

h1 {
  font-size: 2.3em;
  margin-bottom: 10px;
}

p {
  font-size: 1.2em;
}

.buttons {
  margin-top: 25px;
}

button {
  font-size: 1.1em;
  padding: 12px 25px;
  border-radius: 30px;
  border: none;
  cursor: pointer;
  margin: 10px;
}

#yesBtn {
  background: #ff2e63;
  color: white;
}

#noBtn {
  background: #fff;
  color: #ff2e63;
}

.heart {
  position: absolute;
  font-size: 20px;
  animation: floatUp 6s linear infinite;
  opacity: 0.8;
}

@keyframes floatUp {
  0% {
    transform: translateY(100vh) scale(1);
    opacity: 1;
  }
  100% {
    transform: translateY(-10vh) scale(1.5);
    opacity: 0;
  }
}

/* Envelope */
#envelope {
  display: none;
  margin-top: 30px;
}

.envelope {
  width: 280px;
  height: 180px;
  background: #ffb6c1;
  margin: auto;
  position: relative;
  border-radius: 10px;
  overflow: hidden;
}

.envelope::before {
  content: "";
  position: absolute;
  top: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, transparent 50%, #ff8fab 50%);
}

.letter {
  background: white;
  color: #ff2e63;
  width: 240px;
  height: 140px;
  position: absolute;
  top: 20px;
  left: 20px;
  border-radius: 8px;
  padding: 15px;
  box-sizing: border-box;
  animation: popUp 1s ease forwards;
}

@keyframes popUp {
  from { transform: translateY(60px); opacity: 0; }
  to { transform: translateY(0); opacity: 1; }
}

.photo {
  margin-top: 20px;
}

.photo img {
  width: 180px;
  border-radius: 15px;
  box-shadow: 0 10px 25px rgba(0,0,0,0.3);
}
</style>
</head>

<body>

<div class="container" id="main">
  <h1>💖 Hi Jhoana Gualberto 💖</h1>
  <p>
    Would you like to go on a Valentine date with me<br>
    on <strong>February 17, 2026</strong>? 🌹
  </p>

  <div class="buttons">
    <button id="yesBtn">Yes 💘</button>
    <button id="noBtn">No 🙈</button>
  </div>
</div>

<div id="envelope">
  <div class="envelope">
    <div class="letter">
      <h3>💌 Congratulations 💌</h3>
      <p>
        You just made me the happiest person 💕<br><br>
        Our Valentine date is officially a YES! 🌹
      </p>
    </div>
  </div>

  <div class="photo">
    <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/4gHYSUNDX1BST0ZJTEUAAQEAAAHIAAAAAAQwAABtbnRyUkdCIFhZWiAH4AABAAEAAAAAAABh...REDACTED_FOR_DISPLAY..." alt="Us">
  </div>
</div>

<script>
const noMessages = [
  "Are you sure? 🤨",
  "Wrong answer 😏",
  "Try again 💕",
  "That button is broken 🙃",
  "Think about it again 💖",
  "Nice try 😌"
];

let noCount = 0;

document.getElementById("noBtn").addEventListener("click", () => {
  alert(noMessages[noCount % noMessages.length]);
  noCount++;
});

document.getElementById("yesBtn").addEventListener("click", () => {
  document.getElementById("main").style.display = "none";
  document.getElementById("envelope").style.display = "block";
});

// Floating hearts
setInterval(() => {
  const heart = document.createElement("div");
  heart.className = "heart";
  heart.innerHTML = "💖";
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.fontSize = (15 + Math.random() * 20) + "px";
  document.body.appendChild(heart);

  setTimeout(() => heart.remove(), 6000);
}, 400);
</script>

</body>
</html>
