# plonkit-img

Image assets for the TestGuessr autoplay/meta userscript, served via
[jsDelivr](https://www.jsdelivr.com/) from this public GitHub repo.

## Structure

```
images/
  extended-meta/<country>/<slug>.jpg   — Extended Meta pole/tell photos, by country code
  japan-meta/<slug>.jpg                — Japan-specific region meta photos
  license-plates/<country>/<slug>.jpg  — State/province flag icons for the license-plate reference
  useful-info/<slug>.jpg               — Misc reference images (US/CA plate maps, etc.)
```

## Usage in the script

Each image is referenced as:

```
https://cdn.jsdelivr.net/gh/Lovionov/plonkit-img@main/images/<path>.jpg
```

## Updating an image

jsDelivr caches files from the `@main` branch for up to ~7 days (sometimes
faster, but don't rely on it). If you replace an image and need the CDN to
pick it up immediately:

1. Commit and push the new file as usual.
2. Purge the jsDelivr cache for that exact file:
   `https://purge.jsdelivr.net/gh/Lovionov/plonkit-img@main/images/<path>.jpg`
   (open that URL in a browser, or curl it — it returns a small JSON status).

Alternatively, reference a specific commit hash instead of `@main` in the
script for guaranteed-fresh, immutable URLs (trade-off: you'd need to update
every URL in the script each time you change an image).
