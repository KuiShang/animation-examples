<script setup></script>

<template>
  <div class="example-wrapper">
    <div class="title">Example1:水波纹效果</div>
    <div class="content">
      <a class="btn btn-primary btn-lg btn-custom">按钮一</a>

      <a class="btn btn-primary btn-lg ripple">按钮二</a>
    </div>
  </div>
</template>

<style scoped lang="scss">
.btn {
  --bs-btn-padding-y: 0.5rem;
  --bs-btn-padding-x: 1rem;
  --bs-btn-font-size: 1.25rem;
  --bs-btn-border-radius: 0.5rem;
  display: inline-block;
  padding: var(--bs-btn-padding-y) var(--bs-btn-padding-x);
  font-family: var(--bs-btn-font-family);
  font-size: var(--bs-btn-font-size);
  font-weight: var(--bs-btn-font-weight);
  line-height: var(--bs-btn-line-height);
  color: var(--bs-btn-color);
  text-align: center;
  text-decoration: none;
  vertical-align: middle;
  cursor: pointer;
  user-select: none;
  border: var(--bs-btn-border-width) solid var(--bs-btn-border-color);
  border-radius: var(--bs-btn-border-radius);
  background-color: var(--bs-btn-bg);
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out, border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
}
.btn-custom {
  position: relative;
  z-index: 1;
  overflow: hidden;
}

.btn-custom:hover {
  color: #ffffff;
}

.btn-custom:hover::before {
  transform: scale(1, 1);
  background-color: #103dbe;
}

.btn-custom::before {
  content: '';
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  transform: scale(0, 1);
  transition: all 0.6s;
  z-index: -1;
}

.ripple {
  position: relative;
  overflow: hidden;
}

.ripple:after {
  content: '';
  display: block;
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  pointer-events: none;
  background-image: radial-gradient(circle, rgba(0, 0, 0, 0.5) 10%, transparent 10.01%);
  background-repeat: no-repeat;
  background-position: 50%;
  transform: scale(10, 10);
  opacity: 0;
  transition: transform 0.3s, opacity 0.5s;
}

.ripple:active:after {
  transform: scale(0, 0);
  opacity: 0.3;
  transition: 0s;
}
</style>
