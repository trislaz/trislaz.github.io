# trislaz.github.io

Personal academic website built with Jekyll.

## Common edits

| Change                             | File                                                              |
| ---------------------------------- | ----------------------------------------------------------------- |
| Home-page text                     | `_pages/about.md`                                                 |
| Publications                       | `_bibliography/papers.bib`                                        |
| Publication thumbnails             | `assets/img/publication_preview/`                                 |
| News items                         | `_news/`                                                          |
| Profile photo                      | `assets/img/prof_pic.jpg`                                         |
| Downloadable CV                    | `assets/pdf/cv_anglais.pdf`                                       |
| Colors, typography, and layout     | `assets/css/main.scss`                                            |
| Header, profile links, and CV link | `_includes/header.liquid`, `_layouts/about.liquid`, `_config.yml` |

The public site has only three routes: `/`, `/publications/`, and `/404.html`. The CV is linked directly as a PDF.

## Local development

Install Ruby 3.2+, Bundler, and Node.js, then run:

```bash
bundle install
npm ci
bundle exec jekyll serve
```

Open `http://localhost:4000`.

Build the production site with:

```bash
JEKYLL_ENV=production bundle exec jekyll build
```

Check formatting with:

```bash
npm run format:check
```

GitHub Actions deploys `master` to GitHub Pages.
