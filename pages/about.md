---
layout: page
title: About the USRSE Community
description: About the USRSE Community
permalink: /about/
---

This is a search portal to search across the Research Software Engineer
community sites for the [usrse GitHub](https://www.github.com/usrse) 
organization.

## How does it work?

Each community site serves metadata at a data.json served from the root. Using
this data, we use the GitHub API to first get organization names, filter
to those that start with community, and then obtain the data.json for each.
Since they are served from a common GitHub oranization URL, we don't run
into issues with requesting data across origins.

While this is created to help search across research software engineers, 
you could easily adopt this strategy to work for a general search for your GitHub
organization. If you have questions or suggestions, please [open an issue]({{ site.repo }})
