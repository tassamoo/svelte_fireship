<script>
	import { fade, fly} from "svelte/transition";
	export let name;

	let rando;

	function setRando() {
		rando = Math.random();
	}

	$: result = Math.round(rando * 100);
</script>

<main>
	<h1>Hello {name}!</h1>

	<p>The random number is {rando}</p>
	
	<button on:click={setRando}>Randomize</button>
	
	<p>Your score is {result}</p>

	{#if result> 75}
		<p>Big Winner top 25%</p>
	{:else if result > 50}
		<p transition:fade>Decent, top 50%</p>
	{:else}
		<p>Loserrrrr</p>
	{/if}

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