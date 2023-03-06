<script setup>
import NowStatusFooter from './components/NowStatusFooter.vue'
</script>

<template>
  <header>
    <nav class="navbar-dark bg-dark">
      <a class="navbar-brand" href="#">OHM TWINCIRCUIT</a>
    </nav>
  </header>

  <div class="d-flex align-items-center" style="height: 30vh">
    <div class="text-center w-100">
      <div style="font-size: 5vh">2023/03/08 15:00:00</div>
    </div>
  </div>

  <div class="d-flex align-items-center" style="height: 20vh">
    <div class="text-center w-100">
      <div class="mt-5" style="font-size: 30vh">09:59:59</div>
    </div>
  </div>


  <NowStatusFooter />
  
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
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
