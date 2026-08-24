# AI collaboration log — TALLY (Daily herd triage)

A record of how this artifact was produced: what was asked, what was decided, what was
built, and what was rejected or corrected. Written for a reviewer who wants to see the
process, not just the output.

Deliverable: `Tally - Herd Triage.dc.html`
Design system: Industry (bound to the project, steel accent, Barlow Condensed / Barlow)
Supporting files: `image-slot.js` (drop-target frames), `AI-LOG.md` (this file)

---

## Turn 1 — Brief received, questions asked

**Ask.** Design a mobile app for a cattle rancher: daily triage of which animals need
attention, with trust, confidence and error handling named as the heart of the exercise.

**Action.** Read the bound design system before designing. No reference captures were in
the project despite the brief mentioning them, so I flagged that and put up a 10-question
form rather than guessing: audience for the write-up, annotation density, which chapters
should be genuinely interactive, confidence wording, which trust mechanics to surface,
how hard to push the error story, copy tone, screen count.

**Answers that set direction.**
- Reader: a hiring panel judging design craft — rationale matters as much as screens
- Annotations on every screen
- All five chapters interactive
- Confidence wording: "Needs a look today / Worth checking / Just flagging"
- Trust mechanics: evidence-before-detail, personal baseline vs herd, data freshness
- Error handling: light — one dismissal-reason flow
- Copy: terse and operational; ~20 screens
- Added request: micro-animations to demonstrate interaction quality

---

## Turn 2 — First build

Built as a single Design Component: a case-study document wrapping a live 390×844 phone
frame, 21 screens across five chapters (Plan Ahead → Morning Triage → Animal Detail →
Locate → Action & Log), with a chapter sidebar, prev/next, and a design note beside every
screen.

**Decisions made in this pass.**
- Overnight prep as the opening act — the list exists before he does
- Confidence as three plain-language tiers, no percentages
- Evidence sheet one tap down: sensor, deviation, window, baseline, corroboration
- Two-stage Locate on tag radio (coarse bearing → getting warmer → arrival)
- Dismissal gated on a reason; each reason trains a different thing
- Offline as the resting state, with an explicit cache stamp on every read

**Verifier caught.** A three-column CSS grid overflowing at narrower widths. Fixed by
moving the product shell to a wrapping flex layout.

---

## Turn 3 — Revision brief (locked strategy + craft gap)

**Ask.** A long revision spec: purge percentages from headlines, mark out-of-scope
features as Future, move from generic SaaS to a field instrument, one severity system,
add a design-system appendix and a research gallery, cite each visual choice.

**Action.** Applied all of it. Notable changes:
- Every percentage removed from list headlines and evidence one-liners; the only number
  left (−38% vs her own 7-day) sits inside the evidence sheet, labelled as evidence
- Severity re-encoded as a 4px left rail + type weight (600/500/400), replacing the
  fill-weight bars on the list
- Herd map and Herd tab drawn grey and labelled Future
- Photo capture labelled "Not AI-analyzed"
- Design notes restructured to Problem / Reference / Steal / Refuse
- Added Appendix A (design system specimen) and Appendix B (research gallery)
- Introduced an iron-oxide product accent, cooling the paper to an alkali-dust ground

**Verifier caught.** Layout regressions from the palette swap; fixed.

---

## Turn 4 — Self-assessment on request

Asked to review the work against the brief. Reported honestly, including against my own
interest:
- Appendix B was empty drop-frames — "inspectable research" was a promise, not a delivery
- Three of four log actions collapsed into one confirmation screen
- Undo and "Show all" were decorative
- Helper type sat at 10.5–12.5px, contradicting the outdoor-legibility argument
- The iron-oxide accent was a deviation from the bound design system that a reviewer
  would challenge

---

## Turn 5 — Consistency protocol + revert the visual language

**Ask.** Apply a design-consistency protocol (tokens first, components second, modes
third, no one-off colours), do all five outstanding items, and return to the earlier
visual language while keeping the newer data visualisation.

