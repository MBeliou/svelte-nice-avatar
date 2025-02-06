<script lang="ts">
	import Long from './long.svelte';
	import Round from './round.svelte';
	import Short from './short.svelte';

	let { style }: { style: 'long' | 'short' | 'round' } = $props();
</script>

{#if style === 'long'}
	<Long></Long>
{:else if style === 'round'}
	<Round></Round>
{:else}
	<Short></Short>
{/if}
