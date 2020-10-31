<template>
	<div id="app">
		<main>
			<div class="body-wrapper">
				<div class="input-container">
					<input type="text" placeholder="Enter Location or City..." />
				</div>
				<div class="main-display"></div>
			</div>
		</main>
	</div>
</template>

<script>
export default {
	name: "App",
};
</script>

<style>
* {
	padding: 0;
	margin: 0;
}
#app {
	background-image: url(./assets/back.jpg);
	height: 100vh;
	background-size: cover;
}
.input-container {
	width: 100%;
}
input {
	width: 100%;
	padding: 1rem;
	outline: none;
	border-radius: 30px;
	font-size: 1.3rem;
  padding-left: 2rem;
}
main {
	padding-top: 4rem;
	padding-left: 9rem;
	padding-right: 9rem;
	min-height: 100vh;
}
</style>
