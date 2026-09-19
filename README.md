# BRÖDBREAD — link-in-bio

Single-file static site for BRÖDBREAD, a homemade sourdough micro-bakery in Thailand.
Hand-drawn, retro-doodle link-in-bio page (Instagram/Facebook bio link), bilingual
English / Thai: scrolling marquee, social icon buttons, "what is sourdough?" modal,
"this week's menu" teaser panel, and sourdough-care accordions.
One `index.html`, no build step, no external JS. Fonts (Schoolbell, Playpen Sans Thai)
via Google Fonts CDN.

## Local preview

```sh
python3 -m http.server 8137
# open http://localhost:8137
```

## Deploy (Cloudflare Pages)

- **Build command:** none
- **Build output directory:** `/` (repo root)
- Framework preset: None
- `_headers` at the repo root sets security headers and caching
  (`index.html` no-cache, `bread.*` long immutable cache)

`bread.png` must stay at the repo root — it is referenced by the Open Graph tags
and serves as the `<img>` fallback for `bread.webp`.

## Content placeholders

The design ships with placeholders to fill in before going live:

- Phone number: the call button is `tel:+66000000000`
- Ferment time: the about modal says `[YOUR FERMENT TIME]`
- Image slot: the about modal has a `[ IMAGE — starter jar, or a crumb shot ]` placeholder
