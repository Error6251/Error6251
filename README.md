### Hi there 👋
#### I'm Juhair Islam

<canvas id="JS" width="400" height="400"></canvas>

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=Error6251&layout=compact&show_icons=true&theme=radical)](https://github.com/anuraghazra/github-readme-stats)


<script>
window.onload = function () {
  canv = document.getElementById("JS");
  draw = canv.getContext("2d");
  initial();
  setInterval(loop, 1000 / 15);
};

function initial() {
  nameText = new text();
}

function loop() {
  //Background
  draw.fillStyle = "black";
  draw.fillRect(0, 0, canv.width, canv.height);

  nameText.update();
  nameText.check();
}

//Other objects
class text {
  constructor() {
    this.x = 0;
    this.y = 0;
    this.sizeX = 150;
    this.sizeY = 110;
    this.velX = 5;
    this.velY = 7;
    this.color = ["red", "white", "blue", "green"];
    this.colNo = 0;
  }

  update() {
    draw.fillStyle = this.color[this.colNo];
    draw.fillRect(this.x, this.y, this.sizeX, this.sizeY);

    let x = this.x;
    let y = this.y + this.sizeY - 10;
    draw.fillStyle = "black";
    draw.font = "50px Calluna";
    draw.fillText("Juhair", x+15, y-50);
    draw.fillText("Islam", x+20, y-10);
    
    this.x += this.velX;
    this.y += this.velY;
  }
  check() {
    if (this.x + this.sizeX + this.velX > canv.width) {
      this.velX -= this.velX * 2;
      this.colNo = 0;
    }
    if (this.y + this.sizeY + this.velY > canv.height) {
      this.velY -= this.velY * 2;
      this.colNo = 1;
    }
    if (this.x + this.velX < 0) {
      this.velX -= this.velX * 2;
      this.colNo = 2;
    }
    if (this.y + this.velY < 0) {
      this.velY -= this.velY * 2;
      this.colNo = 3;
    }
  }
}
</script>
