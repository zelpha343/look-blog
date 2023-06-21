<script lang="ts">
	import { onMount } from 'svelte';

	export let title = 'This is a cat';
	export let description =
		'Sit adipisicing esse laborum pariatur proident consequat deserunt ullamco mollit. Sit culpa voluptate amet qui amet occaecat pariatur non cupidatat nisi occaecat esse. Reprehenderit irure incididunt aliqua dolor adipisicing quis aute cupidatat quis deserunt ad nulla nisi. Laborum adipisicing cupidatat mollit sunt culpa voluptate enim laboris sit exercitation. Proident commodo ut qui cillum occaecat occaecat pariatur ipsum Lorem.';
	export let imgURL = 'meow.jpeg';
	export let tags = ['Cute', 'Cat', 'Aww'];

	let render = false;

	onMount(() => {
		render = true;
	});
</script>

{#if render}
	<div
		class="flex flex-col h-2/3 w-96 border-solid border-2 border-purple-400 rounded-lg shadow-2xl bg-slate-950 hover:border-red-600 hover:opacity-80 hover:cursor-pointer"
	>
		<div class="flex-basis-1/3"><img src={imgURL} alt="cat" /></div>
		<div class="flex-basis-2/3">
			<div class="flex space-x-4 px-3 pt-2">
				{#each tags as tag}
					<button class="bg-rose-400 text-red-900 py-0 px-3 rounded-sm">{tag}</button>
				{/each}
			</div>
			<div class="text-4xl font-bold text-white px-3 mt-2">{title}</div>
			<div class="text-lg text-white px-3 line-clamp-6">{description}</div>
		</div>
	</div>
{/if}
