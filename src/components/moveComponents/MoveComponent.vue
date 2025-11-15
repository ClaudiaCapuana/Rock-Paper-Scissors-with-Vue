<script setup>
import RockBtn from "./moveButtons/RockBtn.vue";
import PaperBtn from "./moveButtons/PaperBtn.vue";
import ScissorsBtn from "./moveButtons/ScissorsBtn.vue";
</script>

<template>
  <div>
    <h2 class="text-2xl font-semibold mb-2">Choose your move:</h2>
    <div id="btnContainer" class="flex justify-center gap-4 mb-4">
      <rock-btn></rock-btn>
      <paper-btn></paper-btn>
      <scissors-btn></scissors-btn>
    </div>
  </div>
</template>

<style scoped></style>
