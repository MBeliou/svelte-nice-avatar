<script lang="ts">
	import type { EarSize } from '$lib/avatar/types.js';
	import Big from './big.svelte';
	import Small from './small.svelte';

	let { size, color }: { size: EarSize; color: string } = $props();
</script>

{#if size === 'small'}
	<Small {color} />
{:else}
	<Big {color} />
{/if}
