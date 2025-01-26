<script>
	import '../app.css';
	import '@fontsource-variable/eb-garamond/wght.css';
	import '@fontsource-variable/eb-garamond/wght-italic.css';
	import '@fontsource-variable/spline-sans';
	import '@fontsource-variable/geist';
	import '@fontsource-variable/geist-mono';
	import { detectIncognito } from 'detectincognitojs';

	import { ModeWatcher, setMode, userPrefersMode, mode } from 'mode-watcher';

	import 'iconify-icon';

	mode.subscribe(async (currMode) => {
		if (!currMode) {
			return;
		}

		const faviconEl = document.querySelector('link[rel="icon"]');

		const { isPrivate } = await detectIncognito();

		if (isPrivate) {
			faviconEl.href = './favicon-incognito.svg';
		} else if (currMode === 'light') {
			faviconEl.href = './favicon.svg';
		} else {
			faviconEl.href = './favicon-dark.svg';
		}
	});

	let { children } = $props();
</script>

<header class="mx-auto mt-10 mb-20 flex w-fit -translate-x-0.5 flex-col pt-8 md:py-20 lg:translate-x-0">
	<h1 class="font-serif text-7xl font-medium tracking-tight text-emerald-700 sm:text-8xl dark:text-emerald-50">
		goran alković
	</h1>
	<p class="-mt-1 -mr-0.5 ml-auto text-sm text-amber-800/85 sm:text-base dark:text-amber-100">
		frontend developer. designer(-ish).
	</p>
</header>

{@render children?.()}

<footer class="mx-auto mt-24 flex items-center justify-between pr-6 pl-4 text-center text-sm lg:mt-40 mb-24 md:mb-40">
	<div class="flex gap-1">
		<button
			aria-label="Follow system"
			onclick={() => setMode('system')}
			class={[
				'flex rounded-full p-2 transition not-disabled:cursor-pointer focus:outline-3',
				$userPrefersMode === 'system' ?
					'text-emerald-600 dark:text-amber-200'
				:	'text-stone-500 hover:text-amber-600 focus:text-amber-600 dark:text-emerald-50 dark:hover:text-emerald-200 dark:focus:text-emerald-200',
				$userPrefersMode === 'system' ? 'focus:outline-hidden' : 'outline-amber-600/60 dark:outline-emerald-200/60 ',
			]}
		>
			<iconify-icon
				icon="pixelarticons:reload"
				width="18"
				height="18"
			></iconify-icon>
		</button>
		<button
			aria-label="Light mode"
			onclick={() => setMode('light')}
			class={[
				'flex rounded-full p-2 transition not-disabled:cursor-pointer focus:outline-3',
				$userPrefersMode === 'light' ?
					'text-emerald-600 dark:text-amber-200'
				:	'text-stone-500 hover:text-amber-600 focus:text-amber-600 dark:text-emerald-50 dark:hover:text-emerald-200 dark:focus:text-emerald-200',
				$userPrefersMode === 'light' ? 'focus:outline-hidden' : 'outline-amber-600/60 dark:outline-emerald-200/60 ',
			]}
		>
			<iconify-icon
				icon="pixelarticons:lightbulb-on"
				width="18"
				height="18"
			></iconify-icon>
		</button>
		<button
			aria-label="Dark mode"
			onclick={() => setMode('dark')}
			class={[
				'flex rounded-full p-2 transition not-disabled:cursor-pointer focus:outline-3',
				$userPrefersMode === 'dark' ?
					'text-emerald-600 dark:text-amber-200'
				:	'text-stone-500 hover:text-amber-600 focus:text-amber-600 dark:text-emerald-50 dark:hover:text-emerald-200 dark:focus:text-emerald-200',
				$userPrefersMode === 'dark' ? 'focus:outline-hidden' : 'outline-amber-600/60 dark:outline-emerald-200/60 ',
			]}
		>
			<iconify-icon
				icon="pixelarticons:lightbulb"
				width="18"
				height="18"
			></iconify-icon>
		</button>
	</div>

	<p class="text-stone-400 dark:text-emerald-100/80">&copy; Goran Alković, 2025</p>
</footer>

<ModeWatcher />
