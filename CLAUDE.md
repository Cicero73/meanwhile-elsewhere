# Meanwhile, Elsewhere

A parallel-history explorer: pick any year and see what every civilization was doing at the same time, then click an event to see "meanwhile" parallels from elsewhere in the world.

## About the owner

Russell (online: Cicero) is returning to software after a long career that included ABAP development, business analysis, product ownership and ScrumMaster work. He is relearning modern web development with Claude Code. Explain what you are doing in plain language as you go, especially git, terminal commands and new tools, and prefer small steps he can review.

## Current state (v0.1 prototype)

- Everything lives in `index.html`: markup, CSS, the data and the JavaScript.
- The data (`const DATA` in the script) holds 119 events, 42 eras and 11 lanes, taken from Russell's Roman and Abrahamic history spreadsheets.
- Event fields: `y` year (negative = BC), `a` 1 if the date is approximate or traditional, `lane`, `era`, `t` title, `n` note.
- Era fields: `lane`, `name`, `s` start year, `e` end year.
- No build step and no dependencies. Open `index.html` in a browser to run it.

## Ground rules

- Historical accuracy matters more than features. Do not invent events or dates; flag anything uncertain, and mark approximate dates with `a: 1`.
- Keep the app working after every change, and commit to git in small, clearly described steps.

## Likely next steps

1. Put the project under git and push it to GitHub.
2. Move the data out of `index.html` into its own file (for example `data/events.json`).
3. Add regions and events, starting with gaps the app already reports ("A gap worth filling").
4. Later: an AI question layer on top of the checked data, maps, quizzes, then deployment on the app's own domain.
