<template>
  <div class="general">
    <div class="test">卍陽キャ度診断テスト卍</div>
    <div class="main">
      <router-link to="/select" class="title">診断スタート</router-link>
    </div>
    <div class="images">
    <img class="image1" src="https://2.bp.blogspot.com/-moNfsHKQYck/V2vYUVZES8I/AAAAAAAA79c/BPXgiQqVYjMI3tQ-81LynIjOv80xs42FgCLcB/s800/seijinshiki_pipeisu_furyou.png">
    <img class="image2" src="https://1.bp.blogspot.com/-WiADgvcPe74/W9RZLB-o0GI/AAAAAAABPm8/lhcQ7Q8UDEQQTSZ7GyqKLpVpxF325PIdQCLcBGAs/s800/mild_yankee_dqn.png">
    <img class="image3" src="https://3.bp.blogspot.com/-AYN4R2QzQRA/WWXXEbefCwI/AAAAAAABFfE/GSis1305dZ8aXy7zSYT4Zj2dnrzcY7HlwCLcBGAs/s800/mizutabako_sheesha.png">
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
  font-size: 70px;
  font-family: 'HGP行書体';
  /* margin-top: 10px; */
  margin-bottom: 50px;
  padding-top: 50px;
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
  margin-top: 20px;
  /* margin-bottom: 20px; */
}
.general {
  background-image: url(https://1.bp.blogspot.com/-jDerrxr3URQ/XpKjRZJ8DUI/AAAAAAABYVs/u6GYcJxP4DoYvoxbpgtTLOasi7DMyY5cwCNcBGAsYHQ/s1600/dance_night_club.png);
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
