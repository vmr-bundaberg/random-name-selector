<template>
  <div class="p-4 flex flex-col h-3/4 justify-evenly items-center m-auto">
      <div class="py-4">
        <h1 class="text-5xl mb-4 font-bold">Random Name Selector</h1>
        <modal-text-editor v-model="names" />
      </div>
      <div class="py-4">
        <h2 class="text-4xl font-bold mb-4">{{ selectedName }}</h2>
        <Button @click="randomName" :disabled="names.length === 0">
          Randomize Name
        </Button>
      </div>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from 'vue'
import ModalTextEditor from './components/ModalTextEditor.vue'
import Button from './components/Button.vue'
// Credit to Laurens Holst (https://stackoverflow.com/questions/2450954/how-to-randomize-shuffle-a-javascript-array)
function shuffleArray(array: string[]) {
    for (let i = array.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [array[i], array[j]] = [array[j], array[i]];
    }
}

export default defineComponent({
  name: 'App',
  components: {
    ModalTextEditor,
    Button,
  },
  setup() {
    const names = ref("")
    const nameList = computed(() => names.value.trim().split('\n'))
    const selectedName = ref("Random it first")
    const randomName = () => {
      const copiedNameList = [...nameList.value]
      shuffleArray(copiedNameList)
      const timeToStop = Math.random() * (3000 - 100) + 1000
      let index =  0
      for (let i = 0; i < timeToStop; i += 100) {
        setTimeout((): void => {
          selectedName.value = copiedNameList[(i / 100) % copiedNameList.length]
        }, i)
      }
    }

    return {
      names,
      nameList,
      selectedName,
      randomName,
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
</style>