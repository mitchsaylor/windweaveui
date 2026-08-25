<script lang="ts">
	import Container from '#lib/container.svelte';

	const textSizes: string[] = [
		'text-3xs',
		'text-2xs',
		'text-xs',
		'text-sm',
		'text-md',
		'text-base',
		'text-lg',
		'text-xl',
		'text-2xl',
		'text-3xl',
		'text-4xl',
		'text-5xl',
		'text-6xl',
		'text-7xl'
	];
</script>

<Container>
	<h1 class="text-4xl font-bold">WindWeave UI</h1>
	<p>Create your package using @sveltejs/package and preview/showcase your work with SvelteKit</p>
	<p>
		Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation
	</p>
</Container>
<Container>
	{#each textSizes as size (size)}
		<p class={size}>{size}</p>
	{/each}
</Container>
