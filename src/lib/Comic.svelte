<script>
	import Icon from 'svelte-awesome';
	import { faUserEdit, faCalendarCheck } from '@fortawesome/free-solid-svg-icons';

	export let comic;
	const ratingArray = [...Array(comic.rating).keys()];
</script>

<li>
	<div class="px-4 py-4 sm:px-6">
		<div class="flex items-center justify-between">
			<p
				class="text-md uppercase font-medium bg-gradient-to-br from-blue-400 via-indigo-500 to bg-purple-600 text-transparent bg-clip-text  truncate"
			>
				{comic.title}
			</p>
			<div class="ml-2 flex-shrink-0 flex">
				{#each ratingArray as _}
					<span class="text-sm ml-2">⭐</span>
				{/each}
			</div>
		</div>
		<p class="text-gray-400 text-sm italic">
			{comic.issue_numbers}
		</p>
		<div class="mt-2 sm:flex sm:justify-between">
			<div class="sm:flex">
				<p class="text-gray-300 mb-1">
					{comic.number_of_issues}
					{comic.number_of_issues < 2 ? 'issue' : 'issues'}
				</p>
				<p class="flex items-center text-gray-300 mb-1 sm:ml-4">
					<Icon class="mr-2" scale="1.25" data={faUserEdit} />
					{comic.writer}
				</p>
			</div>
			<div>
				<p class="flex items-center text-gray-300">
					<Icon class="mr-2" scale="1.25" data={faCalendarCheck} />
					Read On: {comic.date_read}
				</p>
			</div>
		</div>
	</div>
</li>
