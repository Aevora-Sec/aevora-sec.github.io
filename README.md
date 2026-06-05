# Aevora Security — site

Static, dependency-free website (no build step, no external CDNs/fonts → private,
offline-capable, instant on GitHub Pages). Three pages + one stylesheet.

```
index.html       hero + one number + what makes Aevora different
benchmark.html   the honest policy-gate numbers + reproduce command
about.html       thesis, two layers, principles, contact
styles.css       dark, responsive, self-contained
```

## Preview locally

Just open `index.html` in a browser, or serve it:

```bash
python -m http.server 8000   # then visit http://localhost:8000
```

## Deploy to GitHub Pages (free, when ready — GATED)

Option A — **org/user pages** (serves at `https://aevora-sec.github.io`):
1. Create a public repo named exactly `aevora-sec.github.io` under the `Aevora-Sec` org.
2. Push these files to `main`. Pages builds automatically.

Option B — **project pages** (serves at `https://aevora-sec.github.io/site`):
1. Create a public repo (e.g. `site`), push these files.
2. Repo → Settings → Pages → Source = `main` / root.

Commit identity (repo-scoped, keeps the brand isolated):
```bash
git init
git config user.name  "Aevora"
git config user.email "<your Aevora GitHub noreply email>"   # NOT a personal/BTC-linked address
git add . && git commit -m "feat: Aevora Security site skeleton"
git branch -M main
git remote add origin https://github.com/Aevora-Sec/aevora-sec.github.io.git
git push -u origin main
```

## Custom domain (optional, later)

Buy a domain (e.g. Hetzner/Namecheap, ~€10–15/yr). Add a `CNAME` file containing the
domain, point a DNS `CNAME`/`A` record at GitHub Pages, then set it in Settings → Pages.
A German/EU registrar reinforces the EU-sovereign positioning.

## Editing

- Numbers live inline in `benchmark.html` / `index.html`. Keep them in sync with the
  [`policy-gate-bench`](https://github.com/Aevora-Sec/policy-gate-bench) results and always
  cite the corpus SHA + date (honest-numbers rule).
- A `/blog` section is the next addition (Phase 1) — at that point consider migrating to a
  generator (Hugo/Astro). The draft post "I built an AI that found bugs in its own code" is ready to adapt.
