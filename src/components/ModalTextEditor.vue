<template>
    <Button @click="toggle">
        Edit names
    </Button>
    <teleport to="body">
        <div :class="`modal ${isOpen && 'modal-open'}`">
            <div class="m-auto w-3/4 min-h-1/4 flex flex-col items-center p-4 bg-white">
               <label class="text-left self-start my-2">Insert names here (seperate by newline)</label>
               <textarea :rows="10" v-model="rawNames" class="border p-2 w-full" />
               <Button @click="closeAndSave" color="green" class="mt-4">Save</Button>
            </div>
        </div>
    </teleport>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import Button from './Button.vue'

export default defineComponent({
    props: {
        modelValue: {
            type: String,
            required: true
        }
    },
    components: {
        Button,
    },
    setup(props, {emit}) {
        const isOpen = ref(false)
        const rawNames = ref(props.modelValue)
        const saveNames = () => {
            emit('update:modelValue', rawNames.value)
        }
        const toggle = () => {
            isOpen.value = !isOpen.value
        }
        const closeAndSave = () => {
            toggle()
            saveNames()
        }
        return {
            isOpen,
            toggle,
            rawNames,
            saveNames,
            closeAndSave,
        }
    },
})
</script>

<style scoped>
.modal {
    @apply absolute top-0 left-0 w-full h-full bg-gray-800 bg-opacity-40 hidden;
    &-open {
        @apply flex;
    }
}
</style>
