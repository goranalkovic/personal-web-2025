<script>
	import { mode } from 'mode-watcher';
</script>

<div
	class="pointer-events-none isolate col-start-1 col-end-[span_3] row-start-1 mx-auto grid w-fit grid-cols-1 grid-rows-1 select-none sm:m-0 lg:col-start-2 lg:col-end-[span_2] lg:row-start-2 lg:row-end-4 lg:justify-self-end"
>
	<div
		class="z-10 col-start-1 col-end-1 row-start-1 row-end-1 translate-x-6 translate-y-4 scale-95 rotate-6 self-center justify-self-center mix-blend-multiply blur-xs"
	>
		<div class="mask mask-squircle size-64 bg-black/30 sm:size-80 md:size-96 dark:bg-emerald-950"></div>
	</div>

	{#if $mode === 'light'}
		<img
			class="mask mask-squircle z-20 col-start-1 col-end-1 row-start-1 row-end-1 size-64 rotate-6 self-center justify-self-center not-dark:brightness-115 sm:size-80 md:size-96"
			src="/img/profile-pic.webp"
			alt="Goran Alković"
		/>
	{:else}
		<img
			class="mask mask-squircle z-20 col-start-1 col-end-1 row-start-1 row-end-1 size-64 rotate-6 self-center justify-self-center not-dark:brightness-115 sm:size-80 md:size-96"
			src="/img/profile-pic-dark.webp"
			alt="Goran Alković"
		/>
	{/if}
</div>
