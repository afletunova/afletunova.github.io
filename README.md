# afletunova.github.io

Personal blog. Hugo + PaperMod theme. Deployed via GitHub Pages.

## Stack

- **Hugo** ≥ 0.146.0
- **Theme:** PaperMod (vendored in `themes/PaperMod/`)
- **Custom layouts:** `layouts/` (overrides theme; never edit `themes/` directly)
- **Custom CSS:** `assets/css/extended/` (auto-loaded by PaperMod on top of theme styles)

## Local dev

```bash
hugo server -D        # includes drafts
hugo server           # production-like, drafts excluded
```

Runs at `http://localhost:1313`.

## Structure

```
content/posts/<slug>/index.md   — page bundles (one dir per post)
content/featured/_index.md      — stub for /featured/ page
layouts/baseof.html             — two-column grid (main + sidebar)
layouts/_partials/sidebar.html  — featured block (top 5 weighted posts)
layouts/featured/list.html      — /featured/ full list
assets/css/extended/
  theme.css                     — color tokens, light/dark
  intro.css                     — homepage intro block
  sidebar.css                   — grid layout, sidebar, /featured/ styles
```

## Frontmatter template

```yaml
---
title: ""
date: YYYY-MM-DD
draft: false
tags: []
languages: ["russian"]   # or "english" — drives the language taxonomy
description: ""
# weight: N              # omit if not featured; 1 = top of featured list
# cover:
#   image: cover.jpg
#   alt: ""
#   caption: ""
---
```

## Publication checklist

Before setting `draft: false`:

- [ ] **Language** — `languages: ["russian"]` or `languages: ["english"]` (one value, not both)
- [ ] **Tags** — at least one; reuse existing tags where possible (see `/tags/` in dev server)
- [ ] **Description** — one sentence, shown in post card on the list page
- [ ] **Date** — set explicitly; controls feed order
- [ ] **Featured?** — add `weight: N` if the post should appear in the sidebar and `/featured/`
  - Current featured order: EEO (1) · стало так плохо (2) · You Are Not Inclusive (3)
  - Lower number = higher in the list; existing posts may need renumbering if you insert
- [ ] **Cover image** — optional; place as `cover.jpg` in the post bundle dir
- [ ] **Draft off** — flip `draft: false` (or remove the field)
- [ ] **Build check** — run `hugo server` and confirm the post appears, sidebar is correct

## Deploying

Push to `main`. GitHub Actions (or Pages) picks it up automatically.

```bash
git add content/posts/<slug>/
git commit -m "publish: <post title>"
git push
```
