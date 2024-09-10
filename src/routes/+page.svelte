<script lang="ts">
	import { base } from '$app/paths';
	import { onMount } from 'svelte';

	onMount(() => {
		const div = document.querySelector('main');
		if (div) {
			setTimeout(() => {
				div.style.opacity = '1';

				let index = 0;
				let words = ['Ultimate', 'Definitive', 'Innovative', 'Complete'];
				setInterval(() => {
					const elements = document.querySelectorAll('.mockup') as unknown as [HTMLImageElement];
					elements[index].style.opacity = '0';
					if (elements[index + 1]) {
						``;
						elements[index + 1].style.opacity = '1';
						index++;
					} else {
						elements[0].style.opacity = '1';
						index = 0;
					}
					const wordChange = document.querySelector('#wordChange');
					if (wordChange) {
						wordChange.innerHTML = words[index];
					}
				}, 5000);
			}, 500);
		}
	});
</script>

<head>
	<title>INTO THE DEEP Scorer presented by 20240 Westwood Slingshot</title>
</head>

<main>
	<div>
		<div>
			<img
				id="homeScreen"
				src="{base}/mockups/HomeScreen.png"
				alt="The home screen view of a scoring app made for FTC."
				srcset=""
				class="mockup"
			/>
			<img
				id="scoreScreen"
				src="{base}/mockups/ScoreScreen.png"
				alt="The innovative scorekeeper view made for FTC teams and fans in mind."
				srcset=""
				class="mockup"
			/>
			<img
				id="detailedScreen"
				src="{base}/mockups/DetailedScreen.png"
				alt="Save games to view detailed scoring information afterwards."
				srcset=""
				class="mockup"
			/>
			<img
				id="eventsScreen"
				src="{base}/mockups/EventsScreen.png"
				alt="Relay and view live scores from any official FTC event from around the world."
				srcset=""
				class="mockup"
			/>
		</div>

		<h1>The <span id="wordChange">Ultimate</span> FTC Scorer</h1>
		<h4>September 13th.</h4>

		<a href="https://apps.apple.com/app/into-the-deep-scorer-for-ftc/id6596798391">
			<img src="{base}/appStore/preorder.svg" alt="Pre-order on the App Store" />
		</a>

		<a href="https://apps.apple.com/app/into-the-deep-scorer-for-ftc/id6596798391">
			<img src="{base}/appStore/preorderMac.svg" alt="Pre-order on the Mac App Store" />
		</a>

		<!-- <h3>Sign up for the beta <a href="https://forms.gle/NeyagwVApSCFtyba8">here</a>.</h3> -->

		<p>
			Contact <a target="_blank" href="mailto:support@ftcscoring.app">support@ftcscoring.app</a>
		</p>
	</div>
</main>

<style lang="scss">
	@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

	:global(body) {
		overflow: hidden;
		margin: 0;
		padding: 0;
		font-family: 'Poppins', system-ui, sans-serif;
		color: #fff;
		background-color: #0f0f0f;
	}

	@media (orientation: portrait) {
		main > div {
			div {
				width: 90vw;
				height: calc(90vw / 1837 * 901);

				img {
					left: 5vw;
					width: 90vw;
				}
			}

			h1 {
				margin: 4vh 0 0 0;
				font-size: 3.5vh;
			}

			h4 {
				margin: 0 0 2vh 0;
				font-size: 2vh;
			}

			a {
				margin: 0 0.2vw;
				img {
					height: 5vh;
				}
			}

			h3 {
				margin: 1vh 0;
				font-size: 2.5vh;
			}
		}
	}

	@media (orientation: landscape) {
		main > div {
			div {
				width: 50vw;
				height: calc(50vw / 1837 * 901);

				img {
					left: 25vw;
					width: 50vw;
				}
			}

			h1 {
				margin: 1.5vw 0 0 0;
				font-size: 2vw;
			}

			h4 {
				margin: 0 0 1vw 0;
				font-size: 1vw;
			}

			a {
				margin: 0 0.2vw;
				img {
					height: 3vw;
				}
			}

			h3 {
				margin: 0.8vw 0;
				font-size: 1.5vw;
			}
		}
	}

	main {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100vh;
		opacity: 0;
		transition: all 0.5s;

		div {
			display: flex-block;
			align-items: center;
			text-align: center;

			div {
				img {
					position: absolute;
					opacity: 0;
					transition: opacity 0.5s;
				}

				#homeScreen {
					opacity: 1;
				}
			}

			h1 {
				padding: 0;
				font-weight: 200;

				span {
					font-weight: 500;
				}
			}

			h4 {
				font-weight: 400;
			}

			h3 {
				font-weight: 200;

				a {
					font-weight: 500;
					color: #7e55cb;
					text-decoration: none;
				}
			}

			p {
				font-size: smaller;
				color: #aaa;
				font-weight: 200;
				a {
					color: #aaa;
				}
			}
		}
	}
</style>
