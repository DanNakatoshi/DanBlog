<script>
	import { goto } from '$app/navigation';

	import Icon from '@iconify/svelte';
	export let {
		blogTitle,
		blogSummary,
		gitHubURL,
		youtubeURL,
		difficulty,
		skills,
		publishedDate,
		comments,
		isBookmark,
		blogSlug
	} = {};

	// Bookmark
	function toggleBookmark() {
		isBookmark = !isBookmark;
	}

	const hasComments = () => {
		return comments && comments.length > 0;
	};

	function goToBlog() {
		if (blogSlug) {
			goto(`blog/${blogSlug}`);
		}
	}

	// Class Config
	const getSkillIcons = () => {
		const skillIcons = {
			// FRONTEND + JS
			JavaScript: 'skill-icons:javascript',
			TypeScript: 'skill-icons:typescript',
			HTML: 'skill-icons:html',
			CSS: 'skill-icons:css',
			Svelte: 'skill-icons:svelte',
			Vue: 'skill-icons:vuejs-light',
			React: 'skill-icons:react-dark',
			Nodejs: 'skill-icons:nodejs-dark',
			// BACKEND + PYTHON
			Python: 'skill-icons:python-dark',
			Django: 'skill-icons:django',
			Linux: 'skill-icons:linux-dark',
			Nginx: 'skill-icons:nginx',
			// Blog
			Blog: 'solar:file-smile-outline'
		};
		return skills
			? skills.map((skill) => ({ icon: skillIcons[skill], name: skill })).filter(Boolean)
			: [];
	};

	const cardBgColor = {
		easy: 'bg-emerald-400',
		beginner: 'bg-cyan-400',
		intermediate: 'bg-indigo-400',
		advanced: 'bg-violet-400',
		expert: 'bg-amber-400',
		all: 'bg-cool-green-400'
	};

	function checkBgColor() {
		return cardBgColor[difficulty.toLowerCase()] || 'bg-cool-green-400';
	}

	const iconClass = 'h-6 w-6 lg:h-7 lg:w-7 hover:scale-110';
</script>

<div
	class="
	hover:scale-105
	hover:bg-gray-600
	hover:shadow-cyan-500/80
	hover:shadow-xl
	transition
	ease-in-out
	shadow-lg
	bg-gray-700
	card
	card-bordered
	card-compact
	mb-6
	md:mb-7
	lg:mb-8
	shadow-cyan-500/30
	break-inside-avoid-column"
>
	<div class="group card-body">
		<div class=" card-actions justify-between">
			<div class="flex">
				<!-- ICONS -->
				{#if skills}
					{#each getSkillIcons() as { icon, name }, index (index)}
						<span class="mr-3 tooltip" data-tip={name}>
							<Icon class={iconClass} {icon} />
						</span>
					{/each}
				{/if}

				{#if gitHubURL}
					<span class="mr-3 tooltip" data-tip="Open Source">
						<Icon class={iconClass} icon="skill-icons:github-dark" />
					</span>
				{/if}

				{#if youtubeURL}
					<span class="mr-3 tooltip" data-tip="YouTube">
						<Icon class={iconClass} icon="line-md:youtube-filled" color="red" />
					</span>
				{/if}
			</div>
			<!-- BOOKMARK -->
			<button class=" btn btn-ghost btn-sm btn-square" on:click={toggleBookmark}>
				<Icon
					class={iconClass}
					icon={isBookmark ? 'fluent:bookmark-20-filled' : 'fluent:bookmark-20-regular'}
					color="#facc15"
				/>
			</button>
		</div>

		<h2 class=" card-title text-gray-200 mt-2">{blogTitle}</h2>
		<p class="text-gray-300">
			{blogSummary}
		</p>

		<!-- SUB INFO -->
		<div class="card-actions justify-between items-end">
			<div class="flex justify-start items-center">
				{#if publishedDate}
					<p class="text-gray-300 mr-3">{publishedDate}</p>
				{/if}

				{#if hasComments()}
					<div class="indicator text-gray-300 mr-4">
						<Icon class="h-4 w-4 " icon="mdi:comment-outline" />
						<span class="badge badge-xs badge-primary indicator-item"></span>
					</div>
				{/if}

				{#if difficulty}
					<div class="badge {checkBgColor()} text-stone-800 mr-3">{difficulty}</div>
				{/if}
			</div>
			<button on:click={goToBlog} class="group-hover:-rotate-6 group-hover:scale-125 	 ease-in-out btn btn-secondary btn-sm"
				>読む</button
			>
		</div>
	</div>
</div>
