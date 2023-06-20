<script lang="ts">
	export let selectedHeader = 'Home';

	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

	const headers = ['Home', 'Collection', 'About'];

	let headersDisplay = false;
	const handleClick = (header: string) => {
		dispatch('headerClick', { header });
	};
</script>

<!-- <button
class="text-white hover:font-bold hover:text-purple-400"
on:click={() => handleClick(header)}>{header}</button
> -->

<div
	class="flex fixed w-full h-min items-center bg-gray-950 opacity-90 border-b-4 border-purple-500 shadow-glow-purple appear-animation z-50"
>
	<div>
		<img src="look_logo.svg" alt="logo" height="100" width="100" />
	</div>
	<div class="flex space-x-3 mx-2">
		{#each headers as header}
			{#if selectedHeader == header}
				<button
					class="text-purple-400 font-bold text-lg px-3 py-1 border-t-2 border-solid border-purple-500"
					on:click={() => handleClick(header)}>{header}</button
				>{:else}
				<button
					class="text-white text-lg px-3 py-1 hover:font-bold hover:text-purple-400"
					on:click={() => handleClick(header)}>{header}</button
				>{/if}
		{/each}
	</div>
</div>
