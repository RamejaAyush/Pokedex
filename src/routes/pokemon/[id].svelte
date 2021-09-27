<script context="module">
	export async function load({ page }) {
		const id = page.params.id;
		const url = `https://pokeapi.co/api/v2/pokemon/${id}`;
		const res = await fetch(url);
		const poki = await res.json();
		return { props: { poki } };
	}
</script>

<script>
	export let poki;
	import { fade, fly } from 'svelte/transition';
	const type = poki.types[0].type.name;
</script>

<svelte:head>
	<title>Pokidex | {poki.name}</title>
</svelte:head>

<div class="indPokeman" in:fly={{ y: 100, duration: 1000 }} out:fade>
	<img class="card-image" src={poki.sprites['front_default']} alt={poki.name} />
	<h1>{poki.name}</h1>
	<p>
		Type: {type}
	</p>
	<p>
		Height: {poki.height}
	</p>
	<p>
		Weight: {poki.weight}
	</p>
</div>

<style>
	.indPokeman {
		width: 100%;
		height: 90vh;
		text-align: center;
	}

	.indPokeman img {
		width: 45vw;
		height: 45vh;
		object-fit: cover;
		margin: 1rem;
	}
	.indPokeman h1 {
		font-size: 55px;
		text-transform: uppercase;
	}

	.indPokeman p {
		margin: 1rem;
		text-transform: uppercase;
		font-weight: 700;
	}
</style>
