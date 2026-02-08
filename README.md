<!DOCTYPE html>
<html lang="en">
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine 💖</title>
<style>
body {
  font-family: Arial, sans-serif;
  background-color: #ffe6eb;
  text-align: center;
  padding: 20px;
  overflow: hidden;
  margin: 0;
}

h1 {
  color: #e6005c;
  font-size: 2.5rem; /* bigger heading */
  margin-top: 70px;
  position: relative;
  z-index: 2;
}

.gif {
  width: 300px; /* bigger GIF */
  margin-top: 20px;
  border-radius: 18px;
  position: relative;
  z-index: 2;
}

.buttons {
  margin-top: 25px;
  position: relative;
  z-index: 2;
}

button {
  padding: 20px 40px; /* bigger default */
  font-size: 1.5rem; /* bigger YES button */
  margin: 10px;
  border: none;
  border-radius: 14px;
  cursor: pointer;
  transition: all 0.3s ease;
}

#yesBtn {
  background-color: #ff4d88;
  color: white;
}

#noBtn {
  background-color: #cccccc;
}

/* Floating hearts */
.heart {
  position: absolute;
  bottom: -20px;
  color: #ff4d88;
  animation: floatUp linear infinite;
  opacity: 0.8;
}

@keyframes floatUp {
  from { transform: translateY(0); opacity: 1; }
  to { transform: translateY(-800px); opacity: 0; }
}

/* Confetti */
.confetti {
  position: absolute;
  width: 8px;
  height: 14px;
  animation: fall 3s linear infinite;
}

@keyframes fall {
  from { transform: translateY(-20px) rotate(0deg); }
  to { transform: translateY(800px) rotate(360deg); }
}
</style>
</head>
<body>

<h1>HIII MY SNOOPYYPYPYPPYPYYY, Will you be my Valentine? ❤️</h1>

<img class="gif"
src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExem8zbDUxcm9yNmZjMnl1bDBtaWZxYXF1ZmduZWJqcjF1dDIwdXp1YSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/7k3ThwwMXnHCE/giphy.gif"
alt="cute gif">

<div class="buttons">
  <button id="yesBtn" onclick="yesClick()">Yes 💕</button>
  <button id="noBtn" onclick="noClick()">No ☹️</button>
</div>

<script>
let noTexts = [
  "Are you sure?",
  "What if I ask nicely",
  "Prettyyy pleaseeeeeee",
  "With coco and potcor 🍿",
  "What about Dubai choco 🍫",
  "PLEASEEEEE",
  "But :(",
  "What if I die 😢",
  "I'm dead 😭",
  "Pweaseeeeee",
  ":(((((("
];

let clickCount = 0;
const yesBtn = document.getElementById("yesBtn");
const noBtn = document.getElementById("noBtn");

function noClick() {
  if (clickCount < noTexts.length - 1) {
    noBtn.innerHTML = noTexts[clickCount];
    clickCount++;
  } else {
    noBtn.innerHTML = ":((((((";
    noBtn.style.position = "absolute";
    noBtn.style.left = Math.random() * 70 + "vw";
    noBtn.style.top = Math.random() * 60 + "vh";
  }

  // Make YES button grow bigger each click
  let size = parseFloat(window.getComputedStyle(yesBtn).fontSize);
  yesBtn.style.fontSize = (size + 6) + "px";
  yesBtn.style.padding = "22px 46px";
}

function yesClick() {
  document.body.innerHTML = "";

  // Message
  let title = document.createElement("h1");
  title.innerHTML = "YAYAYAYAYYYY see u on Feb 14!! 💘";
  title.style.color = "#e6005c";
  title.style.fontSize = "2.5rem"; // bigger
  title.style.marginTop = "40px";

  // GIF
  let gif = document.createElement("img");
  gif.src = "https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExMGV0bzhxMjFxZjUwbHh5eGlvZG1xYmFza2V1cnh4aXY2OTU1b2ZsaiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/i17zHLTMt1SmJMv6Aw/giphy.gif";
  gif.style.width = "350px"; // bigger GIF
  gif.style.marginTop = "20px";
  gif.style.borderRadius = "18px";

  document.body.appendChild(title);
  document.body.appendChild(gif);

  startConfetti();
}

// Floating hearts
setInterval(() => {
  let heart = document.createElement("div");
  heart.className = "heart";
  heart.innerHTML = "❤";
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.fontSize = (16 + Math.random() * 24) + "px";
  heart.style.animationDuration = (4 + Math.random() * 3) + "s";
  document.body.appendChild(heart);
  setTimeout(() => heart.remove(), 7000);
}, 350);

// Confetti
function startConfetti() {
  for (let i = 0; i < 120; i++) {
    let conf = document.createElement("div");
    conf.className = "confetti";
    conf.style.left = Math.random() * 100 + "vw";
    conf.style.backgroundColor =
      ["#ff4d88", "#ffd1dc", "#ffcc00", "#ffffff"]
      [Math.floor(Math.random() * 4)];
    conf.style.animationDuration = (2 + Math.random() * 2) + "s";
    document.body.appendChild(conf);
    setTimeout(() => conf.remove(), 4000);
  }
}
</script>

</body>
</html>
