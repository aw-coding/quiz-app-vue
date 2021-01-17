<template>
<div>
  <p v-html="question.question"></p>
  <p v-html="question.incorrect_answers"></p>
  <p v-html="answerOptions"></p>
  <button v-for='answer in question.incorrect_answers' :key="answer" >{{answer}}</button>

</div>

  <!-- <button v-for='answer in question.incorrect_answers' :key="answer" >{{answer}}</button> -->



    <!-- <display-questions v-for='(answer, index) in question' :question='question' :key='index'  ></display-questions> -->
 

</template>

<script>

import DisplayQuestions from './DisplayQuestions.vue';


export default {
    name: 'display-answers',
    data () {
    return {
        answerOptions: [],
    }
  },
    computed: {
      mergeQuestions: function () {
          this.answerOptions.push('first')

      }

  },
    props: ['question'],
    components: {
        'display-questions': DisplayQuestions

    },
    mounted: function () {
        // for (answer in this.question.incorrect_answers) {this.answerOptions.push('first')}
        this.answerOptions.push('first')
        this.answerOptions.push(this.question.correct_answer)
        this.answerOptions.push(this.question.incorrect_answers)
    },


}
</script>

<style>

</style>