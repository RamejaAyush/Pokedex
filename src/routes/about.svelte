<script>
	import { fade, fly } from 'svelte/transition';
</script>

<svelte:head>
	<title>Pokidex | About</title>
</svelte:head>

<div in:fly={{ y: 100, duration: 2000 }} out:fade class="about">
	<h1>About</h1>
	<p>Made to Learn Svelte.It uses API to fetch Pokimon data.</p>
	<a href="https://github.com/RamejaAyush">GitHub</a>
</div>

<style>
	.about {
		text-align: center;
	}

	.about h1 {
		font-size: 55px;
	}

	.about p {
		margin: 1rem;
		font-size: 18px;
	}
	.about a {
		color: white;
	}
</style>
