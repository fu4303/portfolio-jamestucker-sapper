---
title: How to Contribute to Open Source for the First Time
date: "2020-09-14T08:38:00.000Z"
tags:
  - Open-Source
---

## My First Time

The other day I saw Evan You (the creator of [Vue.js](https://vuejs.org/)) tweet about a new repo he was working on, and my interest was piqued. I decided I wanted to contribute!

Thing is, I'd never contributed to an open-source (OSS) project before. I didn't know where to start. But it couldn't be
that hard, right?

I got to the repo and instantly froze. What the hell do I do. I thought to myself,

> If I make a PR, the maintainers are probably going to rip apart my code. I'll forever be known in Dev Land as that guy who couldn't open-source properly. And my career will be over.

Thankfully, I read an article (I wish I remember where) that suggested your first contribution be something low-key. For example, it could be something as simple as fixing a typo.

And that's what I did. I read through the repo's documentation, found several typos, opened a PR - and lo and behold, Evan merged in my changes. I officially became a Vue contributor! Maybe I should put that in my [Twitter](https://twitter.com/tucker_dev) bio?

## "That's Great, But How Can I Get Started?"

Can I tell you how excited I am for you to make your first open-source PR?

Okay, let's get started - I'm going to show you the steps you can take to contribute.

### 1. Find a Project

For inspiration, think of your favorite technology or tool. Do you find yourself using [Gatsby](https://www.gatsbyjs.org/) quite a bit? Check out their [repo](https://github.com/gatsbyjs/gatsby)!

You could also contribute to one of my repos. This one [here](https://github.com/jamesctucker/Fantastic-Front-End-Toolbox) is a list of frontend resources. If you have an item you'd love or find useful, I'd love for you to add it! The best thing is that I promise to be nice when you open a PR. 😉

And finally, [Awesome First PR Opportunities](https://github.com/MunGell/awesome-for-beginners) is a gigantic repo of beginner-friendly open-source projects. There are projects for 22 different languages! (Sorry, there are no COBOL projects 🙃).

### 2. Find Something to Contribute

Familiarize yourself with the project. Go over the Readme. Scan the different folders and files. Get a sense of how the codebase is structured. Just by doing this, you might come across that easy typo fix!

Once you've done that, take a look at the **Issues** section of the project. There you'll find a list of known bugs or suggested features. For someone who's new to the codebase, it may be difficult to discern which issues are beginner-friendly. Luckily, many major projects will have a link to newcomer-friendly issues.

Look, my opinion is that your first contribution should be as low pressure as possible, but if you want to go big that's obviously your choice.

Once you've found something to contribute, you'll want to fork the project.

### 3. Fork the Project

Forking the project creates an exact copy of it in your own Github repo.

![Where to find forking option in Github](https://i.ibb.co/JddB5QQ/forking.png)

### 4. Clone the Project Locally

Next, clone the project to a local folder using the project's URL.

`git clone <project-url>`

This is where you find the URL.

![Image of dropdown where you can clone the repo from](https://i.ibb.co/wB68f2h/cloning.png)

Now that the project is on your machine, open it with your editor. If you think your changes will take a while to make, make sure to sync your project copy with the original so that you're always up-to-date with changes. You can find the exact Git commands to do that [here](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/syncing-a-fork).

### 5. Create a New Branch for Your Changes

Now it's time for you to make your changes/fixes! Create a new branch for your changes to live on.

`git branch <branch-name>`

You can name it whatever you'd like, but from my experience you might see a pattern for branch-naming in the original project. In that case, I recommend following the existing pattern.

A good branch name for something like a typo fix would be `patch/typo-fix`.

You can switch to that branch with `git checkout <branch-name>`.

Now go make your changes!

### 6. Open a Pull Request

Alright, so you've fixed that glaring typo or updated a broken link. You're proud of your work. You want the whole world to know you're one of those mythical 10x developers who can code, do laundry, and watch Netflix all at the same damn time.

Go ahead and push your changes up to your forked Github repo with `git push -u origin <branch-name>`.

Go to your forked Github repo and open a pull request. **Note:** _if you've never made a pull request before, watch this [video](http://makeapullrequest.com/) by Kent Dodds to learn how._

![Image of open PR](https://i.ibb.co/F49rWSq/open-pr.png)

Make sure your branch is pointing to the master branch of the original repo.

![Point your branch to master](https://i.ibb.co/Y86qGwz/pointing.png)

Now you're ready to add details to your PR. Make sure your title clearly conveys what the PR does. Add a description - if you're fixing an existing issue, make sure to reference it.

![Image of detailed Pull Request](https://i.ibb.co/SftCHCN/detailed-pr.png)

Once you're satisfied with your description, submit the PR for a review. Someone with authority to approve PRs will most likely review yours within a few days and do one of several things:

1. Immediately merge your changes.
2. Ask for changes to be made.
3. Close your PR.

Be patient, as many maintainers have full-time jobs/other projects to deal with.

## You Did It!

You're now an open-source contributor! How does it feel? Ready to build your own Node.js competitor? 😉

My hope is that, by making a simple, low-stakes contribution, the prospect of future OSS work has become less intimidating.

For further info on contributing to OSS, check out [Open Source Guides](https://opensource.guide/).

Thanks for reading!

✌️
