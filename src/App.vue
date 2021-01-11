<template>
  <div class="start-screen">
    <h1 class="start-screen__title">Reaction Game</h1>
    <p class="start-screen__sub-title">Test your reaction time</p>
    <button class="start-screen__start-btn">start game</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
    
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
  padding-top: 30vh;
}
.start-screen__title{
  margin-bottom: 24px;
}
.start-screen__sub-title{
  opacity: .4;
  margin-bottom: 80px;
}
.start-screen__start-btn{
  border: 1px solid white;
  text-transform: uppercase;
  width: 250px;
  margin: 0 auto;
  padding: 24px;
  transition: all .2s ease-out;
}
.start-screen__start-btn:hover{
  border: 1px solid white;
  background-color: white;
  color: black;
}
</style>