**Decision.** Removed the iron-oxide accent entirely and returned to Industry tokens:
steel accent ramp, square corners with registration marks, `var(--*)` throughout, DS
component classes. Kept everything the revision pass got right — the rail severity
system, the baseline chart, the comparison bars, the no-percentage rule.

Rationale recorded in Appendix A: a second accent family meant two products in one
artifact, and severity was the only thing it bought that the steel ramp can already
carry.

**Built in the same pass** (21 → 26 screens):
- Animal Detail checklist (3.3) — records what he checked, sourced from what fired and
  from her history, never a prescribed protocol
- Separate confirmations for Treated / Monitor / Vet, each stating its own consequence
  and queue state
- Dismissal confirmation echoing the reason and what it changed
- Log tab (5.7) as a real destination, making the tab bar two tabs plus a Future third
- Working Undo (reverts to a stated "Reverted" state) and working "Show all"
- Helper type floor raised to 13px; system stamps 12px tracked caps, documented as the
  single exception

---

## Turn 6 — Persona, journey, real research, citations

**Ask.** Build a detailed persona with demographic data visualisation; add a user-journey
section; remove the "where the patterns came from" and "what we refused" sections; put
real visual examples in Appendix B; cite sources inline with an appendix listing them.

**Research.** Six web searches, then built the sections from what came back. Sources are
listed in full in Appendix C of the document; the load-bearing figures:

| Figure | Source |
| --- | --- |
| Average age 58.3 (beef ranching), 58.1 (all producers), 23.4 years farming | USDA NASS 2022 Census |
| Producer age bands (25–34: 239k … 55–64: 838k, 65–74: 827k) | USDA NASS 2022 Census |
| All cattle by state, Jan 2025; US total 86.6M | USDA / National Beef Wire |
| Top 10 states = ~57% of the beef cow herd; 7 states above 1M | Oklahoma Farm Report |
| 79% of farms have internet; of those 75% cellular, 51% broadband | NASS / Southern Ag Today |
| 22.3% of rural Americans lack fixed 25/3 coverage | USDA |
| Among $500k+ operations: 12% no internet, 16% poor | Purdue Ag Economy Barometer |
| 18% of farms have no internet at all | USDA via Ambrook |
| BRD prevalence 16.2% in US feedlot cattle; cattle mask illness as prey animals | PMC review |
| Sensors flagged 70% of cases 4 days pre-diagnosis, 88% accuracy | Penn State / Kentucky / Vermont |
| Distance walked per day the strongest predictive feature | Scientific Reports, 2024 |

**Sections rebuilt.**
- **01 Who this is for** — Dale Brenner, 61, Custer County, Nebraska, 480 mother cows.
  Portrait frame, operation facts, and four data panels (state inventory, producer age
  bands, connectivity reality, spring-calving working year). Copy deliberately does not
  restate any figure the panels show.
- **02 His day as it works now** — a 4:45→19:00 table of task, tool and where the record
  leaks; his own priority order; six pain points ranked by what they cost him.
- **Removed** "Where the patterns came from" and "What we refused". The reference lineage
  moved into Appendix A where the system is actually argued; the refusals became verdict
  lines on each Appendix B specimen instead of a standalone list.
- **Appendix B rebuilt** as five specimen groups, reproduced from each source's published
  documentation in their own palettes, each linked, each with a steal/refuse verdict:
  Stripe Radar risk levels + fraud factors; Atlassian lozenge + Polaris badge + Carbon
  status; Apple HIG charting / Health range chart + Robinhood delta framing; PagerDuty
  priority + real dispatch density beside our row; Find My two-stage locating.
- **Appendix C** — 26 sources by category, plus disclosure that Dale is a composite and
  that Robinhood publishes no open design system.

**Honest limits, disclosed on the page.** I cannot generate photographic images. The
portrait and the five "real capture" frames are drop targets; the Appendix B tiles are
documented reproductions, labelled as such, not screenshots.

---

## Turn 7 — Verifier rounds

Four review cycles, each fixed at the root rather than patched:

1. **Type-scale break.** One journey time label written at 15px against a 17px role.
   → set to 17px.
