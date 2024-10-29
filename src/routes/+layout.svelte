<script lang="ts">
	import { ModeWatcher } from 'mode-watcher';
	import '../app.css';
	import { Toaster } from '$lib/components/ui/sonner';
	import DockMenu from '$lib/components/DockMenu.svelte';
	let { children } = $props();
</script>

<main class="relative mx-auto min-h-screen w-full max-w-3xl">
	<Toaster />
	<ModeWatcher />
	{@render children()}
	<DockMenu class="absolute bottom-4 " />
</main>
