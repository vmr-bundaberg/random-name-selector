<template>
    <button @click="toggle" class="button">
        Edit names
    </button>
    <teleport to="body">
        <div :class="`modal ${isOpen && 'modal-open'}`">
            <div class="m-auto w-3/4 min-h-1/4 flex flex-col items-center p-4 bg-white">
               <label class="text-left self-start my-2">Insert names here (seperate by newline)</label>
               <textarea rows="10" class="border p-2 w-full" />
               <button @click="toggle" class="button button-green my-4">Save</button>
            </div>
        </div>
    </teleport>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
    setup() {
        const isOpen = ref(false)
        const toggle = () => {
            isOpen.value = !isOpen.value
        }
        return {
            isOpen,
            toggle
        }
    },
})
</script>


<style scoped>
.button {
    @apply px-4 py-2 font-semibold rounded bg-indigo-500 hover:bg-indigo-600 text-white;
    &-green {
        @apply bg-green-500 hover:bg-green-600;
    }
}
.modal {
    @apply absolute top-0 left-0 w-full h-full bg-gray-800 bg-opacity-40 hidden;
    &-open {
        @apply flex;
    }
}
</style>