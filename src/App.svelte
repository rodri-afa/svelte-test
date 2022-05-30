<script>
	// export let name;
	let name = 'developers'
	let href = 'https://svelte.dev/tutorial'
	import Counter from './Counter.svelte'
	import Calculator from './Calculator.svelte'
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a {href} target="_blank">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<!-- <Counter /> -->
	<!-- <Calculator/> -->
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