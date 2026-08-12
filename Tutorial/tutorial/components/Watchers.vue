<script setup>
import { ref, watch } from 'vue';

const props = defineProps({
    msg: String
})

const emit = defineEmits(['response'])

const todoId = ref(1)
const todoData = ref(null)

async function fetchData() {
    todoData.value = null
    const res = await fetch(
        `https://jsonplaceholder.typicode.com/todos/${todoId.value}`

    )
    todoData.value = await res.json()
}

fetchData()

watch(todoId, fetchData)

emit('response', 'hello from child')
</script>


<template>
    <p>Todo id: {{ todoId }}</p>

    <p>Message: {{ msg }}</p>

    <button @click="todoId++" :disabled="!todoData">Fetch next todo</button>

    <p v-if="!todoData">Loading...</p>
    <pre e-else> {{ todoData }}</pre>
</template>