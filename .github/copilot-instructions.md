# Repository instructions

This is a small Jekyll academic website. Keep the active architecture intentionally narrow.

## Commands

- Install: `bundle install` and `npm ci`
- Serve locally: `bundle exec jekyll serve`
- Production build: `JEKYLL_ENV=production bundle exec jekyll build`
- Format check: `npm run format:check`
- Check one file: `npx prettier <path> --check`

There is no unit-test suite. A production Jekyll build is the primary integration check.

## Active architecture

- `_pages/about.md` is the home page.
- `_pages/publications.md` renders `_bibliography/papers.bib` through `_layouts/bib.liquid`.
- `_news/` supplies the compact update list on the home page.
- `_includes/header.liquid` contains the complete navigation: Home, Publications, and a direct CV download.
- `assets/css/main.scss` is the only site stylesheet. Keep all visual changes there; do not reintroduce Bootstrap, MDB, JavaScript theme frameworks, or Sass partial trees.
- The site intentionally loads no JavaScript.

## Conventions

- Keep public routes limited to `/`, `/publications/`, and `/404.html` unless a new page is explicitly requested.
- Replace `assets/pdf/cv_anglais.pdf` to update the downloadable CV; do not recreate a CV page.
- Add publications only in `_bibliography/papers.bib`. Preview filenames resolve under `assets/img/publication_preview/`.
- Add updates as dated Markdown files in `_news/` with `inline: true`.
- Use semantic HTML and native elements such as `<details>` before adding scripts.
- Preserve the restrained visual system and the small inline SVG profile icons; do not add an icon font or external icon library.
