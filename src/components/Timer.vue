<template>

  <div class="d-flex align-items-center" style="height: 20vh">
    <div class="text-center w-100">
      <div class="mt-5" id="cout_down" style="">{{ countDown }}</div>
    </div>
  </div>
  
</template>

<style>
#cout_down {
  font-size: 34vmin;
}
</style>

<script>
import dayjs from 'dayjs';
import duration from 'dayjs/plugin/duration'

dayjs.extend(duration)

export default {
  data() {
    return {
      countDown: '',
    }
  },
  mounted() {
    this.startTimer();
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
}
</script>


