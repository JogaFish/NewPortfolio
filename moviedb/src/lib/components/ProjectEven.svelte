<script>
	// import all transition tools
	import { text, transition_in } from 'svelte/internal';
	import { fade, slide, scale } from 'svelte/transition';
	import { inview } from 'svelte-inview';

	// variables for transitions and popup
	let isInView;
	export let display = false;

	// variables
	export let title = '';
	export let paragraph = '';
	export let src = '';
	export let alt = '';
</script>

<body>
	<!-- Main div, containing code that allows for the transition onto the screen -->
	<div
		class="website-row row-even"
		use:inview={{ unobserveOnEnter: true, rootMargin: '-40%' }}
		on:change={({ detail }) => {
			isInView = detail.inView;
		}}
	>
		<!-- if statement is to make the following section visible if the above is valid -->
		{#if isInView}
			<div in:fade class="row-image even-image">
				<!-- this button activates the popup and contains the main image -->
				<button class="flipper" on:click={() => (display = !display)}>
					<img class="proj-img" {src} {alt} />
				</button>
			</div>

			<!-- contains the main paragraph -->
			<div in:fade class="row-text even-text">
				<p>{paragraph}</p>
			</div>

			<!-- contains the title of the image -->
			<div in:fade class="row-header even-header">
				<p class="test1">{title}</p>
			</div>
		{/if}
	</div>
</body>

<style>
	/* used to format the grids used to create each row */
	.website-row {
		display: grid;
		height: 30vw;
		grid-template-rows: 0.5fr auto 0.5fr;
	}

	/* odd rows have left images and right text, even rows are the other way */
	.row-even {
		grid-template-columns: 1fr 1fr 1fr 1fr 50px 1fr 1fr 1fr 1fr 1fr;
		grid-template-areas:
			'header header header header header header header header header header'
			'tex tex tex tex overlap image image image image image'
			'footer footer footer footer footer footer footer footer footer footer';
	}

	/* assigns grid areas to each content type for odd/even rows */
	.even-image {
		grid-area: header-start / overlap-start / footer-end / image-end;
	}
	.even-text {
		grid-area: image-start / tex-start / image-end / overlap-end;
		text-align: left;
	}
	.even-header {
		grid-area: header-start / tex-start / header-end / tex-end;
		text-align: left;
	}

	/* formats the image in the row */
	.row-image {
		border-radius: 7.5px;
		padding: 0;
	}

	/* animation for the image on hover */
	.flipper:hover {
		transform: scale(1.005);
		z-index: 1;
	}
	.flipper img:hover {
		box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.2);
	}

	/* formats the box in which the paragraph sits and the paragraph text */
	.row-text {
		background-color: #1f2c5b;
		border-radius: 7.5px;
		box-shadow: 10px 10px 5px rgba(0, 0, 0, 0.2);
		z-index: 2;
		font-family: 'Inter', sans-serif;
		color: white;
		font-size: 16px;
	}

	/* formats the title text */
	.row-header {
		font-family: 'Inter', sans-serif;
		font-weight: 700;
		font-size: 20px;
		color: white;
		position: relative;
	}

	/* fits the image within the container */
	.proj-img {
		min-width: 100%;
		object-fit: cover;
		object-position: 50% 0%;
		height: 100%;
		border-radius: 7.5px;
	}

	/* fits the text within its containers */
	.row-text p {
		margin-left: 20px;
		margin-right: 20px;
		margin-top: 30px;
		margin-bottom: 30px;
		opacity: 0.75;
	}
	.row-header p {
		position: absolute;
		bottom: 0;
		opacity: 0.95;
	}
	.even-header p {
		left: 20px;
	}

	/* formats the button which activates the popup */
	.flipper {
		color: inherit;
		border: none;
		padding: 0;
		cursor: pointer;
		outline: inherit;
		background: none;
		margin: 0;
		height: 30vw;
		width: 100%;
	}
</style>
