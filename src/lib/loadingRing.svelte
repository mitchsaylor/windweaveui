<script lang="ts">
	let { class: classNames }: { class?: string } = $props();
</script>

<span class="sr-only">Loading</span>
<svg
	class="loading-ring inline{classNames ? ` ${classNames}` : ' size-5'}"
	viewBox="25 25 50 50"
	stroke-width="5"
	stroke="currentColor"
>
	<circle cx="50" cy="50" r="20" />
</svg>
