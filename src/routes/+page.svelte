<script lang="ts">
	import LoadingRing from '#lib/loadingRing.svelte';

	let darkMode: boolean = $state(false);
	const toggleDarkMode = () => {
		darkMode = !darkMode;
	};

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
	const colorSpaces: string[] = [
		'bg-white',
		'bg-theme-50',
		'bg-theme-100',
		'bg-theme-200',
		'bg-theme-300',
		'bg-theme-400',
		'bg-theme-500',
		'bg-theme-600',
		'bg-theme-700',
		'bg-theme-800',
		'bg-theme-900',
		'bg-theme-950',
		'bg-black'
	];
</script>

<main class={darkMode ? ' dark' : ''}>
	<div class="dark:bg-theme-950 dark:text-theme-100">
		<div class="page-w-lg py-8 dark:bg-black">
			<p class="mb-4 text-4xl">page-w-lg</p>
			<button
				type="button"
				onclick={toggleDarkMode}
				class="touch round border-theme-500 bg-theme-500 text-sm text-white ring-theme-500 dark:border-theme-400 dark:bg-theme-400 dark:ring-theme-400"
			>
				Toggle dark mode
			</button>
		</div>
		<div class="page-w pad-xl bg-theme-50 py-10 dark:bg-theme-950">
			<p class="mb-4 text-4xl">page-w</p>
			<div class="-mx-2 flex grid-cols-3 flex-col items-start gap-4 sm:grid">
				<div
					class="round-outer-sm border border-black/15 p-1 dark:border-theme-900 dark:bg-theme-900"
				>
					<div class="round justify-between bg-white p-1 shadow dark:bg-theme-800">
						<div class="round-inner-sm border border-black/15 p-5 dark:border-black/50">
							<p>round, round-inner-sm, round-outer-sm</p>
						</div>
					</div>
				</div>
				<div class="round-outer border border-black/15 p-2 dark:border-theme-900 dark:bg-theme-900">
					<div class="round justify-between bg-white p-2 shadow dark:bg-theme-800">
						<div class="round-inner border border-black/15 p-5 dark:border-black/50">
							<p>round, round-inner, round-outer</p>
						</div>
					</div>
				</div>
				<div
					class="round-outer-lg border border-black/15 p-3 dark:border-theme-900 dark:bg-theme-900"
				>
					<div class="round justify-between bg-white p-3 shadow dark:bg-theme-800">
						<div class="round-inner-lg border border-black/15 p-5 dark:border-black/50">
							<p>round, round-inner-lg, round-outer-lg</p>
						</div>
					</div>
				</div>
			</div>
		</div>
		<div class="page-w-sm my-8">
			<p class="mb-2">page-w-sm</p>
			<ul class="flex flex-wrap items-start gap-1">
				<li>
					<button
						type="button"
						class="round touch border-theme-500 bg-theme-500 text-white dark:border-theme-400 dark:bg-theme-400"
					>
						<p>touch</p>
					</button>
				</li>
				<li>
					<button type="button" class="round touch border border-theme-500">
						<p>touch</p>
					</button>
				</li>
				<li>
					<input type="text" class="round input" placeholder="Input" />
				</li>
			</ul>
		</div>
		<div class="page-w-xs my-7">
			<p class="mb-2 text-lg font-medium">page-w-xs</p>
			<p>
				Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
				labore et dolore magna aliqua.
			</p>
			<div class="mt-2 flex">
				<LoadingRing class="size-6 text-theme-500 dark:text-theme-400" />
			</div>
			<div class="mt-6 flex gap-4">
				<div class="round pod-sm bg-error-100 dark:bg-error-900">
					<p class="text-error-500 dark:text-error-400">⚠ Error text</p>
				</div>
				<div class="round pod-sm bg-success-100 dark:bg-success-900">
					<p class="text-success-500 dark:text-success-400">✓ Success text</p>
				</div>
			</div>
		</div>
		<div class="page-w-xs bg-theme-50 py-7 dark:bg-theme-900">
			<p class="mb-2 font-medium">page-w-xs</p>
			<p class="air-sm mb-2 text-sm">
				Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
				labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
				laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in
				voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat
				cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
			</p>
			<p class="air-base mb-2 text-sm">
				Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
				labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
				laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in
				voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat
				cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
			</p>
			<p class="air-lg mb-2 text-sm">
				Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
				labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
				laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in
				voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat
				cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
			</p>
		</div>
		<div class="page-w my-10">
			<h1 class="text-4xl font-bold">WindWeave UI</h1>
			<p>
				Create your package using @sveltejs/package and preview/showcase your work with SvelteKit
			</p>
			<p>
				Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation
			</p>
			<p class="mt-8 mb-4">Theme color scale</p>
			<div class="-mx-2 flex flex-wrap items-start gap-6">
				<div
					class="round grid grid-cols-13 overflow-hidden border border-theme-100 dark:border-theme-800"
				>
					{#each colorSpaces as color (color)}
						<div class="{color} size-10"></div>
					{/each}
				</div>
				<div class="round-outer bg-theme-100 p-2 pt-5 pr-10">
					<div class="round bg-theme-50 p-2 pt-5 pr-10 shadow-xs">
						<div
							class="round-inner flex items-center gap-4 bg-white p-4 px-8 text-theme-950 shadow-xs"
						>
							<p>Light</p>
							<button
								class="touch round w-20 border-theme-500 bg-theme-500 text-xs text-white ring-theme-500"
							>
								Button
							</button>
						</div>
					</div>
				</div>
				<div class="round-outer border border-theme-800 bg-theme-950 p-2 pt-5 pr-10">
					<div class="round bg-theme-900 p-2 pt-5 pr-10 shadow-xs">
						<div
							class="round-inner flex items-center gap-4 bg-theme-800 p-4 px-6 text-white shadow-xs"
						>
							<p class="">Dark</p>
							<button class="touch round w-20 border-theme-400 bg-theme-400 text-xs ring-theme-400">
								Button
							</button>
						</div>
					</div>
				</div>
			</div>
		</div>
		<div class="page-w bg-theme-50 py-10 dark:bg-theme-900">
			{#each textSizes as size (size)}
				<p class={size}>
					<span>{size}</span>
					<span> - Lorem ipsum dolor sit amet, consectetur adipiscing elit</span>
				</p>
			{/each}
		</div>
	</div>
</main>
