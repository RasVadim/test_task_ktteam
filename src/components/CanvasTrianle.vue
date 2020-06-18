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

  canv.width = "501";
  canv.height = "501";

  function setPixel(point, red=255, blue=255, green=255, alpha=255) {
    // point: [x, y]
    var img = ctx.createImageData(1, 1);
    img.data[0] = red; // red
    img.data[1] = green; // green
    img.data[2] = blue; // blue
    img.data[3] = alpha; // alpha
    ctx.putImageData(img, point[0], point[1]);
  }

  let A = [0, 0],
      B = [500, 0],
      C = [500, 500],
      D = [0, 500],
      N = [250, 250];

  let tops = [A, B, C, D];

  for (let top in tops) {
     setPixel(tops[top]);
  };

  setPixel(N);

  let xN = N[0],
      yN = N[1];

  setInterval(function() {
    for (let i = 0; i < 30; i++) {
      let M = tops[Math.floor(Math.random() * 3)];
      xN = (xN + M[0]) / 2;
      yN = (yN + M[1]) / 2;

      let red = Math.floor(xN *255/500), 
          blue =  Math.floor(255 - xN *255/500),
          green =  Math.floor(255 - yN *255/500),
          alpha = 255;
      setPixel([xN, yN], red, blue, green, alpha);
      // return xN, yN;
    }
  }, 100);
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.canvcont {
  height: 600px;
}

#canvas {
  // border: 1px solid green;
}
</style>
