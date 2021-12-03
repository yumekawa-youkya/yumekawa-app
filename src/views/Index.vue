<template>
  <div class="general">
    <div class="test">卍陽キャ度診断テスト卍</div>
    <div class="main">
      <router-link to="/select" class="title">診断スタート</router-link>
    </div>
    <div class="images">
    <img class="image1" src="../assets/seijin.png">
    <img class="image2" src="../assets/mild.png">
    <img class="image3" src="../assets/sheesha.png">
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
.test {
  font-size: 100px;
  font-family: 'HGP行書体';
  /* margin-top: 10px; */
  margin-bottom: 50px;
  padding-top: 40px;
  color: rgb(152, 8, 219);
}
.image {

}
.title {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 80px;
  font-family: 'HGP行書体';
  color: rgb(241, 241, 241);
  background-color: #000000;
  border-radius: 50vh;
  height: 10vh;
  width: 30rem;
  transition: 0.3s;
}
.title:hover {
  background-color:rgb(243, 243, 243);
  color: black;
}
.main {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 60px;
}
.general {
  background-image: url('../assets/club.png');
  height: 800px;
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
  left: 140px;
  top: 400px;
  transform: rotateZ(-10deg);
}
.image2 {
  height: 30rem;
  width: 15rem;
  position: absolute;
  padding: 20px;
  left: 880px;
  top: 200px;
  transform: rotateZ(5deg);
}
.image3 {
  height: 20rem;
  width: 15rem;
  position: absolute;
  padding: 20px;
  left: 620px;
  top: 500px;
  transform: rotateZ(3deg);
}
</style>
