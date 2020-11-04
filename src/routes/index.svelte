<script>
	import { onMount } from 'svelte';
	import { TwitterIcon, GithubIcon, TwitchIcon, YoutubeIcon } from 'svelte-feather-icons'

	const titles = ['software engineer', "husband", "dog dad", "former aspiring pastor", "youtuber", "livestreamer", "outdoor lover"];
	let currentTitle = titles[0];
	let index = 0;

	const loopThroughTitles = () => {
		setTimeout(() => {
			if (index <= titles.length - 1) {
				currentTitle = titles[index]
				index++
				loopThroughTitles();
			} else {
				index = 0;
				loopThroughTitles();
			}
		}, 1000)

	}

	onMount(() => {
		loopThroughTitles();
	})
</script>

<style>
	/* section {
		width: 75%;
	} */

	.title {
		padding: .25rem .5rem;
		background-color: #1A212C;
		color: white;
		border-radius: 3px;
	}

	:global(body.dark-mode) .title {
		color: #1A212C;
		background-color: #ffff;
	}


	.social-link {
		color: #1A212C;
		margin-right: 1rem;
	}

	:global(.social-icon):hover {
		transform: scale(1.2);
	}

	:global(body.dark-mode) .social-link {
		color: #ffff;
	}

</style>


<svelte:head>
	<title>James C. Tucker</title>
</svelte:head>

<section class="intro">
	<h2>Hi, I'm James.</h2>
	<p>I'm a <span class="title">{ currentTitle }.</span></p>
	<p>Welcome to my personal site, where I write about things like JavaScript, getting into technology, and entrepreneurship.</p>
	<div>
		<a class="social-link" href="https://twitter.com/tucker_dev"><TwitterIcon size="24" class="social-icon" /></a>
		<a class="social-link" href="https://github.com/jamesctucker"><GithubIcon size="24" class="social-icon"/></a>
		<a class="social-link" href="https://www.twitch.tv/jamestuckerdev"><TwitchIcon size="24" class="social-icon"/></a>
		<a class="social-link" href="https://www.youtube.com/channel/UCwvTTrYq7ioW3GFrHbcWhRA?view_as=subscriber"><YoutubeIcon size="24" class="social-icon"/></a>
	</div>
</section>


