<script>
	import Charts from '$lib/components/Charts.svelte';
	import FormSection from '$lib/components/FormSection.svelte';
	import Hero from '$lib/components/Hero.svelte';
	import Incrementbutton from '$lib/components/incrementbutton.svelte';
	import Navbar from '$lib/components/Navbar.svelte';
	import TablesSection from '$lib/components/TablesSection.svelte';
</script>

<svelte:head>
	<title>Bank PDF - SvelteKit</title>
	<meta name="description" content="a SvelteKit app with PDF generation" />
</svelte:head>

<main class="h-full w-full">
	<div class="sticky top-0 z-30 pt-6">
		<Navbar />
	</div>
	<Hero />
	<Charts />
	<TablesSection />
	<Incrementbutton />
	<FormSection />
</main>
