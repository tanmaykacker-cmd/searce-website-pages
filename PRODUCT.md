# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

**Primary: enterprise problem owners.** Senior buyers at large enterprises —
CIO, COO, CDO, business-unit heads — evaluating whether Searce can deliver a
specific AI outcome. They arrive on a page, judge whether the firm understands
their problem and can engineer a result, and decide whether to make contact.
This reading was confirmed by the user for the Searce 2026 site work; it is the
same product and the same audience, so it carries forward here.

**Present but unranked: prospective solvers.** Unlike the 2026 repo, this one
ships a real careers surface — `join-us.html` plus the `careers` nav tab. Talent
is therefore an actual audience of this repo, but it was never confirmed as a
design *priority* against the buyer. Treat the ranking as undecided.

**Internal reviewers.** This repo is deployed for stakeholder review (see
Operating Context), so colleagues reading a page to approve it are a real, if
secondary, audience.

## Product Purpose

Searce sells AI Outcome Engineering to large enterprises. A page's job is to let
a problem owner judge credibility without a conversation — name the problem,
show the mechanism, show where value lands, and resolve to the same action:
`bring us a problem →`.

**This repo's job is narrower: it is the workshop.** Individual pages are
designed and expanded here, then ported into the main preview repo at
`~/Desktop/Searce-website-2026`. Confirmed by the user. Success for this repo is
a page good enough to port; success for the product is a qualified inbound
contact from someone who already understands what Searce would do and why it is
different.

## Positioning

Drawn from copy committed in **this** repo, not supplied as a claim:

- **The gap between deployment and result.** `ai-outcome-engineering.html` opens
  on it: "Most enterprises have AI in production. Far fewer can attribute a
  financial result to it." The wedge is attributable outcomes, not access to
  models.
- **A three-way contrast, stated outright.** The same page sets *Traditional AI
  consulting* and *AI implementation* against *AI Outcome Engineering*, and
  leads with "Start with the outcome, work backwards into the process."
- **A named, ordered method.** `ai-outcome-engineering.html`'s execution
  methodology: "Six moves. In order. Every single time. Our delivery methodology
  is a rigid state machine. Each move produces verified mechanical deliverables
  before execution is permitted to advance to the next gate."
- **`evlos` is a separate, third offering** — *solve*, reversed — with its own
  line, "The method behind a decade of outcomes." It sits in the `how we solve`
  nav as a peer of AI Outcome Engineering and Forward-Deployed Solver Squads.
  It is **not** the name of the six moves — do not conflate them. It has no page
  yet: every `evlos` nav link in the repo points at `#`.
- **Named failure modes.** Process Fracture, Data Lineage Decay, Platform
  Rigidity, Incentive Inertia, Human Disconnect. The argument names what breaks,
  rather than listing what is offered.
- **Forward-Deployed Solver Squads.** "A cohesive team built to solve one
  business problem as a unit, around a single accountable outcome." ·
  "One initiative, one owner, no committees." · "Generation speed is a commodity
  now. Verified replacement of systems the business depends on is not." ·
  "Searce does not leave systems without owners." · "You meet the squad before
  you commit to it."
- **Problems-first information architecture.** `index.html` is not a service
  list — it asks "What should work radically better?" and answers with ten
  problem statements: "Every engagement starts as one of these sentences."
- **Four engineering practices** — Business Systems Engineering, Human + AI Work
  Engineering, AI-Ready Platform Engineering, AI Trust & Resilience Engineering.
  The recurring word is *engineering*. ⚠️ Four, not five: the fifth practice
  named in the 2026 repo (*AI Adoption & Change Engineering*) does not appear
  anywhere in this repo.
- **Beyond both sides of the category.** "beyond consulting. beyond execution."
  and "Baselined before we start. Verified when we finish."

## Operating Context

**Workshop, then port.** Pages are built and expanded here and move into
`~/Desktop/Searce-website-2026`. The current state of that relationship:

| Page | Here | In 2026 repo |
|---|---|---|
| `fde.html` | 145KB | byte-identical — in sync |
| `join-us.html` | 120KB | 54KB — this repo is ahead |
| `index.html` | 120KB, "Problems — Searce" | 4KB, "Searce practice pages — review" — a different artifact entirely |
| `ai-outcome-engineering.html` | 207KB | absent — unique to this repo |

Note that `index.html` is **not** the same object in both places. In the 2026
repo it is a flat review list; here it is a designed, filterable Problems page.
Do not port one over the other without deciding which is intended.

