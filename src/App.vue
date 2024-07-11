<script setup>
import {ref, watch} from "vue";

const numbers = ref([1, 2, 3, 4]);

const randomNum = () => {
  numbers.value = Math.floor(Math.random() * 10);
}
watch(
    ()=> numbers,
    () => console.log(`New Numbers Added ${numbers.value}`), {
      deep: true
    }
)
</script>

<template>
  <button @click="randomNum">Push New</button>

</template>

