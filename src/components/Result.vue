<template>
  <div class="result-screen">
	  <p>Your reaction time: {{ finalResult }}ms </p>
  </div>
</template>

<script>
export default {
	props: {
		finalResult: Number
	}
}
</script>

<style>
	.result-screen {
		height: 100vh;
		color: white;
		background-color: #171c22;
		text-align: center;
		padding-top: 50vh;
	}
</style>