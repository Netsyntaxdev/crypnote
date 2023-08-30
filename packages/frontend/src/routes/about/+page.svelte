<script lang="ts">
	import { status } from '$lib/stores/status'
	import AboutParagraph from '$lib/ui/AboutParagraph.svelte'
</script>

<svelte:head>
	<title>About</title>
</svelte:head>

<section class="content">
	<h1>About</h1>

	<p>
		<i>crypnote</i> es un servicio seguro y de código abierto para compartir notas/archivos.
	</p>

	<AboutParagraph title="Como funciona?">
		<span>
			cada nota tiene un generado <code>id (256bit)</code> y <code>key 256(bit)</code>. El
			<code>id</code>
			El id se utiliza para guardar y recuperar la nota. Luego, la nota se cifra con aes en modo gcm
			en el lado del cliente <code>key</code> luego se envía al servidor. los datos se almacenan en la 
			memoria y nunca persisten en el disco. el servidor nunca ve la clave de cifrado y no puede  
			descifrar el contenidode las notas
		</span>
	</AboutParagraph>

	<AboutParagraph title="features">
		<ul>
			<li>El servidor no puede descifrar el contenido debido al cifrado del lado del cliente.</li>
			<li>Limitaciones de tiempo y vista</li>
			<li>En la memoria, sin persistencia</li>
		</ul>
	</AboutParagraph>


	<AboutParagraph title="version">
		<span>
			{#if $status}
				<code>v{$status.version}</code>
			{/if}
		</span>
	</AboutParagraph>
</section>

<style>
	section {
		width: 100%;
		display: flex;
		flex-direction: column;
		gap: 2rem;
	}

	ul {
		margin: 0;
		padding: 0;
		padding-left: 1rem;
		list-style: square;
	}
</style>
