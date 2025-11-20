<script setup>
import { ref } from "vue";

const name = ref("paper");
const emit = defineEmits(["paperMove"]);
const paperMove = () => {
  emit("paperMove", name);
};
</script>

<template>
  <button
    class="bg-blue-500 duration-300 hover:opacity-75 p-4 text-5xl rounded hover:cursor-pointer"
    @click="paperMove"
  >
    &#x270B;
  </button>
</template>

<style scoped></style>
