<script>
	export let name;

	let rando;

	function setRando() {
		rando = Math.random();
	}

	$: result = Math.round(rando) ? 'Winner' : 'Loser';
</script>

<main>
	<h1>Hello {name}!</h1>

	<p>The random number is {rando}</p>
	
	<button on:click={setRando}>Randomize</button>
	
	<p>You are {result}</p>

	<input bind:value={rando}>


</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>