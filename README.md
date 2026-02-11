# kareena will you be my valentine
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kareena 💖</title>

<style>
    body {
        margin: 0;
        overflow: hidden;
        font-family: Arial, sans-serif;
        background: linear-gradient(135deg, #ff9a9e, #fad0c4);
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }

    .box {
        background: white;
        padding: 40px;
        border-radius: 20px;
        text-align: center;
        box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        position: relative;
        z-index: 10;
    }

    h1 {
        margin-bottom: 20px;
    }

    .from {
        margin-top: 20px;
        font-style: italic;
        color: #ff4d6d;
        font-size: 18px;
    }

    button {
        padding: 12px 25px;
        font-size: 18px;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        margin: 10px;
        transition: all 0.3s ease;
    }

    #yesBtn {
        background-color: #ff4d6d;
        color: white;
    }

    #noBtn {
        background-color: #999;
        color: white;
        position: absolute;
    }

    .heart {
        position: absolute;
        color: red;
        font-size: 20px;
        animation: floatUp 4s linear infinite;
    }

    @keyframes floatUp {
        0% { transform: translateY(0); opacity: 1; }
        100% { transform: translateY(-800px); opacity: 0; }
    }

    .final {
        font-size: 40px;
        color: white;
        text-align: center;
        display: none;
    }

    .minion-cute {
        width: 200px;
        margin: 15px 0;
    }

    .minion-hug {
        display: none;
        width: 250px;
        margin-top: 20px;
    }
</style>
</head>

<body>

<div class="box" id="mainBox">

    <h1>💘 Kareena, will you be my Valentine?</h1>

    <!-- Cute Minion with hearts before clicking YES -->
    <img class="minion-cute"
         src="https://tenor.com/view/minions-minion-in-love-gif-8647532" 
         alt="Cute Minion in love with hearts around it"> <!-- Source: Minion in love GIF from Tenor  [oai_citation:1‡Tenor](https://tenor.com/view/minions-minion-in-love-gif-8647532?utm_source=chatgpt.com) -->

    <button id="yesBtn">YES 💖</button>
    <button id="noBtn">NO 😢</button>

    <div class="from">— From Harsimran 💖</div>
</div>

<div class="final" id="finalMessage">
    💍 YAYYYY Kareena!!! 💖<br><br>
    You are mine forever 😌✨<br><br>
    — Harsimran 💘<br><br>

    <!-- Minions hugging GIF after YES -->
    <img class="minion-hug"
         id="minionHug"
         src="https://tenor.com/view/minions-hug-cuddle-love-gif-9709470" 
         alt="Minions hugging in love"> <!-- Minions hugging GIF from GIF site  [oai_citation:2‡Tenor](https://tenor.com/baQcd.gif?utm_source=chatgpt.com) -->
</div>

<audio id="music" loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mp3">
</audio>

<script>
    const yesBtn = document.getElementById("yesBtn");
    const noBtn = document.getElementById("noBtn");
    const music = document.getElementById("music");
    const mainBox = document.getElementById("mainBox");
    const finalMessage = document.getElementById("finalMessage");
    const minionHug = document.getElementById("minionHug");

    let size = 18;

    yesBtn.addEventListener("click", function() {
        music.play();
        size += 20;
        yesBtn.style.fontSize = size + "px";
        yesBtn.style.padding = size/2 + "px";
        yesBtn.style.boxShadow = "0 0 50px rgba(255,0,90,1)";

        if (size > 200) {
            mainBox.style.display = "none";
            finalMessage.style.display = "block";
            minionHug.style.display = "block";
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
            heart.style.fontSize = (Math.random() * 30 + 20) + "px";
            document.body.appendChild(heart);

            setTimeout(() => heart.remove(), 4000);
        }, 200);
    }
</script>

</body>
</html>
