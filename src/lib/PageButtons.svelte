<script>
	import Icon from 'svelte-awesome';
	import { faCaretRight, faCaretLeft } from '@fortawesome/free-solid-svg-icons';

	export let firstPage;
	export let lastPage;
	export let handleNextPage;
	export let handlePrevPage;
</script>

<div class="w-full flex justify-end my-4 p-2 sm:p-0">
	{#if firstPage}
		<button class="flex items-center uppercase text-lg text-gray-400" on:click={handleNextPage}>
			Next Page
			<Icon class="ml-2" scale="2" data={faCaretRight} />
		</button>
	{:else if lastPage}
		<button
			class="flex items-center uppercase text-lg text-gray-400 mr-auto"
			on:click={handlePrevPage}
		>
			<Icon class="mr-2" scale="2" data={faCaretLeft} />
			Prev Page
		</button>
	{:else}
		<button
			class="flex items-center uppercase text-lg text-gray-400 mr-auto"
			on:click={handlePrevPage}
		>
			<Icon class="mr-2" scale="2" data={faCaretLeft} />
			Prev Page
		</button>
		<button class="flex items-center uppercase text-lg text-gray-400" on:click={handleNextPage}>
			Next Page
			<Icon class="ml-2" scale="2" data={faCaretRight} />
		</button>
	{/if}
</div>

<style>
</style>
