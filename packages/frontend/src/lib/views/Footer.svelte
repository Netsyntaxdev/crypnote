<script lang="ts">
	import ThemeToggle from '$lib/ui/ThemeToggle.svelte'
</script>

<footer>
	<ThemeToggle />
	<nav>
		<a href="/">/home</a>
		<a href="/about">/about</a>
		
	</nav>
</footer>

<style>
	footer {
		display: flex;
		justify-content: space-between;
		padding: 1rem;
		position: fixed;
		bottom: 0;
		right: 0;
		width: 100%;
		background-color: var(--ui-bg-0-85);
		backdrop-filter: blur(2px);
	}

	a {
		margin: 0 0.5rem;
	}

	nav {
		display: flex;
		flex-direction: row;
		justify-content: flex-end;
		align-items: center;
	}
</style>
