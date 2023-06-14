<script setup>
import { ref, onMounted } from 'vue'
import Navbar from './components/Navbar.vue'
import About from './components/About.vue'
import ScrollArea from './components/ScrollArea.vue'

// const about = ref(null)

// onMounted(() => {
//   console.log('about', about.value)
// })


</script>

<template>
  <Navbar ref="navbar"/>
  <About ref="about"/>
  <ScrollArea ref="scrollArea"/>

</template>

<style scoped>

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>

