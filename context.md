# Context — Project Handoff & Status

Read this first. This is a status document, not a design/content doc — it orients you and points to the real detail in `README.md`, `docs/RESEARCH.md`, `docs/BACKLOG.md`, and `docs/DESIGN.md` rather than repeating it.

## What this project is

"Bloom & Brush Art Studio" (an explicit placeholder name, not the real studio's) is the planning and early-design phase for a marketing + gallery website for a real, physical art studio. The site needs to advertise in-person art classes, showcase a gallery of real photographed student/instructor artwork, let an admin upload new gallery photos from a phone, and show contact details — in a bright, white/off-white brand with pink and purple accents. As of now, this repo holds only planning documents: no code, no chosen tech stack, and no finalized design direction.

## How this repo was built

The plan was produced by five agents working in stages, kept deliberately separate rather than merged into one voice, so several perspectives could be compared instead of one dominating:

1. **1 research agent** surveyed real, modern art-studio/ceramics-studio/gallery websites and 2025-2026 design trends for patterns worth borrowing.
2. **2 business-analyst agents**, each owning a distinct lane (front-of-house/conversion vs. admin/operations/content), briefed on that research, independently produced separate feature backlogs so neither lane's priorities got diluted by the other's.
3. **2 designer agents**, briefed on the research and both backlogs, each committed to one complete, independent visual direction — intentionally *not* converged with each other — so there are two real options to compare rather than one blended compromise.

That's why the docs below read as distinct voices/sections instead of one unified narrative: it's intentional, to preserve real optionality for whoever chooses between them next.

## Where to look

Read in this order:

| # | Doc | What's in it | Why read it |
|---|---|---|---|
| 1 | [`README.md`](README.md) | Project overview, brand direction, the two open questions for the studio owner, next steps | Fastest orientation to the whole project |
| 2 | [`docs/RESEARCH.md`](docs/RESEARCH.md) | The research agent's full findings: real studio/gallery site patterns, 2025-2026 trends, typography/color/accessibility notes | Grounds the "why" behind the backlog and design choices below |
| 3 | [`docs/BACKLOG.md`](docs/BACKLOG.md) | Both BAs' full backlogs: personas, user journeys, MoSCoW priorities, user stories, admin upload workflow, content taxonomy, NFRs | The feature scope of record — what the site needs to do |
| 4 | [`docs/DESIGN.md`](docs/DESIGN.md) | Both designers' full visual specs: palette, type, layout, components, mood, for "Soft & Painterly" and "Bold & Modern Gallery" | The two visual directions to compare and choose (or blend) between |
| — | [Design canvas ↗](https://claude.ai/artifact/ChQGpoHeDz7vHo8xWqfmZu) | 6 visual mockup artboards (style guide + homepage + gallery page, for each of the two directions, side by side) | See the two directions rendered, not just described in prose |

## What's completed

- [x] Research agent's findings on real studio/gallery site patterns + 2025-2026 trends (`docs/RESEARCH.md`)
- [x] BA1's front-of-house/conversion backlog — personas, journeys, MoSCoW, user stories (`docs/BACKLOG.md`, Part 1)
- [x] BA2's admin/operations/content backlog — upload workflow, taxonomy, contact handling, NFRs (`docs/BACKLOG.md`, Part 2)
- [x] Designer 1's "Soft & Painterly" full visual spec (`docs/DESIGN.md`)
- [x] Designer 2's "Bold & Modern Gallery" full visual spec (`docs/DESIGN.md`)
- [x] All of the above written up, committed, and pushed to this repo
- [x] Design canvas populated with all 6 artboards (style guide + homepage + gallery mockup, ×2 directions) — [view it here](https://claude.ai/artifact/ChQGpoHeDz7vHo8xWqfmZu). Note: the canvas is a private Claude Artifact, not a repo file — it isn't tracked by git and won't show up in `git log`/`git status`; it must be shared from its own Share menu for anyone besides the owner to open it

## What's NOT done / open decisions

- [ ] **No tech stack chosen**, and **no actual website code/scaffold exists** in this repo — it's planning docs only
- [ ] **No decision made on which design direction to build** — "Soft & Painterly" vs. "Bold & Modern Gallery," or a blend of the two
- [ ] **Two questions still need the real studio owner's input** (both BAs flagged these independently; the backlog works either way, but the answers flip several "Should" items to "Must" — wording below is ported directly from `README.md`, don't paraphrase it further):
  1. **Enrollment model:** a simple inquiry/reserve-request flow (studio confirms manually by phone/email — assumed for v1), or real-time paid booking/checkout at launch (e.g., if the studio already uses a tool like Acuity/Square)?
  2. **Gallery scope:** is the gallery purely marketing (showcasing what students make, no transactions), or should visitors eventually be able to buy select original pieces? The backlog treats art e-commerce as an explicit future-growth item, not MVP, unless the owner says otherwise.
- [ ] **The studio's real name, branding, actual photography, and real copy don't exist yet** — everything in this repo is placeholder/example content ("Bloom & Brush" included)
- [ ] **No hosting or deployment has been set up**

## Suggested next steps

1. Review both directions — spec in `docs/DESIGN.md` plus the [Design canvas](https://claude.ai/artifact/ChQGpoHeDz7vHo8xWqfmZu) mockups together — as a set. If sharing this with the studio owner, share the canvas from its own Share menu first (it's private by default).
2. Get the studio owner's answers to the two open questions above; they materially change scope.
3. Pick or blend a design direction based on the owner's reaction and those answers.
4. Confirm the MVP ("Must have") scope in `docs/BACKLOG.md` against real budget/timeline.
5. Choose a tech stack sized for a small business, per the NFR/hosting notes in `docs/BACKLOG.md` (favor low-maintenance managed hosting over self-managed servers).
6. Scaffold the actual site and begin build.
