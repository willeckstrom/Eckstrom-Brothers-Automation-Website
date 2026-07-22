
# Eckstrom Brothers Automation — Design System

## Company & product context
Eckstrom Brothers Automation (EBA) builds custom, open-source AI automation for commercial General Contractors (GCs) and subcontractors — workflow automation for a historically paper-and-spreadsheet-heavy industry (submittals, RFIs, scheduling, punch lists, procurement, field reporting).

**Sources:** none were available for this build. A codebase was referenced (`github.com/willeckstrom/Eckstrom-Brothers-Automation-Website`) but the repository has no commits on `main` or `master` (empty repo, confirmed via API). No Figma file, deck, or brand guide was attached. Everything below — palette, type, components, and UI kits — was **designed from scratch** against the brief: "extremely clean, modern, sleek, and interactive," for a construction-industry AI automation company. If real brand assets, a populated repo, or a Figma file become available, re-run this system against them — the current tokens/components should be treated as a strong, considered starting point, not a locked brand.

**Products (3 surfaces):**
1. **Marketing Website** — public site: homepage, product/how-it-works, case studies, contact.
2. **Customer Portal** — the GC/subcontractor-facing app: project dashboard, automation workflows, document/submittal tracking.
3. **Internal Operations Interface** — EBA's own ops tool for configuring and monitoring automations across customer accounts (denser, darker, more technical).

## Content fundamentals
- **Voice:** direct, competent, unglamorous — talks like an engineer/superintendent, not a startup. No hype adjectives ("revolutionary," "game-changing"). Confidence comes from specificity (named workflows, real numbers, concrete outcomes), not adjectives.
- **Person:** second person ("you") when speaking to the customer/GC; first person plural ("we") when EBA describes its own work. Avoid third-person "the platform."
- **Casing:** sentence case everywhere — headlines, buttons, nav labels. No title case, no all-caps except small eyebrow/label text (which uses letter-spacing instead of shouting).
- **Sentence rhythm:** short declarative sentences. Fragments are fine for emphasis ("No spreadsheets. No chasing subs."). Avoid semicolons and long subordinate clauses in UI copy.
- **Emoji:** none. Never used in product UI or marketing copy — this is a trust/reliability brand for commercial construction, not a consumer app.
- **Numbers/units:** always concrete and real-world (hours saved, submittals processed, days shaved off a schedule) — never vague ("blazing fast," "10x better") without a number attached.
- **Example headline:** "Submittals reviewed in hours, not weeks."
- **Example button copy:** "See it on your project" / "Talk to us" — never "Get started now!!" or "Unlock your potential."
- **Error/empty states:** plain and helpful, no cutesy voice. "No automations running yet. Add your first workflow." not "Nothing here! 👀"

