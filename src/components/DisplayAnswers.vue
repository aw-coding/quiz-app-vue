<template>
  <p v-html="question.question"></p>
    <!-- <display-questions v-for='(answer, index) in question' :question='question' :key='index'  ></display-questions> -->

</template>

<script>

import DisplayQuestions from './DisplayQuestions.vue';


export default {
    name: 'display-answers',
    props: ['question'],
    components: {
        'display-questions': DisplayQuestions

    }

}
</script>

<style>

</style>