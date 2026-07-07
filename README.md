<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Good Morning My Love ❤️</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Segoe UI',sans-serif;
}

body{
    overflow:hidden;
    background:linear-gradient(135deg,#ff9a9e,#fad0c4,#ffd1ff);
    height:100vh;
}

/* PAGE 1 */

#page1{
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    text-align:center;
}

.box{
    background:rgba(255,255,255,0.95);
    padding:35px;
    border-radius:25px;
    width:90%;
    max-width:550px;
    box-shadow:0 10px 25px rgba(0,0,0,.15);
}

h1{
    color:#ff4f81;
    margin-bottom:15px;
}

p{
    color:#444;
    line-height:1.7;
}

button{
    border:none;
    padding:12px 25px;
    margin:12px;
    border-radius:30px;
    cursor:pointer;
    font-size:16px;
    transition:.3s;
}

button:hover{
    transform:scale(1.05);
}

.awake{
    background:#ff4f81;
    color:white;
}

.sleep{
    background:#8e44ad;
    color:white;
}

/* POPUP */

.popup{
    display:none;
    position:fixed;
    top:0;
    left:0;
    width:100%;
    height:100%;
    background:rgba(0,0,0,.45);
    justify-content:center;
    align-items:center;
    z-index:999;
}

.popup-card{
    background:white;
    width:90%;
    max-width:450px;
    padding:25px;
    border-radius:20px;
    text-align:center;
    animation:fadeIn .3s ease;
}

.popup-card h2{
    color:#8e44ad;
    margin-bottom:15px;
}

@keyframes fadeIn{
    from{
        opacity:0;
        transform:scale(.9);
    }
    to{
        opacity:1;
        transform:scale(1);
    }
}

/* PAGE 2 */

#page2{
    display:none;
    height:100vh;
    justify-content:center;
    align-items:center;
}

.game-container{
    position:relative;
    width:90%;
    max-width:900px;
    height:80vh;
    border:4px solid white;
    border-radius:25px;
    overflow:hidden;
    background:rgba(255,255,255,.12);
    backdrop-filter:blur(10px);
    box-shadow:0 0 25px rgba(0,0,0,.15);
}

.game-title{
    text-align:center;
    color:white;
    padding-top:20px;
    font-size:32px;
}

#score{
    text-align:center;
    color:white;
    font-size:22px;
    margin-top:10px;
    font-weight:bold;
}

.heart{
    position:absolute;
    font-size:45px;
    cursor:pointer;
    user-select:none;
    transition:.2s;
}

.heart:hover{
    transform:scale(1.2);
}

#winBox{
    display:none;
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    background:white;
    width:90%;
    max-width:700px;
    padding:30px;
    border-radius:25px;
    text-align:center;
    box-shadow:0 0 30px rgba(0,0,0,.2);
    z-index:100;
    max-height:80%;
    overflow-y:auto;
}

#winBox h2{
    color:#ff4f81;
    margin-bottom:15px;
}

#winBox p{
    margin:12px 0;
}

.floating-heart{
    position:absolute;
    color:red;
    animation:float 6s linear infinite;
    pointer-events:none;
}

@keyframes float{
    from{
        transform:translateY(100vh);
        opacity:1;
    }
    to{
        transform:translateY(-120px);
        opacity:0;
    }
}
</style>
</head>

<body>

<!-- PAGE 1 -->

<div id="page1">
    <div class="box">

        <h1>☀️ Good Morning Beautiful ❤️</h1>

        <p>
            Are you still sleeping 😴<br>
            or have those gorgeous eyes finally opened? ✨
        </p>

        <button class="awake" onclick="startGame()">
            I'm Awake ❤️
        </button>

        <button class="sleep" onclick="showSleepMessage()">
            Still Sleeping 😴
        </button>

    </div>
</div>

<!-- SLEEP POPUP -->

<div id="sleepPopup" class="popup">

    <div class="popup-card">

        <h2>😴 Sweet Dreams Princess ❤️</h2>

        <p>
            May your dreams be as beautiful as your smile,
            and when you finally wake up, remember that
            someone is already thinking about you and wishing
            you the sweetest morning. ☀️💕
        </p>

    </div>

</div>

<!-- PAGE 2 -->

<div id="page2">

    <div class="game-container">

        <h1 class="game-title">❤️ Catch My Love ❤️</h1>

        <div id="score">
            Hearts Collected: 0 / 10 ❤️
        </div>

        <div id="winBox">

            <h2>🎉 You Won My Love 🎉</h2>

            <p>🌹 Good Morning, Beautiful 🌹</p>

            <p>
                You are the most precious and important girl in my life.
            </p>

            <p>
                Every morning feels brighter because of you.
                Your smile is my favorite sunrise,
                your laughter is my favorite song,
                and your happiness means more to me than words can ever explain.
            </p>

            <p>
                Out of all the people in this world,
                you are the one my heart chooses every single day.
            </p>

            <p>
                Thank you for being my comfort,
                my happiness,
                my peace,
                and my favorite person.
            </p>

            <p>
                If I could give you one thing in life,
                it would be the ability to see yourself through my eyes,
                because then you'd realize just how special you truly are.
            </p>

            <p>
                ❤️ I Love You More Than Yesterday
                And Less Than Tomorrow ❤️
            </p>

        </div>

    </div>

</div>

<script>

let score = 0;

/* POPUP */

function showSleepMessage(){
    document.getElementById("sleepPopup").style.display = "flex";
}

document.getElementById("sleepPopup")
.addEventListener("click",function(){
    this.style.display = "none";
});

/* START GAME */

function startGame(){

    document.getElementById("page1").style.display = "none";
    document.getElementById("page2").style.display = "flex";

    for(let i=0;i<3;i++){
        createHeart();
    }
}

/* CREATE HEART */

function createHeart(){

    const game =
    document.querySelector(".game-container");

    let heart = document.createElement("div");

    heart.className = "heart";
    heart.innerHTML = "❤️";

    heart.style.left =
    Math.random()*(game.clientWidth-60)+"px";

    heart.style.top =
    (100+Math.random()*(game.clientHeight-180))+"px";

    game.appendChild(heart);

    let move = setInterval(()=>{

        heart.style.left =
        Math.random()*(game.clientWidth-60)+"px";

        heart.style.top =
        (100+Math.random()*(game.clientHeight-180))+"px";

    },900);

    heart.onclick = function(){

        score++;

        document.getElementById("score").innerHTML =
        "Hearts Collected: " + score + " / 10 ❤️";

        clearInterval(move);

        heart.remove();

        if(score >= 10){

            document.querySelectorAll(".heart")
            .forEach(h => h.remove());

            document.getElementById("winBox")
            .style.display = "block";

            return;
        }

        createHeart();
    };
}

/* FLOATING HEARTS */

function floatingHeart(){

    let h = document.createElement("div");

    h.className = "floating-heart";
    h.innerHTML = "❤️";

    h.style.left = Math.random()*100 + "vw";
    h.style.fontSize = (20 + Math.random()*30) + "px";

    document.body.appendChild(h);

    setTimeout(()=>{
        h.remove();
    },6000);
}

setInterval(floatingHeart,500);

</script>

</body>
</html>
