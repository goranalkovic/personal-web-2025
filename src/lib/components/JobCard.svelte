<script>
	let { position, start, end = null, company, children, class: className, ...rest } = $props();
</script>

<li class={['max-w-xl py-4 first:pt-0 last:pb-0', className]}>
	<p class="col-span-2 text-xl font-medium dark:text-emerald-200">{position}</p>
	{#if children}
		<div class="col-span-2 mt-0.5 space-y-2 text-base text-balance text-stone-600 dark:text-white/90">
			{@render children()}
		</div>
	{/if}
	<p class="mt-1.5 font-serif text-lg font-[450] text-stone-600 dark:text-white/85">
		{company}
		<span
			class="font-bold text-stone-400 dark:text-emerald-100"
			aria-hidden="true"
		>
			&nbsp; &middot; &nbsp;
		</span>

		{#if end && end === start}
			{start}
		{:else if end}
			{start} &hairsp; &ndash; &hairsp; {end}
		{:else}
			<span aria-hidden="true">{start} &hairsp; &ndash;</span>
			<span class="sr-only">Current, since {start}</span>
		{/if}
	</p>
</li>
