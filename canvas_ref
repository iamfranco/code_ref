# Canvas Reference
This is the boilerplate for general JavaScript canvas animation.

```JavaScript
var circleArray = [];

function $(x) {return document.querySelector(x);}

var canvas = $('canvas');
var ctx = canvas.getContext('2d');

var mouse = {x: undefined, y: undefined}
window.addEventListener('mousemove', function(event) {mouse.x = event.x; mouse.y = event.y;})

function Circle(x,y,r) {
  this.x = x;
  this.y = y;
  this.radius = r;
  
  this.draw = function() {
    ctx.beginPath();
    ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2, true);
    ctx.fillStyle = '#345';
    ctx.fill();
  }
  this.update = function() {
    this.draw();
  }
}

function init() {
  canvas.width = window.innerWidth*window.devicePixelRatio;
  canvas.height = window.innerHeight*window.devicePixelRatio;
  canvas.style.width = canvas.width/window.devicePixelRatio+'px';
  canvas.style.height = canvas.height/window.devicePixelRatio+'px';
  ctx.scale(window.devicePixelRatio,window.devicePixelRatio);
  
  circleArray = [];
  circleArray.push(new Circle(100,100,10));
}

function animate() {
  requestAnimationFrame(animate);
  ctx.clearRect(0, 0, innerWidth, innerHeight);
  for (var i=0; i<circleArray.length; i++) {
    circleArray[i].update();
  }
}

init();
animate();
```
