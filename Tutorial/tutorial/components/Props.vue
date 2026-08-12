<script setup>
import { ref } from 'vue';
import Watchers from './Watchers.vue';

const greeting = ref('Hello from parent')
</script>

<template>
    <Watchers :msg="greeting" />
</template>