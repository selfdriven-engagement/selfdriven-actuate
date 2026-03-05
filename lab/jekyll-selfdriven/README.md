# selfdriven Foundation — Areas of Focus

Jekyll site for the selfdriven Foundation's Eight Areas of Focus framework.

## Structure

```
.
├── _config.yml          # Jekyll config
├── _data/
│   └── areas.yml        # All 8 area definitions (title, subtitle, tagline, body)
├── _layouts/
│   └── default.html     # Base layout (nav, CSS, JS, footer)
├── assets/
│   └── img/
│       └── selfdriven-logo.png   # ← Place your logo here
├── index.md             # Homepage with hero, grid, detail panel
└── Gemfile
```

## Setup

1. Add your logo at `assets/img/selfdriven-logo.png`
2. Install dependencies: `bundle install`
3. Serve locally: `bundle exec jekyll serve`
4. Visit: `http://localhost:4000`

## GitHub Pages

Push to a repo named `areas-of-focus` (or update `baseurl` in `_config.yml`).
Enable GitHub Pages in the repo settings (branch: `main`, folder: `/` root).

## Customisation

- **Area content**: Edit `_data/areas.yml` — changes propagate to grid, detail panel, and flow row automatically.
- **Navigation links**: Edit the `<ul class="nav-links">` in `_layouts/default.html`.
- **Colours**: Edit CSS custom properties in `:root` and the dark-mode `@media` block.
- **Add pages**: Create new `.md` files with `layout: default` front matter.
