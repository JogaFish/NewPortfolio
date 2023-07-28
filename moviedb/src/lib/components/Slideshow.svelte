<script>
	export let photoArray = [];
	let index = 0;

	const next = () => {
		index = (index + 1) % photoArray.length;
	};

	const prev = () => {
		if (index == 0) {
			index = photoArray.length - 1;
		} else {
			index = (index - 1) % photoArray.length;
		}
	};
</script>

<div id="slideshow-container">
	{#each [photoArray[index]] as src (index)}
		<img {src} alt="" />
	{/each}

	<button id="prev" on:click={prev}>&lt;</button>
	<button id="next" on:click={next}>&gt;</button>
</div>

<style>
	#slideshow-container {
		width: 100%;
		height: 100%;
		position: relative;
		margin: auto;
		border-radius: 6.5px;
	}

	button {
		position: absolute;
		top: 50%;
		font-family: 'Inter', sans-serif;
		font-weight: 700;
		font-size: 30px;
		color: white;
		background-color: rgba(0, 0, 0, 0);
		cursor: pointer;
		text-decoration: none;
		box-shadow: 0px 0px 0px transparent;
		border: 0px solid transparent;
		padding: 15px;
		align-items: center;
		justify-content: center;
		transition: 0.6s ease;
	}
	button:hover {
		background-color: rgba(0, 0, 0, 0.8);
	}

	#prev {
		left: 0;
		border-radius: 0px 6.5px 6.5px 0px;
	}
	#next {
		right: 0;
		border-radius: 6.5px 0px 0px 6.5px;
	}

	img {
		width: 100%;
		object-fit: cover;
		height: 100%;
		overflow: hidden;
		display: flex;
		align-items: center;
		justify-content: center;
		border-radius: 6.5px;
	}
</style>
