<script>
	// import { goto } from '$app/navigation';

	import Announcement from '$lib/card/Announcement.svelte';
	import BlogTile from '$lib/card/BlogTile.svelte';
	let blogList = [
		{
			id: 1,
			blogTitle: 'Introduction to JavaScript Basics',
			blogSlug: 'javascript-basics',
			blogSummary: 'A beginner-friendly guide to JavaScript fundamentals.',
			blogContents: 'In this blog post, we cover the basics of JavaScript...',
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
		},
		{
			id: 2,
			blogTitle: 'Python Crash Course',
			blogSlug: 'python-crash-course',
			blogSummary: 'A quick dive into Python programming for beginners.',
			blogContents: 'Explore the fundamentals of Python programming...',
			gitHubURL: 'https://github.com/user/python-repo',
			youtubeURL: 'https://www.youtube.com/watch?v=67890',
			difficulty: 'Beginner',
			skills: ['Svelte, React'],
			publishedDate: '2023-02-10',
			nextUpdateDate: '2023-03-01',
			comments: [
				{
					userId: 301,
					commentedDate: '2023-02-12',
					comments: 'Python is my favorite language! Nice tutorial.'
				},
				{
					userId: 402,
					commentedDate: '2023-02-15',
					comments: 'I appreciate the clear explanations. Good job!'
				}
			]
		},
		{
			id: 3,
			blogTitle: 'Getting Started with React',
			blogSlug: 'react-getting-started',
			blogSummary: 'An introduction to building web applications with React.',
			blogContents: 'Learn the basics of React and how to create components...',
			gitHubURL: 'https://github.com/user/react-repo',
			youtubeURL: 'https://www.youtube.com/watch?v=56789',
			difficulty: 'Intermediate',
			skills: ['Linux', 'Django'],
			publishedDate: '2023-03-05',
			nextUpdateDate: '2023-04-01',
			comments: [
				{
					userId: 503,
					commentedDate: '2023-03-08',
					comments: "React is awesome! Can't wait for the next part."
				},
				{
					userId: 606,
					commentedDate: '2023-03-10',
					comments: 'Clear and concise tutorial. Thanks!'
				}
			]
		},
		{
			id: 4,
			blogTitle: 'Dive into Node.js',
			blogSlug: 'nodejs-dive',
			blogSummary: 'Explore server-side JavaScript with Node.js.',
			blogContents: 'Learn how to build scalable and efficient server applications...',
			gitHubURL: 'https://github.com/user/nodejs-repo',
			youtubeURL: 'https://www.youtube.com/watch?v=34567',
			difficulty: 'Intermediate',
			skills: ['Nginx', 'HTML', 'CSS'],
			publishedDate: '2023-04-12',
			nextUpdateDate: '2023-05-01',
			comments: []
		},
		{
			id: 5,
			blogTitle: 'Vue.js Essentials',
			blogSlug: 'vuejs-essentials',
			blogSummary:
				'Learn the fundamentals of Vue.js for building interactive web apps.Learn the fundamentals of Vue.js for building interactive web apps.',
			blogContents: 'Explore Vue.js components, directives, and state management...',
			gitHubURL: 'https://github.com/user/vuejs-repo',
			youtubeURL: 'https://www.youtube.com/watch?v=45678',
			difficulty: 'Intermediate',
			skills: ['JavaScript', 'Vue'],
			publishedDate: '2023-05-20',
			nextUpdateDate: '2023-06-01',
			comments: [
				{
					userId: 901,
					commentedDate: '2023-05-22',
					comments: 'Vue.js makes frontend development so enjoyable!'
				},
				{
					userId: 1002,
					commentedDate: '2023-05-25',
					comments: 'Thanks for the detailed explanation. Thumbs up!'
				}
			]
		},
		{
			id: 6,
			blogTitle: 'RESTful API Design Best Practices',
			blogSlug: 'restful-api-design',
			blogSummary: 'Guidelines for designing scalable and maintainable RESTful APIs.',
			blogContents: 'Learn about resource naming, HTTP methods, and authentication...',
			gitHubURL: 'https://github.com/user/restful-api-repo',
			youtubeURL: 'https://www.youtube.com/watch?v=56789',
			difficulty: 'Advanced',
			skills: ['Django, Linux'],
			publishedDate: '2023-06-10',
			nextUpdateDate: '2023-07-01',
			comments: [
				{
					userId: 1103,
					commentedDate: '2023-06-12',
					comments: 'Invaluable information for API developers!'
				},
				{
					userId: 1204,
					commentedDate: '2023-06-15',
					comments: 'This post is a goldmine. Great work!'
				}
			]
		},
		{
			id: 7,
			blogTitle: 'Advanced TypeScript Concepts',
			blogSlug: 'typescript-advanced',
			blogSummary: 'Master advanced TypeScript features for building robust applications.',
			blogContents: 'Explore type inference, conditional types, and more...',
			gitHubURL: '',
			youtubeURL: '',
			difficulty: 'intermediate',
			skills: ['TypeScript'],
			publishedDate: '2023-07-15',
			nextUpdateDate: '2023-08-01',
			comments: []
		},
		{
			id: 9,
			blogTitle: 'Docker for Beginners',
			blogSlug: 'docker-basics',
			blogSummary: 'A comprehensive guide to containerization with Docker.',
			blogContents: 'Learn how to create, deploy, and manage applications using Docker...',
			gitHubURL: 'https://github.com/user/docker-repo',
			youtubeURL: 'https://www.youtube.com/watch?v=78901',
			difficulty: 'Intermediate',
			skills: ['CSS', 'HTML'],
			publishedDate: '2023-08-10',
			nextUpdateDate: '2023-09-01',
			comments: [
				{
					userId: 1507,
					commentedDate: '2023-08-12',
					comments: 'Docker is a game-changer in the world of containerization!'
				},
				{
					userId: 1608,
					commentedDate: '2023-08-15',
					comments: 'Thanks for simplifying Docker concepts. Great post!'
				}
			]
		},
		{
			id: 10,
			blogTitle:
				'Machine Learning with TensorFlow, Machine Learning with TensorFlow Machine Learning with TensorFlow Machine Learning with TensorFlow Machine Learning with TensorFlow',
			blogSlug: 'tensorflow-ml',
			blogSummary: 'Introduction to machine learning using TensorFlow.',
			blogContents: 'Explore the basics of machine learning and create models with TensorFlow...',
			gitHubURL: 'https://github.com/user/tensorflow-repo',
			youtubeURL: 'https://www.youtube.com/watch?v=89012',
			difficulty: '',
			skills: ['machine-learning', 'Blog'],
			publishedDate: '2023-09-15',
			nextUpdateDate: '2023-10-01',
			comments: [
				{
					userId: 1709,
					commentedDate: '2023-09-18',
					comments: 'TensorFlow is powerful! This post is a great starting point.'
				},
				{
					userId: 1810,
					commentedDate: '2023-09-20',
					comments: 'Clear explanations and practical examples. Well done!'
				}
			]
		},
		{
			id: 11,
			blogTitle: 'Responsive Web Design Best Practices',
			blogSlug: 'responsive-design',
			blogSummary: 'Essential tips and techniques for creating responsive web designs.',
			blogContents: 'Learn about media queries, flexible grids, and responsive images...',
			gitHubURL: 'https://github.com/user/responsive-design-repo',
			youtubeURL: '',
			difficulty: 'easy',
			skills: ['html', 'css', 'responsive-design'],
			publishedDate: '2023-10-10',
			nextUpdateDate: '2023-11-01',
			comments: [
				{
					userId: 1911,
					commentedDate: '2023-10-12',
					comments: "Responsive design is crucial in today's web development. Thanks for the guide!"
				},
				{
					userId: 2012,
					commentedDate: '2023-10-15',
					comments: "I've struggled with responsiveness before. This post is a lifesaver!"
				}
			]
		},
		{
			id: 12,
			blogTitle: 'AWS Cloud Computing Essentials',
			blogSlug: 'aws-cloud-essentials',
			blogSummary: 'Introduction to cloud computing with Amazon Web Services (AWS).',
			blogContents: 'Explore key AWS services, infrastructure as code, and best practices...',
			gitHubURL: '',
			youtubeURL: 'https://www.youtube.com/watch?v=23456',
			difficulty: 'Intermediate',
			skills: ['cloud-computing', 'aws'],
			publishedDate: '2023-11-10',
			nextUpdateDate: '2023-12-01',
			comments: [
				{
					userId: 2113,
					commentedDate: '2023-11-12',
					comments: 'AWS is a powerful platform. This post provides a great introduction!'
				},
				{
					userId: 2214,
					commentedDate: '2023-11-15',
					comments: 'Clear explanations and practical insights into AWS. Well done!'
				}
			]
		}
	];
</script>

<Announcement />

<div class=" columns-1 lg:columns-2 xl:columns-3 gap-5 md:gap-6 lg:gap-7">
	{#each blogList as post (post.id)}
		<BlogTile {...post} />
	{/each}
</div>
