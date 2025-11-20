<script setup>
const props = defineProps({ data: Object });
</script>

<template>
  <p class="text-xl font-semibold">{{ props.data.resultSentence }}</p>
  <p class="text-2xl font-semibold">
    Your score:
    <span class="text-blue-500">{{ props.data.userScore }}</span> Computer
    score:
    <span class="text-red-500">{{ props.data.computerScore }}</span>
  </p>
</template>

<style scoped></style>
