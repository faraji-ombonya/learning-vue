<script setup>
import { ref } from 'vue';

const titleClass = ref('title')
</script>
<template>
    <h1 :class="titleClass">Make me red</h1>

    <!-- use v-bind directive to bind an attribute to a dynamic value -->
    <div v-bind:id="dynamicId"></div>

    <!-- v-bind has a dedicated shorthand syntax -->
    <div :id="dynamicId2"></div>


</template>
<style>
.title {
    color: red;
}
</style>