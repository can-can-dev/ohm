<template>

  <div class="d-flex align-items-center" style="height: 30vh">
    <div class="text-center w-100">
      <div style="font-size: 5vmin">{{ now_datetime }}</div>
    </div>
  </div>
  
</template>

<script>
import dayjs from 'dayjs';

export default {
  data() {
    return {
      now_datetime: '',
    }
  },
  mounted() {
    setInterval(() => {
      this.now_datetime = dayjs().format('YYYY/MM/DD HH:mm:ss');
    }, 1000);
  },
}
</script>


