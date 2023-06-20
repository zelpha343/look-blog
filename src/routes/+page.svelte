<script lang="ts">
	import Header from '../components/Header.svelte';
	import Footer from '../components/Footer.svelte';
	import Solus from '../components/Solus.svelte';
	import FloatCard from '../components/FloatCard.svelte';
	import Carousel from '../components/Carousel.svelte';

	let selectedHeader = 'Home';
	const handleHeaderClick = (event: any) => {
		selectedHeader = event.detail.header;
	};
</script>

<Solus color="rose" />
<Solus color="green" />
<Solus color="blue" />

<Header on:headerClick={handleHeaderClick} {selectedHeader} />
<div class="h-screen w-screen bg-slate-950 flex items-center justify-center">
	<div class="relative flex flex-col space-y-5 items-center">
		<Carousel />
	</div>
</div>
<Footer />