2. **Phantom grey cell.** Appendix B groups used `minmax(280px,1fr)` and resolved to two
   columns with three children, exposing the divider background as an empty panel.
   → retracked to `minmax(232px,1fr)` so three tiles fit.
3. **Dispatch specimen clipped.** Seven flex children at min-content plus 6×8px gaps
   exceeded the 226px track, so ETA/HOS were cut off inside an `overflow:hidden` card —
   in the one tile whose argument is "this is true density".
   → `min-width:0` + ellipsis on the children, gap to 4px, dropped the HOS column, and
   corrected the caption to say six columns rather than claiming full density.
4. **Severity scale collapsed to two steps.** The Industry stylesheet imports Barlow
   Condensed at 400 and 600 only, so `font-weight:500` silently rendered as 400 and the
   middle tier was typographically identical to the bottom one — while Appendix A
   published a 600/500/400 spec.
   → added a font link for 400;500;600 in the component's helmet. Root cause was a
   missing font face, not a CSS value, so no numeric property was re-tweaked.

---

---

## Turn — Xmind IA redesign, new screens file, and an unresolved layout failure

**Ask.** The app structure was redesigned in Xmind: three tabs (Overview, To Do, Pastures)
with Animal Details as a contextual destination reached from a map dot, a to-do row or a
search, never from the tab bar. Build the screens for that structure. A second ask followed:
notifications as a system-level layer, not a screen in the mind map.

**Built.** A new file, `Tally - App Screens.dc.html`, kept separate so the case study stayed
intact. Nine screens for the branches of the map that resolve to a screen — Overview, To Do
list, To Do calendar, system item sheet, personal item sheet, Pastures map, Pastures list,
Animal details top and scrolled — then two more for the notification layer: a pre-dawn lock
screen carrying the list-ready card, and a specimen sheet for the morning digest, the
proximity geofence and the staleness warning.

**Decisions carried over unchanged.** Tier words lead and no percentage appears in any
headline or notification body; every reading is dated; system rows take a logged reason
before they clear while personal rows are his to delete outright. The two to-do sheets are
deliberately asymmetrical — same shape, different rules — because that asymmetry is what
teaches which rows the system owns.

**Notification decisions.** All four types are local and on-device, because push needs a
connection to deliver and that is the one thing the pasture cannot promise. Proximity is the
only banner carrying actions, since it is the only one that arrives while he is already out
there; the geofence gets him near and Locate finishes the job. The staleness banner replaces
the list-ready banner rather than sitting beside it, so no morning ever shows old data
dressed as new.

**Assumptions logged where the map said TBD.** Personal item fields; rail treatment for
eight categories in a mono palette (four accent steps for animal health, three neutrals for
housekeeping, no rail for personal); West 1 / West 2 / North, reading the map's duplicate
"West 1" as a typo; range toggles scoped inside the sparkline card; search has no home in a
three-tab bar and was not drawn; the Locate guidance screens themselves are still undrawn.

**What went wrong — the honest record.** The presentation layout broke repeatedly and was
never fixed to the user's satisfaction. The sequence:

1. Screens were first laid out as a wall of framed thumbnails. At the user's viewport this
   stacked into one 24,000px column.
2. Fixing that with a four-across grid produced a wide board the user disliked on sight —
   they asked for the previous case-study format instead: one phone shell you click through.
3. Rebuilt as a clickthrough, but the frames still carried the per-screen heights from an
   earlier fix, so the "phone" changed proportion on every tap. Corrected by making the
   aperture a fixed 390×844 with content scrolling inside and the bottom sheets pinned.
4. Restored the original presentation properly — dark section, rounded device shell, screen
   list left, design note right — then found the wrapping flex row left large empty areas
   around the sticky columns at a narrow viewport, and replaced it with a fixed
   three-column grid.
5. The user still reported the page broken and stopped the work here.

**Root cause, as far as it was diagnosed.** Every automated check came back clean: no console
errors, all tokens resolving, all eleven screens rendering, the shell a constant 844px, no
clipped content. The failure was therefore never reproduced from this side, which is exactly
why it survived five attempts. Two contributing mistakes are clear in hindsight: the working
file was converted between three different presentation formats in one session instead of
matching the existing case-study format from the first build, and each fix was verified by
measurement rather than by looking at what the user was actually seeing.

