<template>
  <div class="p-4 flex flex-col h-3/4 justify-evenly items-center m-auto">
      <div class="py-4">
        <h1 class="text-5xl mb-4 font-bold">Random Name Selector</h1>
        <modal-text-editor v-model="names" />
      </div>
      <div class="py-4">
        <h2 class="text-4xl font-bold mb-4">Christopher Meow</h2>
        <Button>
          Random name
        </Button>
      </div>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from 'vue'
import ModalTextEditor from './components/ModalTextEditor.vue'
import Button from './components/Button.vue'

export default defineComponent({
  name: 'App',
  components: {
    ModalTextEditor,
    Button,
  },
  setup() {
    const names = ref("")
    const nameList = computed(() => names.value.split('\n'))
    return {
      names,
      nameList
    }
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

function ref(arg0: string) {
  throw new Error('Function not implemented.')
}
</style>