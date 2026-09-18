# Bloom & Brush Art Studio — Website Project

*("Bloom & Brush Art Studio" is a placeholder working name used throughout this repo's planning docs so agents and future contributors have a consistent subject to write about — swap it for the real studio name before launch.)*

## What this is

A marketing + gallery website for a real-world (physical) art studio. The site needs to:

1. **Advertise in-person art classes/workshops** — schedule, pricing, enrollment/inquiry.
2. **Show a gallery of artwork previously made in real classes** — photographed physical art (paintings, ceramics, etc.), not digital/stock work.
3. **Let an admin upload new gallery photos** — no-code, low-friction, from a phone.
4. **Show contact details** — address, hours, phone, email, a way to ask a question.

Brand direction (set by the studio owner): **bright and airy** — white and off-white base, with **pink and purple** as accent colors. Warm and inviting, not corporate. The site will be publicly hosted.

## How this plan was built

This phase used five parallel agents, run in two waves, to avoid one perspective dominating the plan:

- **1 research agent** — surveyed real, modern art-studio / ceramics-studio / gallery websites and 2025-2026 design trends for patterns worth borrowing. See [`docs/RESEARCH.md`](docs/RESEARCH.md).
- **2 business-analyst agents**, each owning a distinct lane so their backlogs wouldn't overlap:
  - **BA1 — Front-of-house & conversion**: personas, user journeys, and the visitor-facing MoSCoW backlog (homepage, class listings, enrollment, gallery browsing, about, contact).
  - **BA2 — Admin, operations & content**: the admin upload workflow, gallery content taxonomy, contact/inquiry handling, non-functional requirements, and the growth/future-features backlog.
  
  See [`docs/BACKLOG.md`](docs/BACKLOG.md) for both, plus the integration points and open questions they flagged between their lanes.
- **2 designer agents**, briefed with the research findings and the full feature set, each committing to a distinct, fully-realized visual direction rather than a single "safe" blend:
  - **Designer 1 — Soft & Painterly**: warm, organic, watercolor/hand-drawn, welcoming to first-timers and parents.
  - **Designer 2 — Bold & Modern Gallery**: editorial, confident, curatorial — treats the student gallery with real design respect.

  Both directions are laid out side by side as artboards on the Design canvas so they can be compared directly: **[Design canvas →](https://claude.ai/artifact/ChQGpoHeDz7vHo8xWqfmZu)**

## Open questions for the studio owner

Both BAs independently flagged the same two decisions as things only the business owner can settle — the backlog is written to work either way, but the answer changes several "Should" items into "Must" items:

1. **Enrollment model:** a simple inquiry/reserve-request flow (studio confirms manually by phone/email — assumed for v1), or real-time paid booking/checkout at launch (e.g., if the studio already uses a tool like Acuity/Square)?
2. **Gallery scope:** is the gallery purely marketing (showcasing what students make, no transactions), or should visitors eventually be able to buy select original pieces? The backlog treats art e-commerce as an explicit future-growth item, not MVP, unless the owner says otherwise.

## Next steps

1. Owner reviews the two open questions above and the two design directions on the canvas, and picks (or blends) a direction.
2. Confirm the MVP ("Must have") scope in [`docs/BACKLOG.md`](docs/BACKLOG.md) against real budget/timeline.
3. Pick a tech stack sized for a small business (see NFR/hosting notes in the backlog — low-maintenance managed hosting is recommended over self-managed servers).
4. Begin build.
