<script>
	import { goto } from '$app/navigation';
</script>

<div class="content">
	<h1>Home</h1>
	<div class="nav">
		<button on:click={() => goto('/snippets')}>Snippets</button>
		<button on:click={() => goto('/countdown')}>Countdown</button>
		<button on:click={() => goto('/breadcrumbs/deeply/nested/url')}>Breadcrumbs</button>
	</div>
</div>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.nav {
		display: flex;
		gap: 16px;
	}

	button {
		background: #fff;
		padding: 8px 16px;
		border: solid 1px black;
		cursor: pointer;
		border-radius: 16px;
	}
</style>
