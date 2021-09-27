<script>
	export let poke;
</script>

<!-- <p>{poke.name}</p> -->
<a href={`/poke/${poke.id}`} class="poke-ele">
	<img src={poke.image} alt={poke.name} />
	<h2>{poke.id}. {poke.name}</h2>
</a>

<style>
	.poke-ele {
		width: 25%;
		height: 40vh;
		border-radius: 15px;
		text-decoration: none;
		color: white;
		display: flex;
		flex-direction: column;
		position: relative;
		z-index: 1;
	}
	.poke-ele::after,
	.poke-ele::before {
		content: '';
		position: absolute;
		z-index: -1;
		top: 0;
		bottom: 5%;
		left: 10%;
		right: 0;
		border-radius: 15px;
		background-color: rgb(152, 23, 238);
		transition: all 150ms ease-in-out;
	}
	.poke-ele:hover::after,
	.poke-ele:hover::before {
		bottom: 0%;
		left: 0%;
	}
	.poke-ele img {
		width: 80%;
		height: 60%;
		object-fit: cover;
		margin: auto;
	}
	.poke-ele h2 {
		height: 40%;
		display: grid;
		place-items: center;
		text-align: center;
	}
	@media only screen and (max-width: 900px) {
		.poke-ele {
			width: 35%;
		}
	}
	@media only screen and (max-width: 700px) {
		.poke-ele {
			width: 40%;
		}
	}
	@media only screen and (max-width: 600px) {
		.poke-ele {
			width: 50%;
		}
	}
	@media only screen and (max-width: 500px) {
		.poke-ele {
			width: 80%;
		}
		.poke-ele h2 {
			font-size: 20px;
		}
	}
</style>
