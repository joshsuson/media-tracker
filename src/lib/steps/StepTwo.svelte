<script>
	import Label from '$lib/Label.svelte';

	export let ratingValue = 1;

	let stars = [1];

	$: {
		stars = [...Array(ratingValue).keys()];
	}
</script>

<Label name="rating" label="Rating" />
<div>
	{#each stars as _}
		<span>⭐</span>
	{/each}
</div>
<div>
	<input type="range" min="1" max="5" name="rating" id="rating" bind:value={ratingValue} />
</div>
