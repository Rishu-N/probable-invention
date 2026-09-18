# Feature Backlog

Produced by two business-analyst agents working in parallel on separate lanes — front-of-house/conversion and admin/operations/content — so the backlog covers both the visitor experience and the studio owner's day-to-day workflow without one dominating the other. See [`../README.md`](../README.md) for project context.

## Integration notes & open questions

Both BAs flagged the same dependencies between their lanes; reconcile these during build:

- The gallery's **"Class/Workshop" field** (BA2, §2) should reference the **same class catalog/IDs** used on the front-of-house side (BA1, §4.2), not a separate free-text list.
- The front-of-house **"Inquire about this class"** button (BA1, §4.3/§4.4) should feed the **single context-aware contact form** described in BA2 §3, with the class name/date pre-filled — not a separate system.
- **Open question for the studio owner — enrollment model:** BA1 assumed an inquiry/reserve-request flow (studio confirms manually) rather than real-time paid checkout, as the realistic default for a first launch. If the studio already uses a booking tool (Acuity, Square Appointments, etc.) or wants online payment at launch, several "Should" items below become "Must."
- **Open question for the studio owner — gallery scope:** BA1 interpreted "browsing the gallery before buying art" as browsing to decide on a *class*, not purchasing original physical artwork — e-commerce for art sales (inventory, shipping, payment-for-goods) is treated as **out of scope / future growth**, not MVP. If the studio also wants to sell finished pieces, that's a materially different feature set (product listings, checkout, fulfillment) and should be scoped as its own initiative.

---

# Part 1 — Front-of-House & Conversion (BA1)

**Lane:** Prospective-student / gallery-visitor experience (marketing site conversion). Admin/upload backend, content taxonomy, and growth/nice-to-have features are covered in Part 2 and referenced here only where they touch the visitor-facing flow.

## 1. User personas

**A — The Curious Beginner** (prospective adult hobbyist). Low-commitment creative outlet seeker, likely a first-timer. *Converts when* pricing is transparent, "no experience necessary" is explicit, a near-term class exists, enrollment takes under ~2 minutes. *Bounces when* pricing is hidden, skill seems required, no near-term dates, site feels dated. Key anxiety: *"Will I look silly? Is this worth the money?"*

**B — The Trust-Seeking Parent.** Looking for a kids' class/camp. *Converts when* age range is explicit, instructor background is visible, logistics (drop-off, duration, supervision) are spelled out, parent testimonials exist. *Bounces when* no age-grouping, no instructor info, vague logistics, no way to ask a question first. Key anxiety: *"Is this a legitimate, safe place for my kid?"*

**C — The Returning Regular.** Already trusts the studio; wants the next date/level-up class fast. *Converts when* schedule is current and what's-new is obvious. *Bounces when* schedule looks stale or they're treated like a first-time stranger. Mostly served by a well-built Must-have flow; dedicated "recognize me" features are Should/Could, bordering on the growth backlog.

**D — The Window Shopper** (casual gallery browser). Often lands directly on Gallery via a shared image, not the homepage. *Converts when* the gallery is rich, well-captioned, and every piece has an obvious path to "the class that made this." *Bounces when* the gallery is sparse, slow, or a dead end with no next step. Success = not bouncing entirely, going one layer deeper even without same-session conversion.

## 2. End-to-end journeys (condensed)

