<script>
	import { pokemon } from '../stores/pokestore';
</script>

<svelte:head>
	<title>Pokidex | Home</title>
</svelte:head>

<h1>Svelte Kit Pokedex</h1>

{#each $pokemon as poke}
	<p>{poke.name}</p>
{/each}

<style>
	h1 {
		text-align: center;
	}
</style>
