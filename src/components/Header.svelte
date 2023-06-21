<script lang="ts">
	import { createEventDispatcher } from 'svelte';

	let dispatch = createEventDispatcher();

	export let headers: any;

	let activeHeader = 'Home';

	const handleClick = (header: string) => {
		dispatch('headerSelection', { header });
		activeHeader = header;
	};
</script>

<div class="fixed w-full h-min flex justify-around items-center z-10">
	<div class="w-36 h-20 py-2 px-3 flex relative">
		<div class="absolute h-20 w-20 hover:bg-pink-500 bg-purple-600 blur-3xl left-1" />
		<img src="look_logo.svg" alt="LOGO" />
	</div>
	<div class="flex space-x-10">
		{#each headers as header, i (header)}
			{#if activeHeader == header}
				<button class="font-bold text-purple-400 text-xl border-b-2 border-purple-400"
					>{header}</button
				>
			{:else}
				<button
					class="text-xl text-white font-bold hover:text-purple-400"
					on:click={() => handleClick(header)}>{header}</button
				>
			{/if}
		{/each}
	</div>
</div>
