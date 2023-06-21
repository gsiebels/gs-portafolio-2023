<script setup>
import { ref, onMounted } from 'vue'
import Stack from './Stack.vue'

const scrollArea = ref(null)
let scrollAreaNode = ''
const spanStart = 200

onMounted(() => {
  scrollAreaNode = scrollArea.value.style

  window.addEventListener('scroll', (e) => {
    const pageY = window.pageYOffset
    console.log(pageY)
    if (pageY > spanStart) {
      if (scrollAreaNode.scale <= 1) {
        scrollAreaNode.scale = 0 + ((pageY - spanStart) * 0.004)
      }
      if (scrollAreaNode.scale > 1) scrollAreaNode.scale = 1
      scrollAreaNode.opacity = 1
    } else {
      scrollAreaNode.opacity = 0
    }

  })
})

</script>

<template>
  <div class="scroll-container">

    <div class="scroll-area" ref="scrollArea">
      <Stack/>
    </div>
  </div>
</template>

<style lang="scss" scoped>

  .scroll-container {
    height: 100vh;
    width: 100%;
    position: sticky;
    top: 0px;
  }
  .scroll-area {
    width: 100%;
    height: 100vw;  
    background: none;
    position: absolute;
    opacity: 0;
    display: flex;
    gap: 0 50px;
    flex-wrap: wrap;
    justify-content: center;
    padding: 100px 0;
  }
</style>