- **A (Beginner):** Landing (search/social, "is this legit/beginner-friendly?") → Explore (Class Listings → Detail → Gallery/About for credibility) → Decision (open, beginner-friendly, affordable class + testimonial) → Action (short Enroll form, class/date pre-filled) → Post-action (on-screen + email confirmation with response-time expectation).
- **B (Parent):** Landing (referral/flyer/search, "is this safe for my child?") → Explore (filter by age, read logistics, check Instructor/About, skim FAQ) → Decision (age-appropriate + trustworthy instructor + clear logistics) → Action (Enroll form with child's age/notes field) → Post-action (confirmation + easy click-to-call/email for follow-up).
- **D (Window Shopper):** Landing directly on Gallery → Explore (lightbox, captions on how a piece was made) → Decision (a piece resonates) → Action (CTA links piece → its class, now behaves like Persona A) → Post-action (converts to inquiry, or leaves having gone one layer deeper — a top-of-funnel win).
- **C (Regular):** Direct/bookmark or "new classes" post → scans schedule for next/level-up date, skips About/FAQ (trust already established) → suitable date exists → quick Enroll submission → confirmation. Main risk: stale schedule or being forced to re-establish trust from zero.

## 3. MoSCoW backlog

### 3.1 Homepage
- **Must:** hero stating what the studio is/for, visible without scrolling; primary CTA ("View Classes") above the fold + in nav; nav to Classes/Gallery/About/Contact; gallery teaser linking to full Gallery; "upcoming classes" teaser with real dates; contact info in footer; 1-2 testimonials; fully responsive.
- **Should:** "What to expect" 3-step first-timer explainer; social feed/link (Instagram); email signup for class announcements.
- **Could:** embedded map preview; seasonal/featured class banner; short studio video clip.
- **Won't (v1):** personalized/login-based content; on-homepage e-commerce for finished pieces (see open question above).

### 3.2 Class Listings / Schedule
- **Must:** list of current/upcoming classes (title, description, date/time, duration, skill level, price); spots-remaining/waitlist/sold-out indicator; CTA per class; mobile-friendly cards.
- **Should:** filter by category/day/skill level (depends on taxonomy — Part 2 §2); sold-out classes stay visible with "notify me"; price visible at a glance.
- **Could:** "add to calendar"; recurring-series indicator; search bar (once catalog is large).
- **Won't:** assigned-seat selection; dynamic/surge pricing.

### 3.3 Individual Class Detail Pages
- **Must:** full description of what's made/learned; date(s)/time(s)/duration; clear price (all-inclusive or "+materials fee"); skill level; spots remaining; primary CTA; instructor name/bio link; relevant photos (ideally sourced from the gallery); what's included/what to bring; location note.
- **Should:** class/medium-specific testimonial(s); class-specific FAQ (age limits, cancellation policy); related-class suggestions; explicit age-restriction flag.
- **Could:** short video preview; printable/shareable flyer; embedded map.
- **Won't:** open public review/comment submission on the page (moderation burden) — curated testimonials serve this role instead.

### 3.4 Enrollment / Inquiry Flow
- **Must:** form reachable from every Class Detail page; fields for name/email/phone/class-date (pre-filled)/participant count/child's age if applicable/notes; client-side validation; on-screen confirmation; automated confirmation email; studio notification with full submission details; blocks submission for a full class without routing to waitlist; mobile-usable.
- **Should:** real-time seat-availability check; waitlist signup for sold-out classes; enroll multiple people in one submission; auto-reply with practical next-step info.
- **Could:** online deposit/payment collection (**business decision — see open question above**); full self-serve checkout (Stripe/Square); SMS confirmations/reminders; lightweight scheduling-tool embed (Calendly/Acuity) as a bridge to real-time booking.
- **Won't:** mandatory account creation to submit an inquiry; full CRM/loyalty system (growth workstream, Part 2).

### 3.5 Gallery Browsing (visitor experience)
- **Must:** grid/masonry of real, high-quality artwork photos; lightbox/full-size view; caption per piece noting class/medium; **CTA linking a piece back to its related class**; optimized image loading; mobile-friendly scroll/swipe.
- **Should:** filter by medium/category (depends on Part 2 §2 taxonomy); pagination/"load more"; social share per image; graceful empty/sparse state for a brand-new site.
- **Could:** student-progress/before-after storytelling; distinguish instructor's own work from student work; zoom/pan on high-res images.
- **Won't:** purchase/checkout for original art pieces (see open question above).

### 3.6 Instructor / About Page
- **Must:** studio story/mission; instructor bio(s) with photo, background, teaching style; real photos of the physical space; CTA to relevant classes.
- **Should:** instructor's own portfolio samples (clearly distinguished from student gallery); explicit studio values ("no experience necessary," "all ages welcome"); "meet the team" treatment if multiple instructors.
- **Could:** instructor intro video; press mentions, years in business, credentials.
- **Won't:** separate full profile pages per instructor with their own booking/gallery (over-engineered for a small single-location studio at launch).

### 3.7 Contact
- **Must:** address + embedded map; click-to-call phone + click-to-email; general-inquiry form (not tied to a class); hours; social links.
- **Should:** parking/transit/accessibility notes; FAQ for common logistics; directions/landmark description.
- **Could:** live chat widget; separate contact channels by purpose (bookings vs. press).
- **Won't:** full ticketing/support-case system.

### 3.8 Cross-cutting conversion elements
- **CTAs — Must:** consistent primary CTA repeated on Homepage/Listings/Detail, persistent in nav. **Should:** contextual secondary CTAs (View Gallery, Meet Instructor). **Could:** sticky/floating mobile CTA.
- **Testimonials — Must:** 3-5 curated testimonials on Homepage + relevant Class Detail, with attribution. **Should:** aggregate rating (linked Google reviews). **Could:** video testimonials. **Won't:** open public review submission hosted on-site.
- **Pricing — Must:** price shown on both Listings and Detail, never "call for pricing." **Should:** what's included/excluded noted. **Could:** package/bundle pricing.
- **FAQ — Must:** covers cancellation/refund, age/skill requirements, what to bring. **Should:** organized by topic. **Could:** searchable/chat-style Q&A.
- **Trust signals — Must:** real (non-stock) studio/instructor photos, physical address, named instructors, testimonials. **Should:** years in business/students taught, visible social presence. **Could:** certifications/insurance/safety credentials, local business associations.

## 4. Top user stories (acceptance-criteria style)

1. **Homepage value prop + CTA** — *As a prospective hobbyist,* I want to immediately understand what the studio offers and see a way to view classes, *so that* I can judge whether to explore further. AC: hero statement visible within the first screen on desktop and mobile; primary CTA above the fold and in nav; no horizontal scroll/overlap on mobile.
2. **Class listings with availability** — *As a hobbyist comparing options,* I want to see all upcoming classes with dates/prices/remaining spots, *so that* I can find one that fits before it fills up. AC: each card shows title/date/price/skill level; spots-remaining or sold-out/waitlist label shown; clicking a card reaches the correct detail page.
3. **Class detail with price/skill/inclusions** — *As a parent,* I want age range, price, what my child will make, and what's included, *so that* I can judge appropriateness and cost before committing. AC: price/age/skill/duration/description all present; "what's included/what to bring" section present; CTA visible without excess scrolling.
4. **Enrollment/inquiry form** — *As a hobbyist ready to sign up,* I want a simple inquiry for a specific class, *so that* I can secure interest without a long process. AC: class/date pre-filled; only name/email/phone/participant count required; on-screen confirmation on submit; validation blocks bad data; mobile-friendly field types.
5. **Confirmation & next steps** — *As a parent who just submitted an inquiry,* I want immediate confirmation and to know what happens next, *so that* I trust the request went through. AC: on-screen confirmation; automated email summarizing class/date/expected response time; studio receives full submission details automatically.
6. **Gallery → class CTA** — *As a casual browser,* I want to see real photos from past classes and easily find the class that made a piece I like, *so that* "I like this" becomes "I want to take that class" in one click. AC: grid of real, fast-loading photos; lightbox with medium/class caption; CTA linking to that class's listing/detail.
7. **Instructor/About trust-building** — *As a parent considering enrolling my child,* I want to learn about the instructor and see the physical studio, *so that* I feel confident before committing. AC: instructor name/photo/bio present; real (non-stock) studio photos; CTA to relevant classes.
8. **Contact page logistics** — *As a visitor who wants to visit/call,* I want address/phone/hours at a glance, *so that* I can plan without digging. AC: address + embedded map, phone, email, hours all present; tap-to-call/email on mobile; contact form submission confirms on-screen.
9. **Testimonials on key pages** — *As a hesitant hobbyist,* I want to see real feedback from past students, *so that* I feel reassured. AC: ≥3 curated testimonials on homepage with attribution; relevant testimonials on class detail pages; each includes a name (and ideally class taken).
10. **FAQ addressing objections** — *As an unfamiliar parent,* I want answers to common questions upfront, *so that* I don't have to email and wait to decide. AC: FAQ covers cancellation/refund, age/skill requirements, what to bring; no further action needed for covered questions; clear link to Contact if not covered.

---

# Part 2 — Admin, Operations & Content (BA2)

**Lane:** admin/upload workflow, content taxonomy, contact/inquiry handling, non-functional requirements, and this scope's MoSCoW backlog.

## 1. Admin artwork-upload workflow

### 1a. Per-artwork fields

| Field | Required? | Type | Notes |
|---|---|---|---|
| Title | Required | Short text | e.g. "Sunset Over the Bay" |
| Medium | Required | Single-select, controlled taxonomy | See §2 — not free text |
| Category/theme tag(s) | Optional | Multi-select, controlled taxonomy | Landscape, Portrait, Abstract, Still Life, Kids' Work |
| Dimensions | Recommended | Structured (H×W×D + unit toggle) | D optional for 2D work |
| Price | Optional | Currency, or "Inquire for price" | Full checkout is out of MVP scope; still useful for purchase-inquiry flow |
| Availability | Required | Enum: Available / Sold / Not for Sale / Reserved | "Not for Sale" covers display-only/student-kept pieces |
| Date created | Recommended | Date picker | Drives newest-first sort/filtering |
| Class/workshop | Optional (recommended) | Reference to shared class catalog, free-text fallback | **Integration point with Part 1 — see note above** |
| Student/artist attribution | Optional | Text name + "display publicly?" toggle, default OFF | Privacy-sensitive, especially for minors |
| Photo(s) | Required, 1+ | Multi-file upload | One flagged primary/cover; multiple angles supported |
| Alt text | Required per photo | Short text | Accessibility + SEO |
| Short description | Optional | Textarea, ~250-500 chars | Story, technique, inspiration |
| Internal admin notes | Optional | Textarea, never public | e.g. "returned to student 6/2" |
| Featured flag | Optional | Boolean | Pins piece to homepage/curated carousel |
| Status | Required | Draft / Published | Stage an entry before it goes live |

### 1b. Single vs. batch upload

Both are needed — the real-world trigger is "a class just ended and I photographed 15 pieces on my phone":

- **Single-item entry** for one-off pieces (instructor showcase, a featured commission).
- **Batch upload** as the primary path: select/drop many photos at once → apply shared metadata to the whole batch (class, date, medium, default availability) → a lightweight spreadsheet-like **quick-edit grid** for per-item differences (title, student name, price/availability override) → can be saved as Draft and finished later in short sessions.
- Admin panel must be **mobile-responsive** — uploads will often happen from a phone on studio wifi right after class.
- Editing always available post-publish; deletion is a **soft archive** (hidden from public gallery, retained internally), not hard delete — these photos may be the only surviving record of a sold/given-away piece.

### 1c. Admin authentication & access model

Sized for a solo owner or at most owner + one instructor, not an enterprise:

- **No public self-registration** anywhere on the site — an open admin registration endpoint on a publicly hosted site is a real attack surface. Accounts provisioned out-of-band.
- **Passwordless/magic-link email login** recommended as default — no password to remember/forget/reset, which matters for a non-technical solo operator. Standard email+password via a managed auth provider is an acceptable fallback.
- **Flat single "Admin" role** for MVP — granular RBAC and multi-instructor accounts are future growth (§5).
- **Baseline security hygiene, sized appropriately:** HTTPS-only, secure session cookies, session auto-expiry, login rate-limiting, CSRF protection on upload/edit forms. Optional TOTP 2FA offered but not mandatory (Should, not Must).
- **Recovery:** simple "email me a new login link," since there's no password to reset.
- Prefer a **managed/hosted auth solution** over custom-built auth — a small business has no security team to maintain one.

## 2. Content taxonomy for the gallery

Goal: stay browsable from dozens to hundreds of pieces over years, without tag soup.

| Facet | Type | Starter values | Purpose |
|---|---|---|---|
| **Medium** (primary) | Single-select, controlled | Painting–Acrylic, Painting–Watercolor, Painting–Oil, Drawing/Illustration, Ceramics–Wheel-thrown, Ceramics–Hand-built, Sculpture, Mixed Media, Printmaking, Fiber Arts, Other | Main browse/filter axis |
| **Class/Workshop** | Reference, shared with front-of-house catalog | Pulled from the same catalog used for class browsing | Links gallery pieces ↔ classes bidirectionally |
| **Date created** | Date | Captured per piece | Newest-first default; date-range filter at volume |
| **Availability** | Enum | Available / Sold / Not for Sale / Reserved | Lets buyers self-filter |
| **Category/theme tag** (secondary) | Multi-select, curated | Landscape, Portrait, Abstract, Still Life, Nature, Kids' Work, Seasonal/Holiday | Cross-cutting browse independent of medium |
| **Featured** | Boolean, admin-only | — | Drives homepage/curated carousel |
| **Instructor** | Reference, captured even if not yet filterable | Defaults to "Studio" for MVP | Future-proofs data for multi-instructor support |

**Governance principle:** Medium and theme-tag values are a **fixed, curated list**, not free text — open text typed per batch upload will drift ("ceramic" vs "ceramics" vs "pottery") and quietly break filtering at scale. A small seeded list (~6-8 mediums) is enough for MVP (Must); a settings screen for the admin to add/rename/retire terms without a developer is a fast-follow (Should/Could).

**Browsability mechanics as the gallery scales:** filter bar (medium/class/availability/tag) + sort (newest/oldest); pagination or infinite scroll past a page or two; individually-permalinked artwork detail pages (better browsing + long-tail SEO); keyword search worth adding once the collection passes ~50-100 pieces.

## 3. Contact / inquiry handling flow

**Design principle:** one flexible contact form with a "context" field, not three separate systems.

| Entry point | Context captured | Extra optional fields |
|---|---|---|
| General "Contact Us" page | None (general inquiry) | Reason dropdown: General / Private event / Purchase inquiry / Press / Other |
| "Ask about this class" (Part 1 owns the button; this lane owns what happens after) | Class name + session/date | Preferred date, group size, experience level |
| "Inquire about this piece" on a gallery detail page | Artwork title + thumbnail reference | — |

**Common fields:** name, email (required); phone, "how did you hear about us?" (optional); message (required); marketing-email opt-in, **unchecked by default**; spam protection (honeypot + rate limiting minimum; hCaptcha/reCAPTCHA if spam becomes a problem).

**Where submissions go:** MVP — emailed directly to the owner's inbox, zero new tooling. Should have — also logged in a simple inquiry list inside the admin panel (open/responded/closed status) so nothing gets lost as volume grows. Notification recipient should be **configurable in admin settings**, not hardcoded.

**Visitor confirmation:** immediate on-page confirmation message (not a silent redirect). Should have: auto-confirmation email restating what they asked about, expected response time, backup contact info — matters for trust on a small local-business site.

**Privacy note:** collect only what's needed; some inquiries (kids' classes) may involve a parent submitting on a minor's behalf — keep data handling conservative, ties to the attribution-toggle default-off in §1a.

