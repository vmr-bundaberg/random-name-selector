<template>
  <div class="p-4 flex flex-col h-3/4 justify-evenly items-center m-auto">
      <div class="py-4">
        <h1 class="text-5xl mb-4 font-bold">Random Name Selector</h1>
        <button class="px-4 py-2 font-semibold rounded bg-indigo-500 hover:bg-indigo-600 text-white">
          Edit names
        </button>
      </div>
      <h2 class="text-4xl font-bold">Christopher Meow</h2>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'App',
})
</script>

<style>
html, body {
  height: 100%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
  display: flex;
}
</style>