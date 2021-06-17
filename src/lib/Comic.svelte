<script>
	export let comic;
	const ratingArray = [...Array(comic.rating).keys()];
</script>

<li>
	<div class="px-4 py-4 sm:px-6">
		<div class="flex items-center justify-between">
			<p
				class="text-md uppercase font-medium bg-gradient-to-br from-blue-400 via-indigo-500 to bg-purple-600 text-transparent bg-clip-text  truncate"
			>
				{comic.title}
			</p>
			<div class="ml-2 flex-shrink-0 flex">
				{#each ratingArray as _}
					<span class="text-sm ml-2">⭐</span>
				{/each}
			</div>
		</div>
	</div>
</li>
