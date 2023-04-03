

<template>
  <header>
    <nav class="navbar-dark bg-dark">
      <span class="navbar-brand">OHM TWINCIRCUIT</span>
    </nav>
  </header>

  <NowDateTime />
  <Timer />

  <NowStatusFooter />
  
</template>

<script>
import NowStatusFooter from './components/NowStatusFooter.vue'
import NowDateTime from './components/NowDateTime.vue'
import Timer from './components/Timer.vue'

export default {
  components: {
    NowStatusFooter,
    NowDateTime,
    Timer
  },
}
</script>