# BRÖDBREAD — link-in-bio

Single-file static site for BRÖDBREAD, a homemade sourdough micro-bakery in Thailand.
Linktree-style bio page (Instagram/Facebook bio link) with a liquid-glass design:
one `index.html`, no build step, no external JS. Fonts via Google Fonts CDN.

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
