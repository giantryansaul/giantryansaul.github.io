# Ryan Saul

Personal site for Ryan Saul

# To-Do list

- [ ] Create a simple blog site
- [ ] Apply new layout and style to the site
- [ ] Register new domain and connect with the site

# Development

## Build locally via Docker

```bash
docker run --rm --volume="$PWD:/srv/jekyll" -it jekyll/jekyll jekyll build
```

## Serve locally via Docker

```bash
docker run --rm --name giantryansaul --volume="$PWD:/srv/jekyll" -p 4000:4000 -it jekyll/jekyll jekyll serve --watch --drafts
```