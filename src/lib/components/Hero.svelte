<script>
	import { mode, toggleMode } from 'mode-watcher';
	import Button from './ui/button/button.svelte';
	import { Sun, Moon, PiggyBank } from 'lucide-svelte';
</script>

<nav>
	<Button href="/"><PiggyBank /></Button>
	<Button
		onclick={() => {
			toggleMode();
		}}
		>{#if $mode === 'dark'}
			<Sun />
		{:else}
			<Moon />
		{/if}</Button
	>
</nav>
