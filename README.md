# Find a Research Software Engineer

This is a search portal to search across the community sites (those that
start with community-*) for the [usrse GitHub](https://www.github.com/usrse) 
organization.

## How does it work?

Each community site serves metadata at a data.json served from the root. Using
this data, we use the GitHub API to first get organization names, filter
to those that start with community, and then obtain the data.json for each.
While this is created to help search across research software engineers, 
you could easily adopt this strategy to work for a general search for your GitHub
organization.
