<template>
  <canvas id="sky" class="sky"></canvas>
</template>

<script>
export default {
  name: 'Stars',
  methods: {
    resizeCanvas: function() {
      var sky = document.getElementById("sky");
      sky.setAttribute('width', window.innerWidth);
      sky.setAttribute('height', window.innerHeight);
    },
    drawStars: function(event) {
      var sky = document.getElementById("sky"),
          ctx = sky.getContext('2d'),
          spreadRadius = 120,
          xMin = event.clientX - spreadRadius,
          xMax = event.clientX + spreadRadius,
          yMin = event.clientY - spreadRadius,
          yMax = event.clientY + spreadRadius,
          x = Math.random() * (xMax - xMin) + xMin,
          y = Math.random() * (yMax - yMin) + yMin,
          radius = Math.random() * (1 - 0.02) + 0.02,
          alpha = Math.random() * (1 - 0.02) + 0.2;
      ctx.beginPath();
      ctx.arc(x, y, radius, 0, 2*Math.PI, false);
      ctx.fillStyle = 'rgba(255, 246, 232, ' + alpha + ')';
      ctx.fill();
    }
  },
  mounted() {
    this.resizeCanvas();
    window.addEventListener('resize', this.resizeCanvas);
    window.addEventListener('mousemove', this.drawStars);
  }
}
</script>

<style scoped lang="scss">
.sky {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
}
</style>
