<script setup>
  import { ref } from 'vue'
  import { useCounterStore } from '@/stores/counter'

  const count = useCounterStore();

  const dialog = ref(null);

  function clickMe() {
    dialog.value.showModal();
    count.increment();
  }

  function closeMe() {
    dialog.value.close();
  }
</script>

<template>
  <div class="about">
    <h1>This is an about page</h1>

    <button @click="clickMe">Click me</button>
  </div>

  <dialog ref="dialog">
    <button @click="closeMe">Close Me</button>
    Hello {{ count.count }}
  </dialog>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
