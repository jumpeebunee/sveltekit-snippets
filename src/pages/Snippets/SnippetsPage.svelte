<script lang="ts">
	import Card from './components/Card.svelte';
</script>

<Card>
	{#snippet telephone()}
		<span>212 555 6342</span>
	{/snippet}

	{#snippet company()}
		<span>
			Pierce &amp; Pierce
			<small>Mergers and Aquistions</small>
		</span>
	{/snippet}

	<span>Patrick BATEMAN</span>
	<span>Vice President</span>

	{#snippet address()}
		<span>358 Exchange Place, New York, N.Y. 10099 fax 212 555 6390 telex 10 4534</span>
	{/snippet}
</Card>
