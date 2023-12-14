<script>
	import { page } from '$app/stores';
	const blogSlug = $page.params.blogSlug;

	let blogObj = {
		id: 1,
		blogTitle: 'Introduction to JavaScript Basics',
		blogSlug: 'javascript-basics',
		blogSummary: 'A beginner-friendly guide to JavaScript fundamentals.',
		blogContents:
			"<p>Welcome to our gardening haven, where concrete jungles meet lush greens! In this comprehensive guide, we'll delve into the world of urban gardening, uncovering the secrets and joys of cultivating your own green oasis in the heart of the city. Whether you're a novice or a seasoned gardener, this blog aims to inspire and equip you with the knowledge and tools to turn your living space into a thriving botanical haven.</p><h2>Chapter 1: Embracing the Green Revolution</h2><p>In this chapter, we'll explore the growing trend of urban gardening and its positive impact on both the environment and mental well-being. From rooftop gardens to community plots, discover how urban dwellers are reclaiming their connection to nature and fostering a sense of community through shared green spaces.</p><h2>Conclusion:</h2><p>As we conclude our journey through the hidden gems of urban gardening, we hope you're inspired to embark on your own green adventure. Urban gardening is not just about cultivating plants; it's a transformative experience that reconnects us with nature and fosters a sense of community in the heart of the city. So, roll up your sleeves, grab your gardening tools, and let's make our urban spaces bloom with life!</p>",
		gitHubURL: 'https://github.com/user/repo',
		youtubeURL: 'https://www.youtube.com/watch?v=12345',
		difficulty: 'Beginner',
		skills: ['JavaScript, Vue'],
		publishedDate: '2023-01-15',
		nextUpdateDate: '2023-02-01',
		comments: [
			{
				userId: 101,
				commentedDate: '2023-01-16',
				comments: 'Great explanation for beginners!'
			},
			{
				userId: 205,
				commentedDate: '2023-01-18',
				comments: 'I learned a lot from this post. Thank you!'
			}
		]
	};
</script>

<h1>Slug Page</h1>
{blogSlug}

<div class="grid grid-cols-6 gap-4">
	<div class="col-span-4 bg-gray-600 card ">
		<div class="card-body">
			<h1 class="text-2xl">
				{blogObj.blogTitle}
			</h1>
			{#if blogObj.blogSummary}
				<h2>サマリー</h2>
				<h3>
					{blogObj.blogSummary}
				</h3>
			{/if}
			<div>
				{@html blogObj.blogContents}
			</div>
		</div>
	</div>
	<div class="col-span-2 card bg-gray-500">
		<ul class="">
			<li>this is good</li>
			<li>this is good</li>
			<li>this is good</li>
			<li>this is good</li>
			<li>this is good</li>
		</ul>
	</div>
</div>
