<script setup>
import { ref } from 'vue'
import { reactive } from 'vue';


// Reactive only works on objects including arrays and built
// in types like Map and Set
const counter = reactive({
    count: 0
})

console.log(counter.count)
counter.count++
console.log(counter.count)

// Ref can take any value type
const message = ref("Hello world!")

console.log(message.value)

message.value = 'Changed'

console.log(message.value)

</script>

<template>
    <!-- We dont need to use .value, it is automatically unwrapped -->
    <h1>{{ message }}</h1>

    <!-- We can use any valid JavaScript expressions inside the moustache. -->
    <h1>{{ message.split('').reverse().join('') }}</h1>
    <p>Count is {{ counter.count }} </p>
</template>