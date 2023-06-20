<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

	const headers = ['Home', 'Collection', 'About'];
	const handleClick = (header: string) => {
		dispatch('headerClick', { header });
	};
</script>

<div
	class="flex fixed w-full h-min items-center bg-gray-950 opacity-90 border-b-4 border-purple-500 shadow-glow-purple"
>
	<div class="text-3xl text-rose-500 mx-3 my-2">
		<img src="look_logo.svg" alt="logo" height="100" width="100" />
	</div>
	<div class="flex space-x-5 text-xl mx-2">
		{#each headers as header}
			<button
				class="text-white hover:font-bold hover:text-purple-400"
				on:click={() => handleClick(header)}>{header}</button
			>{/each}
	</div>
</div>
