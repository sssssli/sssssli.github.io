---
layout: post
title: Setting up your own blog like this
subtitle: How meta...
---

I scrolled through a lot of [examples](https://github.com/jekyll/jekyll/wiki/themes) to just find a Jekyll theme that I like for my own personal GitHub page. My page is built with [Beautiful Jekyll](https://github.com/daattali/beautiful-jekyll). It is actually very easy to set-up, however, there are some tweaks for those who are a bit more familiar GitHub and want to get some **commit history** going from this blog.

Status quo as per [Beautiful Jekyll](https://github.com/daattali/beautiful-jekyll) is to fork the repo and work off of the fork. This is all fine and dandy, except that that currently [work done on forks will not be added to your GitHub profile](https://help.github.com/articles/why-are-my-contributions-not-showing-up-on-my-profile/).

This post explains step-by-step how to set up themed blogs as standalone repos, but I'm assuming that you've *some* git knowledge/experience.

First things first, if you have a GitHub Enterprise account **and** a personal GitHub account, and you're setting this up on a laptop that contains both, then you'll have to configure your local repo like below (after git is initiated) to get commits as your personal GitHub profile.

~~~
git config user.name "John Doe"
git config user.email johndoe@example.com
~~~

Fork the theme that you want on GitHub.

Let's say that you already that you want to set-up a Jekyll theme for a project page (as opposed to your GitHub user page, [read this](https://help.github.com/articles/user-organization-and-project-pages/) if you've no idea what I'm referring to), you'll need to set up a GitHub page branch first:

~~~
git checkout -b gh-pages
~~~

Note that this is because [Jekyll is supported by GitHub](https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages/).

Now you can add the fork remote, **replace fork_link_https_or_ssh**:

~~~
git remote add fork fork_link_https_or_ssh
git fetch fork
git merge fork/master
~~~

Now you may see some conflicts, resolve them and carry on. Note: I've tried to checkout the gh-pages branch as an orphan, but ran into problems of merging gh-pages back into master branch due to different commit history. Also it didn't feel right to completely clear the history of Beautiful Jekyll's commit history, as I'd like to credit the creator whenever and wherever I can. If you'd like, you can also edit _config.yml right now to set it up correctly as well. [Beautiful Jekyll](https://github.com/daattali/beautiful-jekyll) explains it pretty well.

You can then push this to GitHub like any other pushes.

Finally, make sure you merge this back into master with a pull request. You have to do this for your user page to actually launch. I don't believe this is the case for a project page.

TBD on how to launch a local Jekyll site with this Jekyll theme business.
