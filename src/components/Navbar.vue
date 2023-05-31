<script setup>
  import { ref, reactive, computed } from 'vue'
  defineProps({
    
  })

  const navbarOptions = [
    'home.',
    'stack.',
    'work.',
    'experience.',
    'contact.',
  ]

  let chosenOption = ref(0)
  

</script>

<template>
  <nav class="nav">
      <div class="navbar-background" :style="{ left: `-${ chosenOption  * 100 }%` }"/>
      <div class="navbar">
        <p v-for="(option, idx) in navbarOptions" :key="idx" @click="chosenOption = idx">
          {{ option }}
        </p>
        <!-- <p class="nav-el">home.</p>
        <p class="nav-el">stack.</p>
        <p class="nav-el">work.</p>
        <p class="nav-el">experience.</p>
        <p class="nav-el">contact.</p> -->
      </div>
  </nav>
</template>

<style scoped lang="scss">

  .nav {
    height: 50px;
    overflow: hidden;
  }
  .navbar-background {
    // background: linear-gradient(90deg, rgba(131,58,180,1) 0%, rgba(253,29,29,1) 50%, rgba(252,176,69,1) 100%);
    background: linear-gradient(90deg, rgba(131,58,180,1) 0%, rgba(253,29,29,1) 10%, rgba(252,176,69,1) 20%, rgba(252,176,69,1) 30%, rgba(157,252,69,1) 40%, rgba(69,252,221,1) 50%, rgba(90,140,241,1) 60%, rgba(241,90,107,1) 70%, rgba(255,180,188,1) 80%, rgba(190,255,180,1) 90%, rgba(255,255,255,1) 100%);
    color: black;
    display: flex;
    align-items: center;
    padding: 0 0 3px;
    height: 100%;
    width: 500%;
    position: absolute;
    // left: -300%;
    transition: all 2s ease;
  }

  .navbar {
    background: #151515;
    color: white;
    width: 100%;
    height: calc(100% - 3px);
    display: flex;
    align-items: center;
    padding: 0 20px;
    color: white;
    mix-blend-mode: multiply;
    display: flex;
    justify-content: center;
    gap: 80px;

    p {
      font-weight: 600;
      cursor: pointer;
    }

  }
</style>
