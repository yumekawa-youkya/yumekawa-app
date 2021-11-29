<template>
  <div>
    <div>結果発表</div>
    <div>あなたの陽キャ度は...</div>
    <div>{{ totalYoukyado }}です！！！</div>
    <div v-if="this.youkyado <= 2">ほとんど陰キャ！</div>
    <div v-else-if="this.youkyadoCmp <= 4">ちょっと陽キャ！</div>
    <div v-else-if="this.youkyadoCmp <= 6">まあまあ陽キャ！</div>
    <div v-else-if="this.youkyadoCmp <= 8">かなりの陽キャ！</div>
    <div v-else-if="this.youkyadoCmp <= 10">完全なる陽キャ！</div>
  </div>
</template>

<script>
export default {
  props: {
    questions: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {}
  },
  methods: {},
  computed: {
    totalYoukado: function () {
      let youkyadoCmp
      for (let i = 0; i < this.question[i].length; i++) {
        youkyadoCmp += this.question[i].youkyado
      }
      return youkyadoCmp
    },
  },
}
</script>
