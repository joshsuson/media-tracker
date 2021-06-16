<script>
	import StepOne from '$lib/steps/StepOne.svelte';
	import StepTwo from '$lib/steps/StepTwo.svelte';
	import StepThree from '$lib/steps/StepThree.svelte';
	import StepFour from '$lib/steps/StepFour.svelte';

	let step = 1;

	let title;

	$: {
		console.log(title);
	}
</script>

<section>
	{#if step === 1}
		<StepOne bind:value={title} />
	{:else if step === 2}
		<StepTwo />
	{:else if step === 3}
		<StepThree />
	{:else if step === 4}
		<StepFour />
	{/if}

	{#if step === 4}
		<button on:click={() => (step -= 1)}>Back</button>
		<button>Log</button>
	{:else if step < 4 && step > 1}
		<button on:click={() => (step -= 1)}>Back</button>
		<button on:click={() => (step += 1)}>Next</button>
	{:else}
		<button on:click={() => (step += 1)}>Next</button>
	{/if}
</section>
