<script lang="ts">
	export let count: number;
	const modifyCounter = (value: number): number => {
		return count += value;
	};
	export const reset = (): number => count = 0;
</script>

<main>
	<h1>Counter app</h1>
	<h3 class={count === 0 ? "" : count > 0 ? "positive" : "negative"} >counter: {count}</h3>
	<button class="inc" on:click={() => modifyCounter(1)}>+</button>
	<button class="inc" on:click={() => modifyCounter(-1)}>-</button>
	<button class="inc" on:click={reset}>reset</button>
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

	h3 {
		color: #a143dd;
		text-transform: uppercase;
		font-size: 2em;
		font-weight: 0;
	}

	.positive {
		color: #00ff00;
	}

	.negative {
		color: #ff0000;
	}

	button {
		background: #111;
		color: #fff;
		padding: 0.5em;
		border: none;
		border-radius: 15%;
		font-size: 1.25em;
		font-weight: bold;
		cursor: pointer;
	}

	.inc:active {
		background: #fff;
		color: #111;
		border: 1px solid #111;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>