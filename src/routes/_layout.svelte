<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>

<div class="theme-dark bg-default h-full min-h-screen">
	<div class="fixed top-0 h-16 w-full flex flex-row items-center justify-around bg-primary text-primary font-extrabold text-3xl">
		This is a title.
	</div>

	<Nav {segment}/>

	<main class="text-default pt-20 md:pt-40 px-8 pb-8 max-w-4xl mx-auto">
		<slot></slot>
	</main>
</div>