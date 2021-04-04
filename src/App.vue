<template>
  <div class="p-4 flex flex-col h-3/4 justify-evenly items-center m-auto">
      <div class="py-4">
        <h1 class="text-5xl mb-4 font-bold">Random Name Selector</h1>
        <modal-text-editor />
      </div>
      <h2 class="text-4xl font-bold">Christopher Meow</h2>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import ModalTextEditor from './components/ModalTextEditor.vue'

export default defineComponent({
  name: 'App',
  components: {
    ModalTextEditor,
  }
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