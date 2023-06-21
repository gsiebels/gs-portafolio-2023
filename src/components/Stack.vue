<script setup>
  import { onMounted, ref } from 'vue'
  import SkillLevel from './SkillLevel.vue'

  const skillOn = ref(false)

  onMounted(() => {
    const urlParam = window.location.search

    if (urlParam === '?skill') skillOn.value = true

  })


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

</script>

<template>
  <div class="stack-area">
    <div class="stack-container" v-for="(lang, idx) in langList" :key="idx">
        <div class="logo-container">
          <img class="lang-logo" :src="`/src/assets/logos/${lang.img}`" :alt="`${lang.name} icon`">
        </div>
        <p class="lang-name">{{ lang.name }}</p>
        <SkillLevel v-if="skillOn" :level="lang.level" />
      </div>
  </div>
</template>

<style scoped lang="scss">

  .stack-area {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    height: max-content;
    gap: 40px 10px;
  }
  .stack-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 18%;
    height: 200px;
    gap: 10px;

    .logo-container {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100%;
      .lang-logo {
        width: 50%;
        max-height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
      }
    }
  }

  .lang-name {
    color: white;
  }

</style>