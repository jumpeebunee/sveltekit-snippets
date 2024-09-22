<script lang="ts">
	import Counter from './components/Counter.svelte';
</script>

{#snippet blastoff()}
	<span>🚀</span>
{/snippet}

<Counter>
	{#snippet countdown(n: number)}
		{#if n > 0}
			<span>{n}...</span>
			{@const x = n - 1}
			{@render countdown(x)}
		{:else}
			{@render blastoff()}
		{/if}
	{/snippet}
</Counter>
