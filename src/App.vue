

<template>
  <header>
    <nav class="navbar-dark bg-dark">
      <a class="navbar-brand" href="#">OHM TWINCIRCUIT</a>
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