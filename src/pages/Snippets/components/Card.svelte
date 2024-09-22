<script lang="ts">
	import type { Snippet } from 'svelte';

	type Props = {
		telephone: Snippet;
		company: Snippet;
		address: Snippet;
		children: Snippet;
	};

	let { telephone, company, address, children }: Props = $props();
</script>

<div class="card">
	<header>
		{@render telephone()}
		{@render company()}
	</header>

	{#if children}
		{@render children()}
	{:else}
		<p>Name</p>
	{/if}

	<footer>
		{@render address()}
	</footer>
</div>

<style>
	.card {
		width: 24em;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 1.5em 1em 1em 1em;
		line-height: 1.2;
		color: oklch(0% 0 0);
		background-color: oklch(98% 0 0);
		border-radius: 2px;
		aspect-ratio: 3.5 / 2;

		:global(small) {
			display: block;
			font-size: 0.6em;
		}
	}

	header,
	footer {
		width: 100%;
		display: flex;
		flex: 1;
	}

	header {
		justify-content: space-between;
	}

	footer {
		justify-content: center;
		align-items: end;
		font-size: 0.6em;
	}
</style>
