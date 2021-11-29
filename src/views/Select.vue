<template>
  <div>
    <div v-for="(question, index) in questions" v-bind:key="index">
      <div>{{ question.text }}</div>
      <button v-on:click="send(question.answer1)">
        {{ question.answer1 }}
      </button>
      <button v-on:click="send(question.answer2)">
        {{ question.answer2 }}
      </button>
      <button v-on:click="send(question.answer3)">
        {{ question.answer3 }}
      </button>
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
      answerQuestion: "",
    }
  },
  methods: {
    // App.vueを変更する、解答を保存する関数
    send: function (answer) {
      this.$emit("new", this.tempQuestions)
      this.answerQuestion = answer
    },
  },
}
</script>
