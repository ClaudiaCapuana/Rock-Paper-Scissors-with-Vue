<script setup>
import { reactive } from "vue";
import Title from "./components/Title.vue";
import MoveComponent from "./components/moveComponents/MoveComponent.vue";
import ResultComponent from "./components/ResultComponent.vue";
const resultData = reactive({});

const storeData = (data) => {
  Object.assign(resultData, data);
};
</script>

<template>
  <section class="container mx-auto text-center mt-40">
    <Title></Title>
    <move-component @result="storeData"></move-component>
    <result-component :data="resultData"></result-component>
  </section>
</template>

<style scoped></style>
