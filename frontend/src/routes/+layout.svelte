<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
	import TopNav from '$lib/component/TopNav.svelte';

	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<TopNav />
{@render children()}
