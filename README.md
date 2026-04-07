# How to Think About the Future

A companion to Nate Hagens' *How to Think About the Future* Frankly series on [The Great Simplification](https://www.thegreatsimplification.com).

## What this is

A single-page interactive site that lets viewers explore the frameworks from the series rather than just listening to them. Five episode tabs plus a sources reference.

- **Episode 01 — Aerial View.** A short manifesto with the six principles of scenario thinking under uncertainty.
- **Episode 02 — The Lenses.** Interactive grid explorer for the four 2×2 scenario dimensions: economic direction, power and distribution, geopolitics, earth system.
- **Episode 03 — Build a World.** The flagship interactive. Pick one quadrant from each of the four lenses and the site composes a world from your stack. Detects the four canonical worlds Nate describes (Long Repair, Mordor Persists, Fortress, the Unraveling) and generates plausible hybrid descriptions for any other combination, with a plausibility tag based on the gravity rules in Part 3.
- **Episode 04 — Shortfall and Robust Action.** A visualization of the 50/100 finance asymmetry, the irreversible-loss inventory, and a personal worksheet for the three handoff questions (protect / build / let go).
- **Episode 05 — The Spectrums.** A seven-slider self-assessment that maps you to the closest of seven archetypes, with reflection prompts grounded in Renee Lertzman's "myth of apathy" insight.
- **Sources.** Categorized references for everything the series draws on, from Pierre Wack to David Holmgren to Joanna Macy.

## Tech

Single static `index.html`. No build step, no dependencies, no backend. Pure HTML, CSS, and vanilla JavaScript. Google Fonts (Fraunces, Newsreader, JetBrains Mono) loaded from CDN.

Runs on GitHub Pages out of the box. No `.nojekyll` needed since there are no underscore-prefixed files at the root.

## Local preview

```bash
# any static server works, for example:
python3 -m http.server 8000
# then open http://localhost:8000
```

## Editing

Everything is in one file. Tim or whoever maintains this can split out the CSS and JS into separate files later if it grows. For now, the single-file structure is intentional — easier to ship, easier to fork, easier to copy into a new repo.

The content for each episode lives inside the `<script>` block as JavaScript template literals, near the bottom of the file. To edit:

- **Episode 1** — search for `EPISODE 1: AERIAL VIEW` and edit the principles array and prose.
- **Episode 2** — search for `const grids =`. Each grid has four quadrants with name + detail.
- **Episode 3** — search for `const dimensions =` for the option content, and `const canonical =` for the four canonical world descriptions. The hybrid name generator and plausibility check are below.
- **Episode 4** — content is mostly in the HTML template inside `document.getElementById('ep4-content').innerHTML`.
- **Episode 5** — search for `const spectrums =` and `const archetypes =`. Archetypes are matched by Euclidean distance in 7-dimensional space, so changing the centroid values changes which profile users see.
- **Sources** — search for `SOURCES`. Plain HTML, easy to add or remove items.

## Design notes

Aesthetic direction is editorial gravity — dark warm charcoal background, cream text, brass-amber accents. Display font is Fraunces (variable, with the SOFT axis used to soften certain headers and italicize accents). Body is Newsreader (designed for digital long-form). Mono is JetBrains Mono.

The site is mobile-responsive at one breakpoint (768px). Below that, the nav stacks, the grid explorer collapses to a single column, and font sizes scale down.

## Credits

Frameworks by Nate Hagens. Site built for The Great Simplification / ISEOF.
