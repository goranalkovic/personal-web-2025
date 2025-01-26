<script>
	let { children, alt, ...rest } = $props();
</script>

{#if children}
	<h2 class="mb-6 font-mono text-3xl tracking-tight text-emerald-700 md:text-4xl dark:text-amber-200">
		<span
			class="opacity-35 dark:opacity-50"
			aria-hidden="true"
		>
			&gt;
		</span>

		<span class="sr-only">
			{alt}
		</span>

		<span aria-hidden="true">
			{@render children()}
		</span>
	</h2>
{/if}
