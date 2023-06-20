<script lang="ts">
	// export let id: number;
	export let title: string = 'This is a cat';
	export let description: string =
		'A cat is a cat. It says meow. Meow means meow. Yes that is the best translation I can give';
	export let tags: any = ['Animals', 'Cats', 'Cute'];
	export let imgURL: string = '/meow.jpeg';
</script>

<div
	class="flex flex-col w-96 rounded-lg shadow-2xl bg-black text-white border-2 border-white border-solid hover:scale-110 hover:border-purple-400"
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
