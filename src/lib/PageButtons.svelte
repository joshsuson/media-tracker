<script>
	import Icon from 'svelte-awesome';
	import { faCaretRight } from '@fortawesome/free-solid-svg-icons';

	export let firstPage;
	export let lastPage;
	export let handleNextPage;
	export let handlePrevPage;
</script>

<div class="w-full flex justify-end">
	{#if firstPage}
		<button class="flex items-center uppercase text-lg text-yellow-400" on:click={handleNextPage}>
			Next Page
			<Icon class="ml-2" scale="2" data={faCaretRight} />
		</button>
	{:else if lastPage}
		<button on:click={handlePrevPage}>Prev Page</button>
	{:else}
		<button on:click={handlePrevPage}>Prev Page</button>
		<button on:click={handleNextPage}>Next Page</button>
	{/if}
</div>

<style>
</style>
