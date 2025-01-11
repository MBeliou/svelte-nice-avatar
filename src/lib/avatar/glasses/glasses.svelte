<script lang="ts">
	import Round from './round.svelte';
	import Square from './square.svelte';

	let { style }: { style: 'round' | 'square' | 'none' } = $props();
</script>

{#if style === 'round'}
	<Round></Round>
{:else if style === 'square'}
	<Square></Square>
{/if}
