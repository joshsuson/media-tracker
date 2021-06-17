<script>
	import StepOne from '$lib/steps/StepOne.svelte';
	import StepTwo from '$lib/steps/StepTwo.svelte';
	import StepThree from '$lib/steps/StepThree.svelte';
	import StepFour from '$lib/steps/StepFour.svelte';
	import Button from '$lib/Button.svelte';
	import supabase from '$lib/db';

	let step = 1;
	let comic = {};

	let title;
	let dateRead;
	let rating;
	let type;
	let issueNumbers;
	let numberOfIssues;
	let writer;

	const logComic = async () => {
		await supabase.from('comics').insert(comic);
		console.log('Your comic was logged');
	};

	$: {
		comic = {
			title,
			date_read: dateRead,
			rating,
			type,
			issue_numbers: issueNumbers,
			number_of_issues: numberOfIssues,
			writer
		};
	}
</script>

<section class="min-h-screen grid justify-center items-center grid-cols-1">
	<div>
		{#if step === 1}
			<StepOne bind:titleValue={title} bind:dateValue={dateRead} />
		{:else if step === 2}
			<StepTwo bind:ratingValue={rating} />
		{:else if step === 3}
			<StepThree
				bind:typeValue={type}
				bind:issueNumbersValue={issueNumbers}
				bind:numberOfIssuesValue={numberOfIssues}
			/>
		{:else if step === 4}
			<StepFour bind:writerValue={writer} />
		{/if}
		<div class="flex justify-end">
			{#if step === 4}
				<Button click={() => (step -= 1)} text="Back" left={true} />
				<Button text="Log" click={logComic} />
			{:else if step < 4 && step > 1}
				<Button click={() => (step -= 1)} text="Back" left={true} />
				<Button click={() => (step += 1)} text="Next" />
			{:else}
				<Button click={() => (step += 1)} text="Next" />
			{/if}
		</div>
	</div>
</section>
