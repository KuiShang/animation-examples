<script setup>
import Example1 from './components/Example1.vue';
import Example2 from './components/Example2.vue';
import Example3 from './components/Example3.vue';
import Example4 from './components/Example4.vue';
import Example5 from './components/Example5.vue';
import Example6 from './components/Example6.vue';
</script>

<template>
  <div class="app-content">
    <Example1 />
    <Example2 />
    <Example3 />
    <Example4 />
    <Example5 />
    <Example6 />
  </div>
</template>

<style scoped>
.app-content {
  display: flex;
  flex-wrap: wrap;
  .content {
    position: relative;
  }
}
</style>
<style>
.example-wrapper {
  width: 400px;
  height: 400px;
  border: 1px solid #999;
  margin-right: 15px;
  margin-bottom: 15px;
}
</style>
