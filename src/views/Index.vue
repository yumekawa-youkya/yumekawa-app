<template>
  <div class="general">
    <div class="test">卍陽キャ度診断テスト卍</div>
    <div class="main">
      <router-link to="/select/0" class="title">診断スタート</router-link>
    </div>
    <div class="goRanking">
      <router-link to="/ranking" class="rankingTitle">ランキング</router-link>
    </div>
    <div class="images">
      <img class="image1" src="../assets/seijin.png" />
      <img class="image2" src="../assets/mild.png" />
      <img class="image3" src="../assets/sheesha.png" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {},
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=DotGothic16&family=Kaisei+Decol&family=New+Tegomin&display=swap");
@import url("https://fonts.googleapis.com/css2?family=DotGothic16&family=New+Tegomin&display=swap");
@import url("https://fonts.googleapis.com/css2?family=DotGothic16&family=Kaisei+Decol&family=New+Tegomin&family=Rampart+One&display=swap");
@import url("https://fonts.googleapis.com/css2?family=DotGothic16&family=Kaisei+Decol&family=New+Tegomin&family=Rampart+One&family=Yuji+Mai&display=swap");
@import url("https://fonts.googleapis.com/css2?family=DotGothic16&family=Kaisei+Decol&family=New+Tegomin&display=swap");
@import url("https://fonts.googleapis.com/css2?family=DotGothic16&family=New+Tegomin&display=swap");

.test {
  font-size: 80px;
  font-family: "Kaisei Decol", serif;
  /* margin-top: 10px; */
  margin-bottom: 50px;
  padding-top: 30px;
  color: rgb(152, 8, 219);
}

.title {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 67px;
  font-family: "DotGothic16", sans-serif;
  color: rgb(241, 241, 241);
  background-color: #000000;
  border-radius: 50vh;
  height: 10vh;
  width: 30rem;
  transition: 0.3s;
}
.title:hover {
  background-color: rgb(255, 31, 31);
  color: rgb(255, 255, 255);
}
.main {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 60px;
}

.goRanking {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 60px;
}
.rankingTitle {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 67px;
  font-family: "DotGothic16", sans-serif;
  color: rgb(241, 241, 241);
  background-color: #000000;
  border-radius: 50vh;
  height: 10vh;
  width: 30rem;
  transition: 0.3s;
}
.rankingTitle:hover {
  background-color: rgb(255, 31, 31);
  color: rgb(255, 255, 255);
}
.general {
  background-image: url("../assets/club.png");
  height: 100vh;
  width: auto;
  background-repeat: no-repeat;
  background-position: center;
}
.images {
  display: flex;
  flex-direction: column;
}
.image1 {
  height: 20rem;
  width: 25rem;
  position: absolute;
  padding: 20px;
  left: 350px;
  top: 530px;
  transform: rotateZ(-10deg);
}
.image2 {
  height: 30rem;
  width: 15rem;
  position: absolute;
  padding: 20px;
  left: 1200px;
  top: 200px;
  transform: rotateZ(5deg);
}
.image3 {
  height: 20rem;
  width: 15rem;
  position: absolute;
  padding: 20px;
  left: 880px;
  top: 600px;
  transform: rotateZ(3deg);
}
</style>
