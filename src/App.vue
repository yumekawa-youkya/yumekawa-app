<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/select">Select</router-link> |
      <router-link to="/result">Result</router-link>
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
          id: 1,
          question: "カレーとうんちの見分けはつく?",
          answer: [
            {
              text: "はい",
              selected: false,
              rate: 50, // 陽キャ度
            },
            {
              text: "いいえ",
              selected: false,
              rate: 25, // 陽キャ度
            },
            {
              text: "どっちでもない",
              selected: false,
              rate: 10, // 陽キャ度
            },
          ],
        },
        {
          id: 2,
          question: "カレーとうんちの見分けはつく?",
          answer: [
            {
              text: "はい",
              selected: false,
              rate: 50, // 陽キャ度
            },
            {
              text: "いいえ",
              selected: false,
              rate: 25, // 陽キャ度
            },
            {
              text: "どっちでもない",
              selected: false,
              rate: 10, // 陽キャ度
            },
          ],
        },
        {
          id: 3,
          question: "カレーとうんちの見分けはつく?",
          answer: [
            {
              text: "はい",
              selected: false,
              rate: 50, // 陽キャ度
            },
            {
              text: "いいえ",
              selected: false,
              rate: 25, // 陽キャ度
            },
            {
              text: "どっちでもない",
              selected: false,
              rate: 10, // 陽キャ度
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
