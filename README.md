<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Bujiii ❤️</title>

<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Comic Sans MS',cursive;
}

body{
background:linear-gradient(135deg,#ffb6c1,#ffd700,#98fb98,#ffc0cb);
min-height:100vh;
display:flex;
justify-content:center;
align-items:center;
padding:20px;
overflow:hidden;
}

.container{
background:white;
width:100%;
max-width:400px;
padding:25px;
border-radius:25px;
text-align:center;
box-shadow:0 10px 25px rgba(0,0,0,0.15);
}

h1{
color:#ff4081;
margin-bottom:15px;
}

.stickers{
font-size:30px;
margin-bottom:10px;
}

.question{
font-size:22px;
color:#444;
margin:20px 0;
}

.btns{
display:flex;
justify-content:center;
gap:15px;
margin-top:20px;
}

button{
padding:12px 22px;
border:none;
border-radius:20px;
font-size:18px;
cursor:pointer;
transition:0.3s;
}

.yes{
background:#ff4d88;
color:white;
}

.no{
background:#ddd;
}

.emoji{
font-size:55px;
margin-top:15px;
animation:pop .5s ease;
}

@keyframes pop{
0%{transform:scale(0);}
100%{transform:scale(1);}
}

.teddy{
font-size:100px;
}

.message{
font-size:20px;
color:#ff4081;
margin-top:15px;
line-height:1.5;
}

.floating{
position:fixed;
font-size:40px;
animation:float 3s linear forwards;
pointer-events:none;
}

@keyframes float{
0%{
transform:translateY(0);
opacity:1;
}
100%{
transform:translateY(-400px);
opacity:0;
}
}
</style>
</head>
<body>

<div class="container">

<div class="stickers">
🌹🌸💖🧸🌼🌺💝
</div>

<h1>For My Bujiii ❤️</h1>

<div id="content">

<div class="question" id="question">
Do you wanna go on a cute little date with me? 🌷
</div>

<div class="emoji" id="emoji">💖</div>

<div class="btns">
<button class="yes" onclick="yesAnswer()">Yes ❤️</button>
<button class="no" id="noBtn" onclick="noAnswer()">No 🙈</button>
</div>

</div>

</div>

<script>
let step = 0;
let noCount = 0;

const questions = [
"Do you wanna go on a cute little date with me? 🌷",
"Don't you wanna meet me and make beautiful memories together? 🌸",
"Will you keep a tiny place for me in your heart forever? ❤️"
];

const emojis = [
"💋❤️🌹😘🌸",
"💖💋🌺😘🌹",
"❤️💋🌷💖😘"
];

function launchConfetti(){
confetti({
particleCount:120,
spread:100,
origin:{y:0.6}
});
}

function floatingLove(){
const arr=["💋","❤️","🌹","🌸","💖","😘","🌺"];
for(let i=0;i<12;i++){
let el=document.createElement("div");
el.className="floating";
el.innerHTML=arr[Math.floor(Math.random()*arr.length)];
el.style.left=Math.random()*100+"vw";
el.style.top="80vh";
document.body.appendChild(el);

setTimeout(()=>{
el.remove();
},3000);
}
}

function yesAnswer(){

launchConfetti();
floatingLove();

step++;

if(step<questions.length){
document.getElementById("question").innerHTML=questions[step];
document.getElementById("emoji").innerHTML=emojis[step];
}else{

document.getElementById("content").innerHTML=`
<div class="teddy">🧸</div>

<h2 style="color:#ff4081;margin-top:10px;">
Yayyyy Bujiii ❤️
</h2>

<div class="message">
🌹💖💋<br><br>
I Love You So Much My Sweetheart ❤️<br>
Miss You So Muchhhh 🥺💞<br><br>
Forever Sending You Hugs, Flowers,
Kisses & Smiles 🌸🌹💋
</div>
`;

launchConfetti();

setInterval(()=>{
confetti({
particleCount:30,
spread:80
});
},1000);
}
}

function noAnswer(){

noCount++;

if(noCount===1){
alert("Aww Bujiii 🥺 Are you sure? You get one more chance ❤️");

const btn=document.getElementById("noBtn");

btn.style.position="absolute";
btn.style.left=Math.random()*70+"%";
btn.style.top=Math.random()*70+"%";
}
else{
const btn=document.getElementById("noBtn");
btn.innerHTML="Yes ❤️";
btn.className="yes";
btn.onclick=yesAnswer;
}
}
</script>

</body>
</html>
