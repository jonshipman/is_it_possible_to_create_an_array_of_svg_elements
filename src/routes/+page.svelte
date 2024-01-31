<script lang="ts">
	import { FacebookIcon, TwitterIcon } from '$lib/icons';
	import type { ComponentType } from 'svelte';

	type Socials = Array<[string, ComponentType]>;
	const socials: Socials = [
		['https://www.twitter.com', TwitterIcon],
		['https://www.facebooks.com', FacebookIcon]
	];
</script>

<h1 class="mb3">Icons</h1>

<div class="flex">
	<a href="https://www.twitter.com" class="pink">
		<TwitterIcon class="w3 h3" />
	</a>

	<a href="https://www.facebook.com" class="pink">
		<FacebookIcon class="w3 h3" />
	</a>
</div>

<h2 class="mb3">...or in a loop.</h2>

<div class="flex">
	{#each socials as [link, component]}
		<a href={link} class="pink">
			<svelte:component this={component} class="w3 h3" />
		</a>
	{/each}
</div>
