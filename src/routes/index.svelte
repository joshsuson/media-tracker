<script>
	import supabase from '$lib/db';
	import ComicList from '$lib/ComicList.svelte';

	async function getComics() {
		let { data: comics, error } = await supabase
			.from('comics')
			.select('*')
			.order('date_read', { ascending: false });
		return comics;
	}

	getComics();
</script>

<section class="mt-12">
	{#await getComics()}
		<p>Waiting....</p>
	{:then comicsData}
		<ComicList {comicsData} />
	{/await}
</section>
