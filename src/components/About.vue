<script setup>
import { ref, onMounted } from 'vue'

const about = ref(null)
let aboutNode = ''

onMounted(() => {
  aboutNode = about.value.style
  
  
  window.addEventListener('scroll', (e) => {
    const pageY = window.pageYOffset
      aboutNode.scale = 1 + (pageY * (pageY * 0.0002))
  })
})
</script>

<template>
  <dir class="about-area" ref="about">
    <div class="name"> 
      gerardo 
      <div class="surname">s<div>i</div>ebels</div>
    </div>

    <div class="description">
      Full Stack Software Engineer 
    </div>


  </dir>
</template>

<style scoped lang="scss">
  .about-area {
    height: calc(100vh - 70px);
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    color: white;
    position: sticky;
    top: 70px;
    padding: 0;

    .name {
      font-size: 110px;
      display: flex;
      flex-direction: column;
      margin: 0;
      line-height: 77px;
      font-family: 'Space Grotesk', sans-serif;

      .surname {
        margin: 0 0 0 172px;
        display: flex;
        
        div {
          rotate: 180deg;
          margin: 20px 0 0;
        }
      }
    }

    .description {
        font-size: 18px;
        margin: 50px;
        letter-spacing: 3px;
    }

  }
</style>
