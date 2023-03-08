<template>
  <div class="fixed-bottom">
    <div class="row">

      <div class="col p-0 border ">
        <div class="bg-secondary border-bottom">
          <label class="text-white">オンロード</label>
        </div>
        <div class="d-flex justify-content-center align-items-center" :class="onload.class" style="height:10vh">
          {{ onload.text }}
        </div>
      </div>

      <div class="col p-0 border">
        <div class="bg-secondary border-bottom">
          <label class="text-white">オフロード</label>
        </div>
        <div class="d-flex justify-content-center align-items-center" :class="offload.class" style="height:10vh">
          {{ offload.text }}
        </div>
      </div>

    </div>
  </div>
</template>

<script>
import dayjs from 'dayjs';

export default {
  data() {
    return {
      offload: {
        text: '',
        class: '',
      },
      onload: {
        text: '',
        class: '',
      },
    }
  },
  mounted() {
    setInterval(() => {
      let now_minits = parseFloat(dayjs().format('m'));
      let time_group = Math.floor(now_minits * 0.1) % 3;

      switch (time_group) {
        case 0:
          this.onload = {
            text: '上級クラス',
            class: 'bg-danger text-white',
          };

          this.offload = {
            text: '初・中級クラス',
            class: 'bg-warning',
          };
          break;
        case 1:
          this.onload = {
            text: '中級クラス',
            class: 'bg-primary text-white',
          };

          this.offload = {
            text: 'ハイエンド時間　オフストック',
            class: 'bg-primary text-white',
          };
          break;
        case 2:
          this.onload = {
            text: '初・中級クラス',
            class: 'bg-warning',
          };

          this.offload = {
            text: 'ハイエンド時間　モデファイ最優先',
            class: 'bg-danger text-white',
          };
          break;
        default:
          console.log(`out of`);
      }
    }, 1000);
  },
}
</script>