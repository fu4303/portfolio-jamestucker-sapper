---
title: Rebuilding My Blog With Sapper
date: "2020-05-14T08:38:00.000Z"
tags:
  - Svelte
---

Why I've gone through three websites in a year.

<!-- more -->

## Rebuilding My Blog, Again

This is the third iteration of my personal website. The first was in Gatsby, the second in Nuxt.js (Vue), and this time in
[Sapper](https://sapper.svelte.dev/) ([Svelte](https://svelte.dev/)).

Why go through the hassle of building it all over again?

I like shiny technological toys. And I've been fascinated by Svelte. So what better way to learn than to make something
with it?

Also, I've been wanting to consistently blog, and my last site just wasn't writing-centric. But I feel like this one is.
I designed it to be minimalistic, so as to not distract you from the content (that doesn't really exist yet!).

## Cool Functionality

I'm really happy with how the code highlighting turned out. I am using [highlight.js](https://highlightjs.org/) to do this.

Check it out!

```html
<script>
  let count = 0;

  function handleClick() {
    count += 1;
  }
</script>

<button on:click="{handleClick}">
  Clicked {count} {count === 1 ? 'time' : 'times'}
</button>
```

<strike>Another fun detail happens when you toggle dark mode up by the navbar. I'm a bit of a nerd</strike>.

Oops, nevermind it's broken. It's supposed to play a ray gun noise when you click on the toggle.

## My Goal

Now that the basics of my site are online, I'm ready to commit to writing regularly. I love teaching others (though I'm used to doing it through public speaking), and so this will be another outlet for me to share what I'm learning. You can also expect me to post screencasts on occasion.

I'm really excited to [learn in public](https://www.swyx.io/writing/learn-in-public/)!
