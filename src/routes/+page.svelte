<script>
	import { monoco } from '@monokai/monoco-svelte';
	import { Squircle } from '@monokai/monoco';

	import Heading from '$lib/components/Heading.svelte';
	import ContactInfo from '$lib/components/ContactInfo.svelte';
	import ProfilePhoto from '$lib/components/ProfilePhoto.svelte';
	import Intro from '$lib/components/Intro.svelte';
	import JobCard from '$lib/components/JobCard.svelte';
</script>

<section
	class="mx-auto grid grid-cols-3 gap-y-16 px-6 lg:grid-rows-3 lg:gap-y-52 mb-24 md:mb-40"
	id="intro"
>
	<div class="col-start-1 col-end-4 row-start-2 max-w-2xl lg:col-end-3 lg:row-start-1 lg:row-end-3">
		<Heading alt="Who am I?">whoami</Heading>
		<Intro />
	</div>

	<ProfilePhoto />
</section>

<section
	class="mx-auto space-y-6 px-6 mb-24 md:mb-40"
	id="work"
>
	<Heading alt="Work">work</Heading>

	<ul class="divide-y divide-stone-300 dark:divide-emerald-100/25">
		<JobCard
			position="WordPress Lead engineer"
			company="Infinum"
			start="Jan 2021"
		>
			Building custom block-based (Gutenberg) themes and working on the Eightshift DevKit.
		</JobCard>
		<JobCard
			position="Digital designer"
			company="Arbona"
			start="Jul 2020"
			end="Nov 2020"
		>
			I designed online advertising materials, made dynamic Google Display ads and put together great-looking
			newsletters and Viber marketing campaigns.
		</JobCard>
		<JobCard
			position="Summer internship"
			company="Ekobit"
			start="Jun 2019"
			end="Aug 2019"
		>
			I was a part of a team that worked on one of the company's products. C# and SQL were used, also I learned a lot
			about optimizing SQL queries.
		</JobCard>
	</ul>

	<details class="group">
		<summary
			class="flex w-fit cursor-pointer appearance-none items-center gap-1 rounded pr-1 outline-offset-4 outline-emerald-700/40 transition hover:text-emerald-700 focus:outline-3 dark:outline-amber-200/50 dark:hover:text-amber-200"
		>
			<iconify-icon
				class="transition-transform group-open:-scale-y-100"
				icon="pixelarticons:chevron-down"
				width="24"
				height="24"
			></iconify-icon>
			<span class="group-open:hidden">More</span>
			<span class="not-group-open:hidden">Less</span>
		</summary>

		<ul class="divide-y divide-stone-300 pt-4 dark:divide-emerald-100/25">
			<JobCard
				position="Promotional materials"
				company="Temple Bar Stubičke toplice"
				start="Mar 2016"
				end="Feb 2022"
			>
				I designed promotional material for Facebook and Instagram ads for Temple Bar in Stubičke toplice.
			</JobCard>
			<JobCard
				position="Branding and bottle label design"
				company="Aronija Juraj"
				start="Dec 2018"
				end="Dec 2018"
			>
				I designed a logo, a simple brand system and bottle labels for <i>Aronija Juraj</i>.
			</JobCard>
			<JobCard
				position="Lead designer"
				company="STEM Games"
				start="Dec 2018"
				end="May 2019"
			>
				I was the lead of a small design team; also worked on promotional materials, the event map, banners,
				accreditations, &hellip;
			</JobCard>
			<JobCard
				position="Print design, lead designer"
				company="ST@K (student magazine)"
				start="Jan 2016"
				end="Sep 2020"
			>
				<p>
					I was a part of the faculty magazine <i>St@k</i>. Started as a desginer, later lead the design team for a
					while (and still designed).
				</p>

				<p>Working in and leading a team helped me improve my teamwork and leadership skills.</p>

				<p>
					Magazine design was done in Adobe InDesign, together with Adobe Photoshop and Adobe Illustrator for supporting
					materials. Adobe Xd was used for some promotional materials.
				</p>
			</JobCard>
			<JobCard
				position="Branding"
				company="Brucošijada grada Varaždina 2018."
				start="Jan 2016"
				end="Sep 2020"
			>
				I designed a logo, all the promotional materials and accrediations for the annual student welcoming party - <i
					>Brucošijada</i
				>.
			</JobCard>
			<JobCard
				position="Student council"
				company="Faculty of organization and informatics Varaždin"
				start="Jan 2016"
				end="Sep 2020"
			>
				I was a part of the Faculty of organization and informatics' Student council, where I worked on various
				projects.
			</JobCard>
		</ul>
	</details>
</section>

<section
	class="mx-auto space-y-6 px-6 mb-24 md:mb-40"
	id="contact"
>
	<Heading alt="Contact">contact</Heading>
	<ContactInfo />
</section>
