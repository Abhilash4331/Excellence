<script setup>
// import HelloWorld from './components/HelloWorld.vue'
// import test from './components/test.vue'
// import textColor from './components/textColor.vue'
import listRendering from './components/listRendering.vue'
// import customerDetails from './components/customerDetails.vue'
</script>

<template>
  <div>
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />  
  </div>

<!-- <test/>
<textColor/> -->
<listRendering/>
<!-- <customerDetails/> -->
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #054f2eaa);
}
</style>
