<script lang="ts">
	const stats = [
		{ value: '~200 million years', label: 'Age of the oldest fossils linked to its lineage.' },
		{ value: '1994', label: 'Found alive in Wollemi National Park, New South Wales.' },
		{
			value: '2013',
			label: "New Zealand's first, planted at Christchurch Botanic Gardens (NZ Tree Register)."
		}
	];

	const facts = [
		{ term: 'Species', value: '<em>Wollemia nobilis</em>' },
		{ term: 'Family', value: 'Araucariaceae' },
		{ term: 'NZ relative', value: 'Kauri (<em>Agathis australis</em>)' },
		{ term: 'Native to', value: 'Wollemi National Park, NSW' },
		{ term: 'Wild status', value: 'Critically Endangered' },
		{ term: 'Known for', value: 'Knobbly, bubbled dark bark' }
	];

	const guides = [
		{
			title: 'By region',
			body: "[TO WRITE: frost, wind and rainfall notes for Northland through Southland, from NZ growers' experience.]",
			link: 'Regional guide'
		},
		{
			title: 'Pot or ground',
			body: '[TO WRITE: container size, potting mix, drainage, when to plant out, and how big it gets.]',
			link: 'Planting guide'
		},
		{
			title: 'When it sulks',
			body: '[TO WRITE: browning tips, root problems, pests and other common questions, with photos.]',
			link: 'Troubleshooting'
		}
	];

	const specimens = [
		{
			place: 'Christchurch Botanic Gardens',
			town: 'Christchurch, Canterbury',
			planted: 'Planted 2013 · first in NZ'
		},
		{ place: '[SPECIMEN LOCATION]', town: '[TOWN, REGION]', planted: '[YEAR PLANTED]' },
		{ place: '[SPECIMEN LOCATION]', town: '[TOWN, REGION]', planted: '[YEAR PLANTED]' }
	];

	const nurseries = [
		{ name: '[NURSERY NAME]', detail: '[REGION · WEBSITE]' },
		{ name: '[NURSERY NAME]', detail: '[REGION · WEBSITE]' },
		{ name: '[NURSERY NAME]', detail: '[REGION · WEBSITE]' }
	];
</script>

<svelte:head>
	<title>WollemiPine.co.nz</title>
	<meta
		name="description"
		content="A New Zealand guide to the Wollemi pine: what it is, how it grows here, and where you can see one."
	/>
</svelte:head>

<!-- Hero -->
<section class="hero">
	<div class="container split">
		<div>
			<span class="eyebrow">Wollemia nobilis · Aotearoa New Zealand</span>
			<h1>Kauri's lost cousin, growing in New&nbsp;Zealand.</h1>
			<p class="lede">
				The Wollemi pine was known only from fossils until living trees were found in an Australian
				canyon in 1994. This is a New Zealand guide to what it is, how it grows here, and where you
				can stand next to one.
			</p>
			<div class="actions">
				<a class="btn" href="#see-one">Find a Wollemi near you</a>
				<a class="text-link" href="#the-tree">Read the story</a>
			</div>
		</div>

		<figure class="photo">
			<figcaption class="placeholder">
				[YOUR PHOTO: Wollemi foliage, close up. Your own shot or a freely licensed one, credited.]
			</figcaption>
		</figure>
	</div>
</section>

