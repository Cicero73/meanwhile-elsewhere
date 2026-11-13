# Meanwhile, Elsewhere

A parallel-history explorer: pick any year and see what every civilization was doing at the same time, then click an event to see "meanwhile" parallels from elsewhere in the world.

## About the owner

Russell (online: Cicero) is returning to software after a long career that included ABAP development, business analysis, product ownership and ScrumMaster work. He is relearning modern web development with Claude Code. Explain what you are doing in plain language as you go, especially git, terminal commands and new tools, and prefer small steps he can review.

## Current state (v0.1 prototype)

- `index.html` holds the markup, CSS and JavaScript.
- `data/events.js` holds the data as `const DATA = {...}`: 119 events, 42 eras and 11 lanes, taken from Russell's Roman and Abrahamic history spreadsheets. One record per line, so git diffs show exactly which event changed.
- The data is a `.js` file loaded with `<script src>`, not a `.json` file loaded with `fetch()`, because browsers block `fetch()` on pages opened straight from disk (`file://`). Keep it that way until the app is served from a web server.
- Event fields: `y` year (negative = BC), `a` 1 if the date is approximate or traditional, `lane`, `era`, `t` title, `n` note.
- Era fields: `lane`, `name`, `s` start year, `e` end year.
- No build step and no dependencies. Open `index.html` in a browser to run it.

## Ground rules

- Historical accuracy matters more than features. Do not invent events or dates; flag anything uncertain, and mark approximate dates with `a: 1`.
- Keep the app working after every change, and commit to git in small, clearly described steps.

## Likely next steps

1. ~~Put the project under git and push it to GitHub.~~ Done: github.com/Cicero73/meanwhile-elsewhere (public).
2. ~~Move the data out of `index.html` into its own file.~~ Done: `data/events.js`.
3. Add regions and events, starting with gaps the app already reports ("A gap worth filling").
4. Later: an AI question layer on top of the checked data, maps, quizzes, then deployment on the app's own domain.
