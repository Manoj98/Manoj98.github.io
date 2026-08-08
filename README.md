# manojparmar.dev: Personal Portfolio

Personal portfolio site for Manoj Parmar, Senior AI/ML Engineer. Built as a single-page
site with plain HTML/CSS/JS (no build step), targeting AI/ML Engineer, Forward Deployed
Engineer, and Applied Scientist roles.

## Structure

```
index.html          Single-page site (About, Experience, Projects, Skills, Leadership, Resume, Contact)
css/style.css        Styling: light/dark theme via CSS custom properties
js/main.js           Theme toggle, scroll-spy nav, reveal-on-scroll, stat counters
assets/
  Manoj_Parmar_Resume.pdf   Downloadable / embedded resume
  images/                    Headshot (two sizes) + favicon
reference/            Original source files, kept locally only (gitignored)
```

## Local development

No build step, just serve the folder statically, e.g.:

```
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Deployment (GitHub Pages)

This repo is named `Manoj98.github.io`, which GitHub treats as a user site: pushing to
`main` publishes automatically at **https://Manoj98.github.io**, no Pages configuration
needed.

To point a custom domain at it later: add a `CNAME` file with the domain, then configure
your registrar's DNS (A records to GitHub's IPs or a CNAME record to `manoj98.github.io`),
and set the domain under repo **Settings → Pages**.

## Updating the resume or headshot

Both are referenced with a `?v=N` cache-busting query string (e.g. `Manoj_Parmar_Resume.pdf?v=2`)
in `index.html`. Browsers cache PDFs and images aggressively, so whenever you swap either file
for a new version under the same filename, bump `v` in every reference to it, otherwise visitors
may keep seeing the old cached copy.