**Deployed for review on Vercel.** `vercel.json` sets `cleanUrls`,
`trailingSlash: false`, and `must-revalidate, max-age=0` on every `.html` and on
`/` — caching is deliberately defeated so reviewers always see the latest push.

**Reading path.** A problem owner reads a page top to bottom as an argument:
the problem, the mechanism, where value lands, how an engagement starts, then
the CTA. The nav is the lateral path between arguments — `how we solve` (with
subtabs *AI Outcome Engineering*, *Forward-Deployed Solver Squads*, *evlos*),
`problems`, `careers`, plus the persistent `bring us a problem →` and an `EN`
locale control.

## Capabilities and Constraints

**Stack.** Standalone HTML. No framework, no build step, no package manager, no
`package.json`, no bundler. Each page is one self-contained `.html` file at repo
root, kebab-case, with inline `<style>` and inline `<script>`; inter-page links
are relative.

**External dependencies are allowed where they earn it.** Confirmed by the user.
`fde.html` loads GSAP 3.12.5 and ScrollTrigger from cdnjs — this is the
precedent, not an exception to remove. Pages stay single-file but may reference
external scripts when the motion work justifies it.

**Two font strategies are in play, unreconciled:**

- `index.html`, `ai-outcome-engineering.html`, `join-us.html` inline Poppins as
  five base64 `woff2` faces — the code comment states the intent: "inlined as
  base64 so the page needs no network" — and load Google Sans Flex from
  jsDelivr fontsource (`google-sans-flex:vf@latest`), marked "CDN-hosted; falls
  back to system-ui offline".
- `fde.html` instead links Poppins from Google Fonts and inlines nothing.

Decide before adding a page; do not assume either is the rule.

**Deployment is Vercel, via `vercel.json`.** There is no `.github/` directory in
this repo and no GitHub Pages workflow. (`.nojekyll` is present but does nothing
on Vercel; whether it is deliberate is unconfirmed.)

**There is no `assets/` directory** and there never has been in any commit. All
imagery and motion is inline SVG, CSS, and JS — the hero trace field in
`ai-outcome-engineering.html` is built in code, not placed as a file.

**Token system.** Every page's `:root` carries the same core ramp — a
black/white/`#0064ff` system:

```
--ink #000000  --ink-85 #1a1a1c  --ink-60 #54555a  --ink-40 #84868c
--paper #ffffff  --paper-dim #f5f6f8  --paper-line #e4e6ea
--blue #0064ff  --blue-strong #004ecc  --blue-deep #00337f
--blue-06 #eef4ff  --blue-12 #dbe9ff  --blue-24 #b3d0ff
--display 'Poppins'  --body 'Google Sans Flex Variable'
```

Verified identical across all four pages. Pages extend it rather than restate
it: `ai-outcome-engineering.html` adds a dark-chapter set (`--blue-abyss`,
`--blue-void`, `--blue-panel`, `--blue-card`, `--blue-hair`, `--blue-hair-lit`,
`--blue-lift`) plus a `--mono` stack used for gates, stage numbers, and field
labels; `join-us.html` adds `--blue-abyss` and `--blue-lift`; `fde.html` adds
`--sec` and `--mod` at 88px. One drift, cause unconfirmed: `--paper-dim` is
`#f5f6f8` everywhere except `fde.html`, where it is `#f6f7f9`.

**`DESIGN.md` does not describe this repo and must not be corrected against it.**
It is a byte-identical copy of the 2026 repo's `DESIGN.md`, which itself was
imported from the main Next.js project — its paths (`next/src/app/globals.css`,
`next/src/components/ui/button.tsx`), Tailwind `@theme` utilities, and component
names refer to that project. It specifies a navy ramp (`#001630`, `#002659`,
`#003583`) on Cool Paper Blue `#F2F7FF`. **Searce Blue `#0064FF` is the only
value common to both systems**, and these pages set `body { background:
var(--paper) }` — pure white, which DESIGN.md's Daylight Rule rejects.

**Decided:** the divergence stands. Pages built here match the shared `:root`
block above, not DESIGN.md's navy/daylight palette. DESIGN.md remains a carried-in
reference for design *intent* (closed shape vocabulary, single-accent
discipline, register) — read it directly; this file does not restate it. Do not
regenerate it from a scan of these pages.

**Responsive breakpoints are per-page, not a shared scale.** In use across the
repo: 1360, 1280, 1200, 1180, 1080, 1050, 1024, 960, 900, 860, 768, 760, 690,
640, 620, 480px.

