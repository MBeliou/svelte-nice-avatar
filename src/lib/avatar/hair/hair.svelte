<script lang="ts">
	import Normal from './normal.svelte';
	import Thick from './thick.svelte';
	import Mohawk from './mohawk.svelte';
	import WomanLong from './womanLong.svelte';
	import WomanShort from './womanShort.svelte';

	let {
		style,
		color,
		colorRandom
	}: {
		style: 'thick' | 'mohawk' | 'womanLong' | 'womanShort' | 'normal';
		color: string;
		colorRandom: boolean;
	} = $props();

	let Component = (() => {
		switch (style) {
			case 'thick':
				return <Thick color={color} colorRandom={colorRandom} />;
			case 'mohawk':
				return <Mohawk color={color} colorRandom={colorRandom} />;
			case 'womanLong':
				return <WomanLong color={color} />;
			case 'womanShort':
				return <WomanShort color={color} />;
			case 'normal':
			default:
				return <Normal color={color} />;
		}
	})();
</script>

<Component></Component>
