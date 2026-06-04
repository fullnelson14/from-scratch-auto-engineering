# Formula Student Series

Engineering books on building race cars from scratch, published chapter by chapter on GitHub Pages.

## Folder structure

```
.
├── _books/                 # One file per book (overview page + metadata)
├── _chapters/
│   └── book-slug/          # One folder per book; chapters live inside
├── _config.yml             # Site settings
├── _includes/
│   └── sidebar.html        # Left navigation
├── _layouts/
│   ├── docs.html           # Base layout with sidebar
│   ├── book.html           # Book overview pages
│   └── chapter.html        # Chapter pages with prev/next links
├── assets/css/
│   └── style.css           # Dark docs theme
├── about.md                # About the site
└── index.md                # Home page
```

## Adding a book

Create `_books/your-book-slug.md`:

```yaml
---
title: Your Book Title
subtitle: Short description shown on cards and overview
status: in-progress   # or coming-soon
order: 3              # sidebar sort order
---
```

Overview content goes below the front matter. Use `status: coming-soon` for books you haven't started — they'll appear in the sidebar without chapters.

## Adding a chapter

Create a file inside the book's folder, e.g. `_chapters/your-book-slug/02-your-chapter.md`:

```yaml
---
title: Your Chapter Title
chapter: 2
---
```

The folder name must match the book's `_books/` filename (without `.md`). Each book gets its own folder, so you can reuse titles like "Introduction" across books without conflict.

The chapter shows up in the sidebar under that book automatically. Only create files for chapters you've published — nothing else is required.

## Local preview

```bash
bundle install
chmod +x bin/serve   # once
./bin/serve
```

Open the site via the **globe icon** in Cursor's **Ports** tray (recommended), or **http://127.0.0.1:4000/** from inside WSL.

The server uses **live reload** — when you save a file, wait for `...done in X seconds` in the terminal; the browser refreshes automatically. Avoid manual refresh during that window (it can load a half-built page and cache a missing CSS file, which looks like styles vanishing).

If styles ever stick broken: **Ctrl+Shift+R** once, then rely on live reload again.

Use `./bin/serve` (not plain `jekyll serve`). The `github-pages` gem keeps the production `baseurl` unless `_config_dev.yml` is passed on the command line.

### Cursor / WSL port forwarding

Jekyll listens on **port 4000 inside WSL**. The Ports tray entry like `4000 → 4001` means Windows **localhost:4001** tunnels to WSL **4000** — not a second Jekyll process. Always open the site with the Ports **globe icon** so the URL matches the tunnel.

Live reload also uses port **35729**; Cursor should forward it automatically when detected.

```bash
pkill -f "jekyll serve"   # stop stale servers
./bin/serve
```

## Publish

Push to `main` and enable GitHub Pages from the repo root (**Settings → Pages**).

Site URL: `https://fullnelson14.github.io/from-scratch-auto-engineering/`
