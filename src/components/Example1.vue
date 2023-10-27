<script setup></script>

<template>
  <div class="example-wrapper">
    <div class="title">Example1:hover时下划线动态展开效果</div>
    <div class="content">
      <ul>
        <li><a>菜单</a></li>
        <li><a>个人</a></li>
      </ul>
    </div>
  </div>
</template>

<style scoped lang="scss">
/* 零距标准化 body */
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  /* mobile 端切换横竖屏适配 */
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  /* 渲染优化 */
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  font-size: 15px;
}

ul {
  display: inline-block;
  list-style: none;
  margin: 20px;
  border-bottom: 1px solid #f0f0f0;
  padding-left: 0;
  /* 去掉 inline-block 产生的块间隙 */
  font-size: 0;
}

li {
  display: inline-block;
  padding: 20px 30px;
  font-size: 15px;
  font-weight: 700;
  color: #969696;
  position: relative;
}

li a {
  cursor: pointer;
  outline: 0;
  text-decoration: none;
}

li a:hover {
  color: #646464;
}

li:hover:after {
  opacity: 1;
  transform: translate(-50%) scaleX(1);
}

li:after {
  content: '';
  position: absolute;
  left: 50%;
  bottom: -2px;
  width: 100%;
  opacity: 0;
  border-bottom: 2px solid #646464;
  transform: translate(-50%) scaleX(0);
  transition: 0.2s ease-in-out;
}
</style>
