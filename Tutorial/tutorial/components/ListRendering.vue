<script setup>
import { computed, ref } from 'vue';

let id = 0

const newTodo = ref('')

const hideCompleted = ref(false)

const todos = ref([
    { id: id++, text: "Learn HTML", done: true },
    { id: id++, text: "Learn JavaScript", done: true },
    { id: id++, text: "Learn Vue", done: false }
])

function addTodo() {
    todos.value.push({ id: id++, text: newTodo.value, done: false })
}

function removeTodo(todo) {
    todos.value = todos.value.filter((element) => element.id != todo.id)
}

const filteredTodos = computed(() => {
    if (hideCompleted.value) {
        return todos.value.filter((todo) => !todo.done)
    }

    return todos.value
})

function toggleHideCompleted() {
    hideCompleted.value = !hideCompleted.value
}

</script>

<template>
    <!--  -->

    <form @submit.prevent="addTodo">
        <input v-model="newTodo" required placeholder="new todo" />
        <button>Add todo</button>
    </form>

    <ul>
        <li v-for="todo in filteredTodos" :key="todo.id">
            <input type="checkbox" v-model="todo.done" />
            {{ todo.text }}

            <button @click="removeTodo(todo)">X</button>
        </li>
    </ul>


    <button @click="toggleHideCompleted">
        <p v-if="hideCompleted">Show all</p>
        <p v-else>Hide completed</p>
    </button>
</template>