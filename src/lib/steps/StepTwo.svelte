<script>
	import Label from '$lib/Label.svelte';

	export let ratingValue = 1;

	let stars = [1];

	$: {
		stars = [...Array(ratingValue).keys()];
	}
</script>

<Label name="rating" label="Rating" />
<div class="text-center mt-8 pb-8">
	{#each stars as _}
		<span class="text-5xl">⭐</span>
	{/each}
</div>
<div class="m-8">
	<input type="range" min="1" max="5" name="rating" id="rating" bind:value={ratingValue} />
</div>

<style>
	input[type='range'] {
		-webkit-appearance: none;
		width: 100%;
		background: transparent;
	}

	input[type='range']::-webkit-slider-thumb {
		-webkit-appearance: none;
		/* border: 1px solid red; */
		height: 36px;
		width: 26px;
		border-radius: 3px;
		background: linear-gradient(
			90deg,
			#5fa5fa,
			#539afd,
			#4d8eff,
			#4d81ff,
			#5473fe,
			#5f64fb,
			#6d52f5,
			#7c3aed
		);
		cursor: pointer;
		margin-top: -14px;
	}

	input[type='range']:focus {
		outline: none;
	}

	input[type='range']::-ms-track {
		width: 100%;
		cursor: pointer;
		background: transparent;
		border-color: transparent;
		color: transparent;
	}

	input[type='range']::-moz-range-thumb {
		box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d;
		/* border: 1px solid #000000; */
		height: 36px;
		width: 16px;
		border-radius: 3px;
		background: linear-gradient(
			90deg,
			#5fa5fa,
			#539afd,
			#4d8eff,
			#4d81ff,
			#5473fe,
			#5f64fb,
			#6d52f5,
			#7c3aed
		);
		cursor: pointer;
	}

	input[type='range']::-ms-thumb {
		box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d;
		border: 1px solid #000000;
		height: 36px;
		width: 16px;
		border-radius: 3px;
		background: linear-gradient(
			90deg,
			#5fa5fa,
			#539afd,
			#4d8eff,
			#4d81ff,
			#5473fe,
			#5f64fb,
			#6d52f5,
			#7c3aed
		);
		cursor: pointer;
	}

	input[type='range']::-webkit-slider-runnable-track {
		width: 100%;
		height: 8.4px;
		cursor: pointer;
		box-shadow: 0 8px 40px #000000;
		background: #d1d5db;
		border-radius: 1.3px;
		border: 0.2px solid #010101;
	}

	input[type='range']:focus::-webkit-slider-runnable-track {
		/* background: #367ebd; */
		border: 1px solid #7c3aed;
	}

	input[type='range']::-moz-range-track {
		width: 100%;
		height: 8.4px;
		cursor: pointer;
		box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d;
		background: #3071a9;
		border-radius: 1.3px;
		border: 0.2px solid #010101;
	}

	input[type='range']::-ms-track {
		width: 100%;
		height: 8.4px;
		cursor: pointer;
		background: transparent;
		border-color: transparent;
		border-width: 16px 0;
		color: transparent;
	}
	input[type='range']::-ms-fill-lower {
		background: #2a6495;
		border: 0.2px solid #010101;
		border-radius: 2.6px;
		box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d;
	}
	input[type='range']:focus::-ms-fill-lower {
		background: #3071a9;
	}
	input[type='range']::-ms-fill-upper {
		background: #3071a9;
		border: 0.2px solid #010101;
		border-radius: 2.6px;
		box-shadow: 1px 1px 1px #000000, 0px 0px 1px #0d0d0d;
	}
	input[type='range']:focus::-ms-fill-upper {
		background: #367ebd;
	}
</style>
