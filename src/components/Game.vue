<template>
  <div class="game-screen" :class="{ white: clickNow }" @click="react">
	  {{ message }}
  </div>
</template>

<script>
export default {
	data() {
		return {
			message: 'Click anywhere when the background color change',
			timer: null,
			reactionTime: 0,
			clickNow: false,
		}
	},

	props: {
		delay: Number
	},

	mounted() {
		this.timer = setTimeout(() => {
			this.message = 'Click Now'
			this.clickNow = true
			this.startTimer()
		}, this.delay)
	},

	methods: {
		startTimer() {
			// clearTimeout(this.timer)
			this.timer = setInterval(() => {
				this.reactionTime += 10
			}, 10)
		},

		react() {
			clearInterval(this.timer)
			this.$emit('end', this.reactionTime)
			console.log(this.reactionTime)
		}
	}
}
</script>

<style>
	.game-screen {
		height: 100vh;
		color: white;
		background-color: #171c22;
		text-align: center;
		padding-top: 50vh;
	}
	.game-screen.white {
		background-color: white;
		color: #171c22;
		font-size: 2rem;
	}
</style>