<script lang="ts">
	import chroma from 'chroma-js';
	import Short from './short.svelte';
	import Polo from './polo.svelte';
	import Hoody from './hoody.svelte';

	let { style, color }: { style: 'hoody' | 'polo' | 'short'; color: string } = $props();

	const secondColor = chroma(color).brighten(1).hex();
</script>

{#if style === 'hoody'}
	<Hoody {color} lightColor={secondColor}></Hoody>
{:else if style === 'polo'}
	<Polo {color} lightColor={secondColor}></Polo>
{:else}
	<Short {color}></Short>
{/if}
