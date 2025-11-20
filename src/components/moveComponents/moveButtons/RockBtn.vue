<script setup>
import { ref } from "vue";
const name = ref("rock");
const emit = defineEmits(["rockMove"]);
const rockMove = () => {
  emit("rockMove", name);
  console.log("ok");
};
</script>

<template>
  <button
    class="bg-red-500 duration-300 hover:opacity-75 p-4 text-5xl rounded hover:cursor-pointer"
    @click="rockMove"
  >
    &#x270A;
  </button>
</template>

<style scoped></style>
