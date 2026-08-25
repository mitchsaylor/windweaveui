<script lang="ts">
	let { children, size = 'md' }: { children?: Snippet; size?: 'sm' | 'md' | 'lg' } = $props();

	// Types
	import type { Snippet } from 'svelte';
</script>

<div class="px-[3%] py-8">
	{#if children}
		{@render children()}
	{/if}
</div>
