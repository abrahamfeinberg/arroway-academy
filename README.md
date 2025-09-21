# Arroway Academy

A Jekyll-based static site for Arroway Academy, deployed via GitHub Pages.

## Development

### Prerequisites
- [Ruby](https://www.ruby-lang.org/) (via Homebrew)
- [Bundler](https://bundler.io/)
- [Jekyll](https://jekyllrb.com/)

### Run locally
Serve with production + local config:

```bash
bundle exec jekyll serve --config _config.yml,_config.local.yml
````

Open [http://127.0.0.1:4000/](http://127.0.0.1:4000/)

### Project structure

* `_config.yml` — production config (GitHub Pages)
* `_config.local.yml` — local overrides (`url`, `baseurl`)
* `index.md`, `about.md` — example pages
* `_posts/` — dated blog posts
* `_layouts/` — HTML templates
* `_includes/` — reusable snippets

## Deployment

* Site is deployed automatically via GitHub Pages.
* URL: [https://abrahamfeinberg.github.io/arroway-academy/](https://abrahamfeinberg.github.io/arroway-academy/)

Changes to `main` are rebuilt and published within \~2 minutes.
