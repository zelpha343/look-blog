<script lang="ts">
	// export let id: number;
	export let title: string;
	export let description: string;
	export let tags: any;
	export let imgURL: string;
</script>

<div
	class="flex flex-col w-96 rounded-lg shadow-2xl bg-blend-hue text-white border-2 border-white border-solid hover:scale-110 hover:mousedown"
>
	<div class="flex-1"><img src={imgURL} alt="IMG" /></div>
	<div class="flex-1 flex flex-col">
		<div class="flex m-3">
			{#each tags as tag}
				<button class="bg-rose-400 text-red-900 px-3 mx-1 select-none">{tag}</button>
			{/each}
		</div>
		<div class="text-3xl font-bold left-4 relative">{title}</div>
		<div class="text-lg px-3 my-2">{description}</div>
	</div>
</div>
