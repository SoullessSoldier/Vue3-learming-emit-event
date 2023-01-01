<template>
  <h1>Current value is: {{ counter }}</h1>
  <Child @getFromChild="getFromChild" />
</template>

<script setup>
import { ref } from "vue";

import Child from "../components/Child.vue";

let counter = ref(0);

const getFromChild = (data) => {
  counter.value = data.status ? parseInt(data.data) : "";
};
</script>

<style scoped>
h1 {
  text-align: center;
}
</style>
