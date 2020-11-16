---
title: How to Setup a Sapper Project
date: "2020-11-16T08:38:00.000Z"
tags:
  - Sapper
  - Svelte
---

## Prerequisites

You should know basic HTML, CSS, and JavaScript. No prior knowledge of Svelte or Sapper.js is needed. You'll also want to make sure you have `npm` installed. If you don't, here's how install it on [Mac](https://treehouse.github.io/installation-guides/mac/node-mac.html) or [Windows](https://phoenixnap.com/kb/install-node-js-npm-on-windows).

## So You want to learn Sapper

Sapper.js and Svelte are still quite niche, so most of you reading this mostly likely stumbled across this via a specific Google (or DuckDuckGo 🦆) search or are doing your very best to be a JavaScript hipster. So I won't spend too much time elaborating on the excellencies of the Svelte ecosystem.

## What is Sapper

Sapper is what some would call a 'meta' or 'application' framework, a framework to use on top of a web/JavaScript framework. In this case, Sapper is used on top of [Svelte](https://svelte.dev/). Another example that might clear things up is the use case of developing a [React project with Next](https://nextjs.org/).js. Speaking of Next.js, it's a distant cousin of Sapper, and I think it's safe to say even a primary source of inspiration.

Some of the primary benefits of Sapper include advanced routing, server-side rendering (SSR), and code-splitting. To put it in the words of the Sapper team,

> Sapper does all the boring stuff for you so that you can get on with the creative part.

## A Word of Warning Before Going Further

Sapper will be deprecated, so don't use it for production. It's still ok to use for a personal project. Sapper will ultimately be replaced by a new Svelte project that'll include many Sapper features by default. Per Rich Harris, you should be able to easily [migrate your Sapper apps](https://svelte.dev/blog/whats-the-deal-with-sveltekit) to this new framework.

To learn more, you can watch the [official announcement from Rich](https://www.youtube.com/watch?v=qSfdtmcZ4d0&feature=youtu.be&list=PL8bMgX1kyZThM1sbYCoWdTcpiYysJsSeu&t=1188).

## Time to Get Started!

### Install NPX

Check to see if you need to install `npx` - On Windows, might need to manually install - Otherwise, it comes bundled with Node 5.2+

### Install and Run Degit

Install `degit`, a package for quick project scaffolding, with `npx install degit`

Now, run `npx degit "sveltejs/sapper-template#rollup" my-app`. This commands create a project template similar to Create React App, with a default folder structure, example files, and pre-configured Rollup or Webpack settings. It goes without saying you can replace most of the files - these are here to quickly get you off the ground and give you a mental framework for how Sapper operates.

### Open Your Project

Open your file in VS Code or run `cd my-app` in your terminal.
Then, run `npm install`, followed by `npm run dev`. Your app should be running locally now, so go to `localhost:3000` to view it. You should see this as your home view:

<img src="post-images/sapper-home.png" alt="sapper home view" class="blog-post-img" />

## Make Your First Route

One of the best parts of Sapper, in my opinion, is the way routing works. Want to create a new top-level route like `localhost:3000/hello_world`? All you need to do is create a new file called `hello_word.svelte` in `src/routes`.

Once you've created the file, maybe add a header so you can identify the page when you land on it. In Svelte/Sapper, you don't need to use any boilerplate to get your app to recognize what's HTML, styles, or script. Throw on an HTML tag, and it'll work!

```
<h1>Hello World</h1>
```

Ok, so now we need to add the new route to the nav bar. Head over to `src/components/Nav.svelte`. On line 59, or under the last existing `<li>` element, add your new route.

```
<li>
    <a
        aria-current="{segment === 'hello_world' ?'page' : undefined}"
        href="hello_world"
    >
        hello world
    </a>
</li>
```

Take a look at your nav bar and you should your new route as an option. Click on it and you should be greeted with:

<img src="post-images/sapper-route.png" alt="sapper route view" class="blog-post-img"/>

## Final Thoughts

And there you go! You've not only got your first Sapper project up and running, you now know how to create a new route.

Happy building!
