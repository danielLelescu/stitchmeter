# Daniel Lelescu Portfolio — Project Page Guide

This setup keeps the main portfolio and every project page visually consistent without copying the full stylesheet into every project repository.

## Recommended structure

Use the existing `danielLelescu.github.io` repository as the shared design system:

```text
danielLelescu.github.io/
├── index.html
├── styles.css          # existing shared portfolio styles
├── project.css         # NEW: shared project-detail styles
├── script.js           # existing shared dark-mode/mobile-menu script
└── assets/
    └── epfl-logo.png
```

Each separate project repository only needs its own content and files:

```text
stitchmeter/
├── index.html          # NEW project-detail page
├── docs/
├── cad/
└── assets/             # optional project images
```

The project page loads these shared files from the root GitHub Pages site:

```html
<link rel="stylesheet" href="/styles.css" />
<link rel="stylesheet" href="/project.css" />
<script src="/script.js" defer></script>
```

Because all pages are served under `https://daniellelescu.github.io/`, the same dark-mode preference is reused across the portfolio and project pages.

## Apply the new page to StitchMeter

1. In the **danielLelescu.github.io** repository, add `project.css` to the repository root and commit it.
2. In the **stitchmeter** repository, replace `index.md` with the supplied `index.html`.
   - Best option: rename the old `index.md` to `README.md` if you want to keep the Markdown version as repository documentation.
   - Avoid keeping both `index.md` and `index.html` as competing site index files.
3. Keep the existing `docs/` and `cad/` folders exactly where they are; the new HTML page links to them with relative URLs.
4. Commit and push. GitHub Pages should rebuild automatically.
5. Open `https://daniellelescu.github.io/stitchmeter/` and hard-refresh once if the browser has cached the old page.

## Link the project from the main portfolio

Replace the placeholder card in the main `index.html` with the supplied `ROOT_PROJECT_CARD_SNIPPET.html`.

The important link is:

```html
<a href="/stitchmeter/">Project details ↗</a>
```

For every future project, use the corresponding project-repository path, for example:

```text
https://daniellelescu.github.io/robot-arm/
https://daniellelescu.github.io/embedded-controller/
https://daniellelescu.github.io/fpga-project/
```

and link them from the portfolio as `/robot-arm/`, `/embedded-controller/`, etc.

## Create another project page

1. Copy `PROJECT_PAGE_TEMPLATE.html` into the project repository and rename it `index.html`.
2. Search for the uppercase placeholders and replace them:
   - `PROJECT_NAME`
   - `PROJECT_CONTEXT`
   - `YEAR`
   - `GITHUB_REPO_URL`
   - `SKILL_1`, `SKILL_2`, `SKILL_3`
   - metrics, design principles, results, and documentation links
3. Keep the navigation short: **Overview / Design / Results / Documentation** works well for most engineering projects.
4. Put **Daniel's contribution** near the top. Employers should not have to search a team report to determine what he personally designed or implemented.
5. Use 2–4 measurable results in the hero/results sections whenever the project supports them.
6. Add no more than 3–5 skill tags. Prefer specific technical terms over generic tags such as “Teamwork”.
7. Add a card on the main portfolio page that links to the new `/repo-name/` page.

## Adding project images later

If a project has strong CAD renders, prototype photos, oscilloscope traces, or screenshots, put them in that project's `assets/` folder:

```text
project-repo/
└── assets/
    ├── hero.webp
    ├── detail-1.webp
    └── detail-2.webp
```

Then replace the CSS-only `.project-visual` block with an image, for example:

```html
<aside class="project-visual">
  <img src="assets/hero.webp" alt="CAD render of PROJECT_NAME" />
</aside>
```

For portfolio pages, a real project image is preferable to a decorative graphic whenever a good render or prototype photo is available.

## Local testing

The production pages use root-relative shared files (`/styles.css`, `/project.css`, `/script.js`). This is ideal on GitHub Pages, but if you serve an individual project repository by itself locally, those root files will not exist.

Two easy options:

- Test the project page after pushing it to GitHub Pages; or
- Temporarily replace the shared paths with the full URLs while testing locally:

```html
<link rel="stylesheet" href="https://daniellelescu.github.io/styles.css" />
<link rel="stylesheet" href="https://daniellelescu.github.io/project.css" />
<script src="https://daniellelescu.github.io/script.js" defer></script>
```

Switch back to the root-relative paths before committing if you want the cleanest production setup.

## Content formula for employer-facing project pages

A strong engineering project page should answer these questions in this order:

1. **What did you build?** — one sentence.
2. **Why was it technically difficult?** — 2–3 constraints.
3. **What did Daniel personally own?** — concrete design/code/calculation responsibilities.
4. **How does it work?** — 2–3 technical principles or subsystems.
5. **What evidence shows it worked?** — measured results, requirements met, performance, validation.
6. **Where can I inspect the work?** — code, report, CAD, demo, or presentation.

That structure is more useful to internship recruiters and engineering managers than reproducing the full project report on the web page.
