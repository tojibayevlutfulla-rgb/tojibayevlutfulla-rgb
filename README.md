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
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #111;
      color: white;
      font-family: Arial;
    }
    canvas {
      background: black;
      border: 2px solid #0f0;
    }
  </style>
</head>
<body>

<canvas id="game" width="400" height="400"></canvas>

<script>
const canvas = document.getElementById("game");
const ctx = canvas.getContext("2d");

const box = 20;
let snake = [{x: 200, y: 200}];
let direction = "RIGHT";
let food = {
  x: Math.floor(Math.random()*20)*box,
  y: Math.floor(Math.random()*20)*box
};

document.addEventListener("keydown", changeDirection);

function changeDirection(e) {
  if (e.key === "ArrowLeft" && direction !== "RIGHT") direction = "LEFT";
  if (e.key === "ArrowUp" && direction !== "DOWN") direction = "UP";
  if (e.key === "ArrowRight" && direction !== "LEFT") direction = "RIGHT";
  if (e.key === "ArrowDown" && direction !== "UP") direction = "DOWN";
}

function draw() {
  ctx.fillStyle = "black";
  ctx.fillRect(0, 0, 400, 400);

  // snake
  ctx.fillStyle = "lime";
  snake.forEach(part => ctx.fillRect(part.x, part.y, box, box));

  // food
  ctx.fillStyle = "red";
  ctx.fillRect(food.x, food.y, box, box);

  let headX = snake[0].x;
  let headY = snake[0].y;

  if (direction === "LEFT") headX -= box;
  if (direction === "UP") headY -= box;
  if (direction === "RIGHT") headX += box;
  if (direction === "DOWN") headY += box;

  // eat food
  if (headX === food.x && headY === food.y) {
    food = {
      x: Math.floor(Math.random()*20)*box,
      y: Math.floor(Math.random()*20)*box
    };
  } else {
    snake.pop();
  }

  const newHead = {x: headX, y: headY};

  // game over
  if (
    headX < 0 || headY < 0 || 
    headX >= 400 || headY >= 400 ||
    snake.some(p => p.x === headX && p.y === headY)
  ) {
    clearInterval(game);
    alert("Game Over!");
  }

  snake.unshift(newHead);
}

const game = setInterval(draw, 100);
</script>

</body>
</html>









