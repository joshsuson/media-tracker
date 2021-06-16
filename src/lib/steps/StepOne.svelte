<script>
	import Label from '$lib/Label.svelte';

	export let titleValue;
	export let dateValue;
</script>

<div>
	<Label name="title" label="Title" />
	<div class="mt-1">
		<input
			type="text"
			name="title"
			id="title"
			class="h-14 py-4 px-2 text-xl mb-8 text-gray-800 shadow-md focus:ring-indigo-500 focus:border-indigo-500 block w-full rounded-md"
			placeholder="Enter the comic book title"
			bind:value={titleValue}
		/>
	</div>
	<Label name="dateRead" label="Date Read" />
	<div class="mt-1 ">
		<input
			type="date"
			name="dateRead"
			id="dateRead"
			class="h-14 py-4 px-2 text-xl mb-8 text-gray-800 shadow-md focus:ring-indigo-500 focus:border-indigo-500 block w-full rounded-md"
			bind:value={dateValue}
		/>
	</div>
</div>

<style>
	::placeholder {
		@apply text-gray-700;
	}
</style>
