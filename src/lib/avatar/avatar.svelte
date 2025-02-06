<script lang="ts">
	import Ear from './ear/ear.svelte';
	import Eyebrow from './eyebrow/eyebrow.svelte';
	import Face from './face/face.svelte';
	import Glasses from './glasses/glasses.svelte';
	import Hat from './hat/hat.svelte';
	import Mouth from './mouth/mouth.svelte';
	import Nose from './nose/nose.svelte';
	import Shirt from './shirt/shirt.svelte';
	import Hair from './hair/hair.svelte';
	import { genConfig } from './utils.js';
	import Eyes from './eyes/eyes.svelte';
	import type { AvatarConfig } from './types.js';

	let {
		class: className,
		id,
		shape = 'circle',
		hairColorRandom = false,
		configOrSeed
	}: {
		class?: string;
		id?: string;
		shape?: 'circle' | 'rounded' | 'square';
		hairColorRandom?: boolean;
		configOrSeed?: AvatarConfig | string;
	} = $props();

	let config = genConfig(configOrSeed || {});

	let borderRadius = (() => {
		switch (shape) {
			case 'rounded':
				return '6px';
			case 'square':
				return 0;
			case 'circle':
			default:
				return '100%';
		}
	})();
</script>

<div
	{id}
	class={className}
	style="background: {config.bgColor}; overflow: hidden; border-radius: {borderRadius};"
>
	<div style="position: relative; width: 100%; height: 100%;">
		<div style="position: absolute; bottom: 0; width: 100%; height: 90%;">
			<Face color={config.faceColor} />
			{#if config.hatStyle === 'none'}
				<Hair color={config.hairColor} style={config.hairStyle} colorRandom={hairColorRandom} />
			{:else}
				<Hat color={config.hatColor} style={config.hatStyle} />
			{/if}

			<div
				style="position: absolute; right: -3%; top:30%; width: 100%; height: 100%; display: flex; flex-direction: column; align-items:center; justify-content:center;"
			>
				<Eyebrow style={config.eyeBrowStyle} />
				<Eyes style={config.eyeStyle} />
				<Glasses style={config.glassesStyle} />
				<Ear color={config.faceColor} size={config.earSize} />
				<Nose style={config.noseStyle} />
				<Mouth style={config.mouthStyle} />
			</div>

			<Shirt color={config.shirtColor} style={config.shirtStyle} />
		</div>
	</div>
</div>
