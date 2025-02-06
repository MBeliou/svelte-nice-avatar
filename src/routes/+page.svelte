<script lang="ts">
	import { Avatar } from '$lib/index.js';

	const links = [
		{
			label: 'Github',
			href: 'https://github.com/MBeliou/svelte-nice-avatar'
		}
	];
</script>

<div class="flex min-h-svh flex-col">
	<div class="flex flex-1 flex-col items-center justify-center">
		<Avatar class="aspect-square w-[300px]"></Avatar>
	</div>

	<div class="h-[120px]">
		<div class="flex items-center justify-center font-medium">
			{#each links as link}
				<a href={link.href} class="text-stone-400 hover:text-stone-200">{link.label}</a>
			{/each}
		</div>
	</div>
</div>
