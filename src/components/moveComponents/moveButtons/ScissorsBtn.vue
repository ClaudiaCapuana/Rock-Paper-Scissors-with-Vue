<script setup>
import { ref } from "vue";
const name = ref("scissors");
const emit = defineEmits(["scissorsMove"]);
const scissorsMove = () => {
  emit("scissorsMove", name);
  console.log("ok");
};
</script>

<template>
  <button
    class="bg-green-500 duration-300 hover:opacity-75 p-4 text-5xl rounded hover:cursor-pointer"
    @click="scissorsMove"
  >
    &#x270C;
  </button>
</template>

<style scoped></style>
