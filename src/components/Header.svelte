<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	import { fade, fly } from 'svelte/transition';
	import { onMount } from 'svelte';

	let dispatch = createEventDispatcher();

	let animate = false;

	onMount(() => (animate = true));

	export let headers: any;
	export let activeHeader: any;

	const handleClick = (header: string) => {
		dispatch('headerSelection', { header });
	};
</script>

{#if animate}
	<div class="fixed w-full h-min flex justify-around items-center">
		<div class="w-36 h-20 py-2 px-3 flex" transition:fade={{ duration: 1000 }}>
			<img src="look_logo.svg" alt="LOGO" />
		</div>
		<div class="flex space-x-10">
			{#each headers as header, i}
				{#if activeHeader == header}
					<button
						class="font-bold text-purple-400 text-xl border-b-2 border-purple-400"
						transition:fade={{ duration: 1000, delay: 200 * i + 200 }}>{header}</button
					>
				{:else}
					<button
						class="text-xl text-white font-bold hover:text-purple-400"
						transition:fade={{ duration: 1000, delay: 200 * i + 200 }}
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
{/if}
