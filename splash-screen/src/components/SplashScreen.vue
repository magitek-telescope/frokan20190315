<template>
  <div id="splash-launched">
    <div>
      <img src="https://elevenback.jp/_nuxt/img/5e1feb8.svg" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  mounted() {
    setTimeout(() => {
      this.$emit('hide')
    }, 900)
  }
})
</script>

<style scoped>
#splash-launched {
  align-items: center;
  justify-content: center;
}

#splash-launched img {
  animation: slideOut 0.4s 0.5s ease-out forwards;
}

@keyframes slideOut {
  0% {
    transform: translateY(0px);
    opacity: 1;
  }
  100% {
    transform: translateY(10px);
    opacity: 0;
  }
}
</style>
