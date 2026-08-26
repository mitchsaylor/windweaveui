<script lang="ts">
	let {
		class: classNames,
		includedPaths,
		excludedPaths,
		showOnlyParamChange = false
	}: PageLoadIndicatorProps = $props();

	interface PageLoadIndicatorProps {
		/** Class overrides for the component */
		class?: string;
		/** Show the loading indicator only on these routes */
		includedPaths?: string[];
		/** Exclude these routes from showing the loading indicator. Only used if "includedPaths" is undefined. */
		excludedPaths?: string[];
		/** If true, the loading indicator will only be shown when the page search parameters change, not on navigation between pages. */
		showOnlyParamChange?: boolean;
	}

	import { navigating, page } from '$app/state';
	import { Tween } from 'svelte/motion';
	import { cubicOut } from 'svelte/easing';

	const progress: Tween<number> = new Tween(0, {
		duration: 400,
		easing: cubicOut
	});

	let visible: boolean = $state(false);

	$effect(() => {
		if (
			((includedPaths
				? includedPaths?.includes(page.url.pathname)
				: !excludedPaths?.includes(page.url.pathname)) &&
				(!showOnlyParamChange ||
					(navigating?.from?.url?.pathname == page.url.pathname &&
						navigating?.to?.url?.pathname == page.url.pathname))) ||
			visible
		) {
			if (navigating?.to) {
				visible = true;
				progress.set(0, { duration: 0 });
				progress.set(0.8, { duration: 3000 }).catch(() => {});
			} else if (visible) {
				progress
					.set(1, { duration: 400 })
					.then(() => {
						visible = false;
						setTimeout(() => {
							progress.set(1, { duration: 400 });
							progress.set(0, { duration: 0 });
						}, 400);
					})
					.catch(() => {});
			}
		}
	});
</script>

<div
	class="pointer-events-none fixed top-0 left-0 z-99 w-full transition-all duration-200 {visible
		? 'h-1.5'
		: 'h-0'}{classNames ? ` ${classNames}` : ''}"
>
	<div class="h-full bg-theme-600" style="width: {progress.current * 100}%"></div>
</div>
