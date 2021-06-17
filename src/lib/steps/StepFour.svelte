<script>
	import Label from '$lib/Label.svelte';
	export let writerValue;
</script>

<Label name="writer" label="Writer" />
<div class="mt-1">
	<input
		type="text"
		name="writer"
		id="Writer"
		class="h-14 py-4 px-2 text-xl mb-8 text-gray-800 shadow-md focus:ring-indigo-500 focus:border-indigo-500 block w-full rounded-md"
		placeholder="Who wrote the book"
		bind:value={writerValue}
	/>
</div>
