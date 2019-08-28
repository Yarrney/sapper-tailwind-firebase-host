<script>
	import Theme from '../components/Theme.svelte';
</script>

<style>
	h1 {
		@apply font-bold text-4xl;
	}
</style>

<svelte:head>
	<title>Settings</title>
</svelte:head>

<h1>Settings</h1>

<p>This is the 'settings' page. There's not much here.</p>

<div class="flex flex-col md:flex-row">
	<button class="btn btn-primary mt-4 md:mr-2">
		Primary Button
	</button>

	<button class="btn btn-secondary mt-2 md:mt-4">
		Secondary Button
	</button>
</div>


<Theme classes={"mt-12 mx-auto md:mx-0 flex"}/>


