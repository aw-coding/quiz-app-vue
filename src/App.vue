<template>
<div id="app">
<h1> Movie Quiz</h1>
<list-questions :quizQuestions='quizQuestions' > </list-questions>
</div>
  
</template>

<script>

import ListQuestions from './components/ListQuestions.vue';

export default {
  name: 'App',
  data () {
    return {
      quizQuestions: [],
    }
  },
  methods: {
    testMessage: function () {
      console.log(`Correct answer to question1 is ${this.quizQuestions[0].correct_answer}`)
    }
  },
  mounted: function () {
    fetch('https://opentdb.com/api.php?amount=5&category=11&difficulty=medium&type=multiple')
    .then(res => res.json())
    .then(apiFetch => (this.quizQuestions = apiFetch.results))
    console.log('these are the quiz questions', this.quizQuestions)
  },
    components: {
    "list-questions": ListQuestions,

  },

}
</script>

<style lang="css">
h1 {
  display: flex;
  text-align: center;

}

</style>