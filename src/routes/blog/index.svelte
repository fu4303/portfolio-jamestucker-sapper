<script context="module">
  export function preload({ params, query }) {
    return this.fetch(`blog.json`).then(r => r.json()).then(posts => {
      return { posts };
    });
  }
</script>

<script>
  import { stores } from '@sapper/app';
  import Meta from '../../components/Meta.svelte'
  const { page } = stores();
  
  let tag = $page.query.tag
  
  export let posts;

  if (tag) {
    posts = posts.filter(post => post.tags.includes(tag))
  } 

  const metadata = {
		title: `James Tucker's Blog`,
		description: 'James is a software engineer, writer, and public speaker. He loves teaching others code and helping them become better developers',
		image: `https://jamestucker.dev/g/main-site-image.png`,
		imageAlt: 'main site card photo',
		url: 'https://jamestucker.dev/blog'
	}

</script>

<style>
  /* a {
    color: #1A212C;
    text-decoration: none;
  } */

</style>

<Meta {metadata}/>


  
  {#if tag}
    <h1>{tag}</h1>
  {:else}
  <h1>Blog</h1>
  <!-- <p class="mb-8">
    Welcome to my <a href="https://tomcritchlow.com/2019/02/17/building-digital-garden/" target="_blank" rel="noreferrer noopener">digital garden</a> 
    where I share what's currently on my mind. Some of my ideas have just been "planted" and need to be cultivated 
    through further writing and external criticism. Others are deeply-rooted, having been nurtured for quite some time. 
    Basically, don't take me too seriously 🙃.
  </p> -->
  {/if}


  <ul>
  {#each posts as post}
      <li>
          <a rel='prefetch' href='blog/{post.slug}'>{post.title}</a>        
      </li>
  {/each}
  </ul>


