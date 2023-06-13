<script setup>
import { ref, onMounted } from 'vue'
import Navbar from './components/Navbar.vue'
import About from './components/About.vue'
import Stack from './components/Stack.vue'

// const about = ref(null)

// onMounted(() => {
//   console.log('about', about.value)
// })


</script>

<template>
  <Navbar ref="navbar"/>
  <About ref="about"/>
  <Stack ref="stack"/>

  <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>

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