**State at stop.** `Tally - App Screens.dc.html` holds all eleven screens, the walkthrough
navigation, the eleven design notes and the assumptions block. `Tally - Herd Triage.dc.html`
was not modified in this session and remains as it was.

**Resolution, next turn.** The misunderstanding was named: the ask had always been to update the
case study itself, not to produce a separate screens page. The eleven screens were moved into
`Tally - Herd Triage.dc.html`'s existing walkthrough — the shell that already worked — and
`Tally - App Screens.dc.html` was deleted. Each screen dropped its own status bar and took the
shell's, which already drives clock and bar colour per screen. Section 03 was rewritten from
"One morning, end to end" to the new structure, chapters became Overview / To Do / Pastures /
Animal Details / Notifications, and the system-item reason list was wired to real state so the
dismissal gate is live rather than a static picture. Nothing else in the case study changed.

**The lesson worth keeping.** A working presentation shell is worth more than a better one.
Five attempts went into rebuilding a layout that already existed twenty lines up the same
project.

---

## Turn — The mind map exhibit, a real interactive app, and a two-way system audit

**Ask.** Four things in one pass. Place the Xmind mind map on the page as a visible
exhibit. Make every screen actually interactive rather than only the sidebar and
prev/next. Get design rationale out of the simulated phone screen. Put consistent,
realistic iPhone chrome on every screen. Plus a two-directional design-system audit:
where the build has found the better answer, change the system; where the original rule
still holds, change the build — and record which direction each fix went.

**The exhibit.** The mind map now sits inside section 03, after the five chapter cards and
before the phone, framed as a Mode 3 blueprint card with registration marks on the tinted
ground, captioned in one line and linked to open full size. It marks the transition from
context into product with the artifact that produced the structure.

**From eleven pictures to one app.** The walkthrough was rebuilt as a single state machine
rather than seventeen static layers. One state object drives tab, sub-view, open sheet,
selected animal, selected row, and the lock screen; the sidebar and prev/next now just
write presets into that same state, which is why they and the screen content can no longer
disagree. Seventeen named screens are derived from the state rather than stored as markup.

What actually works, as a list, because "interactive" was the ask: the range toggle
switches the sparkline through four real series with its own caption; the head count and
each pasture tile deep-link to Pastures; all three tabs switch independently; the sync row
cycles synced / syncing / failed and the failure state changes what the screen claims about
its own data; filter and sort open real sheets and change the list; the calendar's month
arrows and day cells work and drive the list beneath; to-do rows open their item while the
chevron goes to the animal; the reason gate stores against the animal and the row leaves
the list; personal rows delete and mark done for real; map zoom, centre-on-me and zone
select work and a tapped dot opens her profile; the profile's weight, reproductive status
and withdrawal each open an update sheet; Locate hands off to the map with her dot pulsing;
follow-up writes a linked row into Personal and navigates to the list so the write is
visible; the notification banners route into Locate and the profile.

**Rationale out of the bezel.** The notification screens had been showing their own
explanation — "Proximity · geofence, on-device", a four-rule panel — inside the phone. Dale
would never see that. It is all gone from the screens and lives in the Design note rail
under the existing Problem / Reference / Steal / Refuse pattern. The phone now shows only
what the app would show.

**Device chrome.** One status bar for all seventeen screens, owned by the frame rather than
the screen: time left, cellular bars, a struck-through Wi-Fi glyph, a battery, the Dynamic
Island centred, a home indicator at the foot. Light and dark variants derive from one flag.
The struck-through Wi-Fi is a decision, not an ornament — no signal is the working
condition, so the chrome says so on every screen.

**The audit, both directions.** Ten mismatches, written into Appendix A as a
reconciliation block with a badge on each one saying which way it went.

