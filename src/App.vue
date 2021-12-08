<template>
  <div id="app">
    <div id="nav">
      <router-link to="/index">Home</router-link> |
      <router-link to="/select/0">Select</router-link> |
      <router-link to="/result">Result</router-link> |
      <router-link to="/ranking">Ranking</router-link>
    </div>
    <router-view v-on:new="questions = $event" v-bind:questions="questions" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      questions: [
        {
          id: 0,
          question: "集合写真の立ち位置はどうする？",
          answer: [
            {
              text: "中央と両隅以外",
              selected: false,
              rate: 0, // 陽キャ度
            },
            {
              text: "両隅らへん",
              selected: false,
              rate: 15, // 陽キャ度
            },
            {
              text: "後列の中央",
              selected: false,
              rate: 30, // 陽キャ度
            },
          ],
        },
        {
          id: 1,
          question: "ものを選ぶときに何を基準にする？",
          answer: [
            {
              text: "デザイン",
              selected: false,
              rate: 30, // 陽キャ度
            },
            {
              text: "機能性",
              selected: false,
              rate: 0, // 陽キャ度
            },
            {
              text: "レビュー",
              selected: false,
              rate: 15, // 陽キャ度
            },
          ],
        },
        {
          id: 2,
          question: "好きな食べ物は？",
          answer: [
            {
              text: "ラーメン",
              selected: false,
              rate: 0, // 陽キャ度
            },
            {
              text: "焼肉",
              selected: false,
              rate: 30, // 陽キャ度
            },
            {
              text: "寿司",
              selected: false,
              rate: 15, // 陽キャ度
            },
          ],
        },
        {
          id: 3,
          question: "あなたがもらうとうれしい花束は？",
          answer: [
            {
              text: "バラ",
              selected: false,
              rate: 30, // 陽キャ度
            },
            {
              text: "チューリップ",
              selected: false,
              rate: 0, // 陽キャ度
            },
            {
              text: "ガーベラ",
              selected: false,
              rate: 15, // 陽キャ度
            },
          ],
        },
      ],
    }
  },
  methods: {},
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
