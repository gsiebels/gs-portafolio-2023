<script setup>
import { ref, onMounted } from 'vue'

const stack = ref(null)
let stackNode = ''

onMounted(() => {
  stackNode = stack.value.style

  window.addEventListener('scroll', (e) => {
    console.log(window.pageYOffset)
    if (window.pageYOffset > 3000) {
      // stackNode.scale = stackNode.scale <= 1 ? 0 + ((window.pageYOffset - 3000) * 0.005) : 1
      if (stackNode.scale <= 1) {
        stackNode.scale = 0 + ((window.pageYOffset - 3000) * 0.005)
      }
      if (stackNode.scale > 1) stackNode.scale = 1
      stackNode.opacity = 1
    } else {
      stackNode.opacity = 0
    }

  })
})

</script>

<template>
  <div class="stack-area" ref="stack">
    <div class="stack-container">
      <img class="stack-img" alt="Vue.js">
      <div class="stack-name">Vue.js</div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .stack-area {
    width: 100%;
    height: 100vw;  
    background: rgb(205, 246, 145);
    position: sticky;
    top: 0px;
    opacity: 0;
  }
</style>