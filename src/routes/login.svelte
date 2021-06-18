<script>
	import Button from '$lib/Button.svelte';
	import Label from '$lib/Label.svelte';
	import supabase from '$lib/db';
	import { goto } from '$app/navigation';

	let email;
	let password;

	const handleLogin = async () => {
		await supabase.auth.signIn({
			email,
			password
		});
		goto('/log');
	};
</script>

<section class="min-h-screen grid justify-center items-center grid-cols-1">
	<div class="bg-gray-700 py-24 px-4 sm:px-24 border border-gray-600 shadow-md rounded-lg">
		<div class="mx-auto w-full sm:w-3/4">
			<Label name="email" label="E-mail" />
			<input
				class="h-14 py-4 px-2 text-xl mb-8 text-gray-800 shadow-md focus:ring-indigo-500 focus:border-indigo-500 block w-full rounded-md"
				type="text"
				id="email"
				placeholder="Enter your e-mail"
				bind:value={email}
			/>
			<Label name="password" label="Password" />
			<input
				class="h-14 py-4 px-2 text-xl mb-8 text-gray-800 shadow-md focus:ring-indigo-500 focus:border-indigo-500 block w-full rounded-md"
				type="password"
				id="password"
				placeholder="Enter your password"
				bind:value={password}
			/>
			<Button click={handleLogin} text="Log In" left={false} />
		</div>
	</div>
</section>

<style>
	::placeholder {
		@apply text-gray-600;
	}
</style>
