# David Shmail — Engineering Portfolio

Personal engineering portfolio. Pure HTML/CSS/JS — no build step, no dependencies, no framework.

## Site structure

```
index.html                          ← home: about, skills, experience, category track cards
│
├── edm.html                        ← Category 01: Computational Electromagnetics & Device Modelling
│   └── edm-project.html
│
├── simulation.html                 ← Category 02: Multiphysics Simulation & Numerical Methods
│   ├── fea.html
│   ├── numerical-methods.html
│   └── algorithms.html
│
├── systems.html                    ← Category 03: System Architecture & Integration
│   └── msd.html
│
├── signal.html                     ← Category 04: Signal Processing & Communications
│   ├── sns-filtering.html
│   └── sns-microgrid.html
│
├── embedded-control-dynamics.html  ← Category 05: Embedded Systems, Control & Autonomous Dynamics
│   ├── drone.html
│   ├── chess-engine.html
│   └── alarm.html
│
├── misc.html                       ← Category 07: Miscellaneous
│   ├── fluid-pipe.html
│   └── thermo-workshop.html
│
└── urt.html                        ← standalone: URT project page

assets/
├── <project>_portfolio/            ← images and source notes per project
├── David Shmail Resume.pdf         ← linked from CV download button on index.html
├── transistorFavicon.png
└── (thumbnails, headshot, logos)
```

## Adding a project

**1. Create the project page.**
Copy an existing page (e.g. `algorithms.html`) and update: tag, title, intro paragraph, tech-stack pill, and skill bullets. Update the breadcrumb nav at the top.

**2. Add a card to the category page.**
Add an `<a href="yourpage.html" class="featured-card">` block following the existing pattern.
- With images: put images in `assets/<name>_portfolio/`, add `.fc-img-*` CSS for positioning, reference them in the collage div.
- Without images: add class `fc-full` to the `<a>` tag and omit the `.fc-collage` div entirely.

**3. Optionally add a track card on `index.html`** if this is a new top-level category.
Follow the `.track-preview` pattern. Text-only (no thumbnail) cards use `class="track-preview track-preview--wide"` with no `.track-image` div.

Breadcrumb pattern: `Portfolio / Category Page / Project Title`

## Updating existing content

All content is directly in the HTML — no templates or CMS. Find the relevant file, edit the `<p>`, `<li>`, or heading, and verify in browser.

**To update the CV:** replace `assets/David Shmail Resume.pdf` with the new file, keeping the filename identical.

**To update the skills / experience / leadership modals:** edit the modal `<div>` blocks near the bottom of `index.html` (search for `id="exp-expand-overlay"`, `id="lead-expand-overlay"`, `id="skills-overlay"`).

## Deployment

Static files — no build required. Push to `main` and enable GitHub Pages:
Settings → Pages → Source: Deploy from branch → `main`, `/ (root)`.

For a custom domain, add a `CNAME` file at the repo root containing just the domain (e.g. `davidshmail.com`).
