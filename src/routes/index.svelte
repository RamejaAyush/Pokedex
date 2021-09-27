<script>
	import { pokemon } from '../stores/pokestore';
	import Poke from '../components/poke.svelte';

	let search = '';
	let filterPoke = [];

	// reactive function
	$: {
		console.log(search);
		if (search) {
			// change filtered pokemon
			filterPoke = $pokemon.filter((poke) =>
				poke.name.toLowerCase().includes(search.toLocaleLowerCase)
			);
		} else {
			filterPoke = [...$pokemon];
		}
	}
</script>

<svelte:head>
	<title>Pokidex | Home</title>
</svelte:head>

<h1>Svelte Kit Pokedex</h1>

<div class="textSearch">
	<input type="text" name="search" id="search" placeholder="Search Pokemon" bind:value={search} />
</div>

<div class="pokeCont">
	{#each filterPoke as poke}
		<Poke {poke} />
	{/each}
</div>

<style>
	h1 {
		text-align: center;
		font-size: 42px;
	}
	.pokeCont {
		min-height: 100vh;
		width: 100%;
		padding: 5rem;
		display: flex;
		flex-wrap: wrap;
		gap: 55px;
		align-items: center;
		justify-content: center;
		margin: 0 auto;
	}

	.textSearch {
		width: 100%;
		height: 20vh;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.textSearch input {
		width: 40%;
		padding: 10px;
		outline: none;
		border-radius: 5px;
	}
</style>
