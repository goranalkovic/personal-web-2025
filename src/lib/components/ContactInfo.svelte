<script>
	const contactInfo = [
		{ icon: 'pixelarticons:mail', label: 'E-mail', url: 'mailto:contact@goranalkovic.com', type: 'email' },
		{
			icon: 'pixelarticons:deskphone',
			label: 'Phone',
			text: '+385 976 480 800',
			url: 'tel:+385976480800',
			type: 'generic',
		},
		{
			icon: 'pixelarticons:github',
			label: 'GitHub',
			text: '@goranalkovic',
			url: 'https://github.com/goranalkovic',
			type: 'generic',
		},
	];
</script>

<ul class="space-y-4">
	{#each contactInfo as { icon, label, text, url, type, ariaLabel }}
		<li class="w-fit">
			<a
				class="flex w-fit gap-4 rounded-md outline-offset-8 outline-emerald-700/40 transition hover:text-emerald-700 focus:outline-4 dark:outline-amber-200/50 dark:hover:text-amber-200 hover:[&_p]:text-emerald-600 dark:hover:[&_p]:text-amber-100"
				href={url}
				target="_blank"
			>
				<iconify-icon
					{icon}
					width="24"
					height="24"
					class="mt-0.5 text-emerald-600 transition dark:text-amber-200"
				></iconify-icon>

				<div>
					<span class="font-serif text-xl font-medium transition">{label}</span>

					<p class="text-base opacity-75 transition dark:opacity-80">
						{#if type === 'email'}
							contact<span
								class="ml-1 opacity-40 dark:opacity-55"
								aria-hidden="true">(</span
							>at<span
								class="mr-1 opacity-40 dark:opacity-55"
								aria-hidden="true">)</span
							>goranalkovic.com
						{:else}
							{text}
						{/if}
					</p>
				</div>
			</a>
		</li>
	{/each}
</ul>
