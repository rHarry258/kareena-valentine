# kareena-valentine
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kareena ❤️</title>

<style>
body {
    margin: 0;
    overflow: hidden;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(135deg, #ff6a88, #ff99ac);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    text-align: center;
    color: white;
}

.container {
    background: rgba(255,255,255,0.15);
    backdrop-filter: blur(20px);
    padding: 50px;
    border-radius: 30px;
    box-shadow: 0 10px 50px rgba(0,0,0,0.3);
    position: relative;
}

h1 {
    font-size: 30px;
}

button {
    padding: 15px 30px;
    font-size: 20px;
    border: none;
    border-radius: 12px;
    cursor: pointer;
    margin: 15px;
    transition: 0.3s ease;
}

#yesBtn {
    background: #ff2e63;
    color: white;
}

#noBtn {
    background: #444;
    color: white;
    position: absolute;
}

.final {
    display: none;
    font-size: 45px;
    font-weight: bold;
    animation: zoomIn 1.5s ease forwards;
}

@keyframes zoomIn {
    from { transform: scale(0); opacity: 0; }
    to { transform: scale(1); opacity: 1; }
}

.heart {
    position: absolute;
    font-size: 24px;
    animation: floatUp 5s linear infinite;
}

@keyframes floatUp {
    0% { transform: translateY(0); opacity: 1; }
    100% { transform: translateY(-1000px); opacity: 0; }
}
</style>
</head>

<body>

<div class="container" id="mainBox">
    <h1>
        Kareena… ❤️<br><br>
        Pehli Nazar Mein Kaise Jaadu Kar Diya… ✨<br><br>
        Will you be my Valentine?
    </h1>

    <button id="yesBtn">YES ❤️</button>
    <button id="noBtn">NO 😭</button>
</div>

<div class="final" id="finalMessage">
    Kareena… ❤️<br><br>
    From the first moment, it was always you. 💍✨<br><br>
    Happy Valentine’s Day 💖
</div>

<!-- Hidden Romantic Music -->
<audio id="music" loop>
  <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_6b4e78f7a2.mp3?filename=romantic-background-112194.mp3" type="audio/mp3">
</audio>

<script>
const yesBtn = document.getElementById("yesBtn");
const noBtn = document.getElementById("noBtn");
const mainBox = document.getElementById("mainBox");
const finalMessage = document.getElementById("finalMessage");
const music = document.getElementById("music");

let size = 20;

yesBtn.addEventListener("click", function() {
    music.play();
    size += 25;
    yesBtn.style.fontSize = size + "px";
    yesBtn.style.padding = size/2 + "px";
    yesBtn.style.boxShadow = "0 0 50px rgba(255,0,90,1)";

    if(size > 200){
        mainBox.style.display = "none";
        finalMessage.style.display = "block";
        startHearts();
    }
});

noBtn.addEventListener("mouseover", function() {
    const x = Math.random() * (window.innerWidth - 150);
    const y = Math.random() * (window.innerHeight - 100);
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
});

function startHearts() {
    setInterval(() => {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "💖";
        heart.style.left = Math.random() * window.innerWidth + "px";
        heart.style.bottom = "0px";
        heart.style.fontSize = (Math.random() * 40 + 20) + "px";
        document.body.appendChild(heart);

        setTimeout(() => heart.remove(), 5000);
    }, 150);
}
</script>

</body>
</html>
