<script setup lang="ts">
import { defineProps } from 'vue';

const props = defineProps({
  level: Number,
});

let skillLevel = props.level || 0;

const colors = {
  1: 'linear-gradient(90deg, rgba(182,50,50,1) 0%, rgba(252,120,103,1) 100%)',
  2: 'linear-gradient(90deg, rgba(182,50,50,1) 0%, rgba(252,120,103,1) 100%)',
  3: 'linear-gradient(90deg, rgba(195,124,34,1) 0%, rgba(255,193,88,1) 100%)',
  4: 'linear-gradient(90deg, rgba(214,191,44,1) 0%, rgba(250,252,103,1) 100%)',
  5: 'linear-gradient(90deg, rgba(9,121,27,1) 0%, rgba(0,255,173,1) 100%)'
};

const styles = {
  width: `calc(20% * ${skillLevel})`,
  background: colors[skillLevel],
};

</script>

<template>
  <div class="lang-level">
    <div class="fill" :style="styles" />
  </div>
</template>

<style lang="scss" scoped>
.lang-level {
  display: flex;
  padding: 0;
  background: #373737;
  border: 2px solid #868686;
  width: 100px;
  border-radius: 15px;
  position: relative;
  height: 15px;

  .fill {
    height: 100%;
    width: 0;
    position: absolute;
    border-radius: 15px;
    transition: all 0.5s ease-in-out;
  }
}
</style>