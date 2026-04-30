# Repository instructions for Copilot

This repository is a small static website for Stratus Solutions Consulting.

## Source of truth
- Follow the conventions documented in `README.md`.
- Reuse the existing layout, navigation, and stylesheet patterns.
- Keep changes minimal and consistent with the current site.

## File structure
- Root pages live in the repository root: `index.html`, `about.html`, `services.html`, `contact.html`.
- Audience-specific landing pages live in `services/`.
- Shared CSS lives in `css/style.css`.
- Use lowercase filenames and hyphens for new files.

## Link and path rules
- Root pages link CSS with `css/style.css`.
- Pages inside `services/` link CSS with `../css/style.css`.
- Root pages link to other root pages with simple relative links like `about.html`.
- Pages inside `services/` link to root pages with `../about.html`, `../contact.html`, and similar relative paths.
- Pages inside `services/` link to each other with same-folder links like `hybrid-cloud-checklist.html`.

## Page roles
- `owner-clarity.html` is the executive/business-impact landing page.
- `services/hybrid-cloud-checklist.html` is the technical checklist page.
- Keep each page focused on one audience and one primary call to action.

## Design rules
- Reuse the shared header, nav, and card layout across pages.
- Prefer the shared stylesheet over page-specific styling.
- Keep the visual system consistent and lightweight.
- Make small changes rather than introducing one-off styles.

## Editing behavior
- When asked to update a page, preserve the existing theme and structure unless a change is explicitly requested.
- When creating or editing pages, choose relative paths based on the file’s folder.
- If a link or path is ambiguous, infer the correct relative path from the file location.