<script lang="ts">
	import Footer from '$lib/footer.svelte';
	import Header from '$lib/header.svelte';
	import '../app.css';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href="/assets/LOGO_fgarden_transparente.ico" />
</svelte:head>

<div>
	<img
		src="/assets/background.webp"
		alt="Blurred plant leafs background"
		class="absolute inset-0 object-cover w-full h-full -z-10"
	/>
	<main class="min-h-screen flex flex-col items-center justify-center text-white">
		<Header />
		{@render children?.()}
		<Footer />
	</main>
</div>
