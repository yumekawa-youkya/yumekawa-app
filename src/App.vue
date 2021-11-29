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
          question1: {
            text: "きめせく",
            id: 1,
            selected: false,
            answer1: "きめせくきもちえええ",
            answer2: "きめせくさいこおおお",
            answer3: "きめせくやべええええ",
            youkyado: 0,
          },
          question2: {
            id: 2,
            text: "きめせく",
            selected: false,
            answer1: "きめせくきもちえええ",
            answer2: "きめせくさいこおおお",
            answer3: "きめせくやべええええ",
            youkyado: 0,
          },
          question3: {
            id: 3,
            text: "きめせく",
            selected: false,
            answer1: "きめせくきもちえええ",
            answer2: "きめせくさいこおおお",
            answer3: "きめせくやべええええ",
            youkyado: 0,
          },
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
