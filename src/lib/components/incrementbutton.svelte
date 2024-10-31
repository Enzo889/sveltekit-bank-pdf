<script>
	import Button from './ui/button/button.svelte';

	let inicial = $state(0);
</script>

<div class="my-12 flex w-full flex-col items-center justify-center space-y-4">
	<Button onclick={() => inicial++}>Toca para incrementar</Button>

	<Button>"{inicial}"</Button>

	<Button onclick={() => inicial--}>Toca para decrementar</Button>
</div>
