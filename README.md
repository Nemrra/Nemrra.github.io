# davidshmail.com

This is the source for my engineering portfolio at [davidshmail.com](https://davidshmail.com). It's plain HTML, CSS and JavaScript, so there's no build step and nothing to install.

## How the site is laid out

The home page links to six category pages, and each category page links to its projects.

```
index.html                        home: photo, about blurb, featured projects, category cards

edm.html                          01  Computational Electromagnetics
  edm-project.html

simulation.html                   02  Multiphysics Simulation
  fea.html
  numerical-methods.html
  algorithms.html

systems.html                      03  System Architecture
  msd.html
  urt.html

embedded-control-dynamics.html    05  Embedded Systems, Control & Autonomous Dynamics
  drone.html
  chess-engine.html
  alarm.html

signal.html                       06  Signal Processing & Machine Learning
  sns-filtering.html
  sns-microgrid.html

misc.html                         07  Miscellaneous
  fluid-pipe.html
  thermo-workshop.html
```

Images live in `assets/`, mostly in one folder per project. `project_notes/` has the notes each project page was written from. `embedded.html` is an older version of category 05 that nothing links to any more.

## Adding a project

1. Copy a similar project page (`algorithms.html` is a good starting point) and change the tag, title, intro, tech stack and bullet points. Update the breadcrumb at the top, which follows `Portfolio / Category / Project`.
2. Add a card on the category page by copying an existing `<a class="featured-card">` block. If the card has images, put them in `assets/<project>_portfolio/` and position them with a `.fc-img-*` rule. If it doesn't, add `fc-full` to the card's class and leave out the `.fc-collage` div.
3. For a new category, also add a card to `index.html` using the `.track-preview` pattern. Text-only cards use `track-preview track-preview--wide` with no `.track-image` div.

## Editing content

All the text is written directly into the HTML, so find the page, change it, and check it in a browser. The about blurb is near the top of `index.html`, and each featured project's Details pop-up sits further down in the same file.

## Deploying

GitHub Pages serves the `main` branch from the repo root, and the `CNAME` file points it at davidshmail.com. Pushing to `main` updates the live site.
