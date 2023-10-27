<script setup>
import { onMounted } from 'vue';

const init = () => {
  let canvasEl = document.getElementById('tutorial');
  let ctx = canvasEl.getContext('2d'); // 2d | webgl
  const drawSun = () => {
    ctx.save();
    ctx.translate(150, 150); // 移动坐标
    ctx.strokeStyle = 'rgba(0, 153, 255, 0.4)';
    ctx.beginPath(); // 绘制轨道
    ctx.arc(0, 0, 100, 0, Math.PI * 2);
    ctx.stroke();
    // 绘制sun

    ctx.beginPath();
    const g = ctx.createRadialGradient(-10, -5, 0, 0, 0, 30);
    g.addColorStop(0.0, '#fff');
    g.addColorStop(1.0, '#cc1414');
    ctx.fillStyle = g;
    ctx.arc(0, 0, 30, 0, 2 * Math.PI);
    ctx.fill();

    ctx.restore();
  };
  const drawEarth = () => {
    ctx.save();
    ctx.translate(150, 150); // 移动坐标
    ctx.translate(100, 0); // 圆上的坐标系
    ctx.beginPath();
    const g = ctx.createRadialGradient(-3, -5, 0, 0, 0, 20);
    g.addColorStop(0.0, '#fff');
    g.addColorStop(1.0, 'blue');
    ctx.fillStyle = g;
    ctx.arc(0, 0, 20, 0, 2 * Math.PI);
    ctx.fill();
    ctx.restore();
  };
  const draw = () => {
    console.log('draw');
    ctx.clearRect(0, 0, canvasEl.width, canvasEl.height);

    drawSun();
    // 2.地球
    drawEarth();
  };
  draw();
};
onMounted(() => {
  init();
});
</script>

<template>
  <div class="example-wrapper">
    <div class="title">Example1:svg描边动画</div>
    <div class="content">
      <canvas id="tutorial" width="300" height="300"></canvas>
    </div>
  </div>
</template>

<style scoped lang="scss"></style>
