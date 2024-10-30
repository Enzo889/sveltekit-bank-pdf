<script>
	import ShinyText from './ShinyText.svelte';
	import WordsPullUp from './WordsPullUp.svelte';
</script>

<main class="mt-8 flex flex-col items-center justify-center space-y-8">
	<WordsPullUp
		class="text-4xl font-bold tracking-[-0.02em] text-black dark:text-white md:text-7xl md:leading-[5rem]"
		words="Welcome to Piggy Bank Interfaces"
	/>
	<div class="flex space-x-4">
		<ShinyText text="Explore our documentation" />
	</div>
</main>
