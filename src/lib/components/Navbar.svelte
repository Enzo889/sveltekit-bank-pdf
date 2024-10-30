<script>
	import { mode, toggleMode } from 'mode-watcher';
	import Button from './ui/button/button.svelte';
	import { Sun, Moon, PiggyBank } from 'lucide-svelte';
	import { Root, Content, Provider, Tooltip, Trigger } from './ui/tooltip';
</script>

<nav
	class="mx-auto flex max-w-xl items-center justify-between rounded-3xl border border-neutral-800 p-4"
>
	<Provider>
		<Root>
			<Tooltip>
				<Trigger>
					<Button href="/" variant="outline"><PiggyBank /></Button>
				</Trigger>
				<Content>
					<p>Piggy Bank</p>
				</Content>
			</Tooltip>
			<div class="flex space-x-4">
				<a href="#Charts">Charts</a>
				<a href="#Tables">Tables</a>
				<a href="#Forms">Forms</a>
				<a href="#Docs">Docs</a>
			</div>
			<Tooltip>
				<Trigger>
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
				</Trigger>
				<Content>
					<p>Toggle Mode</p>
				</Content>
			</Tooltip>
		</Root>
	</Provider>
</nav>

<style>
	a {
		display: flex;
		color: #9797a0;
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
			color: #fff;
			text-decoration: none;
			text-shadow: rgba(255, 255, 255, 0.85) 0px 0px 32px;
			opacity: 1;
		}

		&:after {
			content: '';
		}
	}
</style>
