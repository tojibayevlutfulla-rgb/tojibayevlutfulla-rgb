###  I'm aslbek ulugbekovv 👋

<p align="center">
  

 <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%" height="3px">
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=250&color=0:000000,50:4CAF50,100:000000&text=Hii%20I'm%20tojibayevlutfulla-rgb%20Welcome%20to%20my%20GitHub%20profile!&fontSize=30&fontColor=39FF14&animation=twinkling&fontAlignY=38"/>
</p>

 <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%" height="3px">
<h1 align="center" style="color:#39FF14; text-shadow: 0 0 8px #39FF14, 0 0 20px #39FF14;">


<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=26&duration=2800&pause=900&color=00F260&center=true&vCenter=true&width=820&lines=Python+Developer;Al-xorazmiy+vorislari+IT+student" />
</p>


<h2 align="center">🛠 Tech Arsenal</h2>

<p align="center">
<img src="https://skillicons.dev/icons?i=js,ts,react,nextjs,html,css,tailwind,nodejs,express,github,vscode,ai&perline=14" width="100%" />
</p>

<div align="center">

<div align="center">

## 📊 GitHub Analytics.
</div>

<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=&theme=react-dark&hide_border=true&area=true" width="100%" />
</p>

<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=tojibayevlutfulla-rgb&theme=neon&hide_border=true" width="100%" />
</p>





<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Snake Game</title>
<style>
  body {
    margin: 0;
    background: #111;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }

  canvas {
    background: #000;
    border: 3px solid lime;
  }
</style>
</head>
<body>

<canvas id="game" width="400" height="400"></canvas>

<script>
const canvas = document.getElementById("game");
const ctx = canvas.getContext("2d");

const size = 20;
const tileCount = canvas.width / size;

let snake = [{x: 10, y: 10}];
let velocityX = 1;
let velocityY = 0;

let food = {
  x: Math.floor(Math.random() * tileCount),
  y: Math.floor(Math.random() * tileCount)
};

document.addEventListener("keydown", (e) => {
  if (e.key === "ArrowUp" && velocityY === 0) {
    velocityX = 0; velocityY = -1;
  }
  if (e.key === "ArrowDown" && velocityY === 0) {
    velocityX = 0; velocityY = 1;
  }
  if (e.key === "ArrowLeft" && velocityX === 0) {
    velocityX = -1; velocityY = 0;
  }
  if (e.key === "ArrowRight" && velocityX === 0) {
    velocityX = 1; velocityY = 0;
  }
});

function gameLoop() {
  update();
  draw();
}

function update() {
  const head = {
    x: snake[0].x + velocityX,
    y: snake[0].y + velocityY
  };

  // devorga urilish
  if (
    head.x < 0 || head.y < 0 ||
    head.x >= tileCount || head.y >= tileCount ||
    snake.some(s => s.x === head.x && s.y === head.y)
  ) {
    alert("Game Over");
    snake = [{x: 10, y: 10}];
    velocityX = 1;
    velocityY = 0;
    return;
  }

  snake.unshift(head);

  // ovqat yeyish
  if (head.x === food.x && head.y === food.y) {
    food = {
      x: Math.floor(Math.random() * tileCount),
      y: Math.floor(Math.random() * tileCount)
    };
  } else {
    snake.pop();
  }
}

function draw() {
  ctx.fillStyle = "black";
  ctx.fillRect(0, 0, canvas.width, canvas.height);

  // snake
  ctx.fillStyle = "lime";
  snake.forEach(s => {
    ctx.fillRect(s.x * size, s.y * size, size - 2, size - 2);
  });

  // food
  ctx.fillStyle = "red";
  ctx.fillRect(food.x * size, food.y * size, size - 2, size - 2);
}

setInterval(gameLoop, 120);
</script>

</body>
</html>









