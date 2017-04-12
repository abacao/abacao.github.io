---
layout: post
title: How to post from Github with Markdown and Wordpress
---

I just found out that I am able to write my blog with markdown and use GitHub to store my articles.

This way I will always have my articles secured and I will never lose my articles again (I think I am even storing my pictures inside the repo).

Im currently using a plugin called [GitHub Readme](https://wordpress.org/plugins/github-readme/)

THere are some ways you can use it:
```
[github_readme repo="abacao/abacao.github.io"]
```
With this you can use: trim, branch, and cache (seconds to cache)

Some examples:
```
# Remove the top 3 lines
[github_readme repo="abacao/abacao.github.io/_posts" trim="3"]

# Points to a specific files.
[github_markdown repo="abacao/abacao.github.io/_posts" file="2017-03-08-openstack.md"]
```
