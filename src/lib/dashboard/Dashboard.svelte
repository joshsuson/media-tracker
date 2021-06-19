<script>
	export let comics;
	let totalBooks = comics.length;
	let mostRecent = comics[0].title;
	let issuesReadArray = comics.map((comic) => comic.number_of_issues);
	let totalIssues = issuesReadArray.reduce((a, b) => a + b, 0);
	let ratingsArray = comics.map((comic) => comic.rating);
	let ratingsSum = ratingsArray.reduce((a, b) => a + b, 0);
	let ratingAvg = Math.floor(ratingsSum / ratingsArray.length);
	let ratingAvgArray = [...Array(ratingAvg).keys()];
</script>

<div class="px-2">
	<h3 class="text-lg leading-6 font-medium text-gray-300 uppercase">Reading Stats</h3>
	<div class="mt-4">
		<div class="w-full bg-gray-700 rounded-md shadow-lg mb-4 p-4">
			<h3
				class="mb-1 font-semibold text-transparent bg-gradient-to-br from-blue-400 via-indigo-500 to-purple-600 bg-clip-text"
			>
				Most Recent Read
			</h3>
			<p class="font-semibold tracking-wide text-2xl uppercase text-gray-300">{mostRecent}</p>
		</div>
		<div class="flex flex-col sm:flex-row items-center justify-between">
			<div class="bg-gray-700 rounded-md shadow-lg mb-4 p-4 w-full sm:w-1/3">
				<h3
					class="mb-1 font-semibold text-transparent bg-gradient-to-br from-blue-400 via-indigo-500 to-purple-600 bg-clip-text"
				>
					Total Books Read
				</h3>
				<p class="font-semibold tracking-wide text-2xl uppercase text-gray-300">{totalBooks}</p>
			</div>
			<div class="bg-gray-700 rounded-md shadow-lg mb-4 p-4 w-full sm:w-1/3 sm:ml-2">
				<h3
					class="mb-1 font-semibold text-transparent bg-gradient-to-br from-blue-400 via-indigo-500 to-purple-600 bg-clip-text"
				>
					Total Issues Read
				</h3>
				<p class="font-semibold tracking-wide text-2xl uppercase text-gray-300">{totalIssues}</p>
			</div>
			<div class="bg-gray-700 rounded-md shadow-lg mb-4 p-4 w-full sm:w-1/3 sm:ml-2">
				<h3
					class="mb-1 font-semibold text-transparent bg-gradient-to-br from-blue-400 via-indigo-500 to-purple-600 bg-clip-text"
				>
					Average Rating
				</h3>
				<p class="font-semibold tracking-wide text-2xl uppercase text-gray-300">
					{#each ratingAvgArray as _}
						{#if _ === 0}
							<span>⭐</span>
						{:else}
							<span class="ml-2">⭐</span>
						{/if}
					{/each}
				</p>
			</div>
		</div>
	</div>
</div>
