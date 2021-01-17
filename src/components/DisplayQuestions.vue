<template>
  <button v-html="question.correct_answer" ></button>

</template>

<script>
export default {
    name: 'display-questions',
    props: ['question',]

}
</script>

<style>

</style>