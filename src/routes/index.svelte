<script>
	import supabase from '$lib/db';

	async function getComics() {
		let { data: Comics, error } = await supabase.from('Comics').select('*');
		return Comics;
	}

	getComics();
</script>

<h1>Home page</h1>
{#await getComics()}
	<!-- promise is pending -->
	<p>Waiting....</p>
{:then comics}
	<!-- promise was fulfilled -->
	<p>You have comics!</p>
	{#each comics as comic}
		<!-- content here -->
		<p>{comic.Title}</p>
	{/each}
{/await}
