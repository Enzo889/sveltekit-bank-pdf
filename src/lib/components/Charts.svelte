<script>
	import { players } from '$lib/data/nba';

	import BarChart from './BarChart.svelte';
</script>

<div id="Charts" class="mt-12 flex w-full flex-col items-center justify-center space-y-4">
	<h2 class="text-4xl font-bold">Charts Section</h2>
	<p class="text-pretty text-lg">This is the Charts section on the website</p>

	<div class="app">
		<div class="text">
			<h1>Nba Player with most money in Piggy Bank</h1>
		</div>
		<BarChart players={players.sort((a, b) => a['threePointers'] - b['threePointers'])} />
	</div>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		align-items: center;
		height: 100%;
		width: 100%;
		margin: 0 15px;
	}
</style>
