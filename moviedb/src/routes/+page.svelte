<script>
	import Landing from '$lib/components/Landing.svelte';
	import Websites from '$lib/components/Websites.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<head>
	<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Inter" />
	<link
		href="https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@400;700&display=swap"
		rel="stylesheet"
	/>
	<style>
		html {
			scroll-behavior: smooth;
			overflow-x: hidden;
		}
		body {
			background-color: #131c3d;
		}
	</style>
</head>

<body>
	<Landing />
	<Websites />
	<Footer />
</body>
