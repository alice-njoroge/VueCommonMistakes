<script setup>
import {ref, watch} from "vue";

const numbers = ref([1, 2, 3, 4, 5]);

const randomNum = () => {
  numbers.value = [...numbers.value,  Math.floor(Math.random() * 10)]
}
watch(numbers,
    () => console.log('our team score has changed'),
)
</script>

<template>
  {{ numbers }}
  <button @click="randomNum">Push New</button>

</template>

