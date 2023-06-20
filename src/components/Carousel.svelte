<script lang="ts">
	import FloatCard from './FloatCard.svelte';
</script>

<div class="flex relative">
	<div class="relative z-10 -right-[300px] blur-md"><FloatCard /></div>
	<div class="relative z-20"><FloatCard /></div>
	<div class="relative z-10 -left-[300px] blur-md"><FloatCard /></div>
</div>
<div class="flex relative bottom-[300px] justify-between w-5/6">
	<button
		class="h-20 w-20 bg-yellow-300 font-bold text-black rounded-full text-2xl p-3 hover:bg-black hover:text-yellow-300 hover:border-yellow-400 hover:border-4"
		>{'<'}</button
	>
	<button
		class="h-20 w-20 bg-yellow-300 font-bold text-black rounded-full text-2xl p-3 hover:bg-black hover:text-yellow-300 hover:border-yellow-400 hover:border-4"
		>{'>'}</button
	>
</div>
