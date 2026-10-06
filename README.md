# JavaScript Challenge

Thirty small vanilla-JavaScript projects, one per folder — the JavaScript30 syllabus: drum kit,
CSS variables, array cardio, canvas, speech synthesis, geolocation, webcam, whack-a-mole and the
rest. No framework, no build step: open a project and it runs.

| | |
| --- | --- |
| **Live gallery** | not yet — a root gallery plus GitHub Pages is the next scheduled step |
| **Stack** | vanilla JavaScript (ES6+), HTML, CSS; browser-sync for three of the demos |
| **Repo** | https://github.com/Owen5e/JavaScript-challenge |

## What it is

Each folder is a self-contained exercise — `index.html` plus its own CSS and script assets, and
sometimes the media it needs (drum samples, a video clip, a photo). There is no shared bundle, no
dependency graph and nothing to install: every project is meant to be read side by side with the
browser's own dev tools, which is the point of the set.

The thirty folders, in repository order:

```
Adding Up Times with Reduce · Array Cardio Day 1 · Array Cardio Day 2 · CSS Variables ·
Click and Drag · Countdown Timer · Custom Video Player · Dev Tools Domination ·
Event Capture, Propagation, Bubbling and Once · Flex Panel Gallery · Follow-Along Link Highlighter ·
Fun with HTML5 Canvas · Geolocation · Hold Shift and Check Checkboxes · JS and CSS Clock ·
JavaScript DrumKit · JavaScript References VS Copying · Key Sequence Detection · LocalStorage ·
Mouse Move Shadow · Slide in on Scroll · Sort Without Articles · Speech Detection ·
Speech Synthesis · Sticky Nav · Stripe Follow Along Nav · Type Ahead · Video Speed Controller ·
Webcam Fun · Whack A Mole
```

## Getting started

**Open it directly.** Double-click any project's `index.html`, or drag it into a browser. Most
projects need nothing else — a few ask for permission (geolocation, microphone, camera) or want
media in the folder, which is committed alongside them.

**Or serve the folder** if you want `localhost` behaviour (some APIs, like speech and webcam, are
happier there):

```bash
npx serve .              # or: python -m http.server 8000
# then open http://localhost:3000/Geolocation/ , /Webcam%20Fun/ , ...
```

**Three projects ship their own dev server.** `Geolocation/`, `Speech Detection/` and
`Webcam Fun/` each carry a `package.json` for browser-sync:

```bash
cd "Geolocation"
npm start                # browser-sync start --directory --server --files "*.css, *.html, *.js"
```

## Known gaps

- **`node_modules` is committed in three folders** (`Geolocation/`, `Speech Detection/`,
  `Webcam Fun/`) — about 15,800 tracked files, most of them browser-sync's dependency tree, which
  is why the repository is ~53 MB. Those directories should be removed from git and ignored; the
  `package.json` in each folder is all that needs to stay.
- There is no root `.gitignore`, and until now no README — so the GitHub repo page opened straight
  onto a list of 30 folders with no explanation.
- No root gallery page: reaching a project means knowing its folder name. That is the next task.
- No tests, no linting and no CI in this repo — it is a collection, not an application.
- Folder names contain spaces, which means URL-encoded links (`Webcam%20Fun/index.html`) — worth
  knowing before wiring up a gallery.
