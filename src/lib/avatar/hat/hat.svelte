<script lang="ts">
	import Turban from './turban.svelte';
	import Beanie from './beanie.svelte';
	let { style, color }: { style: 'beanie' | 'turban' | 'none'; color: string } = $props();
</script>

{#if style == 'beanie'}
	<Beanie {color} />
{:else if style == 'turban'}
	<Turban {color} />
{/if}
