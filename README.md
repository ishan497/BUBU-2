<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Bubu ❤️</title>

<style>
body {
    margin: 0;
    padding: 0;
    font-family: 'Segoe UI', sans-serif;
    background: radial-gradient(circle at top, #1a0026, #000000);
    color: white;
    text-align: center;
    overflow-x: hidden;
}

/* Intro */
#intro {
    position: fixed;
    width: 100%;
    height: 100%;
    background: black;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 100;
    font-size: 2rem;
    text-align: center;
    padding: 20px;
}

/* Stars */
.star {
    position: absolute;
    width: 2px;
    height: 2px;
    background: white;
    animation: twinkle 2s infinite alternate;
}

@keyframes twinkle {
    from { opacity: 0.2; }
    to { opacity: 1; }
}

/* Hearts */
.heart {
    position: absolute;
    color: rgba(255, 105, 180, 0.7);
    animation: floatUp 6s linear infinite;
}

@keyframes floatUp {
    0% { transform: translateY(100vh); opacity: 1; }
    100% { transform: translateY(-10vh); opacity: 0; }
}

/* Buttons */
button {
    background: linear-gradient(45deg, #ff4da6, #ff99cc);
    color: white;
    border: none;
    padding: 12px 25px;
    font-size: 1rem;
    border-radius: 30px;
    cursor: pointer;
    margin: 10px;
    transition: 0.3s;
}

button:hover {
    transform: scale(1.1);
}

h1 {
    margin-top: 60px;
    font-size: 3rem;
    text-shadow: 0 0 20px #ff4da6;
}

#typedText {
    width: 85%;
    max-width: 750px;
    margin: 20px auto;
    font-size: 1.3rem;
    line-height: 1.6;
    min-height: 140px;
}

#counter {
    margin-top: 15px;
    font-size: 1.2rem;
    color: #ffb3ec;
}

#proposal, #explosion {
    display: none;
}

#explosion {
    font-size: 3rem;
    margin-top: 30px;
    color: #ff4da6;
    text-shadow: 0 0 20px #ff99cc;
    animation: pulse 1s infinite alternate;
}

@keyframes pulse {
    from { transform: scale(1); }
    to { transform: scale(1.1); }
}

canvas {
    position: fixed;
    top: 0;
    left: 0;
    pointer-events: none;
}
</style>
</head>

<body>

<div id="intro"></div>

<canvas id="fireworks"></canvas>

<h1>Manashi, My Bubu 🌌❤️</h1>

<div id="typedText"></div>

<div id="multiverse" style="margin-top:30px; font-size:1.3rem;">
    <p>In this universe 🌎 — I choose you.</p>
    <p>In another universe 🪐 — I still choose you.</p>
    <p>In every lifetime ⏳ — I will find you.</p>
</div>

<div id="counter"></div>

<button onclick="showProposal()">Click here, Short Queen 👑</button>

<div id="proposal">
    <h2>Will you be my forever? 💍</h2>
    <button onclick="yesClicked()">YES ❤️</button>
    <button id="noBtn">No 🙄</button>
</div>

<div id="explosion">I LOVE YOU BUBU ❤️💖💍</div>

<div style="margin-top:60px; font-size:1.2rem; color:#ffb3ec;">
    <h2>One Day... 💫</h2>
    <p>Late night drives together.</p>
    <p>Random airport hugs.</p>
    <p>Cooking in our kitchen.</p>
    <p>Growing old side by side.</p>
    <p>Still calling you short at 80. 👑❤️</p>
</div>

<script>

/* Cinematic Intro */
const introLines = [
"In a world full of billions...",
"My heart chose one.",
"And her name is...",
"Manashi ❤️"
];

let lineIndex = 0;
let charIndex = 0;

