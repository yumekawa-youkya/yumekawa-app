<template>
  <div>
    <div class="test">卍陽キャ度診断テスト卍</div>
    <div class="title">
      <router-link to="/select">診断スタート</router-link>
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
  font-family: "MS Mincho";
  margin-top: 20px;
  margin-bottom: 50px;
}
.title {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 80px;
  color: #fff;
  background-color: #eb6100;
  border-radius: 100vh;
  height: 20vh;
  width: auto;
}
</style>