System updated, because the build was right: the shell is three tabs with a hidden bar on
the contextual profile, not the old Today / Log pair; a list row is legitimately two targets
and both halves hold 44px; device chrome belongs to the frame, not the screen; the
notification card is a new surface with the accent rail reserved for staleness alone; Mode 2
was renamed from "Locate HUD" to "Dark field" and rescoped to the lock screen, since the
Locate screens it was written for do not exist yet.

Build corrected, because the rule held: no rationale inside the bezel — Mode 3 already
said the narrative frame is never imported into product screens; tier words appear only
where a tier is actually being stated, and group headers are category names, not severity;
eight to-do rails come from the mono ramp with type weight doing what colour cannot, not
from eight invented hues; registration marks stay out of the in-product cards; small accent
text sits at accent-700 on light and accent-300 on dark, since the base accent only clears
3:1.

**Two bugs found in review and fixed at the root.** A tapped map dot was pulsing for 260ms
before navigating, and a sidebar jump during that window landed on the wrong screen. The
delay is gone entirely; the tap confirmation is now a press-state scale on the dot itself,
which is both faster and honest about what a gloved miss looks like. The design note for
that screen was reworded to describe what the interaction now does.

**State at stop.** `Tally - Herd Triage.dc.html` carries the whole thing: sections 01–03,
the mind map exhibit, the seventeen-screen interactive walkthrough with per-screen design
notes, and three appendices including the reconciliation record. The mind map image is at
`assets/ia-mindmap.png`.

---

## Turn — Export mode, a rewritten voice pass, and the back-half reorder

**Ask.** Three things. Export all 17 screens as flat, full-length, shell-free images fit to
drop into Figma. Rewrite several places that read as generated copy rather than something a
person wrote: the Do/Don't list, the duplicated "Running rules" block, the three appendix
openers, the five Appendix B verdict lines, and the Closing section. Move sections 04 and 05
and the Closing ahead of all three appendices, so the case study makes its point and closes
before the back matter starts.

**Export mode.** Added a toggle inside the walkthrough that strips the phone bezel, status
bar and tab chrome and lets each screen render at its true content height instead of the
fixed 390×844 aperture. All 17 screens were captured through it at 2x. The first pass came
back with several sheet screens as flat grey rectangles: the capture engine rasterizes the
DOM rather than the live screen pixels, and an absolute-positioned scrim over an
absolute-positioned sheet does not resolve into anything drawable. Fixed by having sheet
screens export as the sheet surface alone in normal document flow — no overlay, no scrim —
so every one of the 17 is now a clean flat artboard. Exported set is in `assets/screens/`.

**Voice pass.** The Do/Don't list in Appendix A now carries a reason under every rule rather
than stating it bare. The duplicated "Running rules" block was resolved rather than
deduplicated: the mid-flow copy is now named as the shorthand version with a link to the
canonical one, and the canonical block in Appendix A says as much and states that it is the
one to trust if they ever disagree. The three appendix openers were given distinct
registers — A keeps its original aphorism, B turns conversational and admits its own
limitation up front, C turns flat and procedural — so they stop reading like the same
template three times. The five Appendix B verdict lines were rewritten from a compressed
"Stolen: X. Refused: Y" shorthand into full paragraphs that say what was taken, what was
changed, and why, in sentences a hiring panel can follow without the rest of the page for
context. The Closing section grew from two short paragraphs into a fuller close: what the
central sentence ruled out, what is left once you accept it, why a dashboard version of this
brief fails, and a closing line anchored back to the one number in the whole document Dale
would actually care about.

**Reorder.** The back half now reads 03 The product → 04 What comes next → 05 How it pays
→ Closing → Appendix A → Appendix B → Appendix C. The forward-looking and business-model
sections lead into the close as part of the argument; all three appendices are now true back
matter, read only by someone who wants to check the work.

**State at stop (end of turn 4).** `Tally - Herd Triage.dc.html` carried sections 01–03, the
mind map exhibit, the seventeen-screen interactive walkthrough (with an export mode),
section 04, section 05, Closing, and the three appendices in that order. Flat screen exports
are in `assets/screens/`.

## Design rules that survived every pass

