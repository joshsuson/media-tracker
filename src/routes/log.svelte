<script>
	import StepOne from '$lib/steps/StepOne.svelte';
	import StepTwo from '$lib/steps/StepTwo.svelte';
	import StepThree from '$lib/steps/StepThree.svelte';
	import StepFour from '$lib/steps/StepFour.svelte';
	import Button from '$lib/Button.svelte';

	let step = 1;

	let title;
	let dateRead;
	let rating;
</script>

<section class="min-h-screen grid justify-center items-center grid-cols-1">
	<div>
		{#if step === 1}
			<StepOne bind:titleValue={title} bind:dateValue={dateRead} />
		{:else if step === 2}
			<StepTwo bind:ratingValue={rating} />
		{:else if step === 3}
			<StepThree />
		{:else if step === 4}
			<StepFour />
		{/if}
		<div class="flex justify-end">
			{#if step === 4}
				<Button click={() => (step -= 1)} text="Back" left={true} />
				<Button text="Log" />
			{:else if step < 4 && step > 1}
				<Button click={() => (step -= 1)} text="Back" left={true} />
				<Button click={() => (step += 1)} text="Next" />
			{:else}
				<Button click={() => (step += 1)} text="Next" />
			{/if}
		</div>
	</div>
</section>
