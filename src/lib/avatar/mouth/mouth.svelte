<script lang="ts">
	import Laugh from './laugh.svelte';
	import Peace from './peace.svelte';
	import Smile from './smile.svelte';

	let { style }: { style: 'laugh' | 'smile' | 'peace' } = $props();
</script>

{#if style === 'laugh'}
	<Laugh></Laugh>
{:else if style === 'smile'}
	<Smile></Smile>
{:else}
	<Peace></Peace>
{/if}
