<script setup>
import { ref, onMounted } from 'vue'

const stack = ref(null)
const langList = [
  {
    name: 'HTML',
    img: 'logoHtml.svg',
    level: 5
  },
  {
    name: 'CSS',
    img: 'logoCss.svg',
    level: 5
  },
  {
    name: 'JavaScript',
    img: 'logoJs.svg',
    level: 4
  },
  {
    name: 'Vue.js',
    img: 'logoVue.svg',
    level: 4
  },
  {
    name: 'Nuxt.js',
    img: 'logoNuxt.svg',
    level: 4
  },
  {
    name: 'Python',
    img: 'logoPython.svg',
    level: 3
  },
  {
    name: 'Django',
    img: 'logoDjango.svg',
    level: 2
  },
  
]
let stackNode = ''

onMounted(() => {
  stackNode = stack.value.style

  window.addEventListener('scroll', (e) => {
    console.log(window.pageYOffset)
    if (window.pageYOffset > 180) {
      if (stackNode.scale <= 1) {
        stackNode.scale = 0 + ((window.pageYOffset - 180) * 0.005)
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
    <div class="stack-container" v-for="(lang, idx) in langList" :key="idx">
      <img :src="`/src/assets/logos/${lang.img}`" :alt="`${lang.name} icon`">
      <p>{{ lang.name }}</p>
      <dir>{{ lang.level }}</dir>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .stack-area {
    width: 100%;
    height: 100vw;  
    background: none;
    position: absolute;
    top: 10%;
    opacity: 0;
    display: flex;
    gap: 0 50px;
    flex-wrap: wrap;
    justify-content: center;
    padding: 100px 0;
  }
  .stack-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 25%;
    height: 200px;
    gap: 10px;

    .lang-icon {
      width: 50%;
      max-height: 100%;
      height: 110px;
      display: flex;
      justify-content: center;
      align-items: center;

      svg {
          max-height: 100%;
      }
    }
  }
</style>