<!-- Stats -->
<section class="stats section--alt">
	<div class="container stat-grid">
		{#each stats as stat (stat.value)}
			<div class="stat">
				<h3>{stat.value}</h3>
				<p>{stat.label}</p>
			</div>
		{/each}
	</div>
</section>

<!-- The tree -->
<section id="the-tree" class="section">
	<div class="container split">
		<div>
			<span class="eyebrow">The tree</span>
			<h2 class="section-title">A conifer everyone thought was extinct.</h2>
			<div class="prose">
				<p>
					In 1994 a New South Wales parks ranger, David Noble, abseiled into a remote sandstone
					canyon and found a stand of trees no botanist could name. They turned out to be a third
					living branch of the Araucariaceae, the family that also holds New Zealand's kauri and the
					Norfolk Island pine.
				</p>
				<p>
					Fewer than a hundred mature trees are known in the wild and the site is kept secret.
					Growing it in gardens around the world is part of the plan to keep the species alive.
				</p>
			</div>
			<div class="actions">
				<a class="text-link" href="/">Full story and botany</a>
			</div>
		</div>

		<dl class="table">
			{#each facts as fact (fact.term)}
				<div class="row">
					<dt>{fact.term}</dt>
					<dd>{@html fact.value}</dd>
				</div>
			{/each}
		</dl>
	</div>
</section>

<!-- Growing in NZ -->
<section id="growing" class="section section--alt">
	<div class="container">
		<span class="eyebrow">Growing in NZ</span>
		<h2 class="section-title">Written for our<br />climate, not Sydney's.</h2>
		<p class="lede">
			Most care advice online assumes Australian or British conditions. These guides are organised
			around New Zealand regions and seasons.
		</p>

		<div class="cards">
			{#each guides as guide (guide.title)}
				<article class="card">
					<h3>{guide.title}</h3>
					<p>{guide.body}</p>
					<a class="text-link" href="/">{guide.link}</a>
				</article>
			{/each}
		</div>
	</div>
</section>

<!-- See one -->
<section id="see-one" class="section">
	<div class="container">
		<span class="eyebrow">See one</span>
		<h2 class="section-title">The New Zealand<br />specimen register.</h2>
		<p class="lede">
			A running list of Wollemi pines in public gardens and parks around the country. Know of one
			that's missing? Send it in.
		</p>

		<div class="register">
			{#each specimens as s, i (i)}
				<div class="register-row">
					<strong>{s.place}</strong>
					<span>{s.town}</span>
					<span class="mono">{s.planted}</span>
				</div>
			{/each}
		</div>

		<div class="actions">
			<a class="btn" href="/">Find a Wollemi near you</a>
			<a class="text-link" href="/">Submit a specimen</a>
		</div>
	</div>
</section>

<!-- Find a nursery -->
<section id="nursery" class="section section--alt">
	<div class="container split">
		<div>
			<span class="eyebrow">Find a nursery</span>
			<h2 class="section-title">We don't sell trees. We point you to people who do.</h2>
			<p>
				This site has no shop and takes no commission. The list links to New Zealand nurseries that
				stock legitimately propagated Wollemi pines.
			</p>
		</div>

		<ul class="table nurseries">
			{#each nurseries as n, i (i)}
				<li class="row">
					<strong>{n.name}</strong>
					<span>{n.detail}</span>
				</li>
			{/each}
		</ul>
	</div>
</section>

<!-- About -->
<section id="about" class="section">
	<div class="container">
		<span class="eyebrow">About this site</span>
		<h2 class="section-title about-title">Independent, non-commercial, and made in New Zealand.</h2>
		<p class="lede">
			Wollemi Pine NZ is a personal project by [YOUR NAME]. It is not affiliated with, endorsed by,
			or licensed by Wollemi Australia Pty Ltd, the Botanic Gardens of Sydney, or any nursery. For
			the official conservation and licensing programme, visit
			<a href="https://wollemipine.com" target="_blank" rel="noopener">wollemipine.com</a>.
		</p>
	</div>
</section>

<style>
	/* Shared two-column layout */
	.split {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 48px clamp(32px, 5vw, 64px);
		align-items: start;
	}

	/* Hero */
	.hero {
		padding: clamp(48px, 8vw, 96px) 0 clamp(64px, 9vw, 96px);
	}

	.hero h1 {
		font-size: clamp(2.75rem, 6.5vw, 4.5rem);
		margin-bottom: 24px;
	}

	.hero .lede {
		font-size: 1.0625rem;
		max-width: 540px;
	}

	.photo {
		margin: 0;
		min-height: 400px;
		height: 100%;
		display: flex;
		align-items: flex-end;
		padding: 20px;
		background: var(--surface);
		border: 1px solid var(--line-strong);
	}

	/* Stats strip */
	.stats {
		padding: 36px 0 40px;
		border-top: 1px solid var(--line);
	}

	.stat-grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 32px;
	}

	.stat {
		border-top: 3px solid var(--accent);
		padding-top: 16px;
	}

	.stat h3 {
		font-size: 1.75rem;
		margin-bottom: 10px;
	}

	.stat p {
		color: var(--text-muted);
		font-size: 0.8125rem;
		max-width: 340px;
	}

	/* The tree */
	.prose {
		display: grid;
		gap: 18px;
	}

	.table {
		margin: 0;
		padding: 0;
		list-style: none;
		border-top: 1px solid var(--line);
	}

	.table .row {
		display: flex;
		justify-content: space-between;
		align-items: baseline;
		gap: 16px;
		padding: 18px 0;
		border-bottom: 1px solid var(--line);
	}

	dt {
		color: var(--text-muted);
		font-family: var(--font-mono);
		font-size: 0.75rem;
		letter-spacing: 0.1em;
		text-transform: uppercase;
	}

	dd {
		margin: 0;
		color: var(--text);
		text-align: right;
	}

	/* Growing in NZ */
	.cards {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 24px;
		margin-top: 48px;
	}

	.card {
		display: flex;
		flex-direction: column;
		gap: 16px;
		padding: 28px;
		background: var(--bg);
		border: 1px solid var(--line-strong);
	}

	.card h3 {
		font-size: 1.375rem;
	}

	.card p {
		font-size: 0.9375rem;
		flex: 1;
	}

	/* Specimen register */
	.register {
		margin-top: 56px;
		border-top: 1px solid var(--line);
	}

	.register-row {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 8px 32px;
		padding: 22px 0;
		border-bottom: 1px solid var(--line);
		font-size: 0.9375rem;
	}

	.register-row strong {
		color: var(--text);
	}

	.mono {
		font-family: var(--font-mono);
		font-size: 0.8125rem;
		color: var(--text-muted);
	}

	/* Nursery */
	.nurseries strong {
		color: var(--text);
	}

	.nurseries span {
		color: var(--text-muted);
	}

	/* About */
	.about-title {
		max-width: 720px;
	}

	@media (max-width: 860px) {
		.split,
		.stat-grid,
		.cards {
			grid-template-columns: 1fr;
		}

		.photo {
			min-height: 280px;
		}

		.register-row {
			grid-template-columns: 1fr;
		}
	}
</style>
