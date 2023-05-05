<script>
	import header from '$lib/images/header.png';
	import './styles.css';
</script>

<div class="app">
	<img src={header} alt="What Asian snack are you?">
	<slot />
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		width: 100%;
		max-width: 900px;
		height: 100%;
		margin: 0 auto;
	}
</style>
