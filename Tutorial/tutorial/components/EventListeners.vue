<script setup>
import { ref } from 'vue';

const count = ref(0)

function increment() {
    count.value++
}
</script>

<template>
    <!-- make this button work -->
    <button @click="increment">Count is: {{ count }}</button>

    <!-- We can listen to DOM evens using the v-on directive -->
    <button v-on:click="increment">{{ count }}</button>

    <!-- v-on also has a shorthand syntax - @ -->
    <button @click="increment">{{ count }}</button>
</template>