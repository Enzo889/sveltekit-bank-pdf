<script>
	import { mode, toggleMode } from 'mode-watcher';
	import Button from './ui/button/button.svelte';
	import { Sun, Moon, PiggyBank } from 'lucide-svelte';
	import { Root, Content, Provider, Tooltip, Trigger } from './ui/tooltip';
</script>

<nav
	class="relative z-20 mx-auto max-w-xl rounded-3xl border border-neutral-800 bg-neutral-100 p-4 dark:bg-neutral-950"
>
	<div class="sticky top-0 flex items-center justify-between">
		<Provider>
			<Root>
				<Tooltip>
					<Trigger>
						<Button href="/" variant="ghost"><PiggyBank /></Button>
					</Trigger>
					<Content>
						<p>Piggy Bank</p>
					</Content>
				</Tooltip>
				<div class="flex space-x-4">
					<a href="#Charts">Charts</a>
					<a href="#Tables">Tables</a>
					<a href="#Forms">Forms</a>
				</div>
				<Tooltip>
					<Trigger>
						<Button
							variant="ghost"
							onclick={() => {
								toggleMode();
							}}
							>{#if $mode === 'dark'}
								<Sun />
							{:else}
								<Moon />
							{/if}</Button
						>
					</Trigger>
					<Content>
						<p>Toggle Mode</p>
					</Content>
				</Tooltip>
			</Root>
		</Provider>
	</div>
</nav>

<style>
	a {
		display: flex;
		color: light-dark(#000, #fff);
		font-weight: 500;
		font-size: 14px;
		margin: 0 0.5rem;
		@media (min-width: 768px) {
			margin: 0 0.75rem;
			font-size: 15px;
		}
		height: 3rem;
		line-height: 3rem;
		border-bottom: 0;
		mix-blend-mode: exclusion;
		transition: 0.15s ease;

		&:hover {
			color: light-dark(#000, #fff);
			text-decoration: none;
			text-shadow:
				0px 0px 32px rgba(0, 0, 0, 0.85),
				0px 0px 32px rgba(255, 255, 255, 0.85);
			opacity: 1;
		}

		&:after {
			content: '';
		}
	}
</style>
