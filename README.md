# TALLY — Daily Herd Triage

**Live case study:** [xiaoseanlu.github.io/tally-daily-herd-triage](https://xiaoseanlu.github.io/tally-daily-herd-triage/)

A mobile app design for a cattle rancher's daily herd triage — which animals need attention today, why, and how confident the system is. Eighteen interactive screens, built with Claude AI design tools over three days.

## Overview

A rancher running a few hundred head of cattle spends hours every week answering one question: which animals need attention today. The data to answer it better already exists — smart ear tags, weigh stations, feed-bunk records — but nobody has time to look at it, and the signals that matter (eating less, moving less, separating from the herd) usually surface too late.

TALLY is the daily experience that turns that data into a decision. Every morning it reads the whole herd overnight and hands the rancher a short, ranked list: what needs a look, why, and how sure the system is — checkable one-handed, in under thirty seconds, with or without signal. The design problem underneath it wasn't the interface, it was trust: how a field tool earns the confidence of someone who's been reading these animals by eye for decades, and how it stays honest about being wrong.

The case study is built around one persona, Dale Brenner — a composite grounded in real USDA demographic and connectivity data, disclosed as such in the appendix — and reasons every design decision back to either his actual day or a cited piece of field research, rather than a generic mobile-app pattern.

## What this is

A complete design artifact with two views, toggled from the top-right of the page:

- **Design** — the interactive 18-screen prototype: Overview, To Do, Pastures, Animal Details, and the on-device notification layer, plus three appendices covering the design system, the research it was reasoned from, and full sourcing.
- **Process Log** — how it was actually built: three AI tools over three days, the decisions and why, the dead ends kept in rather than cleaned up, and the AI/human boundary as implemented.

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

The fullest version of this lives on the live site's **Process Log** page — three tools, three days, the decisions and why, and the dead ends kept in rather than cleaned up. `PROCESS.md` in this repo covers the same ground for anyone browsing the code directly.

## Key design constraints

- **No false precision** — the system reports what it saw, when, and what it compared against, then stops talking
- **One feedback loop** — the rancher corrects the system in a few words, and that answer updates the baseline
- **Coverage > memory** — the bottleneck isn't judgment, it's that one person can't be in three places or remember Tuesday's readings on Thursday
- **Quiet > pretty** — everything refused (ring charts, health indices, color ramps) would have made a better screenshot but would make the rancher stop opening it

## To extend

The case study is frozen. If you're building on this:
1. Keep the Industry design system tokens and components
2. Document new decisions in `PROCESS.md`
3. The toggle state is managed in the logic class (`state.isDesign`) — add pages as siblings to the existing `<div style="display:{{ designDisplay }}">` wrapper
