<template>
<div>
  <p v-html="question.question"></p>
  <p v-html="question.correct_answer"></p>

  <p> {{mergeQuestions}}</p>
  <p> These are answer options {{answerOptions}}</p>

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
        // this.answerOptions.push(this.question.correct_answer)
        // this.question.incorrect_answers.push(this.question.correct_answer)
        // this.answerOptions = this.question.incorrect_answers.sort(() => Math.random() -0.5)
        let randomInt = Math.floor(Math.random() * (4 - 0)) + 0;

        this.answerOptions = [...this.question.incorrect_answers]
        this.answerOptions.splice(randomInt, 0, this.question.correct_answer)
        console.log(randomInt)

        // this.answerOptions.push(this.question.incorrect_answers)
        // this.answerOptions.push(this.question.correct_answer)



        // this.answerOptions.push('first')
        // this.answerOptions.push(this.question.correct_answer)
        // this.answerOptions.push(this.question.incorrect_answers)

        // this.answerOptions = this.question.incorrect_answers.map()

      }

  },
    props: ['question'],
    components: {
        'display-questions': DisplayQuestions

    },
    mounted: function () {
    

    },


}
</script>

<style>

</style>