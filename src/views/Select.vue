<template>
  <div>
    <div>{{ questions[0].text }}</div>
    <button v-on:click="send">{{ questions[0].answer1 }}</button>
    <button v-on:click="send">{{ questions[0].answer2 }}</button>
    <button v-on:click="send">{{ questions[0].answer3 }}</button>
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
