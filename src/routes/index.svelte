<script>
	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';
	import { TwitterIcon, GithubIcon, TwitchIcon, YoutubeIcon } from 'svelte-feather-icons'

	const titles = ['software engineer', "husband", "dog dad", "former aspiring pastor", "youtuber", "livestreamer", "outdoor lover"];
	let currentTitle = titles[0];
	let index = 0;
	let visible = false;

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
		visible = true;
	})

	function typewriter(node, { speed = 75 }) {
		const valid = (
			node.childNodes.length === 1 &&
			node.childNodes[0].nodeType === Node.TEXT_NODE
		);

		if (!valid) {
			throw new Error(`This transition only works on elements with a single text node child`);
		}

		const text = node.textContent;
		const duration = text.length * speed;

		return {
			duration,
			tick: t => {
				const i = ~~(text.length * t);
				node.textContent = text.slice(0, i);
			}
		};
	}
</script>

<style>
	/* section {
		width: 75%;
	} */

	.title {
		padding: .25rem .5rem;
		background-color: #14AC83;
		color: white;
		border-radius: 3px;
	}

	/* :global(body.dark-mode) .title {
		color: #1A212C;
		background-color: #ffff;
	} */


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
	{#if visible}
		<h2 in:typewriter>Hi, I'm James.</h2>
		<div in:fly="{{ y: 200, duration: 2000 }}">
			<p>I'm a <span class="title">{ currentTitle }.</span></p>
			<p>Welcome to my personal site, where I write about things like JavaScript, getting into technology, and entrepreneurship.</p>
			<div>
				<a class="social-link" href="https://twitter.com/tucker_dev"><TwitterIcon size="24" class="social-icon" /></a>
				<a class="social-link" href="https://github.com/jamesctucker"><GithubIcon size="24" class="social-icon"/></a>
				<a class="social-link" href="https://www.twitch.tv/jamestuckerdev"><TwitchIcon size="24" class="social-icon"/></a>
				<a class="social-link" href="https://www.youtube.com/channel/UCwvTTrYq7ioW3GFrHbcWhRA?view_as=subscriber"><YoutubeIcon size="24" class="social-icon"/></a>
			</div>
		</div>
	{/if}
	
</section>


