<script lang="ts" context="module">
	import { writable } from 'svelte/store'

	const Theme = {
		Dark: 'dark',
	}

	export const theme = writable<string>(Theme.Dark)

	theme.subscribe((theme) => {
		if (typeof window !== 'undefined') {
			window.localStorage.setItem('theme', theme)
			const html = window.document.getElementsByTagName('html')[0]
			html.setAttribute('theme', theme)
		}
	})
</script>

<script lang="ts">
	import Icon from '$lib/ui/Icon.svelte'

	function change() {
		// No es necesario cambiar el tema ya que siempre será 'dark'
	}
</script>

<button on:click={change}>
	<Icon class="icon" icon="contrast" />
	{$theme}
</button>

<style>
	button :global(.icon) {
		height: 1rem;
		width: 1rem;
		margin-right: 0.5rem;
	}

	button {
		display: flex;
		flex-direction: row;
		justify-content: flex-end;
		align-items: center;
		cursor: pointer;
	}
</style>
