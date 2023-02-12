<template>
  <div class="counter">
    <a target="_blank" href="https://astro.build/">to-astro</a>
    <div class="counter-message">
      <slot />
    </div>
  </div>
</template>

<script lang="ts">
import { ref } from 'vue';
export default {
  setup() {
    const count = ref(0);
    const add = () => (count.value = count.value + 1);
    const subtract = () => (count.value = count.value - 1);

    return {
      count,
      add,
      subtract,
    };
  },
};
</script>

<style>
.counter {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  height: 100vh;
}

.counter-message {
  text-align: center;
}
a {
  text-decoration: none;
  color: #000;
  font-weight: bolder;
}
</style>
