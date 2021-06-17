<script>
	import Label from '$lib/Label.svelte';

	export let typeValue;
	export let issueNumbersValue;
	export let numberOfIssuesValue;

	const checkedBorder =
		'border-indigo-500 absolute -inset-px rounded-lg border-2 pointer-events-none';
	const notCheckedBorder =
		'border-transparent absolute -inset-px rounded-lg border-2 pointer-events-none';

	const checkedBackground =
		'relative block rounded-lg border border-gray-300 bg-indigo-300 shadow-sm px-6 py-4 cursor-pointer hover:border-gray-400 sm:flex sm:justify-between focus:ring-1 focus:ring-offset-2 focus:ring-indigo-500';
	const notCheckedBackground =
		'relative block rounded-lg border border-gray-300 bg-gray-300 shadow-sm px-6 py-4 cursor-pointer hover:border-gray-400 sm:flex sm:justify-between focus:ring-1 focus:ring-offset-2 focus:ring-indigo-500';
</script>

<Label name="type" label="Type" />
<div class="flex items-center justify-between">
	<div class="w-80">
		<label class={typeValue === 'Collected Volume' ? checkedBackground : notCheckedBackground}>
			<input
				bind:group={typeValue}
				type="radio"
				name="type"
				class="sr-only"
				aria-labelledby="collectedVolume"
				value="Collected Volume"
			/>
			<p id="collectedVolume" class="font-medium text-gray-900">Collected Volume</p>
			<div
				class={typeValue === 'Collected Volume' ? checkedBorder : notCheckedBorder}
				aria-hidden="true"
			/>
		</label>
	</div>
	<div class="w-80">
		<label class={typeValue === 'Single Issue' ? checkedBackground : notCheckedBackground}>
			<input
				bind:group={typeValue}
				type="radio"
				name="type"
				class="sr-only"
				aria-labelledby="singleIssue"
				value="Single Issue"
			/>
			<p id="singleIssue" class="font-medium text-gray-900">Single Issue</p>
			<div
				class={typeValue === 'Single Issue' ? checkedBorder : notCheckedBorder}
				aria-hidden="true"
			/>
		</label>
	</div>
</div>
<div class="mt-12">
	<Label name="issueNumbers" label="Issue Numbers" />
	<input
		type="text"
		name="issueNumbers"
		id="issueNumbers"
		class="h-14 py-4 px-2 text-xl mb-8 text-gray-800 shadow-md focus:ring-indigo-500 focus:border-indigo-500 block w-full rounded-md"
		placeholder="What are the issue numbers you read?"
		bind:value={issueNumbersValue}
	/>
	<Label name="numberOfIssues" label="Number of Issues" />
	<input
		type="number"
		name="numberOfIssues"
		id="numberOfIssues"
		class="h-14 py-4 px-2 text-xl mb-8 text-gray-800 shadow-md focus:ring-indigo-500 focus:border-indigo-500 block w-full rounded-md"
		placeholder="What are the issue numbers you read?"
		bind:value={numberOfIssuesValue}
	/>
</div>
