<script>
	import '../tailwind.css';
</script>

<header class="w-full text-center">
	<h1 class="text-5xl">
		<span
			class="font-semibold text-6xl text-transparent bg-clip-text bg-gradient-to-br from-blue-400 via-indigo-500 to-purple-600"
			>{`<`}</span
		>
		JoshReadsComics
		<span
			class="font-semibold text-6xl text-transparent bg-clip-text bg-gradient-to-br from-blue-400 via-indigo-500 to-purple-600"
			>{`/>`}</span
		>
	</h1>
</header>
<main class="max-w-2xl mx-auto">
	<slot />
</main>

<style>
	:global(body) {
		@apply bg-gray-800 text-gray-200;
	}
</style>
