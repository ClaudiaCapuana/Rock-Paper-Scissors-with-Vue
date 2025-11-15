<script setup>
import Title from "./components/Title.vue";
import MoveComponent from "./components/moveComponents/MoveComponent.vue";
import ResultComponent from "./components/ResultComponent.vue";
</script>

<template>
  <section class="container mx-auto text-center mt-40">
    <Title></Title>
    <move-component></move-component>
    <result-component></result-component>
  </section>
</template>

<style scoped></style>
