<script setup>
  import { ref } from 'vue'
  defineProps({
    
  })

  const navbarOptions = [
    'home.',
    'stack.',
    'experience.',
    'work.',
    'contact.',
  ]

  let chosenOption = ref(0)
  

</script>

<template>
  <nav class="nav">
      <div class="navbar-background" :style="{ left: `-${ chosenOption  * 100 }%` }"/>
      <div class="navbar">
        <p 
          class="nav-option"
          v-for="(option, idx) in navbarOptions"
          :key="idx"
          @click="chosenOption = idx"
          :class="[option, { active: chosenOption === idx }]"
          >
          {{ option }}
        </p>
      </div>
  </nav>
</template>

<style scoped lang="scss">

  .nav {
    height: 70px;
    overflow: hidden;
    font-family: 'Space Grotesk', sans-serif;
    position: sticky;
    top: -67px;
    z-index: 10;
  }
  .navbar-background {
    // background: linear-gradient(90deg, rgba(131,58,180,1) 0%, rgba(253,29,29,1) 50%, rgba(252,176,69,1) 100%);
    // background: linear-gradient(90deg, rgba(131,58,180,1) 0%, rgba(253,29,29,1) 10%, rgba(252,176,69,1) 20%, rgba(252,176,69,1) 30%, rgba(157,252,69,1) 40%, rgba(69,252,221,1) 50%, rgba(90,140,241,1) 60%, rgba(241,90,107,1) 70%, rgba(255,180,188,1) 80%, rgba(190,255,180,1) 90%, rgba(255,255,255,1) 100%);
    // background: linear-gradient(90deg, rgba(152,249,73,1) 0%, rgba(37,237,139,1) 35%, rgba(44,204,190,1) 65%, rgba(50,131,178,1) 100%);
    background: linear-gradient(to right, rgb(0, 220, 130), rgb(54, 228, 218), rgb(22, 167, 158));
    color: black;
    display: flex;
    align-items: center;
    padding: 0 0 3px;
    height: 100%;
    width: 500%;
    position: absolute;
    transition: all 2s ease;
  }

  .navbar {
    background: #1a1a1a;
    color: white;
    width: 100%;
    height: calc(100% - 3px);
    display: flex;
    align-items: center;
    padding: 0 20px;
    color: white;
    mix-blend-mode: darken;
    display: flex;
    justify-content: center;
    gap: 60px;

    .nav-option {
      font-weight: 500;
      cursor: pointer;
      transition: all 0.2s ease-out;
      // rotate: -10deg;
      // transform: rotateY(1deg);

      &.active {
        margin: 5px 0 0;
        text-shadow: 0px 0px 2px #00dd8c;
        // rotate: 0deg;
        // transform: rotateY(360deg);

      }
    }

  }
</style>
