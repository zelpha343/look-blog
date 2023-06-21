<script lang="ts">
	import Header from '../components/Header.svelte';
	import Footer from '../components/Footer.svelte';

	let activeHeader = 'Home';

	function handleHeaderSelection(event) {
		activeHeader = event.detail.header;
	}
</script>

<Header
	headers={['Home', 'Collection', 'About']}
	{activeHeader}
	on:headerSelection={handleHeaderSelection}
/>
<div class="h-screen w-screen bg-stone-950 flex items-center justify-center" />
<Footer />
