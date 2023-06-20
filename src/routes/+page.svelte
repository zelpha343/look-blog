<script lang="ts">
	import Header from '../components/Header.svelte';
	import Footer from '../components/Footer.svelte';
	import Solus from '../components/Solus.svelte';
	import FloatCard from '../components/FloatCard.svelte';

	let selectedHeader = 'Home';
	const handleHeaderClick = (event: any) => {
		selectedHeader = event.detail.header;
	};
</script>

<Solus color="rose" />
<Solus color="green" />
<Solus color="blue" />

<Header on:headerClick={handleHeaderClick} {selectedHeader} />
<div class="h-screen w-screen bg-slate-950">
	<div class="relative top-[200px] left-[100px]">
		<FloatCard
			title="This is a cat"
			description="A cat is a cat. It says meow. Meow means meow. Yes that is the best translation I can give"
			tags={['Animals', 'Cats', 'Cute']}
			imgURL="/meow.jpeg"
		/>
	</div>
</div>
<Footer />
