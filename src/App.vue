

<template>
  <header>
    <nav class="navbar-dark bg-dark">
      <a class="navbar-brand" href="#">OHM TWINCIRCUIT</a>
    </nav>
  </header>

  <div class="d-flex align-items-center" style="height: 30vh">
    <div class="text-center w-100">
      <div style="font-size: 5vh">{{ now_datetime }}</div>
    </div>
  </div>

<!-- TODO: コンポーネント分ける -->
  <div class="d-flex align-items-center" style="height: 20vh">
    <div class="text-center w-100">
      <div class="mt-5" style="font-size: 30vh">{{ countDown }}</div>
    </div>
  </div>


  <NowStatusFooter />
  
</template>

<script >
import NowStatusFooter from './components/NowStatusFooter.vue'
import dayjs from 'dayjs';
import duration from 'dayjs/plugin/duration'

dayjs.extend(duration)

export default {
  data() {
    return {
      now_datetime: '',
      countDown: '',
    }
  },
  mounted() {
    this.startTimer();
    setInterval(() => {
      this.now_datetime = dayjs().format('YYYY/MM/DD HH:mm:ss');
      
    }, 1000);
  },
  methods: {
    startTimer() {
      this.updateCountDown();
      this.timer = setInterval(() => {
        this.updateCountDown();
      }, 1000);
    },
    stopTimer() {
      clearInterval(this.timer);
      this.timer = null;
    },
    updateCountDown() {
      const now = dayjs();
      let currentMinute = now.minute();
      let targetMinute = Math.ceil(currentMinute / 10) * 10;
      let targetTime = dayjs().minute(targetMinute).second(0);
      if (targetTime.diff(now) <= 0) {
        targetTime = targetTime.add(10, 'minute');
      }
      let diff = dayjs.duration(targetTime.diff(now));
      let minutes = diff.minutes().toString().padStart(2, '0');
      let seconds = diff.seconds().toString().padStart(2, '0');
      this.countDown = `${minutes}:${seconds}`;
    },
  },



  components: {
    NowStatusFooter
  },


}
</script>