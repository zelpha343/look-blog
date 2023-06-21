<script lang="ts">
	import { createEventDispatcher } from 'svelte';

	let dispatch = createEventDispatcher();

	export let headers: any;
	export let activeHeader: any;

	const handleClick = (header: string) => {
		dispatch('headerSelection', { header });
	};
</script>

<div class="fixed w-full h-min flex justify-around items-center">
	<div class="w-36 h-20 py-2 px-3 flex"><img src="look_logo.svg" alt="LOGO" /></div>
	<div class="flex space-x-10">
		{#each headers as header}
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
	<div class="flex items-center">
		<input
			type="text"
			class="bg-stone-900 rounded-md p-3 focus:outline-none text-white text-xl"
			placeholder="Search"
		/>
	</div>
</div>
