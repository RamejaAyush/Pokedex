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

<div in:fly={{ y: 100, duration: 2000 }} out:fade>
	<h1>{poki.name}</h1>
	<p>
		Type: <strong>{type}</strong> | Height: <strong>{poki.height}</strong>
		| Weight: <strong>{poki.weight}</strong>
	</p>
	<img class="card-image" src={poki.sprites['front_default']} alt={poki.name} />
</div>
