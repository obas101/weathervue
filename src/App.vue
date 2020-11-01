<template>
	<div id="app">
		<main>
			<div class="body-wrapper">
				<div class="input-container">
					<input
						v-model="query"
						@keypress="fetchWeather"
						type="text"
						placeholder="Enter Location or City..."
					/>
				</div>
				<div class="large-spacing"></div>
				<div class="main-display" v-if="typeof weather.main != 'undefined'">
					<div class="font-styling">
						<span class="city">
							{{ weather.name }}, {{ weather.sys.country }}
							<br />
						</span>

						<div class="font-styling">
							<span class="date">
								{{ dateBuilder() }}
							</span>
						</div>
					</div>
					<div class="large-spacing"></div>
					<div class="font-styling">
						<span class="temperature"
							>{{ Math.round(weather.main.temp) }}&#176;C</span
						>
					</div>
					<div class="large-spacing"></div>
					<div class="condition font-styling ">
						<span>{{ weather.weather[0].description }}</span>
					</div>
				</div>
			</div>
		</main>
	</div>
</template>

<script>
export default {
	name: "App",
	data() {
		return {
			api_key: "8b8661c3d59f8d9630996046a22b4eea",
			base_url: "http://api.openweathermap.org/data/2.5/",
			query: "",
			weather: {},
		};
	},
	methods: {
		fetchWeather(e) {
			if (e.key == "Enter") {
				fetch(
					`${this.base_url}weather?q=${this.query}&units=metric&APPID=${this.api_key}`
				)
					.then((res) => {
						return res.json();
					})
					.then(this.setResults);
			}
		},
		setResults(results) {
			this.weather = results;
		},
		dateBuilder() {
			let d = new Date();
			let months = [
				"January",
				"February",
				"March",
				"April",
				"May",
				"June",
				"July",
				"August",
				"September",
				"October",
				"November",
				"December",
			];
			let days = [
				"Sunday",
				"Monday",
				"Tuesday",
				"Wednesday",
				"Thursday",
				"Friday",
				"Saturday",
			];

			let day = days[d.getDay()];
			let date = d.getDate();
			let month = months[d.getMonth()];
			let year = d.getFullYear();

			return `${day} ${date}, ${month} ${year}`;
		},
	},
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
	width: 25rem;
	padding: 1rem;
	background: rgb(255, 255, 255, 0.2);
	border: none;
	color: white;
	box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
	outline: none;
	border-radius: 30px;
	font-size: 1.3rem;
	padding-left: 2rem;
	margin-top: 3.5rem;
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
	/* margin-top: 1rem; */
	font-size: 2.5rem;
	font-weight: 400;
	letter-spacing: 3px;
}
.temperature {
	/* margin-top: 1rem; */
	font-size: 5.5rem;
	font-weight: 700;
	background: rgb(255, 255, 255, 0.2);
	padding: 1.5rem;
	border-radius: 15px;
	box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
.condition {
	/* margin-top: 1rem; */
	font-size: 2.5rem;
	font-weight: 600;
	text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
</style>
