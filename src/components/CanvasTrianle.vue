<template>
  <div class="canvcont">
    <canvas id="canvas">It's not supported</canvas>
  </div>
</template>

<script>
export default {
  name: "CanvasTrianle",
  props: {
    msg: String
  }
};


window.onload = function() {  
  const canv = document.getElementById("canvas"),
    ctx = canv.getContext("2d");

  canv.width = "500";
  canv.height = "500";

  ctx.fillStyle = "green";
  ctx.strokeStyle = "green";
  ctx.lineWidth = 2;


  let 
  xA = 250, 
  yA = 0, 
  xB = 0, 
  yB = 470, 
  xC = 500, 
  yC = 470;
  
setPixel([250,250]);

  ctx.beginPath();
  ctx.moveTo(xA, yA);
  ctx.lineTo(xB, yB);
  ctx.lineTo(xC, yC);
  ctx.closePath();
  ctx.stroke();




  // ctx.arc(250, 250, 50, 0, Math.PI *2);
  // ctx.stroke();
  // setInterval(function() {
  //   ctx.fillStyle = "white";
  //   ctx.fillRect(0, 0, canv.width, canv.height);
  //   ctx.fillStyle = "green";
  //   ctx.fillRect(x++, 10, 150, 150);
  // }, 10);

function setPixel(point) { // point: [x, y]
    var img = canv.createImageData(1,1);
    img.data[0]=0 // red
    img.data[1]=0 // green
    img.data[2]=0 // blue
    img.data[3]=255 // alpha
    canv.putImageData(img,point[0],point[1]);
};

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.canvcont {
  height: 600px;
}

#canvas {
  border: 1px solid green;
}
</style>