## 4. Non-functional requirements

**Image optimization/responsive images:** every uploaded photo auto re-encoded server-side (WebP/AVIF + JPEG fallback, multiple sizes/srcset) — admin should never manually resize/compress; compressed thumbnails in the grid, full-res only on detail/lightbox; lazy-load below the fold; upload-time size guardrails for weak studio wifi; prefer an image CDN/framework image pipeline over serving raw uploads.

**Mobile-first responsiveness:** applies to both public pages and the admin upload panel (owner uploads from a phone right after class).

**Basic accessibility (WCAG 2.1 AA-leaning):** alt text required at upload time; contrast-checked color pairings within the chosen pink/purple/white palette (light pink/purple text-on-white is a common contrast failure — check against WCAG ratios); keyboard-navigable gallery lightbox/filters (Esc/Tab/arrows, focus management); labeled form fields; semantic heading structure.

**Basic SEO** (people search "[city] art classes"/"[city] pottery classes"): unique titles/meta descriptions per page including category and artwork-detail pages; `LocalBusiness` schema.org data; NAP consistency with the studio's Google Business Profile; clean human-readable URLs; auto-updating sitemap + robots.txt; meaningful image filenames/slugs; fast load times (Core Web Vitals, downstream of image optimization above).

**Hosting/performance:** favor low-maintenance, cost-effective hosting (static/JAMstack public pages + CDN, managed/serverless backend for admin/forms) over self-managed servers; plan for image storage growth over years; **backups matter more than usual** — gallery photos may be the only surviving record of a sold/given-away piece; basic uptime monitoring, especially for a silently-broken contact form (directly costs leads); HTTPS required; lightweight, privacy-respecting analytics to inform which mediums/classes to feature.