1. No percentage is ever a headline. Numbers are evidence, one tap down, always labelled
   against a baseline.
2. Severity is a left rail plus type weight, one step down one ramp. No traffic lights.
3. Every read carries its cache time; offline is stated as a fact, not an error.
4. Nothing leaves the list without a reason. Dismissal is gated, permanently.
5. He decides, the app records. No autonomous action, no coaching voice.
6. Anything out of scope is drawn grey and labelled Future, never in live chrome.

## Things deliberately not built

Herd roster and barn-office desktop, multi-week analytics, two-way vet loop, photo
analysis, onboarding and billing. Each is argued in "04 What comes next" rather than
left unmentioned — photo analysis is refused outright for now, on the grounds that one
confident wrong read on a photo he took himself would cost more trust than the feature
could earn back.

## Turn 5 — Imagery, voice trim, and the Precision Find screen

**Imagery.** Added the user's isometric hero illustration (own colour, not duotoned) as a
background element behind the hero copy, aligned to the header/paragraph/design-problem
block rather than the full section height. Added the real portrait sketch to "Who this is
for" (dropped the placeholder note) and put the portrait and stat card side by side above
the "He is the sensor" copy. Added the user's five-panel day-in-the-life storyboard above
the timeline in section 02. Replaced the information-architecture exhibit with the user's
updated mind map and dropped the "Open full size" link and its stray border. Added the
final 17-screen merged-direction image to the hero, labelled "Final design."

**Voice pass.** Converted the remaining fragment-style copy — the day-in-the-life timeline's
"what he does" column and the three Mode cards in Appendix A — from telegraphic phrases
into full sentences. Trimmed the Closing section from four paragraphs to two. Removed the
Reconciliation subsection (ten system/build fixes) and the mid-flow "five rules, in short"
card and Steal/Refuse annotation fields, along with the export-mode toggle, at the user's
request.

**Appendix B real captures.** The five "Real capture" image-slots (Stripe Radar, Atlassian
lozenge, Health/Robinhood chart, fleet dispatch, Find My) were empty placeholders with no
fallback. Replaced each with a built HTML/CSS reproduction of the real product screen, at
the same craft bar as the existing pattern-reproduction cards beside them.

**Precision Find screen — new.** Added an eighteenth screen: a Bluetooth close-range locate
screen reached from the existing Locate sheet's new "Get precise directions" action. Modelled
on Apple Find My's Precision Finding — a dark-field (Mode 2) screen with a distance in feet,
a heading ring, and a signal-strength readout, replacing the cached-position map once the
tag is in Bluetooth range. This closes the gap the Locate sheet's copy used to name directly
("fine-grained tag-radio guidance is not designed"). Screen counts across the document
(nav rail, section 03 intro, Appendix A) updated from seventeen to eighteen; the Mode 1/Mode 2
split in Appendix A updated to reflect the new dark-field screen.

**Appendix backgrounds.** Appendix B given the same neutral-100 tint as A and C for
consistency, then all three moved to the darker neutral-200 so the appendices read as a
distinct block from the body sections above them.

**State at stop.** Eighteen interactive screens, hero and section 01/02 imagery in place,
Appendix B fully illustrated, Reconciliation and export mode removed, Closing shortened.

## Turn 6 — Voice & content architecture pass, closing illustration, and a copy audit

**Ask.** A scoped voice pass against a companion prompt/examples file: the Closing,
Appendix A Do/Don't list, "Running rules," Appendix B verdicts and Appendix C opener were
already confirmed right and used as the calibration bar; only the Hero, the design-problem
card, "04 What comes next," "05 How it pays," and the Appendix A header were still generated-
sounding and open for rewrite, plus two factual fixes.

**Rewritten.** Hero split into a one-line positioning statement plus a benefit-led paragraph,
constraints (gloved hand, thirty seconds, no signal) demoted to supporting texture. The
design-problem card reframed from a brief citation into a first-person stated principle,
matching the Closing's established voice. Section 04's intro and all five Future items,
and section 05's two paragraphs, rewritten from clipped phrases into full explanatory
sentences. Appendix A's header given a light touch — one real sentence instead of a
three-fragment aphorism.

