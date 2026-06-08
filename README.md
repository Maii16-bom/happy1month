<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy 1 Month ❤️</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Segoe UI',sans-serif;
}

body{
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#ffd1dc,#fff5f8);
    overflow:hidden;
}

.container{
    text-align:center;
}

.envelope{
    width:300px;
    height:200px;
    background:#ff8eb3;
    position:relative;
    cursor:pointer;
    border-radius:0 0 15px 15px;
    box-shadow:0 10px 25px rgba(0,0,0,.15);
}

.flap{
    position:absolute;
    width:0;
    height:0;
    border-left:150px solid transparent;
    border-right:150px solid transparent;
    border-top:110px solid #ff6b9c;
    top:0;
    transform-origin:top;
    transition:1s;
}

.open .flap{
    transform:rotateX(180deg);
}

.letter{
    position:absolute;
    width:260px;
    background:white;
    left:20px;
    top:20px;
    padding:20px;
    border-radius:15px;
    box-shadow:0 10px 20px rgba(0,0,0,.15);
    transform:translateY(100px);
    opacity:0;
    transition:1s;
}

.show{
    transform:translateY(-180px);
    opacity:1;
}

h2{
    color:#ff4f88;
    margin-bottom:15px;
}

#text{
    color:#555;
    line-height:1.8;
    min-height:180px;
}

.heart{
    position:absolute;
    font-size:20px;
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

<div class="container">
    <div class="envelope" id="envelope" onclick="openLetter()">
        <div class="flap"></div>

        <div class="letter" id="letter">
            <h2>❤️ ครบรอบ 1 เดือน ❤️</h2>
            <p id="text"></p>
        </div>
    </div>
</div>

<script>

const message = `
ถึงคนเก่งของเค้า ❤️

ขอบคุณที่เข้ามาเป็นส่วนหนึ่งของชีวิตเค้านะ

1 เดือนที่ผ่านมาอาจดูไม่นาน
แต่สำหรับเค้า มันเป็นช่วงเวลาที่มีความหมายมากจริง ๆ

ขอบคุณที่อยู่ด้วยกัน
ขอบคุณที่รับฟังกัน
ขอบคุณที่ทำให้ทุกวันของเค้ามีรอยยิ้ม

เค้าอาจจะไม่ใช่คนที่สมบูรณ์แบบ
แต่เค้าจะพยายามดูแลเธอให้ดีที่สุดเท่าที่เค้าทำได้

สุขสันต์ครบรอบ 1 เดือนนะคนเก่ง ❤️

รักเธอมาก ☺️
`;

let opened = false;

function openLetter(){

if(opened) return;
opened = true;

document.getElementById("envelope").classList.add("open");
document.getElementById("letter").classList.add("show");

let i = 0;
const text = document.getElementById("text");

const typing = setInterval(()=>{
    text.innerHTML += message.charAt(i);
    i++;

    if(i >= message.length){
        clearInterval(typing);
    }
},40);

startHearts();
}

function startHearts(){

setInterval(()=>{

const heart = document.createElement("div");
heart.classList.add("heart");
heart.innerHTML = "❤️";

heart.style.left = Math.random()*100 + "vw";
heart.style.fontSize = (20 + Math.random()*30) + "px";

document.body.appendChild(heart);

setTimeout(()=>{
heart.remove();
},6000);

},250);

}
</script>

</body>
</html># happy1month
