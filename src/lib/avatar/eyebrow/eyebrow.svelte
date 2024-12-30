<script lang="ts">
	import type { EyeBrowStyle } from '../types.js';
	import Up from './up.svelte';
	import UpWoman from './upWoman.svelte';

	let { style }: { style: EyeBrowStyle } = $props();
</script>

{#if style === 'up'}
	<Up></Up>
{:else}
	<UpWoman></UpWoman>
{/if}
