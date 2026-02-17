<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Valentine's Day Babe ❤️</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    min-height:100vh;
    background:radial-gradient(circle at 30% 30%, #ffb6c1, #ff4d6d);
    font-family:'Segoe UI',Roboto,sans-serif;
    display:flex;
    align-items:center;
    justify-content:center;
    overflow:hidden;
    position:relative;
}

#hearts-container{
    position:absolute;
    width:100%;
    height:100%;
    pointer-events:none;
    z-index:1;
}

.float-heart{
    position:absolute;
    bottom:-10%;
    font-size:2rem;
    animation:floatUp 8s linear infinite;
}

@keyframes floatUp{
    0%{transform:translateY(0) rotate(0deg);opacity:0.7;}
    100%{transform:translateY(-120vh) rotate(360deg);opacity:0;}
}

.card{
    background:rgba(255,240,245,0.9);
    backdrop-filter:blur(12px);
    padding:3rem 4rem;
    border-radius:3rem;
    text-align:center;
    z-index:10;
    max-width:700px;
    box-shadow:0 30px 60px rgba(255,77,109,0.5);
}

.beating-heart{
    font-size:6rem;
    animation:beat 1.2s infinite;
}

@keyframes beat{
    0%,100%{transform:scale(1);}
    25%{transform:scale(1.2);}
    40%{transform:scale(0.95);}
    60%{transform:scale(1.1);}
}

h1{
    font-size:2.8rem;
    color:#c9003e;
    margin:0.5em 0;
}

p{
    font-size:1.6rem;
    color:#b80042;
    margin-bottom:1.5rem;
}

.photo-gallery{
    display:flex;
    gap:15px;
    justify-content:center;
    flex-wrap:wrap;
    margin-bottom:1.5rem;
}

.photo-gallery img{
    width:150px;
    height:150px;
    object-fit:cover;
    border-radius:20px;
    box-shadow:0 10px 25px rgba(255,77,109,0.4);
    transition:0.3s;
}

.photo-gallery img:hover{
    transform:scale(1.1);
}

.btn-love{
    background:#ff3366;
    border:none;
    color:white;
    font-size:1.4rem;
    font-weight:bold;
    padding:0.8rem 2rem;
    border-radius:60px;
    cursor:pointer;
    box-shadow:0 10px 25px #ff3355;
    transition:0.2s;
}

.btn-love:hover{
    transform:translateY(-3px);
    background:#ff4f75;
}

canvas{
    position:absolute;
    width:100%;
    height:100%;
    pointer-events:none;
    z-index:20;
}
</style>
</head>

<body>

<div id="hearts-container"></div>
<canvas id="confetti-canvas"></canvas>

<div class="card">
    <span class="beating-heart">❤️</span>
    <h1 id="valentineTitle"></h1>
    <p>You are my everything 💕</p>

    <div class="photo-gallery">
        <img src="IMG-20260214-WA0000.jpg" alt="">
        <img src="IMG-20260214-WA0001.jpg" alt="">
        <img src="IMG-20260214-WA0002.jpg" alt="">
    </div>

    <button class="btn-love" id="surpriseBtn">💘 Send Love</button>
</div>

<script>
// ===== DYNAMIC NAME =====
const girlfriendName = "Damilola";
document.getElementById("valentineTitle").innerHTML =
    `Happy Valentine's Day Babe ${girlfriendName} ❤️`;

// ===== FLOATING HEARTS =====
const container=document.getElementById('hearts-container');
const hearts=['❤️','💖','💕','💘','💞'];
for(let i=0;i<40;i++){
    const h=document.createElement('div');
    h.className='float-heart';
    h.innerHTML=hearts[Math.floor(Math.random()*hearts.length)];
    h.style.left=Math.random()*100+'%';
    h.style.animationDuration=(Math.random()*6+5)+'s';
    h.style.fontSize=(Math.random()*30+20)+'px';
    container.appendChild(h);
}

// ===== CONFETTI =====
const canvas=document.getElementById('confetti-canvas');
const ctx=canvas.getContext('2d');
canvas.width=window.innerWidth;
canvas.height=window.innerHeight;

let particles=[];

function createConfetti(){
    for(let i=0;i<100;i++){
        particles.push({
            x:Math.random()*canvas.width,
            y:-20,
            size:Math.random()*10+5,
            speed:Math.random()*5+3,
            color:`hsl(${Math.random()*360},100%,70%)`
        });
    }
    animate();
}

function animate(){
    ctx.clearRect(0,0,canvas.width,canvas.height);
    particles.forEach((p,i)=>{
        p.y+=p.speed;
        ctx.fillStyle=p.color;
        ctx.fillRect(p.x,p.y,p.size,p.size);
        if(p.y>canvas.height)particles.splice(i,1);
    });
    if(particles.length>0)requestAnimationFrame(animate);
}

// ===== BUTTON CLICK =====
const music=document.getElementById("bgMusic");

document.getElementById('surpriseBtn').onclick=function(){
    createConfetti();
    music.play(); // plays after user interaction
};
</script>

</body>
</html>
