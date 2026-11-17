# TR-Portfolio

Personal portfolio for Trevor Robey — a de-branded showcase of cross-disciplinary work
(software & operations, AI systems, marketing, e-commerce), separate from the business site
of Trevor Robey Intelligence Network Citations LLC (trevorobeyinc.com).

## Stack

Plain **HTML + CSS + JavaScript** — no frameworks, no build step, no external requests.
Not deployed: GitHub Pages is off for this repo.

```
index.html        one page: About · Experience · Education · Contact
css/style.css     responsive; light/dark (system + manual toggle); reveal-on-scroll
js/main.js        nav, theme toggle, active-link highlight, renders project cards
assets/           résumé PDF + favicon
projects/         PVA Loan Closet case study and build guide (kept, not linked from the page)
ARCHIVED-PROJECTS.md   backup of earlier project write-ups (not shown on the site)
```

## Add a project

The Projects section was removed on 2026-11-14 while no project is featured. To bring it
back, restore the `#projects` section of `index.html` from git history (it holds a
`<script id="projects-data" type="application/json">` block), then append an object to its
`projects` array:

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
- All asset paths are **relative**, so it would also work under a project-site subpath if
  GitHub Pages were turned on.
