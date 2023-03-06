<script setup>
import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <div class="fixed-bottom">
    <div class="row">

      <div class="col p-0 border ">
        <div class="bg-secondary border-bottom">
          <label class="text-white">オンロード</label>
        </div>
        <div class="bg-danger text-white d-flex justify-content-center align-items-center" style="height:10vh">
          上級者
        </div>
      </div>

      <div class="col p-0 border">
        <div class="bg-secondary border-bottom">
          <label class="text-white">オンロード</label>
        </div>
        <div class="bg-warning d-flex justify-content-center align-items-center" style="height:10vh">
          初心者
        </div>
      </div>

    </div>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
