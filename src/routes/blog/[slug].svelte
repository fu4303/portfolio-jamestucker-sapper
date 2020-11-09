<script context="module">
  export async function preload({ params, query }) {
    // the `slug` parameter is available because
    // this file is called [slug].html
    const res = await this.fetch(`blog/${params.slug}.json`);
    const data = await res.json();

    if (res.status === 200) {
      return { post: data };
    } else {
      this.error(res.status, data.message);
    }
  }
</script>

<script>
  import { goto } from '@sapper/app';
  import { onMount } from 'svelte';
  import Meta from '../../components/Meta.svelte'

  export let post

  function findPostsByTag(tag) {
    goto(`/blog?tag=${tag}`)
  }

  onMount(() => console.log(post))

	
	const metadata = {
		title: post.title,
		description: post.excerpt,
		image: `https://jamestucker.dev/g/${post.slug}.png`,
		imageAlt: 'article image',
		url: `jamestucker.dev/blog/${post.slug}`
	}
</script>

<style>
  h1 {
    font-size: 4rem;
  }
  .tag-btn {
    color: #14AC83;
    width: fit-content;
    padding: .2em .4em;
    border-radius: 3px;
    font-size: .75em;
  }

  .tag-btn:hover {
    cursor: pointer;
  }
</style>

<Meta {metadata}/>

<header>
  {#each post.tags as tag, index}
    <p on:click={findPostsByTag(tag)} class="tag-btn">{tag}</p>
  {/each}
  <img src="g/{post.slug}.png" alt="blog hero">
  <h1>{post.title}</h1>
  <p>{post.printDate} - {post.printReadingTime}</p>
  <hr>
</header>

<article>
  {@html post.html}
</article>
