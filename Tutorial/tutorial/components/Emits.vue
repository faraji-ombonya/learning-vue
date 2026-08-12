<script setup>
import { ref } from 'vue';
import Watchers from './Watchers.vue';

const childMessage = ref('No child message yet')
</script>

<template>

    <Watchers @response="(msg) => childMessage = msg" />

    <p>{{ childMessage }}</p>
</template>