<script>
	export let value;
</script>

<h1>Step One</h1>

<div>
	<label for="title" class="block text-sm font-medium text-gray-700">Title</label>
	<div class="mt-1 w-1/2">
		<input
			type="text"
			name="title"
			id="title"
			class="py-2 px-1 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border border-gray-300 rounded-md"
			placeholder="Enter the comic book title"
			bind:value
		/>
	</div>
	<label class="block text-sm font-medium text-gray-700" for="dateRead">Date Read</label>
	<div class="mt-1 w-1/2">
		<input
			type="date"
			name="dateRead"
			id="dateRead"
			class="py-2 px-1 shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border border-gray-300 rounded-md"
		/>
	</div>
</div>
