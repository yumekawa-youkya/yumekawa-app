<template>
  <div>
    <div>{{ this.$route.params.id }}</div>
    <div v-for="(question, index) in questions" v-bind:key="index">
      <div>{{ question.question }}</div>
      <div class="btns">
        <button class="btn1" v-on:click="Answer(index, 0)">
          {{ question.answer[0].text }}
        </button>
        <button class="btn2" v-on:click="Answer(index, 1)">
          {{ question.answer[1].text }}
        </button>
        <button class="btn3" v-on:click="Answer(index, 2)">
          {{ question.answer[2].text }}
        </button>
      </div>
    </div>
    <div class="result">
      <router-link to="/result">診断結果</router-link>
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
      total: 0,
    }
  },

  methods: {
    send: function () {
      this.$emit("new", this.tempQuestions)
    },

    Answer: function (id, num) {
      this.questions[id].answer[num].selected = true
      this.send()
      if (id === this.questions.length - 1) {
        this.$router.push("/result")
      }
    },
    // App.vueを変更する、解答を保存する関数
  },
}
</script>

<style scoped>
.btn1 {
  margin-top: 15px;
  margin-bottom: 30px;
  margin-right: 10px;
  margin-left: 10px;
  color: #fff;
  border-top: 4px solid #48ecc4;
  border-right: 4px solid #0a5f4a;
  border-bottom: 4px solid #0f745b;
  border-left: 4px solid #8cf9de;
  border-radius: 0;
  background: #11a37f;
}
.btn2 {
  margin-top: 15px;
  margin-bottom: 30px;
  margin-right: 10px;
  margin-left: 10px;
  color: #fff;
  border-top: 4px solid #48ecc4;
  border-right: 4px solid #0a5f4a;
  border-bottom: 4px solid #0f745b;
  border-left: 4px solid #8cf9de;
  border-radius: 0;
  background: #11a37f;
}
.btn3 {
  margin-top: 15px;
  margin-bottom: 30px;
  margin-right: 10px;
  margin-left: 10px;
  color: #fff;
  border-top: 4px solid #48ecc4;
  border-right: 4px solid #0a5f4a;
  border-bottom: 4px solid #0f745b;
  border-left: 4px solid #8cf9de;
  border-radius: 0;
  background: #11a37f;
}
</style>
