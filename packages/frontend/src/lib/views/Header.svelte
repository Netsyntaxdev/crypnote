<script lang="ts">
	import { status } from '$lib/stores/status'
</script>

<header>
	<a href="https://crypnote.netsyntax.es/">
		{#if $status?.theme_image}
			<img alt="logo" src={$status.theme_image} />
		{/if}
	</a>
</header>


<style>
	a {
		border: none;
	}

	header {
		text-align: center;
		margin-top: 3rem;
		margin-bottom: 2rem;
	}

	img {
		object-fit: contain;
	}

	@media screen and (max-width: 30rem) {
		header {
			margin-top: 1rem;
			margin-bottom: 1rem;
		}

		header svg,
		header img {
			max-height: 4rem;
		}
	}

	header svg,
	header img {
		width: 100%;
		max-height: 8rem;
		transform: translateX(-1rem);
		fill: currentColor;
	}
</style>
