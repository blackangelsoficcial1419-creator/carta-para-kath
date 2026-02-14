<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Para Mi Kathe ❤️</title>

<style>
body{
  margin:0;
  height:100vh;
  background:linear-gradient(135deg,#ff758c,#ff7eb3);
  display:flex;
  justify-content:center;
  align-items:center;
  font-family:'Segoe UI',sans-serif;
  overflow:hidden;
}

.sobre{
  width:350px;
  height:220px;
  background:#ff4d6d;
  position:relative;
  cursor:pointer;
  border-radius:10px;
  display:flex;
  justify-content:center;
  align-items:center;
  color:white;
  font-weight:bold;
}

.carta{
  position:absolute;
  width:320px;
  background:white;
  padding:25px;
  border-radius:15px;
  top:10px;
  opacity:0;
  transform:translateY(20px);
  transition:0.8s;
  box-shadow:0 10px 30px rgba(0,0,0,0.3);
  color:#444;
  font-size:15px;
  line-height:1.6;
}

.abierto .carta{
  opacity:1;
  transform:translateY(-150px);
}

h2{
  text-align:center;
  color:#ff4d6d;
}

.corazon{
  position:absolute;
  color:red;
  animation:caer 5s linear infinite;
}

@keyframes caer{
  0%{transform:translateY(-10vh);}
  100%{transform:translateY(110vh);}
}
</style>
</head>

<body>

<audio autoplay loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mp3">
</audio>

<div class="sobre" onclick="abrirCarta()">
  Haz clic aquí 💌
  <div class="carta" id="carta">
    <h2>Mi Kathe ❤️</h2>
    <p id="texto"></p>
  </div>
</div>

<script>

let mensaje = `Mi Kathe, sé que estamos lejos, pero siento que tú eres la persona por la cual podría dar mi vida. 
A pesar de haber experimentado muy pocos momentos contigo, los guardo en mi corazón con todo el cariño del mundo, 
porque me encantas… no solo por lo bonita que eres, sino por la forma especial en la que te expresas, 
tu manera de ver la vida y la energía tan hermosa que siempre me transmites.

Sé que por el momento es a través de una pantalla, pero la verdad es que cada día me haces desear conocerte más.
Y aunque la distancia exista, lo que siento por ti es completamente real. ❤️`;

let i = 0;

function escribir(){
  if(i < mensaje.length){
    document.getElementById("texto").innerHTML += mensaje.charAt(i);
    i++;
    setTimeout(escribir, 30);
  }
}

function abrirCarta(){
  document.querySelector(".sobre").classList.add("abierto");
  escribir();
}

// corazones flotando
setInterval(()=>{
  let heart = document.createElement("div");
  heart.classList.add("corazon");
  heart.innerHTML="💖";
  heart.style.left=Math.random()*100+"vw";
  heart.style.fontSize=Math.random()*20+10+"px";
  document.body.appendChild(heart);
  setTimeout(()=>heart.remove(),5000);
},500);

</script>

</body>
</html>
