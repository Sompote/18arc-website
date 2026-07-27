# 18ARC — Design Spec ("Earth Strata")

Reusable style summary for the 18th Asian Regional Geotechnical Engineering Conference
site (Bangkok, 15–19 November 2027 · IMPACT Forum, Muang Thong Thani). Direction:
**modern & bold, academic authority** — layered earth strata, warm ink and cream,
terracotta accents. Built for a geotechnical audience: the palette is soil.

Held under the auspices of ISSMGE; hosted by the Thai Geotechnical Society. That
attribution appears in three places — hero sub-badge, About sidebar, footer legal line.

---

## 1. Colors

| Role | Hex | Use |
|---|---|---|
| Ink (primary dark) | `#17130E` | Dark section backgrounds, nav, footer, body text |
| Cream (primary light) | `#F5EFE3` | Page background, text on dark |
| Sand (alt light) | `#EFE6D6` | Alternating light sections (speakers, sponsors), budget badge |
| Terracotta (accent) | `#E07A3E` | CTAs, eyebrows on dark, highlights, current-year cell |
| Clay (accent dark) | `#C85A2B` | Eyebrows/links on light backgrounds, list indices |
| Umber (deep) | `#7A3B22` | Stats strip background, link hover, budget badge text |
| Teal (secondary) | `#1C6E68` | Registration section, session tags, conference-hotel badge |
| Gold (tint) | `#EBD9B8` | Large numerals on dark, hero badge text |
| Pure white | `#FFFFFF` | Cards on cream (program rows, hotels, transit, committee) |
| MRT Pink | `#E4007F` | **Only** in the Pink Line transit diagram — a wayfinding literal, not a brand color |

**Supporting alphas**
- Text on dark: `rgba(245,239,227,.78)` body · `.62` auspices line · `.6` muted · `.45` legal
- Body text on light: `#4a4238` · muted `#6a6156` · caption `#8a8073` · legal `#7d746a`
- Hairlines: `rgba(245,239,227,.12)` on dark · `rgba(23,19,14,.10)` on light · `.14` rules
- Card fill on dark: `rgba(245,239,227,.05)`, border `rgba(245,239,227,.12)`

**Rules**
- Max two background colors competing per screen; alternate ink → cream → sand.
- Terracotta is for action and emphasis only — never a large fill except the one
  "current" highlight (2027 cell, Full Registration tier).
- Teal appears once as a full section, plus the single conference-hotel badge.
- Pink is quarantined to the transit diagram. Never borrow it for UI.

---

## 2. Typography

- **Display:** Archivo — 800/900, tight tracking. Headlines, numerals, logo, buttons.
- **Body:** IBM Plex Sans — 300/400/500/600. Paragraphs, labels, nav.

| Element | Spec |
|---|---|
| H1 hero | Archivo 900 · `clamp(44px, 8vw, 116px)` · line-height .92 · letter-spacing -3px |
| H2 section | Archivo 800 · `clamp(30px, 4.4vw, 52px)` · line-height 1.02 · ls -1.5px |
| H2 theme (feature) | Archivo 800 · `clamp(30px, 5vw, 60px)` · line-height 1 · ls -2px |
| H3 subsection | Archivo 800 · `clamp(24px, 3vw, 36px)` · line-height 1.05 · ls -1px |
| Card title | Archivo 700–800 · 20–24px |
| Eyebrow | 12px · 700 · uppercase · letter-spacing 2px · terracotta/clay |
| Micro-label (badges, transit) | 11–12px · 700 · uppercase · ls 1–1.4px |
| Lead paragraph | 300 · `clamp(16px,1.7vw,21px)` |
| Body | 400 · 17px · color `#4a4238` |
| Meta / caption | 13–14px · muted |
| Big stat numeral | Archivo 900 · 40–46px · ls -2px |

Set `text-wrap: balance` on headlines, `pretty` on paragraphs. Cap measure at
`46–62ch`. Headline max-width `15–18ch`.

---

## 3. Layout & spacing

- Content max-width **1200px** (wide sections) / **1080px** (reading sections).
- Section padding **110px 40px**; compact sections 88px; strips 34px.
- Subsection break inside a section: `margin-top:72px; padding-top:56px` above a
  2px `rgba(23,19,14,.14)` rule (used for Accommodation inside Venue).
- `scroll-margin-top: 88px` on every anchor target (sticky nav clearance).
- Card grids: `repeat(auto-fill|auto-fit, minmax(220–300px, 1fr))`, gap 18–22px.
- Two-column splits: `minmax(0,1.15fr) minmax(0,1fr)`, gap 56–64px.
- **Always flex/grid + `gap`** — never margin-spaced inline siblings.

**Radii:** 12px buttons/tabs · 14px small tiles · 16–18px cards · 20px feature panels ·
`999px` pills, badges and CTAs.

