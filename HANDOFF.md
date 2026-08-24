# Handoff to Claude Code

This project is a design artifact (case study + process documentation) ready for GitHub hosting.

## What's included

- `index.html` — Main Design Component; open in browser, no build needed
- `PROCESS.md` — Full process log with decisions, timeline, dead ends
- `support.js` — DC runtime (auto-generated, do not edit)
- `image-slot.js` — Image drop utility (auto-generated, do not edit)
- `_ds/` — Industry design system (colors, fonts, components, styles)

## For Claude Code

Set up a GitHub repo with:

1. **Basic setup**
   - Initialize as a public repo (showcase/portfolio piece)
   - Add `.gitignore` (ignore OS files, node_modules if you add npm scripts)
   - Root files: `index.html`, `README.md`, `PROCESS.md`, directories as-is

2. **Pages**
   - GitHub Pages serving from root (`/`)
   - Main URL is `index.html` (rename to `index.html` if not already)

3. **Optional enhancements** (not required for launch)
   - Add a GitHub Actions workflow to validate the HTML on push
   - Create an `/exports` folder for future PPTX/PDF snapshots
   - Set up Discussions for feedback on design decisions

4. **No build step** — this is a static site. Browsers load the Design Component runtime from `support.js` inline.

## How it works for viewers

- Open the repo's GitHub Pages URL
- Click **Design** to see the 26-screen prototype
- Click **Process Log** to read how it was built
- No interaction beyond page toggle — it's a viewing experience

## Design system binding

The Industry design system is vendored in `_ds/`. All color, type, spacing, and component tokens flow from there. Don't delete or move it — the stylesheet and bundle paths are hardcoded relative.

## Questions for Claude Code

- Should this live in a monorepo with other case studies, or standalone?
- Do you want a separate branch/folder for development iterations, or keep master clean?
- Any CI/CD checks beyond basic HTML validation?
