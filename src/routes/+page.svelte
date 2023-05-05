<script>
	import data from '$lib/data.js';
	import Counter from '$lib/Lines.svelte';

	const counts = data.map(() => 0);
</script>

<svelte:head>
	<title>What Asian snack are you?</title>
</svelte:head>

<main>
	{#each data as { id, imgsrc, color }, i (id)}
		<button
			class="category"
			on:click={() => counts[i]++}
		>
			<img src={imgsrc} alt={id} />
			<Counter
				n={counts[i]}
				color={color}
			/>
			<span style:color={color}>{counts[i]}</span>
		</button>
	{/each}
</main>

<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		gap: 8px;
		width: 100%;
	}

	button {
		all: unset;
		display: flex;
		align-items: center;
		gap: 16px;
		cursor: pointer;
	}

	.category {
		display: flex;
		width: 100%;
		max-height: 80px;
	}

	img {
		max-height: 50px;
		user-select: none;
	}

	@media (min-width: 600px) {
		img {
			max-height: 70px;
		}
	}

	span {
		font-family: 'Courier New', Courier, monospace;
		font-size: 36px;
		font-weight: bold;
	}
</style>
