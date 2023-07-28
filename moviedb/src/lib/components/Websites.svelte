<script>
	import { text, transition_in } from 'svelte/internal';
	import { fade, slide, scale } from 'svelte/transition';
	import { inview } from 'svelte-inview';
	import Popup from '$lib/components/Popup.svelte';
	import ProjectOdd from '$lib/components/ProjectOdd.svelte';
	import ProjectEven from '$lib/components/ProjectEven.svelte';

	// for button to make project div appear
	let display1;
	let display2;
	let display3;
	let display4;

	// variables for project text and images
	let title1 = 'TMG Podcast Website';
	let paragraph1 =
		'A minimal, dark blue theme for VS Code, Sublime Text, Atom, iTerm, and more. Available on \
					Visual Studio Marketplace, Package Control, Atom Package Manager, and npm.';
	let src1 = 'Images/TMG.jpg';
	let alt1 = 'TMG';

	let title2 = 'Penna Framing Website';
	let paragraph2 =
		'A web app for visualizing personalized Spotify data. View your top artists, top tracks,\
					recently played tracks, and detailed audio information about each track.';
	let src2 = 'Images/penna.jpg';
	let alt2 = 'Penna';

	let title3 = 'Messi Barcelona Design';
	let paragraph3 =
		"Unlike tutorials that only cover a few concepts and leave you with half-baked GitHub \
					repositories, this course covers everything from explaining the principles of REST APIs to \
					implementing Spotify's OAuth flow and fetching API data in a React app.";
	let src3 = 'Images/messi.jpg';
	let alt3 = 'Messi';

	let title4 = 'Renforth Barber Website';
	let paragraph4 =
		'A minimal, dark blue theme for VS Code, Sublime Text, Atom, iTerm, and more. Available on \
					Visual Studio Marketplace, Package Control, Atom Package Manager, and npm.';
	let src4 = 'Images/barber.png';
	let alt4 = 'Barber';

	// variables for slideshow
	const photoArray1 = ['Images/TMG.jpg', 'Images/penna.jpg', 'Images/messi.jpg'];
	const photoArray2 = ['Images/TMG.jpg', 'Images/barber.png', 'Images/messi.jpg'];
	const photoArray3 = ['Images/TMG.jpg', 'Images/barber.png', 'Images/messi.jpg'];
	const photoArray4 = ['Images/TMG.jpg', 'Images/barber.png', 'Images/messi.jpg'];
</script>

<div class="websites">
	<p class="title" id="project-anchor">projects</p>
	<div class="website-grid-container">
		<ProjectOdd
			bind:display={display1}
			title={title1}
			paragraph={paragraph1}
			src={src1}
			alt={alt1}
		/>
		<ProjectEven
			bind:display={display2}
			title={title2}
			paragraph={paragraph2}
			src={src2}
			alt={alt2}
		/>
		<ProjectOdd
			bind:display={display3}
			title={title3}
			paragraph={paragraph3}
			src={src3}
			alt={alt3}
		/>
		<ProjectEven
			bind:display={display4}
			title={title4}
			paragraph={paragraph4}
			src={src4}
			alt={alt4}
		/>
	</div>
</div>

<Popup bind:display={display1} photoArray={photoArray1} />
<Popup bind:display={display2} photoArray={photoArray2} />
<Popup bind:display={display3} photoArray={photoArray3} />
<Popup bind:display={display4} photoArray={photoArray4} />

<style>
	.websites {
		height: auto;
	}
	.title {
		font-family: 'Roboto Mono', sans-serif;
		font-weight: 700;
		color: white;
		opacity: 0.2;
		font-size: 12.5vw;
		line-height: 0px;
		margin-left: 10vw;
		margin-top: 50px;
	}
	#project-anchor {
		scroll-margin-top: 100px;
	}
	.website-grid-container {
		display: grid;
		grid-template-rows: repeat(4, 1fr);
		grid-gap: 5vw;
		padding-left: 10vw;
		padding-right: 10vw;
	}
</style>
