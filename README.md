# nicksawhney.github.io/me

My personal site. Hand-written static HTML and CSS — no framework, no build
step, no JavaScript.

## Structure

```
index.html        the whole site, one page
css/site.css      the whole stylesheet
fonts/            self-hosted woff2 (Inter variable, IBM Plex Serif 600)
images/           WebP with JPEG fallbacks
```

## Working on it

There is nothing to install and nothing to compile. Edit the files and open
`index.html`, or serve the directory if you want correct relative paths:

```sh
python3 -m http.server 8000
```

## Deploying

GitHub Pages serves the `main` branch from the repo root. Pushing to `main`
publishes. `.nojekyll` tells Pages to copy files straight through rather than
running them through Jekyll.

Because this is a *project* page served from `/me/`, all asset paths must stay
relative (`css/site.css`, never `/css/site.css`).

## Images

Re-encode with Pillow; keep originals out of the repo. Targets are WebP with a
JPEG fallback, `width`/`height` on every `<img>`, and `loading="lazy"` on
anything below the fold.
