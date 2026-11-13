<script lang="ts">
	import { navLinks } from '#lib';
</script>

<footer>
	<div class="container">
		<div class="top">
			<div class="brand">
				<a class="name" href="/">Wollemi Pine NZ</a>
				<p class="tagline">
					A New Zealand guide to kauri's lost cousin: what it is, how it grows here, and where to
					see one.
				</p>
				<a class="btn" href="#see-one">Find a Wollemi near you</a>
			</div>

			<nav aria-label="Footer">
				<span class="heading">Explore</span>
				<ul>
					{#each navLinks as link (link.href)}
						<li><a href={link.href}>{link.label}</a></li>
					{/each}
				</ul>
			</nav>
		</div>

		<div class="bottom">
			<p>Unofficial fan-page dedicated to the Wollemi Pine. Not affiliated with the, <a href="https://www.wollemipine.com/" target="_blank" rel="noopener noreferrer">Wollemi Pine®</a> trademark, <a href="https://www.nationalparks.nsw.gov.au/" target="_blank" rel="noopener noreferrer">NSW National Parks and Wildlife Service</a> or the <a href="https://www.botanicgardens.org.au/" target="_blank" rel="noopener noreferrer">Botanic Gardens of Sydney</a>.</p>
			<p>Website designed by <a href="mailto:batcsg1@samuelbatchelor.nz" target="_blank" rel="noopener noreferrer">Samuel Batchelor</a> with the assistance of <a class="claude" href="https://claude.ai" target="_blank" rel="noopener noreferrer">Claude by Anthropic</a> [batcsg1@samuelbatchelor.nz] · <a href="https://batchelornz.com" target="_blank" rel="noopener noreferrer">batchelornz.com</a> · Photo credits on each page</p>
		</div>
	</div>
</footer>

<style>
	footer {
		position: relative;
		padding: clamp(64px, 9vw, 104px) 0 40px;
		background: linear-gradient(45deg, #000 0%, #121212 45%, #2e2e2e 100%);
		color: #9a9a9a;
		font-size: 0.875rem;
	}

	/* Thin accent rule fading out from the left */
	footer::before {
		content: '';
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		height: 2px;
		background: linear-gradient(90deg, var(--accent), transparent 70%);
	}

	.top {
		display: grid;
		grid-template-columns: 2fr 1fr;
		gap: 48px;
		padding-bottom: 56px;
	}

	.brand {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		gap: 16px;
		max-width: 440px;
	}

	.name {
		color: #f2f2f2;
		font-family: var(--font-display);
		font-weight: 700;
		font-size: 1.75rem;
		letter-spacing: -0.015em;
		text-decoration: none;
	}

	.tagline {
		color: #b8b8b8;
		font-size: 1rem;
		margin-bottom: 8px;
	}

	.heading {
		display: block;
		margin-bottom: 18px;
		color: var(--accent);
		font-family: var(--font-mono);
		font-size: 0.75rem;
		letter-spacing: 0.12em;
		text-transform: uppercase;
	}

	ul {
		margin: 0;
		padding: 0;
		list-style: none;
		display: grid;
		gap: 12px;
	}

	nav a {
		color: #e6e6e6;
		font-weight: 600;
		text-decoration: none;
		transition: color 0.15s;
	}

	nav a:hover {
		color: var(--accent);
	}

	.bottom {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 16px 48px;
		padding-top: 28px;
		border-top: 1px solid rgba(255, 255, 255, 0.1);
		font-size: 0.8125rem;
		line-height: 1.6;
	}

	.bottom p:last-child {
		text-align: right;
	}

	.bottom a {
		color: #d0d0d0;
		text-underline-offset: 3px;
	}

	.bottom a:hover {
		color: var(--accent);
	}

	/* Claude's brand terracotta */
	.bottom a.claude {
		color: #d97757;
		font-weight: 600;
	}

	.bottom a.claude:hover {
		color: #e8957a;
	}

	@media (max-width: 760px) {
		.top,
		.bottom {
			grid-template-columns: 1fr;
		}

		.bottom p:last-child {
			text-align: left;
		}
	}
</style>
