<script>
	import Comic from '$lib/Comic.svelte';
	export let comics;
</script>

<div class="bg-gray-700 shadow overflow-hidden sm:rounded-md">
	<ul class="divide-y divide-gray-600">
		{#each comics as comic}
			<Comic {comic} />
		{/each}
	</ul>
</div>
