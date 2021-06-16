<script>
	export let click;
	export let text;
	export let left;

	const rightButton = 'mt-8';
	const leftButton = 'mt-8 mr-auto';
</script>

<div class={left ? leftButton : rightButton}>
	<button
		class="block w-48 uppercase text-gray-200 text-lg tracking-wider rounded-lg bg-gradient-to-br from-blue-400 via-indigo-500 to-purple-600 p-4"
		on:click={click}>{text}</button
	>
</div>

<style>
	button {
		box-shadow: 0 8px 16px hsla(251, 83%, 63%, 0.4);
	}
</style>
