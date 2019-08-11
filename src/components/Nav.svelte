<script>
	export let segment;
</script>

<style>

	a {
		@apply flex no-underline h-full justify-center mx-2 items-center;
	}

	.selected { 
		@apply text-white; 
	}

	svg {
		@apply fill-current inline-flex h-6 w-6 mr-2;
	}

	p {
		@apply hidden;
	}

	@screen md {
		.selected {
			@apply text-purple-700 border-solid border-b-2 border-purple-700;
			padding-top: 2px;
		}

		svg {
			@apply hidden;
		}

		p {
			@apply block;
		}

		li {
			@apply h-full;
		}

	}

</style>

<nav class="bg-purple-700 md:bg-gray-300 font-light text-purple-400 md:text-gray-800 h-16 w-full fixed md:mt-16 bottom-0 md:bottom-auto">
	<ul class="flex flex-row items-center justify-around md:justify-start md:mx-8 h-full">
		<li>
			<a class='{segment === undefined ? "selected" : ""}' href='.'>
				<svg>
					<use xlink:href="solid.svg#home"></use>
				</svg>
				<p>home<p>
			</a>
		</li>
		<li>
			<a rel=prefetch class='{segment === "timesheets" ? "selected" : ""}' href='timesheets'>
				<svg>
					<use xlink:href="solid.svg#calendar-check"></use>
				</svg>
				<p>timesheets<p>
			</a>
		</li>
		<li>
			<a class='{segment === "settings" ? "selected" : ""}' href='settings'>
				<svg>
					<use xlink:href="solid.svg#cog"></use>
				</svg>
				<p>settings<p>
			</a>
		</li>
	</ul>
</nav>