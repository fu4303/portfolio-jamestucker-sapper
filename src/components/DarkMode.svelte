<script>
export let isDarkMode = false;

function toggle() {
	window.document.body.classList.toggle('dark-mode')
	isDarkMode = !isDarkMode;
}
</script>
<button on:click={toggle}>
	<slot/>
</button>
<style>
	button {
		color: #1A212C;
        padding: 1rem;
        display: flex;
		align-items: center;
		border: none;
		
	}
	:global(body.dark-mode) button {
        color: white;
	}
</style>