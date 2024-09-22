<script lang="ts">
	import { page } from '$app/stores';

	const breadcrumbs = $derived($page.url.pathname.split('/').filter(Boolean));
</script>

{#snippet breadcrumb({ href, text }: { href: string; text: string })}
	<li>
		<span>/</span>
		<a {href}>{text}</a>
	</li>
{/snippet}

<ul>
	{@render breadcrumb({ href: '/', text: 'home' })}

	{#each breadcrumbs as bread, i}
		{@const href = breadcrumbs.slice(0, i + 1).join('/')}

		{@render breadcrumb({
			href: `/${href}`,
			text: bread
		})}
	{/each}
</ul>

<style>
	ul {
		display: flex;
		align-items: center;
		gap: 16px;
		list-style: none;
	}

	li {
		color: black;
		font-size: 24px;
	}

	a {
		color: black;
		text-decoration: none;
	}
</style>