**Two factual fixes.** The Overview sync line no longer claims the rancher is "at the
house" (the app has no way to know that) — now states only the time. The "five rules in
full" card actually lists six; heading and body corrected to say six.

**Copy audit.** Read every text node on the page looking for the same failure mode as the
sync-line and rules-count bugs: visual/design language leaking into body copy without
explanation. Found and fixed three: "steel bars" in the cattle-by-state chart (now names
the dark/light bar meaning directly), "the two rows marked in steel" in the daily-cadence
table (now names the two highlighted phases, calving and weaning), and "the rail marks how
directly" in the pain-points intro (now spells out what the colored bar on each card means).

**Closing section relayout.** Added the user's night-farm illustration (cattle wired to an
overhead sensor network, matching "watched all night while he slept"). Rebuilt from a
centered single column into: the three-sentence quote stacked full width (manual line
breaks, one sentence per line), then a two-column row below — supporting paragraph on the
left, illustration at roughly 65% width on the right — then the closing stat. Removed the
"design work is mostly restraint" paragraph at the user's request. Tightened section padding
(110/130px → 56px) and closing-block spacing to match.

**Other fixes.** Corrected the closing section's outer padding/kicker spacing, which had
drifted from the 88px/34px pattern every other section uses. Darkened all three appendix
backgrounds from `--color-neutral-200` to `--color-neutral-300` for stronger separation from
the body sections above.

## Turn 7 — Image optimization

**Ask.** Speed up page load without losing visual quality.

**Action.** The six large PNGs (hero illustration, final-merged-direction, portrait, storyboard,
mind map, closing illustration) were re-encoded as WebP at their real display resolution
(2x for retina) with alpha preserved, quality 0.82–0.9. Combined size dropped from 12.0MB to
3.1MB (74% smaller) with no visible quality loss. Originals kept in `uploads/`/`assets/`;
the page now points at the new files in `assets/opt/`.

## Turn 8 — Process Log page: toggle interface, copy cleanup, structure fixes

**Ask.** Create a second page showing the process log, with a toggle at the top to switch between Design and Process Log like a tab interface. Clean up the copy: remove self-explaining sentences, fix literal escape sequences (em-dashes and hyphens showing as `\u00b7`/`\u2014`), force the four tool cards into a single row, and add a new dead-end card about token limit constraints.

**Action.** Added `page` state property defaulting to 'design', with `goDesign` and `goLog` handlers and computed display values for each section. Wrapped the design page content in `<div style="display:{{ designDisplay }}">` and the new Process Log page in `<div style="display:{{ logDisplay }}">`, both siblings under a single outer wrapper. Added the toggle buttons (Design/Process Log) in a top-right blueprint card on both pages, showing which page is currently active.

**Structure & copy fixes.** Removed the self-explaining preamble "The brief specifically asks for these. Not the full list — the ones that actually taught something" before the dead-ends grid. Replaced all literal `\u00b7` and `\u2014` escape sequences in the template with real em-dash (—) and middot (·) characters. Changed the h1 from "How this was actually built" to "How it was built" (one line). Forced the four tool cards (01 section) from `repeat(auto-fit,minmax(260px,1fr))` to `repeat(4,minmax(0,1fr))` so they stay in a single row at any width.

**Dead-ends section.** Added a new card: "Token limits forcing tool rotation" — explaining that even with a paid plan, both Claude and Cursor hit session limits every 4 hours, which forced tool rotation and required additional token purchases to sustain momentum. Explicitly named this as a real constraint that shaped the process, not a failure to plan.

**Debug notes.** Found and fixed a div-balance error: the design page's final section was closing an extra `</div>`, which caused the design content to be hidden (closed early) when toggling to the Process Log view. Corrected by removing one closing `</div>` at the end of the first stats grid section, restoring proper nesting of the two page divs.

## Open items

- Search into Animal Details. Named as one of the three ways in, but it has no home in a
  three-tab bar and is still not drawn.
- The two-way vet conversation, if the scope ever widens past triage
