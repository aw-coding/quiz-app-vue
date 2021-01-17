<template>
<div>
  <p v-html="question.question"></p>

  <p> {{mergeQuestions}}</p>

<select name="things" id="things">
    <display-questions :value='choice' > </display-questions>


    <option value="0" v-html="answerOptions[0]" ></option>
    <option value="1" v-html="answerOptions[1]" ></option>
    <option value="2" v-html="answerOptions[2]" ></option>
    <option value="3" v-html="answerOptions[3]" ></option>

</select>
</div>

</template>

<script>

import DisplayQuestions from './DisplayQuestions.vue';


export default {
    name: 'display-answers',
    data () {
    return {
        answerOptions: [],
        singleAnswerPicked: null
,       answersPicked: [],
        choice: null
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


      },
        addToAnswersPicked: function(item) {
            this.answersPicked.push(item)
        }
    

  },
    props: ['question'],
    methods: {
    },

    components: {
        'display-questions': DisplayQuestions

    },
    mounted: function () {
    

    },


}
</script>

<style>

</style>