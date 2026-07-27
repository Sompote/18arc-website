# 18ARC — Conference Website

Website for the 18th Asian Regional Conference on Soil Mechanics and
Geotechnical Engineering (18ARC), Bangkok, 15–19 November 2027.
Hosted by the Thai Geotechnical Society with EIT, under the auspices of ISSMGE.

**Live site:** https://sompote.github.io/18arc-website/

## Structure

- `index.html` — the whole site (single page). Markup, styles, and the
  countdown/timeline logic in the `data-dc-script` block at the bottom.
- `support.js`, `image-slot.js` — rendering runtime; do not edit.
- `uploads/` — photos and logos (keep each under ~450 KB).
- `18ARC-design-spec.md` — the "Earth Strata" design system reference.

## Editing

Edit `index.html` directly, then:

```bash
git add -A && git commit -m "describe the change" && git push
```

GitHub Pages redeploys automatically ~30 seconds after each push.
