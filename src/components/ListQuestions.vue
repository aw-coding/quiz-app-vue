<template>
<ul>
    <display-answers v-for='(question, index) in quizQuestions' :question='question' :key='index' > </display-answers>
</ul>
</template>

<script>
import DisplayAnswers from './DisplayAnswers.vue';

export default {
    name: 'list-questions',
    props: ['quizQuestions'],
    components: {
        'display-answers': DisplayAnswers,
    }

}
</script>

<style>

</style>