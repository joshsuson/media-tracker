<script context="module">
	import supabase from '$lib/db';

	export async function load() {
		let { data: comics, error } = await supabase
			.from('comics')
			.select('*')
			.order('date_read', { ascending: false });

		return {
			props: {
				comics
			}
		};
	}
</script>

<script>
	import ComicList from '$lib/ComicList.svelte';

	export let comics;
</script>

<section class="mt-12">
	<ComicList {comics} />
</section>
