<template>
  <div>
    <div v-for="(question, index) in questions" v-bind:key="index">
      <div>{{ question.text }}</div>
      <button v-on:click="send">{{ question.answer1 }}</button>
      <button v-on:click="send">{{ question.answer2 }}</button>
      <button v-on:click="send">{{ question.answer3 }}</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    questions: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      tempQuestions: this.questions,
    }
  },
  methods: {
    // ボタンを押した時にquestionsを変更する関数
    answer: function () {},
    // App.vueを変更する関数
    send() {
      this.$emit("new", this.tempQuestions)
    },
  },
}
</script>
