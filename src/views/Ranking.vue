<template>
  <div class="app">
    <div class="title">〜陽キャ度ランキング〜</div>
    <div>
      <div class="rank1">
        1位 : {{ rankings[0].name }}>>>{{ rankings[0].youkyado }}
      </div>
      <div class="rank2">
        2位 : {{ rankings[1].name }}>>>{{ rankings[1].youkyado }}
      </div>
      <div class="rank3">
        3位 : {{ rankings[2].name }}>>>{{ rankings[2].youkyado }}
      </div>
      <div class="rank">
        4位 : {{ rankings[3].name }}>>>{{ rankings[3].youkyado }}
      </div>
      <div class="rank">
        5位 : {{ rankings[4].name }}>>>{{ rankings[4].youkyado }}
      </div>
      <div class="rank">
        6位 : {{ rankings[5].name }}>>>{{ rankings[5].youkyado }}
      </div>
      <div class="rank">
        7位 : {{ rankings[6].name }}>>>{{ rankings[6].youkyado }}
      </div>
      <div class="rank">
        8位 : {{ rankings[7].name }}>>>{{ rankings[7].youkyado }}
      </div>
      <div class="rank">
        9位 : {{ rankings[8].name }}>>>{{ rankings[8].youkyado }}
      </div>
      <div class="rank">
        10位 : {{ rankings[9].name }}>>>{{ rankings[9].youkyado }}
      </div>
    </div>
    <div>あなたの得点</div>
    <div class="youkyado">{{ this.totalYoukyado }}</div>
    <div class="home">
      <button class="homeButton" v-on:click="youkyadoreset()">
        <router-link to="/index">ホームに戻る</router-link>
      </button>
    </div>
  </div>
</template>

<script>
import firebase from "firebase"

export default {
  data() {
    return {
      rankings: [],
    }
  },
  props: {
    questions: {
      type: Array,
      required: true,
    },
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
  created() {
    firebase
      .firestore()
      .collection("ranking")
      .orderBy("youkyado", "desc")
      .limit(10)
      .get()
      .then((snapshot) => {
        snapshot.docs.forEach((doc) => {
          this.rankings.push({
            id: doc.id,
            ...doc.data(),
          })
        })
      })
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
.homeButton {
  margin: 40px;
  align-items: center;
  justify-content: center;
  font-size: 25px;
  font-family: "DotGothic16", sans-serif;
  color: gold;
  background-color: rgb(104, 86, 86);
  border-radius: 50vh;
  height: 5rem;
  width: 15rem;
  transition: 0.2s;
}
.homeButton:hover {
  color: rgb(255, 255, 255);
  background-color: rgb(0, 0, 0);
}
.title {
  font-size: 80px;
  font-family: "Kaisei Decol", serif;
}
.rank1 {
  position: relative;
  display: center;
  height: 70px;
  width: 100%;
  font-size: 25px;
  font-weight: bold;
  font-family: "Times New Roman", serif;
  font-weight: bold;
  background-color: gold;
}
.rank2 {
  height: 60px;
  width: 100%;
  font-size: 25px;
  font-weight: bold;
  font-family: "Times New Roman", serif;
  font-weight: bold;
  background-color: silver;
}
.rank3 {
  height: 50px;
  width: 100%;
  font-size: 25px;
  font-weight: bold;
  font-family: "Times New Roman", serif;
  font-weight: bold;
  background-color: #c47222;
.rank {
  margin: 20px;
  height: 40px;
  width: 100%;
  font-size: 25px;
  font-weight: bold;
  font-family: "Kaisei Decol", serif;
  font-weight: bold;
  background-color: #f0d0b6;
}
.youkyado {
  margin: 20px;
  height: 40px;
  width: 100%;
  font-size: 25px;
  font-weight: bold;
  font-family: "Kaisei Decol", serif;
  font-weight: bold;
  background-color: skyblue;
}
</style>
