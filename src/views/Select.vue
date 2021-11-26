<template>
  <div>
    <div>{{ question.text }}</div>
    <button v-on:click="send">{{ question.answer1 }}</button>
    <button v-on:click="send">{{ question.answer2 }}</button>
    <button v-on:click="send">{{ question.answer3 }}</button>
  </div>
</template>

<script>
export default {
  props: {
    question: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      question2: [
        {
          id: 2,
          text: "question",
          answer1: "1",
          answer2: "2",
          answer3: "3",
          youkyado: 0,
        },
      ],
    }
  },
  methods: {
    send() {
      this.$emit("new", this.question2)
    },
  },
}
</script>
