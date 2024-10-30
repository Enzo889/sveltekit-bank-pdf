<script lang="ts">
	import { ModeWatcher } from 'mode-watcher';
	import '../app.css';
	import { Toaster } from '$lib/components/ui/sonner';
	let { children } = $props();
</script>

<main class="relative mx-auto min-h-screen w-full max-w-3xl border-x border-neutral-800">
	<Toaster />
	<ModeWatcher />
	{@render children()}
</main>
