# GitHub Copilot instructions — Public Website

Purpose
- Short, actionable instructions to help AI code agents make safe, useful edits to this repository.

Big picture
- This workspace contains two related folders: the static site in `vsCode - Public Website` (primary) and a collection of samples/assets in `vsCode - Getting Started`.
- The Public Website is a purely client-side, static site: HTML files at the root (`index.html`, `about.html`, `services.html`, `contact.html`) and a collection of assets inside `Tech Consultant - Telarus University_files/` (CSS, JS, images).
- Many JS files are classic library bundles (e.g., `jquery.min.js`, `select2.min.js`) and site-specific scripts (e.g., `index.js`, `cv.js`, `rsvp.js`). Ordering matters: vendor libs must remain before site scripts.

Key files & folders to inspect before editing
- `index.html` — entry page and canonical example of how assets are wired.
- `Tech Consultant - Telarus University_files/` — contains CSS/JS assets (look for `index.js`, `jquery.min.js`, `style.css`, `style.min.css`).
- `vsCode - Getting Started/` — contains examples and an exported WP-like asset bundle used as reference.

Developer workflows (how to run & test locally)
- No build system detected. To preview locally, use either:

```powershell
# From inside the project folder
python -m http.server 8000
# or use VS Code Live Server extension and open the workspace folder
```

- After edits, open the site in a browser and refresh — there are no automated test runners.

Project-specific patterns and conventions
- Asset duplication: there are both minified (`*.min.css`, `*.min.js`) and non-minified copies; prefer editing the non-minified files when making changes, then update the minified variants if required.
- Inline ordering: many pages assume `jquery.min.js` loads before `index.js` and other site scripts — do not reorder scripts unless you update their dependencies.
- Multiple style files: `style.css`, `style.min.css`, and other theme-related CSS are present. Changes to visual styling are usually centralized in `style.css`.

Integration points & external dependencies
- The codebase uses third-party libs: jQuery, Select2, Magnific Popup, Waypoints, etc. Changes that remove or replace these libraries must update all references and dependent code.
- Some files look like WordPress-exported front-end assets — avoid renaming files referenced by HTML without updating the corresponding references.

Editing guidance for AI agents
- When modifying HTML/JS/CSS:
  - Preserve vendor script order (e.g., `jquery.min.js` before `index.js`).
  - Make minimal, incremental edits; test by running `python -m http.server` and checking the live page.
  - Prefer edits to non-minified files. If you change a minified file directly, note it in the commit message.
- When adding new files, place them into `Tech Consultant - Telarus University_files/` only if they are static assets; prefer creating a `assets/` folder for new development assets to avoid confusing the exported bundle.

What not to do
- Do not presume a Node/NPM build pipeline — none is present. Avoid adding heavy toolchain changes unless the user asks.
- Avoid sweeping auto-formatting changes across many files; this repository is served statically and small diffs are easier to verify.

Examples (common edits)
- Fix a JS bug in `index.js`: ensure jQuery is not referenced before script load; keep `<script src=".../jquery.min.js"></script>` above `<script src=".../index.js"></script>` in `index.html`.
- Change site styles: edit `Tech Consultant - Telarus University_files/style.css` and verify in browser.

If you need more context
- Ask the user where they serve the site from (which root folder), whether they want a build pipeline, or if you should sync changes to the `vsCode - Getting Started` sample folder.

Feedback
- If any part of this guidance is unclear or you'd like me to add repository-specific examples (diffs or safe refactors), tell me which file to open and I'll iterate.
