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
watch(
    () => numbers.value.ourTeam, //here I don't need the deep option because I am using the getter to fetch a specific key
    (ourScore) => console.log('our team score has changed', ourScore),
)
</script>

<template>
  {{ numbers }}
  <button @click="randomNum">Push New</button>

</template>

