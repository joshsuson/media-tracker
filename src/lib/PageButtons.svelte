<script>
	export let firstPage;
	export let lastPage;
	export let handleNextPage;
	export let handlePrevPage;
</script>

<div>
	{#if firstPage}
		<button on:click={handleNextPage}>Next Page</button>
	{:else if lastPage}
		<button on:click={handlePrevPage}>Prev Page</button>
	{:else}
		<button on:click={handlePrevPage}>Prev Page</button>
		<button on:click={handleNextPage}>Next Page</button>
	{/if}
</div>
