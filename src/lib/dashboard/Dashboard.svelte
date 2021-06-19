<script>
	export let comics;
	let totalBooks = comics.length;
	let mostRecent = comics[0].title;
	let issuesReadArray = comics.map((comic) => comic.number_of_issues);
	let totalIssues = issuesReadArray.reduce((a, b) => a + b, 0);
</script>

<div>
	<h2>Total Books Read:</h2>
	<p>{totalBooks}</p>
</div>
<div>
	<h2>Total Issues Read:</h2>
	<p>{totalIssues}</p>
</div>
<div>
	<h2>Most Recent Read:</h2>
	<p>{mostRecent}</p>
</div>
