<template>
  <div>
    <div class="resultTitle">〜結果発表〜</div>
    <div class="resultComment">あなたの陽キャ度は...</div>
    <div class="Youkyado">{{ totalYoukyado }}</div>
    <div class="bunmatsu">です！！！</div>
    <div v-if="this.totalYoukyado <= 2" class="result">ほとんど陰キャ！</div>
    <div v-else-if="this.totalYoukyado <= 4" class="result">
      ちょっと陽キャ！
    </div>
    <div v-else-if="this.totalYoukyado <= 6" class="result">
      まあまあ陽キャ！
    </div>
    <div v-else-if="this.totalYoukyado <= 8" class="result">
      かなりの陽キャ！
    </div>
    <div v-else-if="this.totalYoukyado <= 10" class="result">
      完全なる陽キャ！
    </div>
    <div class="rankingComment">名前を入力してランキングに追加しよう！</div>
    <input type="text" class="inputText" v-model="inputName" /><input
      type="button"
      value="追加"
      class="addButton"
      v-on:click="rankingButton"
    />
  </div>
</template>

<script>
import firebase from "firebase"
export default {
  props: {
    questions: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      inputName: "",
    }
  },
  methods: {
    rankingButton: function () {
      const timeStamp = firebase.firestore.Timestamp.now()
      const data = {
        name: this.inputName,
        youkyado: this.totalYoukyado,
        timestamp: timeStamp.toDate(),
      }
      firebase.firestore().collection("ranking").doc("doc1").set(data)
    },
  },
  computed: {
    totalYoukyado: function () {
      let youkyadoCmp = 0
      for (let i = 0; i < this.questions.length; i++) {
        youkyadoCmp += this.questions[i].youkyado
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
  padding: 20px;
  text-align: left;
  font-family: "Times New Roman";
  font-size: 20px;
  background-color: lightblue;
}
.Youkyado {
  padding-bottom: 40px;
  height: 15rem;
  font-family: "Times New Roman";
  font-size: 17rem;
  font-weight: bold;
  background-color: lightblue;
}
.bunmatsu {
  padding: 20px;
  text-align: right;
  font-family: "Times New Roman";
  font-size: 20px;
  background-color: lightblue;
}
.result {
  height: 70px;
  padding-top: 30px;
  font-size: 20px;
  color: white;
  background-color: steelblue;
  text-align: center;
  font-family: "Times New Roman";
}
</style>
