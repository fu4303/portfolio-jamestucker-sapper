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

  export let post

  function findPostsByTag(tag) {
    goto(`/blog?tag=${tag}`)
  }
</script>

<style>
  h1 {
    font-size: 4rem;
  }
  .tag-btn {
    background: #cb48b7;
    color:white;
    width: fit-content;
    padding: .2em .4em;
    border-radius: 3px;
    font-size: .75em;
  }

  .tag-btn:hover {
    cursor: pointer;
  }
</style>

<svelte:head>
  <title>{post.title}</title>
</svelte:head>

<header>
  <h1>{post.title}</h1>
  <p>{post.printDate} - {post.printReadingTime}</p>
  {#each post.tags as tag, index}
    <p on:click={findPostsByTag(tag)} class="tag-btn">{tag}</p>
  {/each}
</header>

<article>
  {@html post.html}
</article>
