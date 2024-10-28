<script lang="ts">
	import { ModeWatcher } from 'mode-watcher';
	import '../app.css';
	import FlickeringGrid from '$lib/components/FlickeringGrid.svelte';
	let { children } = $props();
</script>

<main class="mx-auto relative min-h-screen w-[600px]">
    <ModeWatcher />
    {@render children()}
    
    <FlickeringGrid
        class="-z-10 absolute inset-0 size-full"
        squareSize={4}
        gridGap={6}
        color="#6B7280"
        maxOpacity={0.5}
        flickerChance={0.1}
        width={600}
        height={1400}
    />
</main>

	