## 5. MoSCoW backlog — admin/upload/content-ops/NFR scope

**Must have (launch-blocking):** admin login restricted to manually-provisioned accounts; single-artwork upload (title, medium, 1+ photo, availability, draft/published); photo upload with auto-optimization + required alt text; edit and archive (soft-delete) entries; public gallery filterable by medium at minimum; individual artwork detail page with permalink; general contact form with spam protection, emailed to owner; on-page confirmation after submit; mobile-responsive public gallery/contact; SEO fundamentals (titles/meta, sitemap, LocalBusiness schema, clean URLs); HTTPS, CSRF/honeypot, upload validation.

**Should have (near-term post-launch):** batch upload with shared metadata + quick-edit grid; additional filters (class/date/availability/tag); class- and artwork-specific contact form variants; auto-confirmation email to submitter; admin-visible inquiry log/dashboard; configurable notification recipient; student name display toggle (default off); internal admin notes; featured flag; magic-link admin login; responsive image pipeline + lazy loading; accessibility pass (contrast, keyboard nav, semantic headings).

**Could have (post-MVP):** admin-editable taxonomy management screen; keyword search across the gallery; optional 2FA; analytics surfaced inside the admin panel itself.

**Won't have:** enterprise role hierarchies/SSO; full CRM beyond a simple inquiry log; native mobile app (responsive web covers both admin and visitor needs).

