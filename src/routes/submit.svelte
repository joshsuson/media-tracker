<script>
	import supabase from '$lib/db';

	let title;
	let dateRead;
	let type;
	let issueNumbers;
	let numberOfIssues;
	let writer;
	let rating;
	let comic = {};

	function handleClick() {
		console.log(comic);
	}

	async function logComic() {
		const newComic = await supabase.from('Comics').insert(comic);
	}

	$: {
		comic = {
			Title: title,
			Type: type,
			Date_Read: dateRead,
			Rating: rating,
			Issue_Numbers: issueNumbers,
			Number_of_Issues: numberOfIssues,
			Writer: writer
		};
	}
</script>

<div>
	<input type="text" bind:value={title} name="Title" placeholder="Enter The Title" />
	<input type="date" bind:value={dateRead} name="Date Read" placeholder="Date Read" />
	<h1>Type:</h1>
	<label for="collectedVolume">Collected Volume</label>
	<input type="radio" id="collectedVolume" name="type" bind:group={type} value="Collected Volume" />
	<label for="singleIssue">Single Issue</label>
	<input type="radio" id="singleIssue" name="type" bind:group={type} value="Single Value" />
	<label for="rating">Rating</label>
	<select name="rating" id="rating" bind:value={rating}>
		<option value="1">1</option>
		<option value="2">2</option>
		<option value="3">3</option>
		<option value="4">4</option>
		<option value="5">5</option>
	</select>
	<div class="inner-container">
		<input type="text" name="Issue Numbers" bind:value={issueNumbers} placeholder="Issue Numbers" />
		<input
			type="number"
			name="Number of Issues"
			bind:value={numberOfIssues}
			placeholder="Number of Issues"
		/>
		<input type="text" name="Writer" bind:value={writer} placeholder="Writer" />
	</div>
	<button on:click={logComic}>Log Comic</button>
	<button on:click={handleClick}>Console Log Comic</button>
</div>

<style>
	.inner-container {
		margin-top: 16px;
	}
</style>
