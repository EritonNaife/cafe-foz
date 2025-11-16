<script>
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';
	import Navigation from '$lib/components/Navigation.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="">
	<Navigation />
	<main class="">
		<slot />
	</main>
	<Footer />
</div>
