<script setup>
import RockBtn from "./moveButtons/RockBtn.vue";
import PaperBtn from "./moveButtons/PaperBtn.vue";
import ScissorsBtn from "./moveButtons/ScissorsBtn.vue";
import { ref, computed } from "vue";
const computerChoice = ref(null);
const userChoice = ref(null);
const computerScore = ref(0);
const userScore = ref(0);
const random = ref(0);
const resultSentence = ref("");
const computerMove = computed(() => {
  switch (random.value) {
    case 1:
      computerChoice.value = "rock";
      break;
    case 2:
      computerChoice.value = "paper";
      break;
    case 3:
      computerChoice.value = "scissors";
      break;
  }
  return computerChoice.value;
});

const playGame = (data) => {
  random.value = Math.floor(Math.random() * 3 + 1);
  userChoice.value = data.value;
  computerChoice.value = computerMove.value;
  console.log(random.value, userChoice.value, computerChoice.value);

  if (userChoice.value === computerChoice.value) {
    resultSentence.value = "It's a tie";
  } else if (
    (userChoice.value === "paper" && computerChoice.value === "rock") ||
    (userChoice.value === "rock" && computerChoice.value === "scissors") ||
    (userChoice.value === "scissors" && computerChoice.value === "paper")
  ) {
    userScore.value++;
    resultSentence.value = `you win ${userChoice.value} beats ${computerChoice.value}`;
  } else {
    computerScore.value++;
    resultSentence.value = `you lose ${computerChoice.value} beats ${userChoice.value}`;
  }
};
const emit = defineEmits(["result"]);
const sendResult = () => {
  emit("result", { userScore, computerScore, resultSentence });
};
</script>

<template>
  <div>
    <h2 class="text-2xl font-semibold mb-2">Choose your move:</h2>
    <div class="flex justify-center gap-4 mb-4">
      <rock-btn @rock-move="playGame" @click="sendResult"></rock-btn>
      <paper-btn @paper-move="playGame" @click="sendResult"></paper-btn>
      <scissors-btn
        @scissors-move="playGame"
        @click="sendResult"
      ></scissors-btn>
    </div>
  </div>
</template>

<style scoped></style>
