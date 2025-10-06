<script lang="ts">
	import Footer from '$lib/footer.svelte';
	import Header from '$lib/header.svelte';
	import '../app.css';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href="/assets/LOGO_fgarden_transparente.ico" />

	<!-- Primary Meta Tags -->
	<title>f.gardn - Garden Design & Landscaping</title>
	<meta name="title" content="f.gardn - Garden Design & Landscaping" />
	<meta
		name="description"
		content="Professional garden design and landscaping services. Creating beautiful, sustainable outdoor spaces."
	/>
	<meta
		name="keywords"
		content="garden design, landscaping, outdoor spaces, sustainable gardens, f.gardn"
	/>
	<meta name="author" content="f.gardn" />

	<!-- Open Graph / Facebook / WhatsApp -->
	<meta property="og:type" content="website" />
	<meta property="og:url" content="https://fgarden.pt/" />
	<meta property="og:title" content="f.gardn - Garden Design & Landscaping" />
	<meta
		property="og:description"
		content="Professional garden design and landscaping services. Creating beautiful, sustainable outdoor spaces."
	/>
	<meta property="og:image" content="https://fgarden.pt/assets/LOGO_fgarden_transparente.png" />
	<meta property="og:image:alt" content="f.gardn logo" />
	<meta property="og:site_name" content="f.gardn" />
	<meta property="og:locale" content="pt_PT" />

	<!-- Twitter / Instagram -->
	<meta property="twitter:card" content="summary_large_image" />
	<meta property="twitter:url" content="https://fgarden.pt/" />
	<meta property="twitter:title" content="f.gardn - Garden Design & Landscaping" />
	<meta
		property="twitter:description"
		content="Professional garden design and landscaping services. Creating beautiful, sustainable outdoor spaces."
	/>
	<meta
		property="twitter:image"
		content="https://fgarden.pt/assets/LOGO_fgarden_transparente.png"
	/>

	<!-- WhatsApp specific -->
	<meta property="whatsapp:title" content="f.gardn - Garden Design & Landscaping" />
	<meta
		property="whatsapp:description"
		content="Professional garden design and landscaping services. Creating beautiful, sustainable outdoor spaces."
	/>
	<meta
		property="whatsapp:image"
		content="https://fgarden.pt/assets/LOGO_fgarden_transparente.png"
	/>

	<!-- Additional metadata for better sharing -->
	<meta name="theme-color" content="#22c55e" />
	<meta name="msapplication-TileColor" content="#22c55e" />
	<link rel="canonical" href="https://fgarden.pt/" />
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
