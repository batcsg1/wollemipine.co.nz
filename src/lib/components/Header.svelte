<script lang="ts">
	const links = [
		{ href: '#the-tree', label: 'The tree' },
		{ href: '#growing', label: 'Growing in NZ' },
		{ href: '#see-one', label: 'See one' },
		{ href: '#nursery', label: 'Find a nursery' },
		{ href: '#about', label: 'About' }
	];

	let open = $state(false);
</script>

<header>
	<div class="container bar">
		<a class="brand" href="/">
			<span class="name">Wollemi Pine NZ</span>
			<span class="tag">Independent guide</span>
		</a>

		<button class="toggle" aria-expanded={open} aria-controls="site-nav" onclick={() => (open = !open)}>
			{open ? 'Close' : 'Menu'}
		</button>

		<nav id="site-nav" class:open>
			{#each links as link (link.href)}
				<a href={link.href} onclick={() => (open = false)}>{link.label}</a>
			{/each}
		</nav>
	</div>
</header>

<style>
	header {
		position: sticky;
		top: 0;
		z-index: 10;
		background: var(--header-bg);
		border-bottom: 1px solid var(--line);
	}

	.bar {
		display: flex;
		align-items: center;
		justify-content: space-between;
		height: 72px;
	}

	.brand {
		display: flex;
		align-items: baseline;
		gap: 10px;
		text-decoration: none;
	}

	.name {
		color: var(--text);
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 1.25rem;
	}

	.tag {
		color: var(--text-muted);
		font-family: var(--font-mono);
		font-size: 0.6875rem;
		letter-spacing: 0.08em;
		text-transform: uppercase;
	}

	nav {
		display: flex;
		gap: 28px;
	}

	nav a {
		color: var(--text);
		font-size: 0.875rem;
		font-weight: 600;
		text-decoration: none;
	}

	nav a:hover {
		color: var(--accent);
	}

	.toggle {
		display: none;
		background: none;
		border: 1px solid var(--line-strong);
		color: var(--text);
		font: 600 0.875rem var(--font-body);
		padding: 8px 14px;
		cursor: pointer;
	}

	@media (max-width: 820px) {
		.toggle {
			display: block;
		}

		.tag {
			display: none;
		}

		nav {
			display: none;
			position: absolute;
			top: 72px;
			left: 0;
			right: 0;
			flex-direction: column;
			gap: 0;
			background: var(--header-bg);
			border-bottom: 1px solid var(--line);
		}

		nav.open {
			display: flex;
		}

		nav a {
			padding: 16px var(--gutter);
			border-top: 1px solid var(--line);
		}
	}
</style>
