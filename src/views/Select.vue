<template>
  <div>
    <div v-for="(question, index) in questions" v-bind:key="index">
      <transition name="fade" mode="out-in">
        <div v-if="question.id == $route.params.id">
          <div class="question">
            <span class="questionBox"
              >Question{{ Number($route.params.id) + 1 }}</span
            >
            <div class="Text">{{ question.question }}</div>
          </div>
          <div class="btns">
            <button class="btn1" v-on:click="Answer(index, 0)">
              {{ question.answer[0].text }}
            </button>
            <button class="btn2" v-on:click="Answer(index, 1)">
              {{ question.answer[1].text }}
            </button>
            <button class="btn3" v-on:click="Answer(index, 2)">
              {{ question.answer[2].text }}
            </button>
          </div>
        </div>
      </transition>
    </div>
    <div class="back"></div>
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
    return {
      tempQuestions: this.questions,
      total: 0,
      show: false,
    }
  },

  methods: {
    send: function () {
      this.$emit("new", this.tempQuestions)
    },

    Answer: function (id, num) {
      this.questions[id].answer[num].selected = true
      this.send()
      if (this.pageId === this.questions.length - 1) {
        this.$router.push("/result")
      } else {
        this.$router.push("/select/" + (this.pageId + 1))
      }
    },
  },
  computed: {
    pageId() {
      return Number(this.$route.params.id)
    },
  },
  // App.vueを変更する、解答を保存する関数
}
</script>

<style scoped>
.fade-enter {
  transform: translate(-100px, 0);
  opacity: 0;
}
.fade-enter-to {
  opacity: 1;
}

.fade-enter-active {
  transition: all 3s 0s ease;
}

.fade-leave {
  transform: translate(0, 0);
  opacity: 1;
}
.fade-leave-to {
  transform: translate(100px, 0);
  opacity: 0;
}
.fade-leave-active {
  transition: all 0.3s 0s ease;
}

.back {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: #ffe9a7;
  opacity: 0.4;
  z-index: -1;
  background-image: repeating-linear-gradient(
      45deg,
      #ffc107 25%,
      transparent 25%,
      transparent 75%,
      #ffc107 75%,
      #ffc107
    ),
    repeating-linear-gradient(
      45deg,
      #ffc107 25%,
      #ffe9a7 25%,
      #ffe9a7 75%,
      #ffc107 75%,
      #ffc107
    );
  background-position: 0 0, 20px 20px;
  background-size: 40px 40px;
}
.question {
  position: relative;
  margin: 2em;
  margin-left: auto;
  margin-right: auto;
  padding-top: 5em;
  border: solid 3px #62c1ce;
  height: 15ch;
  width: 80%;
  background-color: #fff;
}
.question .questionBox {
  position: absolute;
  display: inline-block;
  font-family: "Kaisei Decol", serif;
  top: -40px;
  left: -3px;
  padding: 0 9px;
  height: 40px;
  width: 10ch;
  line-height: 32px;
  font-size: 25px;
  background: #62c1ce;
  color: #ffffff;
  font-weight: bold;
  border-radius: 5px 5px 0 0;
}
.question .Text {
  text-align: center;
  font-family: "DotGothic16", sans-serif;
  margin: 0;
  padding: 0;
  font-size: 40px;
}

.btn1 {
  font-size: 20px;
  margin: 50px;
  padding: 10px;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  -webkit-transition: all 0.3s;
  transition: all 0.3s;
  text-align: center;
  vertical-align: middle;
  text-decoration: none;
  letter-spacing: 0.1em;
  color: #212529;
  border-radius: 0.5rem;
  color: #fff;
  border-top: 4px solid #48ecc4;
  border-right: 4px solid #0a5f4a;
  border-bottom: 4px solid #0f745b;
  border-left: 4px solid #8cf9de;
  border-radius: 0;
  background: #11a37f;
}

.btn1:hover {
  color: #fff;
  border-top: 4px solid #0f745b;
  border-right: 4px solid #8cf9de;
  border-bottom: 4px solid #48ecc4;
  border-left: 4px solid #0a5f4a;
}
.btn2 {
  font-size: 20px;
  margin: 50px;
  padding: 10px;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  -webkit-transition: all 0.3s;
  transition: all 0.3s;
  text-align: center;
  vertical-align: middle;
  text-decoration: none;
  letter-spacing: 0.1em;
  color: #212529;
  border-radius: 0.5rem;
  color: #fff;
  border-top: 4px solid #48ecc4;
  border-right: 4px solid #0a5f4a;
  border-bottom: 4px solid #0f745b;
  border-left: 4px solid #8cf9de;
  border-radius: 0;
  background: #11a37f;
}

.btn2:hover {
  color: #fff;
  border-top: 4px solid #0f745b;
  border-right: 4px solid #8cf9de;
  border-bottom: 4px solid #48ecc4;
  border-left: 4px solid #0a5f4a;
}

.btn3 {
  font-size: 20px;
  margin: 50px;
  padding: 10px;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  -webkit-transition: all 0.3s;
  transition: all 0.3s;
  text-align: center;
  vertical-align: middle;
  text-decoration: none;
  letter-spacing: 0.1em;
  color: #212529;
  border-radius: 0.5rem;
  color: #fff;
  border-top: 4px solid #48ecc4;
  border-right: 4px solid #0a5f4a;
  border-bottom: 4px solid #0f745b;
  border-left: 4px solid #8cf9de;
  border-radius: 0;
  background: #11a37f;
}

.btn3:hover {
  color: #fff;
  border-top: 4px solid #0f745b;
  border-right: 4px solid #8cf9de;
  border-bottom: 4px solid #48ecc4;
  border-left: 4px solid #0a5f4a;
}
</style>