function typeIntro() {
    if (charIndex < introLines[lineIndex].length) {
        document.getElementById("intro").innerHTML += introLines[lineIndex].charAt(charIndex);
        charIndex++;
        setTimeout(typeIntro, 60);
    } else {
        setTimeout(() => {
            document.getElementById("intro").innerHTML = "";
            charIndex = 0;
            lineIndex++;
            if (lineIndex < introLines.length) {
                typeIntro();
            } else {
                document.getElementById("intro").style.display = "none";
            }
        }, 1200);
    }
}
typeIntro();

/* Stars */
for (let i = 0; i < 100; i++) {
    const star = document.createElement("div");
    star.classList.add("star");
    star.style.left = Math.random() * 100 + "vw";
    star.style.top = Math.random() * 100 + "vh";
    star.style.animationDuration = Math.random() * 3 + 1 + "s";
    document.body.appendChild(star);
}

/* Typing Letter */
const message = `To my beautiful Bubu,

You are my brightest star.
My happiness.
My peace.

I love everything about you.
Even when I call you short just to tease you 😌

You are my forever.
In this lifetime and the next. ❤️`;

let i = 0;
function typeWriter() {
    if (i < message.length) {
        document.getElementById("typedText").innerHTML += message.charAt(i);
        i++;
        setTimeout(typeWriter, 35);
    }
}
typeWriter();

/* Relationship Counter */
/* CHANGE THIS DATE */
const startDate = new Date("2024-01-01");

setInterval(() => {
    const now = new Date();
    const diff = now - startDate;
    const days = Math.floor(diff / (1000*60*60*24));
    const hours = Math.floor((diff / (1000*60*60)) % 24);
    const minutes = Math.floor((diff / (1000*60)) % 60);

    document.getElementById("counter").innerHTML =
        `We have loved each other for ${days} days, ${hours} hours, ${minutes} minutes ❤️`;
}, 1000);

/* Floating Hearts */
function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 20 + 15 + "px";
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 6000);
}
setInterval(createHeart, 500);

/* Floating Love Notes */
const loveNotes = [
"You are enough.",
"My heart chose you.",
"Short but powerful 👑",
"My forever girl.",
"You are my peace."
];

function createNote() {
    const note = document.createElement("div");
    note.innerHTML = loveNotes[Math.floor(Math.random()*loveNotes.length)];
    note.style.position = "absolute";
    note.style.left = Math.random()*100 + "vw";
    note.style.top = Math.random()*100 + "vh";
    note.style.opacity = "0.7";
    note.style.fontSize = "14px";
    note.style.color = "#ff99cc";
    document.body.appendChild(note);
    setTimeout(()=> note.remove(),4000);
}
setInterval(createNote, 3000);

/* Proposal */
function showProposal() {
    document.getElementById("proposal").style.display = "block";
}

function yesClicked() {
    document.getElementById("explosion").style.display = "block";
    launchFireworks();
}

/* Runaway NO Button */
const noBtn = document.getElementById("noBtn");
noBtn.addEventListener("mouseover", function() {
    noBtn.style.position = "absolute";
    noBtn.style.left = Math.random() * window.innerWidth + "px";
    noBtn.style.top = Math.random() * window.innerHeight + "px";
});

/* Fireworks */
const canvas = document.getElementById("fireworks");
const ctx = canvas.getContext("2d");
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

function launchFireworks() {
    for (let i = 0; i < 120; i++) {
        setTimeout(() => {
            ctx.fillStyle = "hsl(" + Math.random()*360 + ",100%,50%)";
            ctx.beginPath();
            ctx.arc(Math.random()*canvas.width,
                    Math.random()*canvas.height,
                    5, 0, Math.PI*2);
            ctx.fill();
        }, i*20);
    }
}
</script>

<!-- Background Music -->
<audio autoplay loop>
<source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
</audio>

<!-- Heartbeat -->
<audio autoplay loop>
<source src="https://www.soundjay.com/human/heartbeat-01a.mp3" type="audio/mpeg">
</audio>

</body>
</html>
