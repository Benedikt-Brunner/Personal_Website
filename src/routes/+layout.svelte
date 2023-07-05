<script>
		import Nav from "./nav.svelte";
</script>
<div class="nav">
	<Nav/>
</div>
<div class="app">
	<main>
		<slot />
	</main>


</div>

<style>

	.nav{
		width: 90%;
		margin-left: 5%;
		display: flex;
		justify-content: center;
	}
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
		align-items: center;
		justify-content: center;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 100rem;
		justify-content: center;
		align-items: center;
		box-sizing: border-box;
	}

.nav{
	position: absolute;
}

</style>
