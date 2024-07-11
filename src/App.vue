<script setup>
import {ref, watchEffect} from "vue";

const numbers = ref([1, 2, 3, 4]);

const randomNum = () => {
  numbers.value.push(Math.floor(Math.random() * 10));
}
watchEffect(() => console.log(`New Numbers Added ${numbers.value}`),)
</script>

<template>
  <button @click="randomNum">Push New</button>

</template>

