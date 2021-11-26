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
import Result from "./views/Result.vue"

export default {
  data() {
    return {
      components: { Result },
      questions: [
        {
          id: 1,
          text: "質問1",
          answer1: "1",
          answer2: "2",
          answer3: "3",
          youkyado: 0,
        },
        {
          id: 2,
          text: "質問2",
          answer1: "4",
          answer2: "5",
          answer3: "6",
          youkyado: 0,
        },
        {
          id: 3,
          text: "質問3",
          answer1: "7",
          answer2: "8",
          answer3: "9",
          youkyado: 0,
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
