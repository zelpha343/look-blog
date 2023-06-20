<script lang="ts">
	import Header from '../components/Header.svelte';
	import Footer from '../components/Footer.svelte';

	const handleHeaderClick = (event: any) => {
		console.log(event.detail.header);
	};
</script>

<Header on:headerClick={handleHeaderClick} />
<div class="h-screen w-screen bg-slate-950" />
<Footer />
