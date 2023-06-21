<script lang="ts">
	import Header from '../components/Header.svelte';
	import Footer from '../components/Footer.svelte';
	import Home from '../components/Home.svelte';
	import Collection from '../components/Collection.svelte';
	import About from '../components/About.svelte';

	let scroll: number;
	let winWidth: number;
	let factor: number;
	$: factor = scroll / winWidth;

	let activeHeader = 'Home';

	function handleHeaderSelection(event: any) {
		activeHeader = event.detail.header;
	}
</script>

<svelte:window bind:scrollX={scroll} bind:innerHeight={winWidth} />

<Header headers={['Home', 'Collection', 'About']} on:headerSelection={handleHeaderSelection} />
<div class="h-screen w-screen bg-stone-950 flex flex-col relative">
	{#if activeHeader == 'Home'}
		<Home />
	{:else if activeHeader == 'Collection'}
		<Collection />
	{:else}
		<About />
	{/if}
</div>

<Footer />
