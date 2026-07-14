# TR-Portfolio

Personal portfolio for Trevor Robey — a de-branded showcase of cross-disciplinary work
(software & operations, AI systems, marketing, e-commerce), separate from the
Trevor Robey Inc. business site.

**Live:** https://trevoralexanderrobey.github.io/TR-Portfolio/

## Stack

Plain **HTML + CSS + JavaScript** — no frameworks, no build step, no external requests.
Deployed via **GitHub Pages** from the `main` branch.

```
index.html        one page: About · Projects · Experience · Education · Contact
css/style.css     responsive; light/dark (system + manual toggle); reveal-on-scroll
js/main.js        nav, theme toggle, active-link highlight, renders project cards
assets/           résumé PDF + favicon
ARCHIVED-PROJECTS.md   backup of earlier project write-ups (not shown on the site)
```

## Add a project

Edit the inline JSON in `index.html` (the `<script id="projects-data" type="application/json">`
block) and append an object to the `projects` array:

```json
{
  "eyebrow": "Category",
  "title": "Project name",
  "subtitle": "Stack / one-liner",
  "description": "What it is and who it's for.",
  "highlights": ["Key point", "Another point"],
  "tags": ["Tech", "Tech"],
  "links": [{ "label": "View source", "href": "https://github.com/..." }]
}
```

No other changes needed — `js/main.js` renders the array on load.

## Local preview

Open `index.html` directly in a browser (it works over `file://`), or serve the folder:

```bash
python3 -m http.server 8080   # then visit http://localhost:8080
```

## Notes

- `.nojekyll` disables Jekyll processing (this is a plain static site).
- All asset paths are **relative**, so it works under the `/TR-Portfolio/` project-site subpath.
