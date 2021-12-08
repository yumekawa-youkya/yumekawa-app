<template>
  <div class="app">
    <div>〜陽キャ度ランキング〜</div>
    <div>
      <!--v-for="(ranking, index) in rankings" :key="ranking.id"-->
      <div class="rank">
        1位 : {{ rankings[0].name }}>>>{{ rankings[0].youkyado }}
      </div>
      <div class="rank">
        2位 : {{ rankings[1].name }}>>>{{ rankings[1].youkyado }}
      </div>
      <div class="rank">
        3位 : {{ rankings[2].name }}>>>{{ rankings[2].youkyado }}
      </div>
      <div class="rank">
        4位 : {{ rankings[3].name }}>>>{{ rankings[3].youkyado }}
      </div>
      <div class="rank">
        5位 : {{ rankings[4].name }}>>>{{ rankings[4].youkyado }}
      </div>
      <div class="rank">
        6位 : {{ rankings[5].name }}>>>{{ rankings[5].youkyado }}
      </div>
      <div class="rank">
        7位 : {{ rankings[6].name }}>>>{{ rankings[6].youkyado }}
      </div>
      <div class="rank">
        8位 : {{ rankings[7].name }}>>>{{ rankings[7].youkyado }}
      </div>
      <div class="rank">
        9位 : {{ rankings[8].name }}>>>{{ rankings[8].youkyado }}
      </div>
      <div class="rank">
        10位 : {{ rankings[9].name }}>>>{{ rankings[9].youkyado }}
      </div>
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
      .orderBy("youkyado", "desc")
      .limit(10)
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

<style scoped>
.rank {
  margin: 20px;
}
</style>
