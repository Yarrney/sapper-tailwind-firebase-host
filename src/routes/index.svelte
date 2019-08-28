<script>
	import Theme from '../components/Theme.svelte';
	let data = "undraw_to_the_moon_v1mv.svg"
</script>

<style>
	h1, object, p {
		text-align: center;
		margin: 0 auto;
	}

	h1 {
		font-size: 2.8em;
		font-weight: 700;
		margin: 0 0 0.5em 0;
		line-height: 1;
		@apply text-default;
	}

	object {
		width: 100%;
		max-width: 700px;
		margin: 0 auto 1em auto;
	}

	@media (min-width: 480px) {
		h1 {
			font-size: 4em;
		}
	}

</style>

<svelte:head>
	<title>Sapper Template</title>
</svelte:head>

<h1>Great success!</h1>

<object class="w-full" type="image/svg+xml" data={data} title="illustration">Illustration</object>

<p>Illustration by <a class="link-primary" href="https://undraw.co" target="_blank">unDraw</a></p>

<Theme classes={"mt-12 md:mt-4 mx-auto flex"}/>
