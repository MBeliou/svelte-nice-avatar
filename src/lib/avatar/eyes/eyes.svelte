<script lang="ts">
	import type { EyeStyle } from '../types.js';
	import Circle from './circle.svelte';
	import Oval from './oval.svelte';
	import Smile from './smile.svelte';

	let { style }: { style: EyeStyle } = $props();
</script>

{#if style === 'circle'}
	<Circle></Circle>
{:else if style === 'oval'}
	<Oval></Oval>
{:else}
	<Smile></Smile>
{/if}
