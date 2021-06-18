<script>
	export let click;
	export let text;
	export let left;

	const rightButton = 'sm:mt-8 w-full sm:w-auto';
	const leftButton = 'mt-16 sm:mt-8 mb-4 mr-auto w-full sm:w-auto';

	const notLogin =
		'block w-full sm:w-48 uppercase text-gray-200 text-lg tracking-wider rounded-lg bg-gradient-to-br from-blue-400 via-indigo-500 to-purple-600 p-4';
	const login =
		'block w-full uppercase text-gray-200 text-lg tracking-wider rounded-lg bg-gradient-to-br from-blue-400 via-indigo-500 to-purple-600 p-4';
</script>

<div class={left ? leftButton : rightButton}>
	<button class={text === 'Log In' ? login : notLogin} on:click={click}>{text}</button>
</div>

<style>
	button {
		box-shadow: 0 8px 16px hsla(251, 83%, 63%, 0.4);
	}
</style>
