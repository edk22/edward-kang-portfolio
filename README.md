# Edward Kang — Portfolio

Personal portfolio site. Static HTML / CSS / vanilla JS — no build step.

## Files

```
.
├── index.html          # main site
├── case-study.html     # dynamic case-study template (?id=<slug>)
├── 404.html            # branded error page
├── projects.js         # shared project data + YouTube embed helper
├── favicon.svg         # generated from the E mark
└── assets/
    └── work/           # project screenshots and YouTube thumbs
```

## Local development

Open `index.html` directly in a browser, or serve over HTTP for full YouTube
autoplay reliability:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Routes

- `/` — homepage (Index list, Showreel, Featured, About, Capabilities, Contact)
- `/case-study.html?id=<slug>` — case study for any project
- `/index.html#/<slug>` — deep-link that auto-opens the modal for a project
- `/404.html` — error page (also surfaces if a case-study slug is unknown)

## Adding / editing projects

All project data lives in `projects.js` under `window.PROJECTS`. Each entry:

```js
{
  num, title, client, year, type, role, output,
  color, tint,      // accent palette for the modal/featured contexts
  img,              // path under assets/work/
  video,            // YouTube video ID, or null
  aspect,           // "portrait" or "wide"
  copy, approach, outcome
}
```

`window.PROJECT_ORDER` controls the prev/next sequence in the modal and on
case-study pages.