## 6. Future growth (beyond MVP)

| Feature | Why it's future growth, not MVP |
|---|---|
| **Sell art online** (checkout, payment, shipping/pickup) | Needs payment integration, tax/shipping logic, inventory-vs-physical-availability sync — meaningfully larger than an "inquire to purchase" flow, which covers MVP adequately. **Ties to the gallery-scope open question above.** |
| **Newsletter signup** | Needs an email-marketing tool integration and ongoing content cadence commitment. |
| **Blog/news or events calendar** | A whole second content type + editorial cadence beyond gallery uploads — better validated after the core site proves out. |
| **Social media feed embed** | Nice freshness signal, but a third-party dependency not core to the gallery/contact job. |
| **Student testimonials/reviews (on-site)** | Valuable but needs its own moderation workflow (who approves a testimonial before it's public); arguably front-of-house territory. |
| **Multi-instructor support** (attribution, per-instructor filter, RBAC) | Only relevant once the studio isn't a single-owner operation — premature complexity at launch. |
| **Class waitlists** | Depends on the front-of-house class/enrollment data model being finalized first. |
| **Automated social-share image generation** per artwork | Polish feature once the core upload/gallery pipeline is stable. |
| **Multi-language support** | Only relevant if the studio's actual local audience needs it — don't build speculatively. |

## 7. Key recommendations

1. **Batch upload with a quick-edit grid** is the single highest-leverage admin feature — the realistic workflow for "just finished a class, have 15 phone photos to post."
2. **Fixed, curated taxonomy** (not free-text tags) keeps the gallery browsable as it scales past the first few dozen pieces.
3. **One contact form, context-aware**, rather than three separate systems, keeps the inquiry build simple while meeting the general/class-specific/artwork-specific requirement.
4. **Auth should optimize for a solo non-technical owner** — passwordless login, no public registration surface, flat single-role model.
5. Photography-heavy content makes **image pipeline automation** a load-bearing NFR, not a nice-to-have.
