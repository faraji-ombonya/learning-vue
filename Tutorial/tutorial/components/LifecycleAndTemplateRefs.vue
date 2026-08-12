<script setup>
import { ref, onMounted } from 'vue';

const pElementRef = ref(null)


onMounted(() => {
    // component is now mounted
    pElementRef.value.textContent = "Hey"
})
</script>

<template>
    <p ref="pElementRef">Hello</p>
</template>
