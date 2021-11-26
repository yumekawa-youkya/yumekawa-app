<template>
  <div>
    <div>結果発表</div>
    <div>あなたの陽キャ度は...</div>
    <div>{{ Totalyoukyado }}です！！！</div>
    <div v-if="this.youkyado <= 2">ほとんど陰キャ！</div>
    <div v-else-if="this.youkyado <= 4">ちょっと陽キャ！</div>
    <div v-else-if="this.youkyado <= 6">まあまあ陽キャ！</div>
    <div v-else-if="this.youkyado <= 8">かなりの陽キャ！</div>
    <div v-else-if="this.youkyado <= 6">完全なる陽キャ！</div>
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
    Totalyoukado: function () {
      let youkyado
      for (let i = 0; i < this.question.length; i++) {
        youkyado += this.question.youkyado
      }
      return youkyado
    },
  },
}
</script>
