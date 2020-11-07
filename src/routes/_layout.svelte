<script>
	import Nav from '../components/Nav.svelte';
	import Footer from '../components/Footer.svelte';
</script>

<style>
	main {
		flex: 1 0 auto;
		padding: 2em;
	}

	:global(body) {
		max-width: 40em;
		margin: 0 auto;
		height: 100%;
		display: flex;
		flex-direction: column;
	}

	:global(html) {
		height: 100%;
	}

	:global(#sapper) {
		height: 100%;
    	display: flex;
    	flex-direction: column;
	}
	
</style>

<Nav/>
<main>
	<slot></slot>
</main>
<Footer />
