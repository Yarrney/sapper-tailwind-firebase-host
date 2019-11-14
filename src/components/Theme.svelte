<script>
	import { darkTheme } from '../components/stores.js';
	export let classes;

	function toggle() {
		darkTheme.update(value => !value);
	}
</script>

{#if $darkTheme}
	<button class="btn btn-primary {classes}" on:click={toggle}>
		Toggle Dark Theme
	</button>
{:else}
	<button class="btn btn-primary {classes}" on:click={toggle}>
		Toggle Light Theme
	</button>
{/if}
