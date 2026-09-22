# aks_docs

Documentation site for the **POS Kitchen Display (KDS)** Odoo module
([`abichinger_kitchen_screen`](https://apps.odoo.com/apps/modules/19.0/abichinger_kitchen_screen)).

Built with [MkDocs](https://www.mkdocs.org/) and
[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

## Requirements

- Python 3.14 (see `.python-version`)
- `mkdocs-material` and `mkdocs-glightbox`

## Setup

```sh
python -m venv .venv
source .venv/bin/activate
pip install mkdocs-material mkdocs-glightbox
```

## Preview locally

```sh
mkdocs serve
```

The site is served at <http://127.0.0.1:8000> and reloads on every change.

## Build

```sh
mkdocs build
```

The output is written to `site/`. Add `--strict` to fail the build on warnings.

## Project layout

```
mkdocs.yml          # Site configuration
docs/               # Markdown sources
  index.md          # Home
  demo.md           # Demo
  troubleshooting.md
  release-notes.md
  guide/            # How-to guides
  assets/           # Images and screenshots
  stylesheets/      # Custom CSS (KDS color scheme)
includes/           # Reusable snippets (links.md)
overrides/          # Theme overrides
site/               # Build output (git-ignored)
```

## Writing conventions

- Use `**bold**` for UI labels, for example **Point of Sale ‣ KDS**.
- Use admonitions (`!!! note`, `!!! tip`, `!!! warning`) instead of blockquotes.
- Use card grids (`<div class="grid cards" markdown>`) for feature overviews.
- Add screenshots as `![Alt text](assets/screenshots/name.png)` with a caption.