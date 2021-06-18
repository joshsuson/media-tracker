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
	import PageButtons from '$lib/PageButtons.svelte';

	export let comics;
	let currentPage = 1;
	let comicsPerPage = 10;
	let currentComics = comics.slice(0, 10);
	let lastPage;
	let firstPage = true;

	const handleNextPage = () => {
		currentPage++;
		const indexOfLastComic = currentPage * comicsPerPage;
		const indexOfFirstComic = indexOfLastComic - comicsPerPage;
		currentComics = comics.slice(indexOfFirstComic, indexOfLastComic);
	};

	const handlePrevPage = () => {
		currentPage--;
		const indexOfLastComic = currentPage * comicsPerPage;
		const indexOfFirstComic = indexOfLastComic - comicsPerPage;
		currentComics = comics.slice(indexOfFirstComic, indexOfLastComic);
	};

	$: {
		// if (currentComics.length < 10) lastPage = true;
		currentComics.length < 10 ? (lastPage = true) : (lastPage = false);
		// if (currentPage > 1) firstPage = false;
		currentPage > 1 ? (firstPage = false) : (firstPage = true);
	}
</script>

<section class="mt-12">
	<PageButtons {lastPage} {firstPage} {handleNextPage} {handlePrevPage} />
	<ComicList comics={currentComics} />
</section>
