# Visual Design Directions

Two designer agents each produced an independent, fully-realized visual direction — briefed with the same brand constraints (bright, white/off-white base, pink + purple accents) and the findings in [`RESEARCH.md`](RESEARCH.md), but told not to converge with each other. This document is the full written spec for both (source of truth for exact hex values, type scales, and component rules). The corresponding visual mockups (style guide + homepage + gallery for each direction, side by side) live on the **[Design canvas](https://claude.ai/artifact/ChQGpoHeDz7vHo8xWqfmZu)**.

**Decision: Direction A ("Soft & Painterly") has been chosen.** Direction B stays below for reference. Two things were added on top of the original spec after that decision — both apply to Direction A only:

- **A Teacher Gallery**, alongside the Student Gallery: a separate page structured by instructor (a short bio block per teacher, then a row of their own pieces), distinct from the student-work grid — this was "Could have" territory in `BACKLOG.md` §3.6 ("instructor's own portfolio samples, clearly distinguished from the student gallery") and is now a confirmed page, not just a nice-to-have.
- **Motion and interaction**: sections reveal with a subtle scroll-linked fade/rise (CSS `animation-timeline: view()`, no JavaScript required — degrades gracefully to a normal one-time fade-in on browsers that don't support it) rather than appearing all at once; and the homepage carries a small collage of gallery-piece thumbnails tucked into its edges at a few scroll depths, their order shuffled client-side on each load, each linking through to that piece's Artwork Detail page. Neither changes the palette/type/component rules below — they're additions to the existing system, not a new one.

The [Design canvas](https://claude.ai/artifact/ChQGpoHeDz7vHo8xWqfmZu) now carries both: the original static comparison artboards (style guide + homepage + gallery, ×2 directions) AND a live, clickable Direction A prototype (Home, Classes, Student Gallery, Teacher Gallery, About, Contact, Artwork Detail) built on this spec.

---

# Direction A — "Soft & Painterly"

A sunlit studio, not a museum. Leans into watercolor-blob backgrounds, rounded soft-edged UI, hand-drawn accents, and warm candid photography — built for first-time hobbyists, parents booking a kid's class, and casual gallery browsers who'd feel cold in anything slick or gallery-white.

## 1. Palette

| # | Name | Hex | Role |
|---|------|-----|------|
| 1 | Sunlit White | `#FFFCF7` | Primary page background — warm off-white, never stark |
| 2 | Petal Blush | `#F8D9E6` | Pale pink — organic blob shapes, soft section washes, inactive filter-chip fill |
| 3 | Watercolor Pink | `#F0A8C9` | Mid pink — badges, tags, icon fills, card hover borders |
| 4 | Berry Blossom | `#C23E7A` | Saturated pink — primary button fill (white text), links, active states |
| 5 | Lilac Wash | `#E6DAF5` | Pale purple — organic blob shapes (alternates with Petal Blush for rhythm), secondary washes |
| 6 | Orchid | `#B78BDE` | Mid purple — secondary accents, icons, hover tints |
| 7 | Deep Iris | `#7B4FA0` | Saturated purple — secondary/outline button fill, focus rings |
| 8 | Charcoal Plum | `#3B2F38` | Primary reading text (headlines + body); also the footer's dark anchor background |
| 9 | Deep Berry | `#6B2545` | Alternate deep text — pull-quotes, headline text set directly on a pastel blob |

**Accessibility (computed):** Charcoal Plum on Sunlit White ≈ 12.4:1; Deep Berry on Sunlit White ≈ 10.4:1; white text on Berry Blossom ≈ 4.9:1 (passes AA); white text on Deep Iris ≈ 6.1:1. Petal Blush, Watercolor Pink, Lilac Wash, and Orchid are **background/shape/chip fills only — never text color**. Shadows use Charcoal Plum at low opacity, never pure black.

Pure `#FFFFFF` may be used for card surfaces sitting on the page background for gentle layering — not a core palette color.

## 2. Typography

**Display: Fraunces** (variable) · **Body: Nunito Sans** (variable)

Fraunces' variable SOFT axis lets letterforms go gently rounded rather than crisp-editorial, and its italic has a loose, brush-like flow well-suited to quotes and warm emphasis. Body deliberately avoids Inter (reads as default SaaS-product font) in favor of **Nunito Sans**, whose rounded terminals echo Fraunces' softness. Optional accent-only face **Caveat** (handwriting-style) for tiny hand-labeled elements only, never headings or body.

Fallback stacks: `'Fraunces', Georgia, serif` / `'Nunito Sans', 'Segoe UI', sans-serif`

| Level | Font / settings | Weight | Desktop | Mobile | Usage |
|---|---|---|---|---|---|
| H1 | Fraunces, opsz 72–144, SOFT ~50 (occasional italic emphasis word) | 600 | 60px / 1.05 lh | 38px / 1.15 lh | Hero headline only — one per page |
| H2 | Fraunces, opsz ~48, SOFT ~40 | 600 | 40px / 1.15 lh | 28px / 1.2 lh | Section titles |
| H3 | Fraunces, opsz ~28, italic for card/quote variants | 500 | 26px / 1.25 lh | 21px / 1.3 lh | Class/gallery card titles, subsection heads |
| Body | Nunito Sans | 400 (500 emphasis) | 18px / 1.6 lh | 16px / 1.6 lh | Paragraphs, descriptions, form help text |
| Button / nav label | Nunito Sans, +0.01–0.02em tracking | 600 | 16–17px | 15px | Buttons, nav links |
| Caption / meta / chip | Nunito Sans (italic for captions) | 400–500 | 14px / 1.4 lh | 13px / 1.4 lh | Gallery hover captions, class meta, filter chips |

## 3. Layout concept

**Grid foundations:** content max-width ~1280px, centered; gutters 24px mobile / 40–64px desktop; base spacing unit 8px.

**Recurring motif — the blob layer:** every section below the hero sits on 1–2 soft organic blob shapes (Petal Blush / Lilac Wash alternating), 40–70% opacity, blurred edge, bleeding off at least one viewport edge. Content always sits on top. Never more than two blobs per viewport.

**Homepage (top → bottom):** transparent nav over hero (dark scrim, "Book a Class" pill always visible) → full-bleed ~90vh hero photo with warm-white bottom scrim, H1 + one emphasis word in italic with a hand-drawn wavy underline, one primary CTA + secondary text link ("See the Gallery →") → short centered welcome strip → "Classes This Month" preview (Lilac blob behind a row of 3–4 class cards) → "From Our Students" gallery teaser (loose offset grid, a couple of tilted/larger frames like a corkboard, Petal Blush blob peeking) → About/Instructor teaser (Petal Blush full-width band, two-column photo + bio) → centered italic pull-quote testimonial directly on a Lilac blob, no card → footer.

**Gallery:** header band with a blob peeking behind the heading → pill filter chips by medium (Petal Blush inactive / Berry Blossom active) → clean, aligned masonry grid (4 cols desktop, white photo-mat cards, 16px radius, soft shadow, hover reveals medium + class name/date caption, no price, no tilt — calmer than the homepage teaser) → lightbox with "Reserve a spot in this class →" CTA → centered "Load More Work" ghost button.

**Class Listings:** same blob-behind-heading header → identical filter-chip system → card grid over 1–2 background blobs; each card: 4:3 photo with an overlapping badge ("BEGINNER FRIENDLY" / "FEW SPOTS LEFT"), eyebrow medium label, H3 title, meta row, quiet price line, primary "Reserve Your Spot" button; sold-out variant desaturates the photo and switches to an outline button.

**Other pages (brief):** Class Detail reuses the card photo/badge/meta language at larger scale plus the enrollment-form styling. About/Instructor extends the homepage teaser into a full bio layout. Contact pairs the form styling with the footer's map/hours block promoted into the page body. Admin upload (conceptual only): calmer, no blobs/doodles, single-column form with the same rounded inputs, a dashed-border drag-and-drop zone, and a thumbnail row with inline metadata fields.

## 4. Component styling

- **Primary button:** full pill (`radius: 999px`), Berry Blossom fill, white text, soft colored shadow; hover darkens + lifts 2px; focus ring in Deep Iris.
- **Secondary/outline:** 2px Deep Iris border, transparent fill; hover fills Lilac Wash.
- **Ghost/text link:** hand-drawn wavy underline that draws in on hover.
- **Chips/badges:** pill, tracked uppercase; inactive = Petal Blush fill + Deep Berry text, active = Berry Blossom fill + white text.
- **Class card:** white surface, `radius: 24px`, no hard border, ambient warm shadow deepening on hover, card lifts 6px, photo scales 1.03×.
- **Gallery item:** white photo-mat, `radius: 16px`, image `8px` radius, loose Polaroid proportions; slight rotation only in the homepage teaser, never in the strict Gallery grid.
- **Nav:** transparent-over-hero → crossfades to solid Sunlit White with soft shadow on scroll; wavy-underline hover; mobile = full-screen overlay with a blob behind large centered links.
- **Forms:** white card (`radius: 24–32px`) with one blob peeking from a corner (never behind inputs); inputs `radius: 14–16px`, 1.5px warm-gray border, label above field; focus = Berry Blossom/Deep Iris border + soft glow; errors in warm terracotta, never harsh red; class picker rendered as mini class cards, not a plain `<select>`; success state shows a hand-drawn checkmark/paint-splatter icon.
- **Footer:** full-width Charcoal Plum background (the one deliberate dark anchor), fine grain + a faint Orchid blob at one edge; 4 columns (Logo/social, Visit Us + map, Hours, Get in Touch).

## 5. Imagery & texture

Warm color grading (lifted shadows, amber white balance, natural/golden-hour light), candid over posed. Cropping is a soft-rounded rectangle (24–32px radius); one blob-masked (irregular) photo allowed per page as a special moment. A single consistent hand-drawn SVG line (imperfect, ~3–4px stroke) supplies underline flourishes, small motif icons, dividers, and a sparkle/checkmark on success states — one sprite set, not mixed clipart. Fine film-grain (4–6% opacity, overlay/soft-light blend) sits on flat pastel blobs and color bands only — never on photographs or small UI chrome — so pastels read as gouache/watercolor paper, not flat vector fills.

## 6. Mood

Bloom & Brush should feel like walking into a sunlit studio on a Saturday morning — paint-smudged tables, someone's kid proudly holding up a lopsided but beautiful bowl — never a sterile online gallery or a corporate workshop booking. Soft watercolor blobs bleed gently behind crisp white cards, hand-drawn underlines and paint-splatter doodles hint that a real person built this, and every corner is rounded just enough to feel touched rather than templated.

---

# Direction B — "Bold & Modern Gallery"

Design point of view in one line: **this is a small independent gallery that happens to teach — not a craft-corner storefront.** Hard-edged geometric color blocking over organic blobs, big didone display type over friendly rounded type, a strict curatorial grid over loose masonry, real photography doing the emotional work instead of decorative texture.

## 1. Palette

| Hex | Name | Role |
|---|---|---|
| `#FFFFFF` | Pure White | Primary background; gallery grid negative space; card surfaces |
| `#F4EFE9` | Gallery Bone | Warm off-white; alternate section background |
| `#E01166` | Flash Pink | Primary accent — CTA button fill, hero color panel, largest graphic blocks |
| `#B83374` | Rose Magenta | Secondary pink — button hover/active, secondary blocks, safe as small accent-color text on white |
| `#F6D2E3` | Blush Tint | Pastel pink — background tints, badge fills, section washes. **Backgrounds/shapes only — never text** |
| `#6D28D9` | Signal Violet | Primary purple accent — secondary CTA fill, links, icons, focus/checked states |
| `#E3D6F9` | Lavender Tint | Pastel purple — alternating section washes. **Backgrounds/shapes only — never text** |
| `#1B1420` | Ink Black | Near-black, plum-tinted charcoal — primary body copy & headline text |
| `#5C1A44` | Deep Berry | Alternate reading text — pull-quotes, editorial emphasis |

**Verified contrast (WCAG AA normal text needs ≥4.5:1):** Ink Black on White 17.99:1 / on Gallery Bone 15.73:1. Deep Berry on White 12.45:1 / on Gallery Bone 10.89:1 / on Blush Tint 9.04:1 / on Lavender Tint 9.05:1. White text on Flash Pink 4.73:1, on Rose Magenta 5.58:1, on Signal Violet 7.10:1 — all pass. Flash Pink/Rose Magenta/Signal Violet also work as small accent-color text on white (contrast is symmetric). The two pastel tints are quarantined to backgrounds/shapes only.

## 2. Typography

**Display: Bodoni Moda** (variable, true italic) · **Body/UI: Archivo** (variable, Expanded width available)

A genuine high-contrast didone — deliberately *not* Playfair Display or Fraunces (the two "safe" pairings) — reads fashion-magazine-masthead / art-book-cover, matching the premium-editorial-gallery register, and photographs dramatically at large sizes. Archivo is the calm counterweight: a neutral mechanical grotesque that doesn't compete with the artwork photography. Used in Expanded width + uppercase + wide tracking for nav/buttons/labels, it reads like museum wall signage next to the huge expressive headlines — the core typographic "move" of this direction.

Fallback stacks: `'Bodoni Moda', 'Times New Roman', serif` / `'Archivo', Helvetica, sans-serif`

| Element | Font / Weight | Size (desktop) | Line-height | Letter-spacing | Color |
|---|---|---|---|---|---|
| H1 (hero) | Bodoni Moda 700 | `clamp(2.75rem, 6vw, 6rem)` (~44–96px) | 0.98 | −0.01em | Ink Black or White (on color panel) |
| H2 (section head) | Bodoni Moda 700 | `clamp(2rem, 3vw, 3.5rem)` (~32–56px) | 1.05 | −0.005em | Ink Black |
| H3 (card/piece title) | Bodoni Moda 600 | ~22–28px | 1.15 | 0 | Ink Black |
| Eyebrow/kicker | Archivo Expanded 700 | 12–13px | 1.2 | +0.10em, uppercase | Flash Pink or Signal Violet |
| Body | Archivo 400 | 17px | 1.6 | 0 | Ink Black |
| Body — lead | Archivo 500 | 19–20px | 1.55 | 0 | Ink Black |
| Meta/caption | Archivo 500 | 13–14px | 1.4 | +0.01em | Ink Black/White at 70% |
| Button label | Archivo Expanded 600–700 | 14–15px | 1 | +0.08em, uppercase | White (fill) / Ink Black (outline) |
| Pull-quote | Bodoni Moda italic 500 | 32–40px | 1.2 | 0 | Deep Berry |

## 3. Layout concept

**Homepage:** sticky nav (transparent+scrim over hero → solid white + 1px hairline on scroll, no drop shadow) → **asymmetric split hero** (~92vh): left 42% solid Flash Pink panel with eyebrow, H1, one support line, and a white-filled CTA button (inverted for pop); right 58% full-bleed documentary photo with a hard 90° seam against the pink panel — no gradient, no scrim, no text ever sits on the photo (guarantees contrast regardless of the photo swapped in) → "From the Gallery" preview: editorial cluster (one 2×2 featured image + 4–5 smaller cells, sharp corners, Ink Black caption bar slides up on hover) → "Upcoming Classes" preview on a Gallery Bone band (3-col card row) → About/Instructor teaser on a full-width Signal Violet band (portrait + Deep Berry italic pull-quote) → pre-footer CTA strip (solid Ink Black or Flash Pink, one punchy line + outline button) → footer.

**Gallery:** no photo hero — the artwork is the hero; generous top padding like a gallery entrance → sharp rectangular filter chips (1px Ink Black border, active fills Signal Violet) → **strict aligned grid** (not masonry — reads like a catalog): 4 cols desktop / 3 tablet / 2 mobile, mostly 1×1 cells with an occasional 1×2 featured span, 16px gutters, **0px radius**, no card chrome, no shadow at rest (images butt edge-to-edge, gutter alone separates) → hover scales image + Ink Black-at-85% caption panel slides up (medium + class/date, no price) → lightbox shows the full uncropped piece plus a Flash-Pink underlined link back to the class → centered "Load More Work" outline button.

**Class Listings:** same header/filter register as Gallery (deliberate visual rhyme) → 3-col card grid, 32px gutters (looser than the gallery's 16px); each card: 4:3 photo, an overlapping sharp-rectangle kicker badge ("ACRYLIC" / "BEGINNER FRIENDLY"), H3 title, date/instructor meta, price + CTA on a shared bottom baseline; hover = lift + a crisp **hard offset shadow** (8px 8px 0, not soft-blurred) — a deliberate screenprint-poster signature device. Optional secondary compact table view for date-sorting; cards remain default.

**Other pages (brief):** Class Detail, About, Contact extend the same hero/band/hairline-rule language. Admin upload (conceptual only) reuses the same form language — underline inputs, square checkboxes, sharp 4px buttons, a dashed-border drop zone — no separate design system needed.

## 4. Component styling

- **Primary button:** solid fill (Flash Pink default, Signal Violet for a secondary action), white uppercase Archivo text, **4px radius** (a hair of softness, not a pill, not fully sharp); hover deepens fill + lifts 2px + a hard 4px offset shadow appears; focus = 2px Ink Black outline.
- **Secondary/outline:** transparent fill, 2px Ink Black (or white on color/dark) border; hover inverts to solid fill.
- **Text link:** no underline at rest, 2px underline draws in on hover, arrow glyph shifts 4px right.
- **Class card:** white surface, **6px** radius, no border at rest; hover = hard offset shadow + lift + 1.03× image zoom.
- **Gallery grid item:** **0px** radius, no chrome at rest; hover = 1.04× scale + Ink Black caption overlay.
- **Radius discipline (explicit rule):** radius shrinks as a surface gets closer to photography/print — 4px buttons → 6px content cards → 0px image tiles/badges. No soft/pill radius anywhere in this system — that's reserved for the other, softer direction.
- **Nav:** 92px desktop / 68px mobile; mobile menu is a full-screen Ink Black takeover with huge stacked Bodoni Moda links, not a generic slide-out drawer.
- **Forms:** single column, **underline-only** inputs (2px Ink Black bottom border → Flash Pink on focus, no boxed background) rather than filled boxes — a boutique-inquiry feel; static uppercase labels above fields, not floating labels; **square** 20×20px checkboxes/radios (checked = solid Signal Violet), not circular; a dedicated error red (`#C81E3A`) kept separate from the brand pinks; success state replaces the form with a full-width color confirmation card.
- **Footer:** full-bleed Ink Black, 4-column grid (Studio / Visit Us + duotone map thumbnail / Hours / Contact); thin-stroke geometric line icons, not filled badges; 1px white-10% hairline above the bottom bar.

## 5. Imagery & texture

Punchy, boosted-contrast photography — true blacks, clean whites, increased local contrast so brushstrokes/clay texture/glaze sheen have tactile presence; true-to-life color (never grade the artwork's actual color toward pink/purple). Tight, confident, editorial crops disciplined into a small fixed set of ratios (1:1 primary, 4:5 featured) rather than raw natural aspect ratios. Sparing black-and-white/duotone treatment (2–3 spots sitewide only — instructor portrait, one homepage moment) for gravitas; **never** applied to gallery artwork photos, which must stay full accurate color (documentation-critical). No grain overlay, no paper texture, no watercolor PNGs — texture comes only from the real photographed paint/clay/canvas, a deliberate contrast with the softer sibling direction. One allowed exception: a very faint (2–4% opacity) halftone/print-screen dot pattern inside solid color panels only, never on text or photos. Graphic language is hard-edged color panels, oversized display numerals used graphically (e.g. "No. 04" on a Class Detail page), Deep Berry italic pull-quotes as text-as-graphic breaks, and 1px Ink Black hairline rules in place of soft dividers/shadows.

## 6. Mood

Bloom & Brush, rendered Bold & Modern, should feel like a small independent gallery that happens to teach — a fashion-magazine masthead crossed with a well-run contemporary art space. Huge, high-contrast Bodoni Moda headlines sit inside hard-edged blocks of hot magenta and electric violet, cut clean against white gallery walls; nothing is rounded into softness or dusted with hand-drawn texture. Photography does the emotional work — real hands, real paint, real finished pieces — shown in a disciplined grid that treats a first-year student's canvas with the same visual respect as a group show.
