<script lang="ts">
	import Header from '../components/Header.svelte';
	import Footer from '../components/Footer.svelte';
	import Card from '../components/Card.svelte';

	let activeHeader = 'Home';

	function handleHeaderSelection(event: any) {
		activeHeader = event.detail.header;
	}
</script>

<Header headers={['Home', 'Collection', 'About']} on:headerSelection={handleHeaderSelection} />
<div class="h-screen w-screen bg-stone-950 flex items-center justify-center">
	{#if activeHeader == 'Home'}
		<Card />
	{/if}
</div>
<Footer />
