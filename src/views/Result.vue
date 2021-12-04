<template>
  <div>
    <div class="resultTitle">〜結果発表〜</div>
    <div class="resultComment">あなたの陽キャ度は...</div>
    <div class="Youkyado">{{ totalYoukyado }}</div>
    <div class="bunmatsu">です！！！</div>
    <div v-if="this.totalYoukyado <= 20" class="result">
      ほとんど陰キャ！
      <div class="sentence">
        あなたはもう救いようのない陰キャです。あきらめましょう。
      </div>
    </div>
    <div v-else-if="this.totalYoukyado <= 40" class="result">
      ちょっと陽キャ！
      <div class="sentence">
        あなたはまだまだ陽キャとはほど遠い存在です。精進しましょう。
      </div>
    </div>
    <div v-else-if="this.totalYoukyado <= 60" class="result">
      まあまあ陽キャ！
      <div class="sentence">
        あなたは言っても平凡です。何もかもが普通でつまらないでしょう。
      </div>
    </div>
    <div v-else-if="this.totalYoukyado <= 80" class="result">
      かなりの陽キャ！
      <div class="sentence">
        完全なる陽キャにギリギリなれない惜しい人です。中途半端はやめましょう。
      </div>
    </div>
    <div v-else-if="this.totalYoukyado > 80" class="result">
      完全なる陽キャ！
      <div class="sentence">
        人生がさぞ楽しいことでしょう。その楽しさをぜひ皆に分け与えてください。
      </div>
    </div>
    <div class="restart">
      <button v-on:click="youkyadoreset()">
        <router-link to="/select">もう一度診断する</router-link>
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
    return {}
  },
  methods: {
    youkyadoreset: function () {
      for (let i = 0; i < this.questions.length; i++) {
        if (this.questions[i].answer[0].selected === true) {
          this.questions[i].answer[0].selected = false
        }
        if (this.questions[i].answer[1].selected === true) {
          this.questions[i].answer[1].selected = false
        }
        if (this.questions[i].answer[2].selected === true) {
          this.questions[i].answer[2].selected = false
        }
      }
    },
  },
  computed: {
    totalYoukyado: function () {
      let youkyadoCmp = 0
      for (let i = 0; i < this.questions.length; i++) {
        if (this.questions[i].answer[0].selected === true) {
          youkyadoCmp += this.questions[i].answer[0].rate
        }
        if (this.questions[i].answer[1].selected === true) {
          youkyadoCmp += this.questions[i].answer[1].rate
        }
        if (this.questions[i].answer[2].selected === true) {
          youkyadoCmp += this.questions[i].answer[2].rate
        }
      }
      return youkyadoCmp
    },
  },
}
</script>

<style scoped>
.resultTitle {
  background-color: skyblue;
  height: 70px;
  font-family: "Times New Roman";
  padding-top: 30px;
  font-size: 20px;
  font-weight: bold;
}
.resultComment {
  display: flex;
  align-items: left;
  padding: 20px;
  font-family: "Times New Roman";
  font-size: 20px;
  background-color: turquoise;
}
.Youkyado {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
  height: 15rem;
  font-family: "Times New Roman";
  font-size: 200px;
  font-weight: bold;
  text-align: center;
  background-color: turquoise;
}
.bunmatsu {
  padding: 20px;
  text-align: right;
  font-family: "Times New Roman";
  font-size: 20px;
  background-color: turquoise;
}
.result {
  height: 50px;
  color: red;
  text-align: center;
  font-family: "Times New Roman";
  font-size: 5em;
}
.sentence {
  color: black;
  text-align: center;
  font-size: 30px;
}
.restart {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
}
</style>
