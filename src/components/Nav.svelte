<script>
	export let segment;
</script>

<style>

	a {
		@apply flex h-full justify-center mx-2 items-center;
	}

	svg {
		@apply fill-current inline-flex h-6 w-6 mr-2;
	}

	p {
		@apply hidden;
	}

	@screen md {
		.selected {
			@apply text-secondary border-solid border-b-2 border-purple-700;
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

<nav class="bg-primary md:bg-secondary font-light text-default md:text-default h-16 w-full fixed md:mt-16 bottom-0 md:bottom-auto">
	<ul class="flex flex-row items-center justify-around md:justify-start md:mx-8 h-full">
		<li>
			<a class='{segment === undefined ? "text-primary" : ""}' href='.'>
				<svg>
					<use xlink:href="solid.svg#home"></use>
				</svg>
				<p>home<p>
			</a>
		</li>
		<li>
			<a rel=prefetch class='{segment === "blog" ? "text-primary" : ""}' href='blog'>
				<svg>
					<use xlink:href="solid.svg#calendar-check"></use>
				</svg>
				<p>blog<p>
			</a>
		</li>
		<li>
			<a class='{segment === "settings" ? "text-primary" : ""}' href='settings'>
				<svg>
					<use xlink:href="solid.svg#cog"></use>
				</svg>
				<p>settings<p>
			</a>
		</li>
	</ul>
</nav>