**Borders:** 1px hairline. Emphasis rules 2px solid ink (table headers, subsection rules).

---

## 4. Components

**Sticky nav** — ink at 92% + `backdrop-filter: blur(10px)`, bottom hairline. Wordmark
`18` cream + `ARC` terracotta, with a 2-line uppercase descriptor. Text links at
`rgba(cream,.82)`; one pill CTA in terracotta.

**Hero** — ink background, four stacked layers in this order:
1. full-bleed photo `<img>` (`object-fit:cover`, `object-position:center 58%`);
2. directional scrim `linear-gradient(100deg, .92 → .72 → .22 → .5 ink)` — dark under
   the type, near-clear over the subject on the right;
3. strata lines (`repeating-linear-gradient` every 118/120px at 5% terracotta);
4. ghost numeral `18` at 5% opacity, bleeding off the right edge.

Content order: badge pill → ISSMGE auspices line → H1 → lead → date block +
countdown → two CTAs.

**Countdown** — four tiles, `min-width:74px`, 5% cream fill; the *seconds* tile is
distinguished with terracotta fill/border/text. Numerals Archivo 900/34px. Driven by a
1s `setInterval` on component state.

**Stats strip** — umber band, `auto-fit minmax(160px,1fr)`, gold numeral over a muted
caption. Use it to break two long sections.

**Dark topic card** — 5% cream fill, terracotta index number, title, muted description;
hover lifts to 12% terracotta fill + 40% terracotta border.

**Timeline rows** — `180px 1fr auto` grid, 2px ink top rule, hairline row separators.
Date in clay Archivo, label in 600, status pill on the right. Tags in use: Deadline,
Register, Payment, Event.

**Program tabs** — day buttons flip to ink fill + cream text when active; the panel
below is a white card with `150px 1fr auto` session rows and teal tags.

**Price cards** — three tiers; the featured tier (Full Registration) inverts to a solid
terracotta fill with ink text, others stay cream. Numeral 46px Archivo 900.

**Hotel cards** — white, 18px radius, `auto-fit minmax(300px,1fr)`. Pill badge at top
(teal = conference hotel, sand/umber = budget), Archivo 800/24px name, muted
description, then a clay 13px uppercase footer line pushed down with `margin-top:auto`
so the footers align across cards of unequal height.

**Transit diagram** — white card. Header dot in MRT Pink + uppercase line name, short
paragraph, then a `14px 1fr` grid running vertically: hollow ring (interchange) →
4px pink connector → filled ring (destination), each paired with a station name and a
12px caption. Vertical, not horizontal — it lives in a narrow column.

**History grid** — 18 cells, 2px gaps, 3% cream fill, the current edition flipped to
solid terracotta with ink text. Whole block clipped to 16px radius.

**Photography** — venue mosaic is a 2-col grid: one full-width 200px row (IMPACT Forum
exterior) over two 160px tiles (Wat Arun / Chao Phraya, Yaowarat street food). Real
photos are plain `<img>` with `object-fit:cover`; still-empty slots keep
`<image-slot>` on `#241d15`, 4:5 for portraits.

**Buttons** — pill, 15px/30px padding. Primary: terracotta on ink text, 700.
Secondary: transparent with a 35% cream border.

---

## 5. Images

- Compress every photo before use: longest edge ≤ 1400px, JPEG q ≈ 0.85, target
  **< 450 KB**. A multi-megabyte PNG in the hero stalls first paint.
- Reference photos as project files (`./uploads/name.jpg`) — never base64 data URIs
  inline in the template; large ones fail to decode and bloat the source.
- Always set a meaningful `alt`; always set `object-position` deliberately rather than
  accepting the centre crop.

---

## 6. Motion

Restrained. `transition: .16–.18s` on links, tabs, and card hovers only. Smooth-scroll
anchors. No entrance animations on load; no parallax.

---

## 7. Voice

British-English, institutional but not stiff: "Programme", "Organised by".
Headlines are short declaratives — *"Five days, one field."*, *"Secure your place."*,
*"Stay a walk from the halls."* Eyebrows name the section plainly.
Always flag provisional data in a 14px muted line rather than hiding it.

---

## 8. Reuse checklist

1. Load Archivo (400–900) + IBM Plex Sans (300–600).
2. Set body to cream `#F5EFE3` / ink `#17130E`; define `a` and `a:hover` as clay/umber.
3. Alternate section backgrounds ink → cream → sand; one teal section only.
4. Eyebrow + H2 + lead opens every section, no exceptions.
5. Reserve terracotta for CTAs and the single "current" highlight.
6. Repeat the strata gradient on any full-dark section for continuity.
7. Any photo behind type needs a directional scrim, not a flat overlay.
8. Compress before placing; check the page still paints in about a second.
