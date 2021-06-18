<script>
	import StepOne from '$lib/steps/StepOne.svelte';
	import StepTwo from '$lib/steps/StepTwo.svelte';
	import StepThree from '$lib/steps/StepThree.svelte';
	import StepFour from '$lib/steps/StepFour.svelte';
	import StepFive from '$lib/steps/StepFive.svelte';
	import Button from '$lib/Button.svelte';
	import supabase from '$lib/db';
	import { session } from '$app/stores';
	import { goto } from '$app/navigation';
	import { browser } from '$app/env';

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
		step += 1;
		title = null;
		dateRead = null;
		rating = null;
		type = null;
		issueNumbers = null;
		numberOfIssues = null;
		writer = null;
		console.log('Your comic was logged');
	};

	if (browser) {
		$session = supabase.auth.session();
		if (!$session) goto('/login');
	}

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
	<div class="p-4">
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
		{:else if step === 5}
			<StepFive />
		{/if}
		<div class="sm:flex sm:justify-end">
			{#if step === 4}
				<Button click={() => (step -= 1)} text="Back" left={true} />
				<Button text="Log" click={logComic} left={false} />
			{:else if step === 5}
				<Button click={() => (step = 1)} text="Log Another" left={false} />
			{:else if step < 4 && step > 1}
				<Button click={() => (step -= 1)} text="Back" left={true} />
				<Button click={() => (step += 1)} text="Next" left={false} />
			{:else}
				<Button click={() => (step += 1)} text="Next" left={false} />
			{/if}
		</div>
	</div>
</section>
