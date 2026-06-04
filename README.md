# From Scratch Automotive Engineering

Jekyll site for publishing Formula Student / FSAE engineering books chapter by chapter.

**Live site:** https://fullnelson14.github.io/from-scratch-auto-engineering/

## What this is

A home for long-form engineering writing aimed at students and teams getting started in Formula Student. Books are released incrementally — only published chapters appear in the sidebar.

**Books**

| Book | Slug | Status |
|------|------|--------|
| *Fundamentals in Formula* | `fundamentals-in-formula` | In progress |
| *Learn in Formula* | `learn-in-formula` | Coming soon |

Weekly writing also goes out on [Substack](https://fsautoeng.substack.com/) (*The Contact Patch*). Community discussion lives on [Hideout](https://enterhideout.app/c/fsae).

## How the site is built

Static Jekyll site using the `github-pages` gem. Content is Markdown; layout is a dark docs-style theme with a left sidebar.

```
_books/          Book overview pages (title, status, order)
_parts/          Optional part groupings within a book (nav only)
_chapters/       Chapter markdown, one folder per book slug
_includes/       Sidebar, footer, book chapter nav
_layouts/        docs (base), book, chapter
assets/css/      Theme styles
_config.yml      Site metadata, collections, social links
_config_dev.yml  Local preview overrides (empty baseurl)
bin/serve        Local dev server with live reload
index.md         Home page
about.md         About the author and series
```

**Collections** — `books` and `chapters` are rendered as pages; `parts` is nav-only metadata. Chapters optionally reference a part via front matter (`part: 1`).

**Local preview** — `./bin/serve` then open http://127.0.0.1:4000/

**Publish** — push to `main`; GitHub Pages builds from the repo root.
