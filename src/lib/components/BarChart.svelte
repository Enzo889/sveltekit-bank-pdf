<script>
	import * as d3 from 'd3';

	export let players;

	const formatLabel = d3.format(',.0f');

	const margin = {
		top: 30,
		right: 100,
		bottom: 0,
		left: 110
	};

	let width = 400;
	let height = 320;

	$: innerWidth = width - margin.left - margin.right;
	let innerHeight = height - margin.top - margin.bottom;

	$: xScale = d3
		.scaleLinear()
		.domain([0, d3.max(players, (d) => d.threePointers)])
		.range([0, innerWidth]);

	const yScale = d3
		.scaleBand()
		.domain(players.map((d) => d.name))
		.range([innerHeight, 0])
		.padding(0.25);
</script>

<div class="wrapper" bind:clientWidth={width}>
	<svg {width} {height}>
		<g transform={`translate(${margin.left}, ${margin.top})`}>
			{#each players as player}
				<text
					class="text-white"
					text-anchor="end"
					x={-10}
					y={yScale(player.name) + yScale.bandwidth() / 2}
					dy=".35em"
				>
					{player.name}
				</text>
				<rect
					x={0}
					y={yScale(player.name)}
					width={xScale(player.threePointers)}
					height={yScale.bandwidth()}
				/>
				<text
					text-anchor="start"
					x={xScale(player.threePointers)}
					dx="10"
					y={yScale(player.name) + yScale.bandwidth() / 2}
					dy=".35em"
				>
					{formatLabel(player.threePointers)}
				</text>
			{/each}
		</g>
	</svg>
</div>

<style>
	.wrapper {
		position: relative;
		width: 100%;
		max-width: 700px;
	}

	rect {
		fill: #4427ca;
	}

	text {
		font-size: 12px;
	}
	@media (prefers-color-scheme: dark) {
		text {
			fill: #4427ca;
		}
	}
</style>
