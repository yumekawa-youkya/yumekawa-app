<template>
  <div id="app">
    <div id="nav">
      <router-link to="/index">Home</router-link> |
      <router-link to="/select/0">Select</router-link> |
      <router-link to="/result">Result</router-link> |
      <router-link to="/ranking">Ranking</router-link>
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
          id: 0,
          question: "集合写真の立ち位置はどうする？",
          answer: [
            {
              text: "中央と両隅以外",
              selected: false,
              rate: 0, // 陽キャ度
            },
            {
              text: "両隅らへん",
              selected: false,
              rate: 15, // 陽キャ度
            },
            {
              text: "後列の中央",
              selected: false,
              rate: 30, // 陽キャ度
            },
          ],
        },
        {
          id: 1,
          question: "ものを選ぶときに何を基準にする？",
          answer: [
            {
              text: "デザイン",
              selected: false,
              rate: 30, // 陽キャ度
            },
            {
              text: "機能性",
              selected: false,
              rate: 0, // 陽キャ度
            },
            {
              text: "レビュー",
              selected: false,
              rate: 15, // 陽キャ度
            },
          ],
        },
        {
          id: 2,
          question: "好きな食べ物は？",
          answer: [
            {
              text: "ラーメン",
              selected: false,
              rate: 0, // 陽キャ度
            },
            {
              text: "焼肉",
              selected: false,
              rate: 30, // 陽キャ度
            },
            {
              text: "寿司",
              selected: false,
              rate: 15, // 陽キャ度
            },
          ],
        },
        {
          id: 3,
          question: "あなたがもらうとうれしい花束は？",
          answer: [
            {
              text: "バラ",
              selected: false,
              rate: 30, // 陽キャ度
            },
            {
              text: "チューリップ",
              selected: false,
              rate: 0, // 陽キャ度
            },
            {
              text: "ガーベラ",
              selected: false,
              rate: 15, // 陽キャ度
            },
          ],
        },
        {
          id: 4,
          question: "ベンチに座って休憩いるのは？",
          answer: [
            {
              text: "50代ぐらいのサラリーマン",
              selected: false,
              rate: 0, // 陽キャ度
            },
            {
              text: "赤ちゃんを抱いたママ",
              selected: false,
              rate: 15, // 陽キャ度
            },
            {
              text: "高校生カップル",
              selected: false,
              rate: 30, // 陽キャ度
            },
          ],
        },
        {
          id: 5,
          question: "ズバリ！おでんの具といえばどれ？",
          answer: [
            {
              text: "卵",
              selected: false,
              rate: 30, // 陽キャ度
            },
            {
              text: "こんにゃく",
              selected: false,
              rate: 0, // 陽キャ度
            },
            {
              text: "大根",
              selected: false,
              rate: 15, // 陽キャ度
            },
          ],
        },
        {
          id: 6,
          question: "秋のシーズンであなたが食べたいものはどれ？",
          answer: [
            {
              text: "サンマ",
              selected: false,
              rate: 15, // 陽キャ度
            },
            {
              text: "栗",
              selected: false,
              rate: 30, // 陽キャ度
            },
            {
              text: "松茸",
              selected: false,
              rate: 0, // 陽キャ度
            },
          ],
        },
        {
          id: 7,
          question: "次のオバケのうち、一番怖いと感じるのはどれ？",
          answer: [
            {
              text: "獣人",
              selected: false,
              rate: 30, // 陽キャ度
            },
            {
              text: "骸骨",
              selected: false,
              rate: 0, // 陽キャ度
            },
            {
              text: "吸血鬼",
              selected: false,
              rate: 15, // 陽キャ度
            },
          ],
        },
        {
          id: 8,
          question: "「純」という漢字で熟語を作るなら？",
          answer: [
            {
              text: "「純粋」",
              selected: false,
              rate: 30, // 陽キャ度
            },
            {
              text: "「純情」",
              selected: false,
              rate: 15, // 陽キャ度
            },
            {
              text: "「純金」",
              selected: false,
              rate: 0, // 陽キャ度
            },
          ],
        },
        {
          id: 9,
          question:
            "あなたは森の中で迷ってしまいました。これからどうしますか？",
          answer: [
            {
              text: "来た道を戻る",
              selected: false,
              rate: 15, // 陽キャ度
            },
            {
              text: "水と食糧の確保",
              selected: false,
              rate: 30, // 陽キャ度
            },
            {
              text: "スマホで位置を把握",
              selected: false,
              rate: 0, // 陽キャ度
            },
          ],
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
  padding: 35px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
/* comment */
</style>
