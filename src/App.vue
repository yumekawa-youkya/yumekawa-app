<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/select">Select</router-link>
      <router-link to="/result">Result</router-link>
      <Question v-on:new="questions = $event" />
    </div>
    <router-view />
  </div>
</template>

<script>
import Question from "src/views/Select.vue"
export default {
  date() {
    return {
      questions: [
        {
          id: 1,
          text: "質問",
          answer1: "1",
          answer2: "2",
          answer3: "3",
          youkyado: 0,
        },
      ],
    }
    components: {
      Question
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
