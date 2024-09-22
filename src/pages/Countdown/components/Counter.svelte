<script lang="ts">
	import type { Snippet } from 'svelte';

	const {
		countdown
	}: {
		countdown: Snippet<[number]>;
	} = $props();
</script>

<div class="counter">
	{@render countdown(5)}
</div>

<style>
	.counter {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 10px;
	}
</style>
