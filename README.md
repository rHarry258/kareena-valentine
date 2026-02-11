# kareena-valentine
index.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Be My Valentine 💖</title>

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
        margin-bottom: 30px;
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
</style>
</head>

<body>

<div class="box" id="mainBox">
    <h1>💘 Can you be my Valentine?</h1>
    <button id="yesBtn">YES 💖</button>
    <button id="noBtn">NO 😢</button>
</div>

<div class="final" id="finalMessage">
    💍 YAYYYY!!! You are mine forever 💖
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

    let size = 18;

    // YES button grows
    yesBtn.addEventListener("click", function() {
        size += 20;
        yesBtn.style.fontSize = size + "px";
        yesBtn.style.padding = size/2 + "px";
        music.play();

        if(size > 200){
            mainBox.style.display = "none";
            finalMessage.style.display = "block";
            startHearts();
        }
    });

    // NO button runs away
    noBtn.addEventListener("mouseover", function() {
        const x = Math.random() * (window.innerWidth - 100);
        const y = Math.random() * (window.innerHeight - 50);
        noBtn.style.left = x + "px";
        noBtn.style.top = y + "px";
    });

    // Floating hearts
    function startHearts() {
        setInterval(() => {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            heart.innerHTML = "💖";
            heart.style.left = Math.random() * window.innerWidth + "px";
            heart.style.bottom = "0px";
            heart.style.fontSize = (Math.random() * 30 + 20) + "px";
            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 4000);

        }, 200);
    }
</script>

</body>
</html>
