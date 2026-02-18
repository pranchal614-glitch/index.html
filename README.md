# index.html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Happy Birthday Pihu 🎂</title>

<style>
body{
    margin:0;
    padding:0;
    overflow:hidden;
    font-family:'Comic Sans MS', cursive;
    background:black;
    text-align:center;
    color:white;
}

/* Intro Screen */
.intro{
    position:absolute;
    width:100%;
    height:100%;
    display:flex;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    animation: fadeOut 4s forwards;
    animation-delay:3s;
}

.intro h2{
    font-size:35px;
    opacity:0;
    animation: fadeIn 3s forwards;
}

@keyframes fadeIn{ to{opacity:1;} }
@keyframes fadeOut{ to{opacity:0; visibility:hidden;} }

/* Main Content */
.main{
    position:absolute;
    width:100%;
    top:50%;
    transform:translateY(-50%);
    opacity:0;
    animation: showMain 3s forwards;
    animation-delay:6s;
}

@keyframes showMain{ to{opacity:1;} }

h1{
    font-size:55px;
    animation: glow 1.5s infinite alternate;
}

@keyframes glow{
    from{ text-shadow:0 0 10px pink; }
    to{ text-shadow:0 0 30px yellow; }
}

/* Cake */
.cake{
    font-size:100px;
    cursor:pointer;
    transition:0.5s;
}

.cut{
    transform:rotate(-10deg) scale(1.1);
}

/* Flowers */
.flower{
    position:absolute;
    top:-50px;
    font-size:30px;
    animation: fall linear infinite;
}

@keyframes fall{
    to{ transform: translateY(100vh); }
}
</style>
</head>

<body>

<!-- Music -->
<audio id="music" autoplay loop>
<source src="https://www2.cs.uic.edu/~i101/SoundFiles/HappyBirthday.mid" type="audio/midi">
</audio>

<div class="intro">
    <h2>✨ For My Beautiful and cut Sister ✨</h2>
</div>

<div class="main">
    <h1> Happy Birthday Pihu </h1>
    <p>💖 Meri Pyari Bahan 💖</p>
    <p>Cake se zyada sweet ho…
        Duniya ke liye cute, par mere liye full time tension✨</p>

    <div class="cake" onclick="cutCake()" id="cake">
        🎂
    </div>
    <p>👉 Cake par click karo 
        aur jaldi se cake kato
        bhook lagi hai 🎉</p>
</div>

<script>

setTimeout(startRain,6000);

function startRain(){
    setInterval(function(){
        let flower=document.createElement("div");
        flower.classList.add("flower");
        flower.innerHTML="🌸";
        flower.style.left=Math.random()*100+"vw";
        flower.style.animationDuration=(3+Math.random()*5)+"s";
        document.body.appendChild(flower);
    },300);
}

function cutCake(){
    let cake=document.getElementById("cake");
    cake.innerHTML="🍰";
    cake.classList.add("cut");
    alert("🎉 Cake Cut Ho Gaya! Happy Birthday Pihu 💖✨");
}

</script>

</body>
</html>
