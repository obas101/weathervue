<template>
	<div id="app">
		<main>
			<div class="body-wrapper">
				<div class="input-container">
					<input type="text" placeholder="Enter Location or City..." />
				</div>
				<div class="large-spacing"></div>
				<div class="main-display">
					<div class="font-styling">
						<span class="city">
							Nigeria
							<br />
						</span>

						<div class="font-styling">
							<span class="date">
								24th May 2020
							</span>
						</div>
					</div>
					<div class="large-spacing"></div>
					<div class="font-styling">
						<span class="temperature">50&#176;C</span>
					</div>
					<div class="large-spacing"></div>
					<div class="condition font-styling "><span>Clear</span></div>
				</div>
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
	font-family: helvetica, sans-serif;
}
#app {
	background-image: url(./assets/back.jpg);
	height: 100vh;
	background-size: cover;
}
.input-container {
	width: 100% !important;
	display: flex;
	justify-content: center;
	align-items: center;
}
input {
	/* position: absolute; */
	/* left: 50%; */
	width: 30rem;
	padding: 1rem;
	background: rgb(255, 255, 255, 0.2);
  border: none;
  color: white;
  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
	outline: none;
	border-radius: 30px;
	font-size: 1.3rem;
	padding-left: 2rem;
	margin-top: 4rem;
}
main {
	/* padding-top: 3rem; */
	padding-left: 8rem;
	padding-right: 8rem;
	background-image: linear-gradient(
		to bottom,
		rgba(0, 0, 0, 0.75),
		rgba(0, 0, 0, 0.75)
	);
	/* background-image: linear-gradient(to bottom, grey 0.75, black 0.25); */
	min-height: 100vh !important;
}
.large-spacing {
	margin-top: 3rem;
	width: 100%;
}
.small-spacing {
	margin-top: 2rem;
	width: 100%;
}
.font-styling {
	color: white;
	text-align: center;
}
.date {
	font-size: 13px;
	letter-spacing: 2.5px;
	color: gray;
}
.city {
	font-size: 3rem;
	font-weight: 400;
	letter-spacing: 3px;
}
.temperature {
	font-size: 6rem;
	font-weight: 700;
	background: rgb(255, 255, 255, 0.2);
	padding: 1.5rem;
	border-radius: 15px;
	box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
.condition {
	font-size: 3rem;
	font-weight: 600;
	text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
</style>
