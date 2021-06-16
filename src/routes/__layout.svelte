<script>
	import '../tailwind.css';
</script>

<main class="max-w-2xl mx-auto">
	<slot />
</main>

<style>
	:global(body) {
		@apply bg-gray-800 text-gray-200;
	}
</style>
