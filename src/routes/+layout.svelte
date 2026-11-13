<script lang="ts">
	import '../app.css';
	import favicon from '#lib/assets/favicon.svg';
	import Header from '#lib/components/Header.svelte';
	import Footer from '#lib/components/Footer.svelte';
	import type { LayoutProps } from './$types';

	let { children }: LayoutProps = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link
		rel="stylesheet"
		href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+Condensed:ital,wght@0,400;0,600;0,700;1,400&family=IBM+Plex+Mono:wght@400&display=swap"
	/>
</svelte:head>

<Header />
<main>
	{@render children()}
</main>
<Footer />
