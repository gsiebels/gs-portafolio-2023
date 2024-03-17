<script setup>
import { ref, onMounted } from 'vue'
import Stack from './Stack.vue'

const scrollArea = ref(null)
const scrollContainer = ref(null)
const scrollContinues = 800
let scrollAreaNode = ''
let scrollContainerStyle = ''
const spanStart = 400

onMounted(() => {
  scrollAreaNode = scrollArea.value.style
  scrollContainerStyle = scrollContainer.value.style

  window.addEventListener('scroll', (e) => {
    const pageY = window.pageYOffset
    console.log(pageY)
    if (pageY > spanStart) {
      if (scrollAreaNode.scale <= 1) {
        scrollAreaNode.scale = 0 + ((pageY - spanStart) * 0.004)
      }
      if (scrollAreaNode.scale > 1) scrollAreaNode.scale = 1
      // scrollAreaNode.opacity = 1
    } else {
      // scrollAreaNode.opacity = 0
    }

    // if (pageY >= scrollContinues) {
    //   scrollContainerStyle.position = 'absolute'
    // } else scrollContainerStyle.position = 'sticky'
  })



})

</script>

<template>
  <div class="scroll-container" ref="scrollContainer">
    <div class="scroll-area" ref="scrollArea">
      <Stack/>
      <div class="test">test</div>
    </div>
  </div>
</template>

<style lang="scss" scoped>

  .scroll-container {
    height: 100vh;
    width: 100%;
    // position: sticky;
    top: 0px;
    background: #30303029;
    backdrop-filter: blur(10px);
    border: 2px solid #10de980f;
    border-radius: 7px;
    box-shadow: 0px -1px 7px 7px #10de980f;
  }

  .scroll-area {
    width: 100%;
    height: 100vw;  
    background: none;
    position: absolute;
    // opacity: 0;
    display: flex;
    gap: 0 50px;
    flex-wrap: wrap;
    justify-content: center;
    padding: 100px 0;
  }
</style>