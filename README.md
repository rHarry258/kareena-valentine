# kareena-valentine
index.html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kareena ❤️</title>

<style>
    body {
        margin: 0;
        overflow: hidden;
        font-family: 'Segoe UI', sans-serif;
        background: linear-gradient(135deg, #ff758c, #ff7eb3);
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        text-align: center;
        color: white;
    }

    .container {
        background: rgba(255,255,255,0.15);
        backdrop-filter: blur(15px);
        padding: 50px;
        border-radius: 25px;
        box-shadow: 0 10px 40px rgba(0,0,0,0.3);
        position: relative;
        z-index: 10;
    }

    h1 {
        font-size: 32px;
        margin-bottom: 20px;
    }

    button {
        padding: 15px 30px;
        font-size: 20px;
        border: none;
        border-radius: 12px;
        cursor: pointer;
        margin: 10px;
        transition: all 0.3s ease;
    }

    #yesBtn {
        background: #ff2e63;
        color: white;
        box-shadow: 0 0 20px rgba(255,0,90,0.7);
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
        animation: fadeIn 2s ease forwards;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: scale(0.5); }
        to { opacity: 1; transform: scale(1); }
    }

    .heart {
        position: absolute;
        font-size: 24px;
        animation: float 5s linear infinite;
    }

    @keyframes float {
        0% { transform: translateY(0); opacity: 1; }
        100% { transform: translateY(-1000px); opacity: 0; }
    }

    iframe {
        display: none;
    }
</style>
</head>

<body>

<div class="container" id="mainBox">
    <h1>Kareena… 💖<br><br>
    Pehli Nazar Mein Kaise Jaadu Kar Diya… ✨<br><br>
    Will you be my Valentine?</h1>

    <button id="yesBtn">YES ❤️</button>
    <button id="noBtn">NO 😭</button>
</div>

<div class="final" id="finalMessage">
    Kareena… ❤️<br><br>
    From the first moment, it was always you. 💍✨<br><br>
    Happy Valentine’s Day 💖
</div>

<!-- YouTube Music Embed -->
<iframe id="music"
src="https://www.youtube.com/embed/BadBAMnPX0I?autoplay=1&loop=1&playlist=BadBAMnPX0I"
allow="autoplay">
</iframe>

<script>
    const yesBtn = document.getElementById("yesBtn");
    const noBtn = document.getElementById("noBtn");
    const mainBox = document.getElementById("mainBox");
    const finalMessage = document.getElementById("finalMessage");
    const music = document.getElementById("music");

    let size = 20;

    yesBtn.addEventListener("click", function() {
        size += 25;
        yesBtn.style.fontSize = size + "px";
        yesBtn.style.padding = size/2 + "px";
        yesBtn.style.boxShadow = "0 0 40px rgba(255,0,90,1)";

        if(size > 200){
            mainBox.style.display = "none";
            finalMessage.style.display = "block";
            music.style.display = "block";
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

            setTimeout(() => {
                heart.remove();
            }, 5000);

        }, 150);
    }
</script>

</body>
</html>
