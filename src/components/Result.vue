<template>
  <div class="result-screen">
	  <p>Your reaction time:</p>
	  <div class="result-screen__result-box" :style="resultBoxColor">
		  {{ finalResult }}ms
		  <p class="result-screen__result-box__message">{{ resultMessage }}</p>
	  </div>
	  <button class="result-screen__restart-btn" @click="restartGame">Play Again</button>
  </div>
</template>

<script>
export default {
	data() {
		return {
			resultBoxColor: {
				background: null,
				color: null,
			},
			resultMessage: ''
		}
	},

	mounted() {
		if(this.finalResult < 300) {
			this.resultBoxColor.background = '#1efd73'
			this.resultBoxColor.color = 'black'
			this.resultMessage = 'Rapid Reflex'
		}

		else if(this.finalResult < 500) {
			this.resultBoxColor.background = '#4639ff'
			this.resultBoxColor.color = 'white'
			this.resultMessage = 'Good Reaction'
		}

		else {
			this.resultBoxColor.background = '#fd1e56'
			this.resultBoxColor.color = 'white'
			this.resultMessage = 'Slow Poke'
		}
	},

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
	.result-screen__result-box {
		padding: 3rem 2rem;
		margin: 1.5rem auto 0;
		/* background: #fd1e56;
		color: black; */
		width: 300px;
		font-size: 1.5rem;
	}
	.result-screen__result-box__message {
		margin-top: 2rem;
		font-size: .75rem;
	}
	.result-screen__restart-btn {
		border: 1px solid white;
		text-transform: uppercase;
		width: 300px;
		margin: 1.5rem auto 0;
		padding: 1.5rem;
		transition: all .2s ease-out;
	}
	.result-screen__restart-btn:hover {
		border: 1px solid white;
		background-color: white;
		color: black;
	}
</style>