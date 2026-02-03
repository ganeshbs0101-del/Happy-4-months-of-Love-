# Happy 4 Months of Love
<html lang="en">
<head>
<meta charset="UTF-8">
<title>4 Months of Love ❤️</title>

<style>
/* ===== BODY ===== */
body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    background: url('https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif') no-repeat center center fixed;
    background-size: cover;
    overflow-x: hidden;
    color: #880e4f;
}

/* ===== HIDE YOUTUBE ===== */
iframe {
    display: none;
}

/* ===== ROUND MUSIC BUTTON ===== */
.music-btn {
    position: fixed;
    bottom: 25px;
    left: 50%;
    transform: translateX(-50%);
    width: 65px;
    height: 65px;
    background: #d81b60;
    color: white;
    border: none;
    border-radius: 50%;
    font-size: 24px;
    cursor: pointer;
    z-index: 1000;
    box-shadow: 0 6px 18px rgba(0,0,0,0.35);
}

.music-btn:hover {
    background: #ad1457;
}

/* ===== SECTIONS ===== */
.section {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
}

/* ===== CARDS ===== */
.card, .letter {
    background: rgba(255, 192, 203, 0.92);
    padding: 35px 40px;
    border-radius: 25px;
    text-align: center;
    max-width: 520px;
    box-shadow: 0 12px 35px rgba(0,0,0,0.35);
}

/* ===== TEXT ===== */
h1 {
    color: #c2185b;
}

h2 {
    color: #ad1457;
    margin-top: 5px;
}

p {
    font-size: 18px;
    line-height: 1.7;
}

/* ===== HEART ===== */
.heart {
    font-size: 48px;
    animation: beat 1s infinite;
}

@keyframes beat {
    0% { transform: scale(1); }
    50% { transform: scale(1.25); }
    100% { transform: scale(1); }
}

/* ===== CENTER BUTTON ===== */
.main-btn {
    display: block;
    margin: 25px auto 0;
    padding: 12px 32px;
    background: #d81b60;
    color: white;
    border: none;
    border-radius: 30px;
    font-size: 16px;
    cursor: pointer;
}

.main-btn:hover {
    background: #ad1457;
}

/* ===== ROSE PETALS ===== */
.petal {
    position: fixed;
    top: -40px;
    font-size: 22px;
    animation: fall linear infinite;
    pointer-events: none;
}

@keyframes fall {
    from {
        transform: translateY(0) rotate(0deg);
        opacity: 1;
    }
    to {
        transform: translateY(110vh) rotate(360deg);
        opacity: 0;
    }
}
</style>
</head>

<body>

<!-- 🎵 MUSIC -->
<iframe
id="music"
src="https://www.youtube.com/embed/v_g2tIGeZN4?enablejsapi=1&loop=1&playlist=v_g2tIGeZN4&mute=1"
allow="autoplay">
</iframe>

<!-- 🔊 ROUND MUSIC BUTTON -->
<button class="music-btn" onclick="toggleMusic()">🔇</button>

<script>
let playing = false;
const music = document.getElementById("music");
const btn = document.querySelector(".music-btn");

function toggleMusic() {
    if (!playing) {
        music.contentWindow.postMessage('{"event":"command","func":"unMute","args":""}', '*');
        music.contentWindow.postMessage('{"event":"command","func":"playVideo","args":""}', '*');
        btn.innerText = "🔊";
        playing = true;
    } else {
        music.contentWindow.postMessage('{"event":"command","func":"mute","args":""}', '*');
        btn.innerText = "🔇";
        playing = false;
    }
}
</script>

<!-- 🌹 ROSE PETALS -->
<script>
for (let i = 0; i < 26; i++) {
    const petal = document.createElement("div");
    petal.className = "petal";
    petal.innerHTML = "🌹";
    petal.style.left = Math.random() * 100 + "vw";
    petal.style.animationDuration = (6 + Math.random() * 6) + "s";
    petal.style.fontSize = (16 + Math.random() * 18) + "px";
    document.body.appendChild(petal);
}
</script>

<!-- ❤️ SECTION -->
<div class="section">
    <div class="card">
        <div class="heart">❤️</div>
        <h1>Happy 4 Months</h1>
        <h2>Ruchitha 💖</h2>

        <p>
            Since <strong>October 4, 2025</strong>,<br>
            every moment with you has been filled<br>
            with love, laughter, and warmth.
        </p>

        <p>🌹 Forever & Always 🌹</p>

        <button class="main-btn"
            onclick="document.getElementById('letter').scrollIntoView({behavior:'smooth'})">
            Read My Love Letter 💌
        </button>
    </div>
</div>

<!-- 💌 LETTER -->
<div class="section" id="letter">
    <div class="letter">
        <h1>My Dearest Ruchitha 💖</h1>

        <p>
            Just like two playful cats sharing joy,  
            our love is gentle, comforting, and full of happiness.  
            These four months have been the most beautiful  
            chapter of my life.
        </p>

        <p>
            I promise to stand by you,  
            laugh with you,  
            support you,  
            and love you more every single day.
        </p>

        <p style="text-align:right; font-style:italic;">
            Forever yours,<br>
            ❤️ With endless love
        </p>

        <button class="main-btn"
            onclick="window.scrollTo({top:0, behavior:'smooth'})">
            Back to Top ⬆️
        </button>
    </div>
</div>

</body>
</html>
