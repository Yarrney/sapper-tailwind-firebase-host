<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>

<div class="fixed top-0 bg-purple-700 h-16 w-full text-white flex flex-row items-center justify-around font-extrabold text-3xl">
	Timesheets
</div>

<Nav {segment}/>

<main class="pt-20 md:pt-40 px-8 pb-8 max-w-4xl mx-auto">
	<slot></slot>
</main>