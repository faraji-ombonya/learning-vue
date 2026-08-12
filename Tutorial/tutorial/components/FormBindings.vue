<script setup>
import { ref } from 'vue';

const text = ref('')

function onInput(e) {
    text.value = e.target.value
}
</script>

<template>

    <!-- We can use v-bind and v-on to create to-way bindings -->
    <input :value="text" @input="onInput" placeholder="Type here" />

    <p>{{ text }}</p>

    <!-- We can use v-model to simplify two-way binding -->
    <input v-model="text" />
</template>