<script setup>
import {ref, watch} from "vue";

const numbers = ref({
  ourTeam: 3,
  otherTeam: 4
});

const randomNum = () => {
  numbers.value.ourTeam = Math.floor(Math.random() * 10);
  numbers.value.otherTeam = Math.floor(Math.random() * 10);
}
watch(numbers,
    () => console.log('the object changed', numbers.value),
    {
      deep: true
    } // you have to add this option when watching the whole object
)
</script>

<template>
  {{ numbers }}
  <button @click="randomNum">Push New</button>

</template>

