<template>
  <div class="container">
    <form action="/" class="form" @submit.prevent>
      <input
        type="number"
        name="text"
        id="text"
        v-model="inputText"
        required
        placeholder="Enter number only!"
      />
      <button type="submit" class="btn" @click="emitEvent">Send me</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";
const emit = defineEmits(["getFromChild"]);
const inputText = ref("");
const emitEvent = () => {
  const pattern = /\d+/;
  if (inputText.value.toString().match(pattern)) {
    emit("getFromChild", { status: true, data: inputText.value });
  } else {
    // do nothing ))
    //emit("getFromChild", { status: false, data: "" });
  }
};
</script>
