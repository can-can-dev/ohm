<template>

  <div :class="{'blink':isBlink}">
    <slot />
  </div> 
  
</template>

<style>
.blink {
  animation: flash 2.5s linear infinite;
  min-height: 100vh;
}

@keyframes flash {
	0%,
	100% {
    background: #0091EA;
	}

	50% {
    background: #fff;
	}
}
</style>

<script>
export default {
  props: {
    isBlink: Boolean,
  }
}
</script>


