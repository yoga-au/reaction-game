<template>
  <div class="result-screen">
	  <p>Your reaction time: {{ finalResult }}ms </p>
	  <button class="result-screen__restart-btn" @click="restartGame">Play Again</button>
  </div>
</template>

<script>
export default {
	props: {
		finalResult: Number
	},

	methods: {
		restartGame() {
			this.$emit('restart')
		}
	}
}
</script>

<style>
	.result-screen {
		height: 100vh;
		color: white;
		background-color: #171c22;
		text-align: center;
		padding-top: 30vh;
	}
	.result-screen__restart-btn {
		border: 1px solid white;
		text-transform: uppercase;
		width: 250px;
		margin: 80px auto 0;
		padding: 24px;
		transition: all .2s ease-out;
	}
	.result-screen__restart-btn:hover {
		border: 1px solid white;
		background-color: white;
		color: black;
	}
</style>