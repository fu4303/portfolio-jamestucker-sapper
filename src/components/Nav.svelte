<script>
import Button from '../components/DarkMode.svelte';
import { MoonIcon, SunIcon } from 'svelte-feather-icons';

let isDarkMode;

</script>

<style>
	nav {
		/* border-bottom: 1px solid rgba(255,62,0,0.1); */
		font-weight: 300;
		display: flex;
		justify-content: space-between;
		padding: 2em;
		/* margin: 0 auto; */
		align-items: center;
	}

	.nav-links {
		display: flex;
		align-items: center;
	}


	a {
		text-decoration: none;
		padding-right: 1em;
		display: block;
	}

	a:hover {
		transform: scale(1.1);
		text-decoration: underline;
		text-decoration-color: #FF3F01;
	}

	.brand {
		font-size: 18px;
		font-weight: 700;
	}

	.brand:hover {
		text-decoration: none;
	}

	/* dark mode styles */
	:global(body) {
		background-color: #ffff;
		color: #1A212C;
		transition: background-color 0.3s
	}
	:global(body) a {
		color: #1A212C;
		transition: background-color 0.3s
	}
	:global(body.dark-mode) {
		background-color: #1A212C;
		color: #ffff;
	}

	:global(body.dark-mode) a {
		color: #ffff;
		transition: background-color 0.3s
	}

</style>

<nav>
	<div class="nav-brand">
		<a class="brand" href=".">JT</a>
	</div>
	<div class="nav-links">
		<a href="about">about</a>
		<a href="talks">talks</a>
		<a href="uses">uses</a>
		<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
		<a rel=prefetch href="blog">blog</a>
		<Button bind:isDarkMode={isDarkMode}>
			{#if isDarkMode}
				<SunIcon size="18" />
			{:else}
				<MoonIcon size="18"/>
			{/if}
		</Button>
	</div>
</nav>
