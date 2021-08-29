<template>
  <div class="container">
    <h1>score {{ score }}</h1>
    <div v-if="counter <= 3">
      <h1>{{ quiz[counter].question }}</h1>
      <div>
        <h4>Answer</h4>
        <button @click="answer(0)">{{ quiz[counter].answer[0] }}</button>
        <button @click="answer(1)">{{ quiz[counter].answer[1] }}</button>
        <button @click="answer(2)">{{ quiz[counter].answer[2] }}</button>
        <button @click="answer(3)">{{ quiz[counter].answer[3] }}</button>
      </div>
    </div>
    <h1 v-else>GAME OVER</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      counter: 0,
      score: 0,
      quiz: [
        {
          question: "Capital of Russia",
          answer: ["Moscow", "Beirut", "London", "Tallin"],
          correct: 0,
        },
        {
          question: "Worlds biggest city",
          answer: ["Beijing", "Tokyo", "Mexico City", "Cairo"],
          correct: 1,
        },
        {
          question: "First FIFA world cup was hosted by:",
          answer: ["Germany", "Brazil", "Uruguay", "Italy"],
          correct: 2,
        },
        {
          question: "Paper was created in",
          answer: ["Egypt", "Iran", "India", "China"],
          correct: 3,
        },
      ],
    };
  },
  methods: {
    answer(num) {
      if (this.quiz[this.counter].correct === num) {
        this.score++;
      }
      this.counter++;
    },
  },
};
</script>

<style scoped>
.container {
  margin: 0 auto;
  max-width: 1200px;
  background: gray;
}
</style>
