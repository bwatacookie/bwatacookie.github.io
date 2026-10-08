# bwatacookie.github.io

Studio site for Bwatacookie Studio, served by GitHub Pages at
<https://bwatacookie.github.io/>.

## Why the repo is named this

A repo named `<username>.github.io` is published at the **root** of the
domain. Any other name publishes under `/<repo-name>/`, a subpath — and
`app-ads.txt` only counts when it sits at the domain root, because that is
where AdMob's crawler looks. So the name is load-bearing; don't rename it.

## Contents

| File | Purpose |
| --- | --- |
| `index.html` | Studio landing page and the game list |
| `site.css` | Shared design system: tokens, page chrome, document layout |
| `privacy.html` | Privacy policy — covers every app the studio publishes |
| `terms.html` | Terms of use — same scope |
| `app-ads.txt` | AdMob publisher authorisation (must stay at the root) |
| `.nojekyll` | Skips GitHub's Jekyll build; these are plain static files |

Keep `privacy.html` and `terms.html` in sync with the copies bundled in each
game (for Ball Journey: `lib/ui/legal_screen.dart`) and with
`store/publisher-pages/` in the game repo.

## Publishing

GitHub Pages serves whatever is on the default branch:

```bash
git add -A && git commit -m "Update site" && git push
```

First-time setup, once the repo exists on GitHub:

```bash
git init -b main
git remote add origin https://github.com/bwatacookie/bwatacookie.github.io.git
git add -A
git commit -m "Studio site: games, legal pages, app-ads.txt"
git push -u origin main
```

Then in the repo's **Settings → Pages**, set the source to `main` / `/ (root)`.
The site is live a minute or two later.

## Game art

Each game's key art is inline SVG, not an image file — crisp at any size, no
extra requests, and it can't render as a broken-image box. Replace it with a
real screenshot whenever you have one worth showing.

## Open items

- `index.html`: Pixel Breakers' store button is a disabled "Coming soon".
  Swap in the real store URL and remove `aria-disabled="true"`.
- Ball Journey's Play Store link assumes the package id
  `com.games.ball_journey`; it 404s until the listing is public.
