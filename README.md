# TALLY — Daily Herd Triage Case Study

A 26-screen mobile app design for a rancher's daily cattle triage workflow, built with Claude AI design tools over three days.

## What this is

A complete design artifact showing:
- **Design page**: Interactive 26-screen prototype of the TALLY app — a system that alerts a rancher to which animals need his attention today, why, and how confident the system is.
- **Process Log page**: Detailed breakdown of how the design was built, including tools used, decisions made, dead ends, and the AI/human boundary as implemented.

Toggle between pages with the **Design** / **Process Log** buttons in the top-right.

## Tech stack

- **Design Component format** (.dc.html) — streams live from first character, no build step
- **Industry design system** — steel-blue wireframe aesthetic with blueprint cards and corner marks
- **Vanilla JS logic** — no framework, no npm dependencies

## To run locally

1. Clone the repo
2. Open `index.html` in a browser
3. No server required — everything is static

## To edit

Edit `index.html` directly:
- **Template** (markup between `<x-dc>` and `</x-dc>`) — changes stream live
- **Logic class** (the `class Component extends DCLogic` block) — changes hot-reload
- **Styles** — inline only (no stylesheets). All tokens from `var(--*)` come from the Industry design system stylesheet

The design system is loaded from `_ds/industry-*/styles.css` and `_ds/industry-*/_ds_bundle.js`. All components (buttons, cards, navigation) come from that bundle — don't recreate them.

## Process & decisions

See `PROCESS.md` for:
- Tools used (Claude Design, Cursor, Figma)
- Three-day timeline and what happened when
- Design decisions and rationale
- Dead ends worth knowing about
- How the AI/human boundary was managed

## Key design constraints

- **No false precision**: The system reports what it saw, when, and what it compared against — then stops talking
- **One feedback loop**: The rancher corrects the system in four words, and that answer updates the baseline
- **Coverage > memory**: The bottleneck isn't judgment; it's that one person can't be in three places or remember Tuesday's readings on Thursday
- **Quiet > pretty**: Everything refused (ring charts, health indices, color ramps) would have made a better screenshot but would make the rancher stop opening it

## To extend

The case study is frozen. If you're building on this:
1. Keep the Industry design system tokens and components
2. Document new decisions in `PROCESS.md`
3. The toggle state is managed in the logic class (`state.isDesign`) — add pages as siblings to the existing `<div style="display:{{ designDisplay }}">` wrapper
