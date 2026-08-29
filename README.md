# khoanguyen01004.github.io

Source for my portfolio at <https://khoanguyen01004.github.io>.

One static page, no build step. Everything is in `index.html` — markup, CSS and JS
in a single file. The only external dependencies are the Archivo webfont from Google
Fonts and Three.js r128 from a CDN, both loaded over https.

## Layout

```
index.html      the whole site
favicon.svg     browser tab icon
404.html        fallback page for unknown URLs
images/         portrait, project screenshots, social share card
uploads/        CV as PDF, English and Vietnamese
```

## Demos

Three of the projects have a working version embedded in the page, all running on
static sample data with no backend:

- **Fleet load planner** — the 3D truck packing view from the dispatch platform,
  using the same Three.js scene setup and package palette. The three trucks are real
  vehicles from the roster, drawn to their actual cargo dimensions.
- **AgriLens** — the Android app's inference panel over the same 39-class label set.
- **Robotic arm** — the FastAPI controller's sorting state machine rebuilt in the
  browser, with the joint order, limits and HOME pose from the real controller. The
  poses are solved with two-link inverse kinematics, so the gripper reaches the block
  instead of the block snapping to the gripper.

## Running it locally

Open `index.html` in a browser, or serve the folder if you want the paths to behave
exactly as they do in production:

```
python -m http.server 8000
```

Then visit <http://localhost:8000>.

## Deploying

Pushing to `main` publishes the site. GitHub Pages serves the repository root, and
`.nojekyll` stops Jekyll from touching the files on the way through.

Both languages and both themes live in the same HTML. `data-lang` and `data-theme`
on the root element drive the CSS, and the choice is kept in `localStorage`.
