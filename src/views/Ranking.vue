<template>
  <div class="app">
    <div>〜陽キャ度ランキング〜</div>
    <div>
      <p v-for="ranking in rankings" :key="ranking.id">
        {{ ranking.name }}>>>{{ ranking.youkyado }}
      </p>
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
  methods: {},
  created() {
    firebase
      .firestore()
      .collection("ranking")
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
}
</script>

<style scoped></style>
