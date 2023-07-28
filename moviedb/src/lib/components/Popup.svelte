<script>
	// import slideshow module and transition modules
	import { fade } from 'svelte/transition';
	import { onMount } from 'svelte';
	import Slideshow from '$lib/components/Slideshow.svelte';
	import Description from './Description.svelte';

	// variable to be exported
	export let display = false;

	// console log the display
	console.log(display);
	const hidePopup = () => {
		display = false;
	};

	// exported variable for slideshow
	export let photoArray = [];

	// exported variable for description
</script>

<!-- this closes and opens the popup, and the div contains all contents -->
<div class={display ? 'popup-proj' : 'hidePopup'} id="proj1" in:fade out:fade>
	<!-- image slideshow and description of slideshow sections -->
	<div id="slide">
		<Slideshow {photoArray} />
	</div>
	<div id="desc">
		<Description />
	</div>

	<!-- margin section to keep the above sections within their proper areas -->
	<div id="top-margin" />
	<div id="right-margin" />
	<div id="left-margin" />
	<div id="bottom-margin" />

	<!-- full screen section behind popup that when clicked on, closes the popup  -->
	<button class="full-screen" on:click={() => (display = !display)} />
</div>

<style>
	/* this class hides the popup when it is not in use */
	.hidePopup {
		display: none;
	}

	/* the container for the whole project, maintains grid structure */
	.popup-proj {
		z-index: 2;
		position: sticky;
		display: grid;
		grid-template-columns: repeat(9, 1fr);
		grid-template-rows: minmax(0, 0.1fr) minmax(0, 1fr) minmax(0, 0.1fr);
		grid-template-areas:
			'top-margin top-margin top-margin top-margin top-margin top-margin top-margin top-margin top-margin'
			'nun1 slide slide slide slide slide desc desc nun2'
			'bottom-margin bottom-margin bottom-margin bottom-margin bottom-margin bottom-margin bottom-margin bottom-margin bottom-margin';
		grid-column-gap: 5px;
		width: 100vw;
		height: 100vh;

		bottom: 0;
		left: 0;
	}

	/* properties for the slideshow container */
	#slide {
		grid-area: slide;
		z-index: 1;
		border-radius: 7.5px;
		box-shadow: 10px 10px 5px rgba(0, 0, 0, 0.2);
	}

	/* properties for the description container */
	#desc {
		grid-area: desc;
		z-index: 1;
		overflow-y: auto;
		background-color: #1f2c5b;
		border-radius: 7.5px;
		box-shadow: 10px 10px 5px rgba(0, 0, 0, 0.2);
	}

	/* both properties remove the scrollbar for the description */
	::-webkit-scrollbar {
		width: 0;
		background: transparent;
	}

	/* properties and grid names for all the spacer grid areas */
	#top-margin {
		grid-area: top-margin;
		z-index: -1;
	}
	#bottom-margin {
		grid-area: bottom-margin;
		z-index: -1;
	}
	#left-margin {
		grid-area: nun1;
		z-index: -1;
	}
	#right-margin {
		grid-area: nun2;
		z-index: -1;
	}

	/* properties of the button that closes the popup */
	.full-screen {
		position: fixed;
		width: 100%;
		height: 100%;
		top: 0px;
		right: 0px;
		bottom: 0px;
		left: 0px;
		z-index: 0;

		background: none;
		color: inherit;
		border: none;
		padding: 0;
		font: inherit;
		cursor: pointer;
		outline: inherit;
		background-color: black;
		opacity: 0.5;
	}
</style>
