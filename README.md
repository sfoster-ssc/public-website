# Public Website

This repository contains a static public website (HTML/CSS/JS) exported into the `vsCode - Public Website` folder.

## Preview locally

From inside the `vsCode - Public Website` folder run:

```powershell
python -m http.server 8000
```

Then open http://localhost:8000 in your browser.

## Uploading to GitHub (quick steps)

1. Initialize or clone the repository:

- Initialize in-place:

```powershell
cd "c:\Users\StevenFoster\OneDrive - Stratus Solutions Consulting\Documents\vsCode - Public Website"
git init
```

- Or clone the remote and copy files into it:

```powershell
git clone https://github.com/sfoster-ssc/public-website.git my-site-clone
# copy files into my-site-clone, then
cd my-site-clone
```

2. Configure Git user (if needed):

```powershell
git config user.name "Your Name"
git config user.email "you@example.com"
```

3. Add remote (if you initialized in-place):

```powershell
git remote add origin https://github.com/sfoster-ssc/public-website.git
```

4. Commit & push:

```powershell
git add .
git commit -m "Initial site upload"
git branch -M main
git push -u origin main
```

You can authenticate using HTTPS + a Personal Access Token (PAT) or SSH keys (recommended).

## GitHub Pages

- After pushing, enable GitHub Pages in the repository settings (Source: `main` / root). The published URL will appear in the Pages section.
- Common Pages URL: `https://sfoster-ssc.github.io/public-website/` (may vary until Pages is ready).

## Notes

- Static assets are stored alongside the HTML files — preserve relative paths when copying.
- Edit non-minified CSS/JS files when possible and verify in a local preview before pushing.

---

If you want, I can now initialize Git in this folder and push the site for you; tell me whether to use HTTPS (PAT) or SSH.