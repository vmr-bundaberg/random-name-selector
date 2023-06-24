<template>
    <button :class="`button button-${color}`" :disabled="disabled">
        <slot></slot>
    </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    props: {
        color: {
            type: String,
            default: 'blue'
        },
        disabled: {
            type: Boolean,
            default: false
        }
    },
    setup() {

    },
})
</script>

<style scoped>
.button {
    @apply px-4 py-2 font-semibold rounded bg-indigo-500 hover:bg-indigo-600 text-white;
    &-indigo {
        @apply bg-indigo-500 hover:bg-indigo-600;
    }
    &-green {
        @apply bg-green-500 hover:bg-green-600;
    }
    &-blue {
        @apply bg-blue-500 hover:bg-blue-600;
    }
    &:disabled {
        @apply bg-red-400 bg-opacity-30 cursor-not-allowed;
    }
}
</style>
