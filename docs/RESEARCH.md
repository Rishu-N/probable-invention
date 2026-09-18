# Design Inspiration Research

Produced by a research agent as part of the site-planning process (see [`../README.md`](../README.md) for context). Covers real, modern art-studio, ceramics-studio, and gallery/portfolio websites plus current 2025-2026 web design trends, to ground the two visual design directions in `docs/` and on the [Design canvas](https://claude.ai/artifact/ChQGpoHeDz7vHo8xWqfmZu).

**Methodology note:** conducted through web search, which surfaced real, named, currently-live sites plus design-press/award coverage (Awwwards, Squarespace/agency case studies, design-inspiration roundups) describing their layouts in detail. Every pattern below is sourced to where it was seen. Before final mockups ship to development, pull up the named URLs directly to confirm pixel-level details.

---

## Top 10 patterns to borrow

1. **One hero, one job.** Full-bleed photo of the studio/students/artwork in action, a short warm headline, and a *single* primary CTA ("Book a Class"). Don't split hero attention between "shop the gallery" and "book a class" — pick the CTA that drives revenue (classes), let gallery be the supporting proof point below the fold. *Seen across artist/hero-design best-practice roundups (Squarespace artist examples, Perfect Afternoon/DreamHost hero guides) and pottery-studio sites (Salt Lake Pottery Studio, The Pottery Studio NYC/SF, Brooklyn Pottery Studio) which lead with lifestyle photography of hands-on class moments, not product shots.*
2. **Organic blob/arch shapes as the primary way to use pink & purple.** Soft, irregular color washes behind white content cards — not flat color blocks — read as "comfortable and approachable" rather than corporate. This is *the* most on-brief current trend for this project. *2025-2026 "organic shapes" trend coverage (Squarespace Circle "Organic Matter," Envato).*
3. **Masonry or clean uniform-grid gallery + lightbox.** Staggered masonry (Pinterest-style) handles mixed-aspect-ratio photos of paintings/ceramics gracefully; click-to-enlarge lightbox is now a baseline user expectation for any portfolio-style gallery. *General convention across art-portfolio roundups (Hostinger, Pixpa) and gallery-plugin documentation (FooGallery, Redesignee).*
4. **Class "cards," not a text list.** Image + title + day/time + price + one CTA button, in a responsive card grid — the format every booking tool (Bookwhen, SuperSaaS, Mindbody-style) and studio example (Art Gecko Studio & Gallery, Phi Phi Artland) converges on because it's scannable on mobile.
5. **Two-track booking, not one.** Real-time self-serve booking widget embedded on standard/recurring class cards; a separate "inquire" contact form for private events, parties, and corporate workshops (custom scheduling doesn't fit instant-book). *Pattern repeated across Salt Lake Pottery Studio's "experiences vs. courses vs. private events" split and booking-software guides (Seldonframe, StudioBookings).*
6. **Serif display headline + humanist/geometric sans body.** The single safest, most-repeated pairing in this space — see specific font names below.
7. **Grain/texture overlay on pastel color fields.** A thin film-grain/noise layer (cheap: one SVG filter) over blush/lavender backgrounds stops "bright and airy" from reading flat, cheap, or AI-slick — makes pastel feel handmade and analog instead.
8. **Hand-drawn accents** (dividers, doodled icons, brush-stroke underlines). A real, physical, handmade craft business is exactly the brand this trend was made for — sketchy/imperfect marks signal "a person made this," which doubles as authenticity marketing for the class offering itself. *Creative Market "Naive Doodles," Switchpoint "Drawn-On Website Elements."*
9. **Founder/instructor storytelling block** near the top of the homepage or on About. Warm portrait photo + short human story builds the trust a local, in-person, small business specifically needs.
10. **Footer as the "come visit us" trust block.** Embedded map, studio hours, phone, email, and Instagram link, always present — non-negotiable for a physical studio where the whole point is getting people to walk in the door.

**Two watch-outs:**

- **Pastel-on-white contrast risk:** WCAG/WebAIM color-contrast research is explicit that pale pink and pale lavender *text* fails accessibility contrast on a white background. Use pink/purple for backgrounds, shapes, buttons (filled, white text), and icons — keep body copy and most headline copy in charcoal/near-black or a deep, saturated plum/eggplant, not light pink-on-white.
- **Video hero adds real risk for a small hosted site:** static hero images load faster and are nearly as effective; bounce rate climbs sharply past 3-4 second load times. Default to a strong static/rotating photo hero unless there's a real performance budget for video.

---

## 1. Homepage / hero patterns

- **Above the fold:** large photo (studio interior, hands working clay/paint, finished pieces styled warmly) + short warm headline + one CTA button.
- **Classes vs. gallery balance:** revenue comes from classes, not art sales — **classes/booking get the primary hero CTA; gallery is a secondary section/nav item that functions as social proof**, not a competing hero.
- **Real examples of the "bright, community, hands-on" hero mood:** Salt Lake Pottery Studio (saltlakepotterystudio.com), The Pottery Studio (thepotterystudio.com, NYC/SF), Brooklyn Pottery Studio (brooklynpotterystudio.com), Brooklyn Clay Industries (brooklynclayindustries.com), Artshack Brooklyn (artshackbrooklyn.org, nonprofit community ceramics, good reference for warm/inclusive tone).
- **Higher-design-budget reference (tone, not literal template):** Ōmbia Studio (ombiastudio.com) — LA sculptural ceramics studio, Awwwards Site of the Day — "organic and imperfect qualities of handcrafted design."
- **Emerging option — bento-style modular hero/landing:** a bento grid of tiles (upcoming classes / gallery teaser / about teaser / contact) gives all four of the brief's core jobs equal footing on one screen. Use with restraint.

## 2. Gallery layout patterns (real, physical, photographed artwork)

- **Masonry vs. grid:** Masonry (staggered, Pinterest-style) is dominant *because* physical artwork photos come in mixed aspect ratios. A uniform grid with generous negative space and no captions is the cleaner, more minimal alternative.
- **Lightbox click-to-enlarge** is close to a baseline expectation for any image-heavy portfolio gallery.
- **Filtering:** small galleries (a few dozen to low hundreds) work best with **button/pill filters** ("All / Painting / Ceramics / Mixed Media / Student Work"), not dropdowns.
- **Filter by class/session**, not just medium — e.g. "Fall 2025 Ceramics," "Intro to Watercolor" — doubles as indirect marketing and bridges Classes ↔ Gallery. (Coordinate with the shared class catalog — see integration note in `BACKLOG.md`.)
- **Price/medium/availability display — usually not needed here.** Sites that *sell* the pieces shown do show price + availability, following the physical-gallery-label convention. Bloom & Brush's gallery documents past student/instructor work, not a shop — lighter convention: a caption on hover/lightbox with medium + class name/date + maybe student first name (with permission), no price/availability, unless the studio also sells select instructor pieces (in which case only that subset gets tagged, to avoid confusing "student showcase" with "shop").
- **Photography consistency matters as much as web design here:** neutral/white backdrop, camera parallel to the piece, diffused light at ~45°, tight crop with no stray mat/frame/shadow. Worth a one-page "how to photograph a finished piece" cheat sheet for whoever uploads new gallery photos.

## 3. Classes/workshops: presentation & booking

- **Class card anatomy:** photo, class title, next date/time or "ongoing/weekly," skill level, price, one CTA ("Book Now" or "Inquire").
- **Pricing/structure patterns found repeatedly:** single drop-in class (~$30-80 typical market range; community-center rates lower, $15-30); multi-class packages/series at a discount (Art Gecko Studio & Gallery's 8-session package model); monthly membership/open-studio access (Phi Phi Artland offers drop-in *or* month-to-month); private/group events kept clearly separate from the standard schedule (Salt Lake Pottery Studio).
- **Booking flow — the practical hybrid that keeps showing up:** an embedded real-time booking widget for standard recurring classes, paired with a plain contact/inquiry form for anything custom. Forcing every booking type through one instant-book flow is where these sites get complicated.
- **Schedule display:** a card-based "this week/this month" view is trending over dense calendar tables — more scannable on mobile.
- **Instructor bios attached to class listings** build trust — small instructor photo/name/mini-bio on the class card or detail page.

## 4. Navigation & site structure

- **Keep top-level nav to 5-7 items, ideally fewer.** Natural set for this site: **Home / Classes / Gallery / About / Contact**, with **"Book Now"** styled as a distinct filled-pill CTA button separate from plain nav links — repeated in header, hero, and footer.
- **Dropdowns limited to two levels max** (e.g. Classes → Painting / Ceramics / Kids Classes / Private Events is fine).
- **Multi-page beats one-page for this business:** distinct visitor intents (check schedule vs. browse gallery vs. get directions) plus SEO value from separate indexable pages people can land on from search.
- An **admin-managed gallery upload requirement** points toward a platform with a real content-management backend rather than a static site — the admin needs to add photos without touching code.

## 5. Contact / footer patterns

- **Footer = the "trust and visit" block:** address with embedded Google Map, studio hours, phone, email, social icons, simple copyright bar.
- For a physical studio, **map + hours are non-negotiable.**
- **Contact form *and* raw phone/email, not one or the other** — some visitors (last-minute bookers, older visitors) will always prefer to just call.
- **Instagram is the dominant social channel for this category** — repeatedly the primary marketing surface for pottery/ceramics studios in this research. An embedded or linked live feed near the footer or gallery keeps the site feeling current between formal gallery updates.

## 6. Typography pairings & color usage

**Font pairing formula that recurs everywhere in this space:** an expressive/warm serif (or serif-leaning display face) for headlines, paired with a clean humanist or geometric sans-serif for body copy and UI.

| Headline (display/serif) | Body (sans) | Why |
|---|---|---|
| **Playfair Display** | **Source Sans 3** | "The most tested, most versatile combination" for content-driven sites |
| **Playfair Display** | **Raleway** | "Old-world serif drama meets modern minimalist balance" |
| **Fraunces** | **Inter** | "Retro-modern editorial meets functional digital clarity" — Fraunces is a *variable* font with a "soft" axis that can swing from crisp/formal to almost hand-drawn/wonky, unusually well-suited to a warm, handmade-craft brand |
| **Raleway** (alone) | — | Called out for "chic feminine" combos paired with a black/white/rich-pink palette |

- **Named display/accent fonts for logotype or big feminine headlines** (not body text): **Virga** (modern, elegant, ligatures, luxury/creative feel) and **Silcuty** (bold feminine, luxury/vintage serif with a modern edge) — use sparingly, e.g. the wordmark or a hero headline, not paragraph text.
- **Color palette formula repeated across pastel/boutique-brand roundups:** blush pink + soft lavender + cream + a touch of mauve/cocoa-brown as a "warmer, boutique/lifestyle" variant of a straight pink-purple palette. Blush-to-cream gradients feel fresher/more premium than flat "millennial pink."
- **Purple's brand-psychology association** (creativity, craftsmanship, elevated/quality feel) directly reinforces the "creative, quality craft" positioning, beyond just "looks pretty."
- **Reference point for "pink done at scale without looking cheap":** Glossier, Charlotte Tilbury, Benefit Cosmetics use pink as a dominant brand color while relying on generous white space and restrained, neutral typography rather than pink-on-pink everywhere.
- **Accessibility caveat (important, practical):** pale pink/lavender **text** on white fails AA contrast; those same light pastels pass fine as **backgrounds** (with dark text on top) or against a dark surface. Reserve pastel pink/lavender for backgrounds, shapes, buttons, icons, illustration accents; keep actual reading text in charcoal/near-black or a deep, saturated plum/berry tone (contrast-checked), never light pink or lavender directly on white.

## 7. 2025-2026 web design trends — fit for this brand

| Trend | Fit? | Why |
|---|---|---|
| Organic/blob shapes, anti-grid asymmetry | **Strong fit** | Matches "warm, inviting, not corporate" — soft pink/purple blobs behind white cards let accent colors carry personality without heavy flat blocks. |
| Hand-drawn/doodle accents | **Strong fit** | A real, physical, handmade craft business is precisely the brand category this trend serves. |
| Grain/noise texture overlays | **Fit** | Near-zero performance cost, keeps pastel fields from reading flat/AI-generated-slick — reinforces the "real photographed student art" authenticity angle. |
| Bento grids | **Fit, used sparingly** | Good for a homepage overview section (class types / gallery teaser / about / contact as parallel tiles). Don't over-engineer into a dense dashboard layout. |
| Big/expressive typography | **Partial fit** | Oversized, confident display headlines fit well at no extra cost. Skip elaborate kinetic/animated type if timeline is tight — only worth it if purposeful (guides to a CTA), not decorative. |
| Glassmorphism / "liquid glass" | **Skip as primary style; tiny accent only** | 2026 commentary describes it as shifted from headline trend to "supporting actor." Reads more tech/SaaS than warm handmade studio. |
| "Nature-distilled"/muted earthy palette trend | **Skip / actively counter** | A competing 2026 palette trend leans muted-earth. Worth flagging *because* it's popular right now — consciously choose the brief's bright pink/purple direction instead of drifting toward it. |
| AI-generated-visual backlash / preference for human-made imagery | **Fit, reinforces the brief directly** | Validates the core gallery requirement — real photos of real, sometimes-imperfect student/instructor artwork, styled with hand-drawn/organic accents, reads more trustworthy and on-trend than a slicker, stock-photo-driven alternative. |

---

## Quick reference: named sites & sources cited above

**Pottery/ceramics/craft studios (booking + gallery pattern reference):**
Salt Lake Pottery Studio (saltlakepotterystudio.com) · The Pottery Studio, NYC/SF (thepotterystudio.com) · Brooklyn Pottery Studio (brooklynpotterystudio.com) · Brooklyn Clay Industries (brooklynclayindustries.com) · Artshack Brooklyn, nonprofit (artshackbrooklyn.org) · AA Clay Studio (alexadamsclaywork.com) · Art Gecko Studio & Gallery (artgeckostudio.org/classes) · Phi Phi Artland, St. Petersburg FL (phiphiartland.com)

**Painting/art class schools (booking + navigation reference):**
Art House Studios (arthousestudios.org/classes) · The Art Studio NY (theartstudiony.com) · Insight Fine Art Studio, Skokie & Chicago (insightfineartstudio.com)

**Higher-design-budget ceramics/craft brands (visual tone, Awwwards-recognized):**
Ōmbia Studio (ombiastudio.com) · Olive Ateliers (oliveateliers.com) · Kevala Ceramics, CaiYawen Ceramics, Specialist Ceramics, Moyceram (Awwwards Honorable Mentions) · Ghost Wares Ceramics (Squarespace "Wexley" template case study) · Krista Coons (ceramics artist, personal site)

**Pink-forward brand references (color-at-scale proof point, not art-specific):**
Glossier · Charlotte Tilbury · Benefit Cosmetics

**Key research/trend articles referenced:** Squarespace ("5 Inspiring Artist Website Examples for 2026," "Art Studio Website Templates," "8 Creative Services Website Examples"); Squarespace Circle ("2025 Design Trend: Organic Matter"); WriterDock ("Bento Grids & Beyond: 7 UI Trends Dominating Web Design 2026"); Creative Market ("Naïve Doodles"); Creative Bloq ("Messy, meaningful and made by humans"); WebAIM/Venngage (color-contrast guides); Typewolf/Fontpair/BonFX (Playfair Display pairings); Artisan Themes ("Best Google Fonts & Color Combinations for a Feminine Website"); kdesign, Design Pixie, Higo Creative, Steph Corrigan Design (pastel palette roundups); Soley Creative ("Purple: The Colour of Luxury, Creativity and Quiet Power"); Format/ExpertPhotography/Associated Artists of Pittsburgh (photographing-artwork guides).