## Visual foundations
- **Color:** Two-accent system on a cool graphite neutral base. **Signal amber** (`--amber-500 #F97316`) is the primary action color — a nod to construction hi-vis/safety-orange, refined rather than literal. **Automation cyan** (`--cyan-500 #17B8CF`) is the secondary/informational accent, used for AI/automation-specific moments (live status, in-progress states, data highlights) so it never competes with amber CTAs. Neutrals are cool-toned graphite, not warm gray — `--gray-950` through `--gray-50`. No purple, no gradients used as backgrounds; gradients are avoided entirely except a very subtle 2-stop wash on hero sections (amber→transparent) at low opacity.
- **Type:** three families, all Google Fonts (no source files were provided — flagging this substitution; swap in real brand fonts if/when available). **Archivo** (display/headings) — geometric, structural, slightly industrial grotesque, good at large sizes. **Public Sans** (body/UI) — a government/enterprise-proven, highly legible workhorse sans, deliberately not Inter. **JetBrains Mono** (data/technical) — used for IDs, timestamps, code-like automation configs, log output.
- **Spacing:** 4px base unit, scale at 4/8/12/16/20/24/32/40/48/64/80/96/128. Generous whitespace in marketing contexts, tighter (8/12/16) in dense operational UI (Internal Ops).
- **Backgrounds:** flat surfaces, not full-bleed photography or illustration (none was provided to draw from — see Iconography). Marketing hero sections use a subtle blueprint-grid texture (thin graphite grid lines at very low opacity) as the only recurring "texture" motif, evoking construction drawings without being literal. No hand-drawn illustration style; no repeating decorative patterns elsewhere.
- **Corner radii:** modest and consistent — 6px (small controls: inputs, chips), 8px (buttons, default controls), 12px (cards, panels), 16px (large surfaces/modals). Never pill-shaped buttons; a hint of pill (`--radius-full`) is reserved for status badges/tags only.
- **Cards:** flat white (or `--surface-inverse-raised` in dark ops contexts) surface, 12px radius, 1px `--border-subtle` hairline + `--shadow-sm`. No colored left-border accent strip (explicitly avoided). Hover raises to `--shadow-md` with a 1px border color shift to `--border-default`, no lift/scale.
- **Shadows:** soft, layered, low-opacity ambient shadows (`--shadow-xs` through `--shadow-xl`) — two-layer (tight + diffuse) rather than a single hard drop shadow, for a refined "sleek" feel. No inner shadows/skeuomorphism.
- **Borders:** hairline 1px throughout, graphite-based (`--border-subtle` / `--border-default` / `--border-strong`), never colored except on focus/error states.
- **Animation:** purposeful and quick, never bouncy. Standard ease `cubic-bezier(.2,0,0,1)`, 120–200ms for hover/press, 200–320ms for panel/modal transitions. Fades + subtle 4–8px slide-ins for entrances; no springs, no overshoot, no confetti.
- **Hover states:** buttons/links darken one step (`--brand-primary` → `--brand-primary-hover`); ghost/secondary controls gain a `--surface-sunken` fill. No lightening, no opacity-fade hover on solid buttons.
- **Press/active states:** darken one step further (`--brand-primary-active`) plus a 1px scale-down (~0.98) on buttons for tactile feedback — quick, 100ms.
- **Focus states:** visible 3px amber ring (`--shadow-focus`), always present for keyboard users — this is a professional field/office tool, accessibility is non-negotiable.
- **Transparency/blur:** used sparingly — only for overlay scrims behind modals/drawers (`rgba(11,13,16,.5)`, no blur) and a light `backdrop-filter: blur(8px)` on the sticky marketing nav once scrolled.
- **Imagery color vibe:** none provided. Where photography is used in the UI kits it's placeholder (`<image-slot>`), specced for warm-neutral, naturally-lit jobsite photography (not staged/glossy, not desaturated/moody) — real photos should be requested from EBA.
- **Layout rules:** marketing max content width 1200px; sticky top nav on all three products; Internal Ops uses a fixed left icon+label rail (not collapsible) since it's a daily-use tool for a small ops team.
- **Dark surfaces:** the Internal Operations Interface uses a dark graphite surface (`--surface-inverse` family) rather than the light surfaces used by the Marketing site and Customer Portal — this differentiates "your business" (light, approachable) from "our operations console" (dark, technical) while sharing the same tokens/components.

## Iconography
No icon assets, icon font, or SVG sprite were provided. **Substitution:** using **Lucide** (lucide.dev) via CDN — a clean 1.5px-stroke outline set that matches the brand's precise, non-decorative, technical character (closest available match to an unspecified system; flagging for the user to confirm or replace with real icons). No emoji, no unicode glyphs as icons. Icons render at 16/20/24px, always paired with the `--text-secondary`/`--text-primary` color (never colored decoratively except for semantic status: success/warning/danger).

## Logo
**No logo file was provided.** Per policy, none was drawn or approximated. Everywhere a mark would go, the wordmark "Eckstrom Brothers Automation" (or "EBA" short form) renders in `--font-display` type. Flag: please attach a real logo (SVG preferred) to replace this placeholder.

## Index
- `styles.css` — root stylesheet, imports all tokens (link this one file).
- `tokens/` — `colors.css`, `fonts.css`, `typography.css`, `spacing.css`, `effects.css` (radius/shadow/motion).
- `guidelines/` — foundation specimen cards (Colors, Type, Spacing, Brand, Motion).
- `components/core/` — Button, IconButton, Input, Select, Checkbox, Radio, Switch, Textarea, Badge, Tag, Card, Tabs, Dialog, Toast, Tooltip, NavBar, StatCard (see each `.prompt.md`). Standard set authored from scratch — no source inventory to enumerate against.
- `ui_kits/marketing-website/` — homepage, product/how-it-works, case study, contact.
- `ui_kits/customer-portal/` — login, project dashboard, workflow detail, submittals.
- `ui_kits/internal-ops/` — accounts overview, automation config, monitoring/logs.

## How this connects to the site
This design system is the **source of truth for the look** and lives in the Claude Design project *"Eckstrom Brothers Automation Design System"* (claude.ai/design). These files are pulled down via the `DesignSync` tool / `/design-sync` skill.

The current site (`/index.html`) is a **compiled standalone bundle** exported from Claude Design — the tokens below are already baked into it. This folder exists so that (a) the tokens are version-controlled and reviewable, and (b) when the site is rebuilt from editable source, it can `@import 'design-system/styles.css'` and share one source of truth with the design system.

_Full component library (React `.jsx` source + previews) and the editable UI-kit screens remain in the Claude Design project and can be pulled down on request._
