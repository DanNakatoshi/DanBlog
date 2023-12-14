<script>
	import '../app.css';
	import Header from '$lib/layout/Header.svelte';
	import Footer from '$lib/layout/Footer.svelte';
</script>

<div class="md:container md:mx-auto">
	<div class="flex flex-col h-screen justify-between">
		
		<header class="z-10"><Header /></header>
	
			<div class="flex flex-col justify-center px-2 md:px-4">
				<slot />
			</div>
	
		<Footer />
	</div>
</div>