**Current page set (5 files):**

- `index.html` — "Problems — Searce". Ten problem cards rendered from a JS array,
  filterable by practice (4) and industry (7: Insurance, Financial services,
  Healthcare, Enterprise finance, Logistics, Telecom, Enterprise-wide). Has a
  real empty state: "No cards match these filters."
- `ai-outcome-engineering.html` — the method argument. Largest page in the repo.
- `fde.html` — Forward-Deployed Solver Squads.
- `join-us.html` — careers.
- `join-us-sections.html` — **not a page.** A drop-in fragment with no `<title>`,
  documented in its own header: paste the `<style>` into the host head and the
  markup where the two old sections were.

**Rename in flight:** `forward-deployed-solver-squads.html` is deleted (tracked)
and `fde.html` is added (untracked). Not yet committed as of this writing.

**Undecided:** whether these pages are ultimately served as searce.com or remain
a preview. Do not assume production-grade SEO, analytics, or legal obligations
until asked.

## Brand Commitments

**Confirmed and present in this repo:**

- Name **Searce**; positioning line **"AI Outcome Engineering"**.
- **evlos** — the named method (*solve*, reversed).
- **futurify.ai** — "the business engineering company · a Searce company", held
  quiet and low in the footer.
- The **"happier"** letter cards, in `join-us.html` and `join-us-sections.html`.
- Footer refrain: "reimagine what's next · redefine the how · realize the next
  now". Copyright reads © 2026 Searce Technologies Inc.
- Voice: lowercase nav and CTAs, short declaratives, middot sequences, an arrow
  on every action (`bring us a problem →`).

**⚠️ Carried in the 2026 repo but absent here — do not assume they apply:**
"Twenty-two years of solving for better", "We futurify businesses", "Project
Better Living", and the fifth practice *AI Adoption & Change Engineering*. None
appears in any file in this repo. Partner pages (Anthropic, OpenAI) also live
only in the 2026 repo.

**Copy source.** `Website_content_2026.md` is the authoritative copy source for
this work, but it is **not present in this repo** — it is referenced from the
2026 repo. Future work needs it supplied before writing new copy. Claims are not
invented to fill a layout.

**1:1 mapping to the production Next.js implementation** was a commitment in the
2026 repo, where mirrored pages keep production's real class names so they port
cleanly. No page in this repo carries that header comment. Treat it as a
requirement that attaches on port, and confirm before assuming it here.

## Evidence on Hand

- **Real copy** in all four committed pages — the full method argument, the
  squad argument, the careers narrative, and ten problem statements with their
  practice/industry taxonomy.
- **`DESIGN.md`** — the imported design system, as a reference target only.
- **In-code visuals** — the hero trace field, the scroll-drawn chart, the stage
  panes and metric ladder are all built in inline SVG/CSS/JS. They are real
  assets, but they live inside the HTML.

**Absences future work must not fabricate:** no testimonials, no named client
logos, no case studies, no benchmarks, no pricing anywhere in this repo. No
`assets/` directory, no photography, no video. The "by the numbers" figures live
in the 2026 repo's `who-we-are.html`, not here. `Website_content_2026.md` is
referenced but not present.

## Product Principles

1. **Write for someone deciding, not browsing.** The reader is a senior buyer
   comparing firms. Every section either advances their judgment or is cut.
2. **Show the mechanism.** Searce's advantage is that it names how the work is
   engineered — ordered moves, named failure modes, accountable squads. Prefer
   the specific mechanism over the adjective; a claim a competitor could copy
   verbatim is not positioning.
3. **Copy is sourced, never invented.** Headings and body text come from the
   2026 content doc. Where it is silent, ask — do not generate plausible
   enterprise prose, and never manufacture proof.
4. **Build to port.** A page is one standalone HTML file that must survive the
   move into the 2026 repo. External libraries are allowed where they earn it,
   but nothing may assume a build step, a bundler, or a server.
5. **One argument per page.** Each page exists to make a single case a buyer can
   retell. Pages that become capability inventories stop persuading; if a
   section does not advance that one argument, it belongs on a different page or
   nowhere.

## Accessibility & Inclusion

No accessibility standard was established by the user for this project. Existing
codebase practice, worth preserving rather than treated as a stated requirement:
every page honors `prefers-reduced-motion: reduce`, and all four draw explicit
`:focus-visible` outlines. Confirm a target standard before treating anything
beyond that as required.
