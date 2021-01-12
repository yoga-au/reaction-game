<template>
  <div class="start-screen" v-if="showStartScreen">
    <h1 class="start-screen__title">Reaction Game</h1>
    <p class="start-screen__sub-title">Test your reaction time</p>
    <button class="start-screen__start-btn" @click="startGame">Start Game</button>
  </div>
  <Game v-if="showGameScreen" :delay="delay" @end="endGame" />
  <Result v-if="showResult" :finalResult="result" @restart="restart" />
</template>

<script>
import Game from './components/Game.vue'
import Result from './components/Result.vue'

export default {
  name: 'App',
  components: {
    Game,
    Result
  },

  data() {
    return {
      showStartScreen: true,
      showGameScreen: false,
      showResult: false,
      delay: null,
      result: null
    }
  },

  methods: {
    startGame() {
      this.showStartScreen = false
      this.showGameScreen = true
      this.delay = Math.floor(2000 + (Math.random() * 3000))
      // console.log(this.delay)
    },

    endGame(reactionTime) {
      this.result = reactionTime
      this.showGameScreen = false
      this.showResult = true
      // console.log('clicked')
    },

    restart() {
      this.delay = Math.floor(2000 + (Math.random() * 3000))
      this.showGameScreen = true
      this.showResult = false
      // console.log(this.delay)
    }
  }
}
</script>

<style>
  #app {
    font-family: 'Press Start 2P', cursive;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    /* padding-top: 50vh; */
  }
  .start-screen {
    height: 100vh;
    color: white;
    background-color: #171c22;
    text-align: center;
    padding-top: 25vh;
  }
  .start-screen__title{
    margin-bottom: 1.5rem;
    line-height: 161.8%;
  }
  .start-screen__sub-title{
    opacity: .4;
    margin-bottom: 5rem;
    line-height: 161.8%;
  }
  .start-screen__start-btn{
    border: 1px solid white;
    text-transform: uppercase;
    width: 250px;
    margin: 0 auto;
    padding: 1.5rem;
    transition: all .2s ease-out;
  }
  .start-screen__start-btn:hover{
    border: 1px solid white;
    background-color: white;
    color: black;
  }

  @media (min-width: 420px) {
    .start-screen {
      padding-top: 30vh;
    }
  }
</style>
