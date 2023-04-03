<template>
  <Blink :isBlink="isBlink">
    <header>
      <nav class="navbar-dark bg-dark">
        <span class="navbar-brand">OHM TWINCIRCUIT</span>
      </nav>
    </header>

    <NowDateTime />
    <Timer @setBlink="setBlink" />

    <NowStatusFooter />
  </Blink>
  
</template>

<script>
import NowStatusFooter from './components/NowStatusFooter.vue'
import NowDateTime from './components/NowDateTime.vue'
import Timer from './components/Timer.vue'
import Blink from './components/Blink.vue'

export default {
  data(){
    return {
      isBlink: false,
    }
  },
  methods: {
    setBlink(value){
      this.isBlink = value;
    }
  },
  components: {
    Blink,
    NowStatusFooter,
    NowDateTime,
    Timer
  },
}
</script>