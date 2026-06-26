# Across Lines — personal site

A static, multi-page portfolio for Yunzhi (Wendy) Zhang, positioned for AI governance / safety policy roles. Plain HTML/CSS/JS, no build step. Lives at https://wz2002.github.io/.

## Files
```
acrosslines-site/
├── index.html              Home (hero, focus areas, selected writing)
├── about.html              Bio, education, skills (full-bleed photo)
├── research.html           Publications, grouped: AI policy · energy/regulatory · other · independent commentary
├── projects.html           Projects (ONE-AGI, BYOP database, K-12 survey, museum project) + Beyond the work (service)
├── ai-action-plan.html     Independent-commentary article pages,
├── oil-and-renewables.html   each linked from the "Independent
├── iowa-clean-energy.html    commentary" group on research.html
├── redistricting.html
├── styles.css              All styling (one file; colors in :root at the top)
├── main.js                 Scroll-reveal
├── .nojekyll               Tells GitHub Pages to serve files as-is (skip Jekyll)
└── assets/
    ├── Yunzhi-Zhang-Resume.pdf   linked by every "Résumé" button
    └── about.jpg                 the photo on the About page
```

## Preview locally
Open `index.html` in a browser, or run a tiny server from the folder:
```
cd acrosslines-site
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Deploy to GitHub Pages (wz2002.github.io)
Pages is already enabled on the `wz2002.github.io` repo, so pushing new content auto-rebuilds the live site (~30–60s). No build step, no settings to change.

**Option A — command line (cleanest):**
```bash
cd ~/Desktop
git clone https://github.com/WZ2002/wz2002.github.io.git
cd wz2002.github.io
git rm -r .                              # clear the old site (git history kept)
cp -R ~/Desktop/acrosslines-site/. .     # copy in the new site (incl. assets and .nojekyll)
git add -A
git commit -m "Replace site with new portfolio"
git push
```
Then hard-refresh https://wz2002.github.io/ (Cmd+Shift+R).

**Option B — GitHub Desktop (no command line):**
1. Clone the `wz2002.github.io` repo.
2. In Finder, delete the old files in the clone (keep the hidden `.git` folder).
3. Copy in everything from `acrosslines-site` (incl. the `assets` folder and `.nojekyll`).
4. Commit, then Push.

> Avoid plain drag-and-drop upload on github.com: it only overwrites same-named files and leaves old ones behind. Use Option A or B for a clean replace.

## Updating content
- **Text / links:** edit the `.html` files directly.
- **Photo:** replace `assets/about.jpg` (keep the same filename).
- **Résumé:** replace `assets/Yunzhi-Zhang-Resume.pdf` (keep the same filename) — every "Résumé" link keeps working.
- **Styling:** colors live in `:root` at the top of `styles.css` (change `--accent` / `--gold` to re-theme). After editing `styles.css`, bump the `?v=N` number in the `<link rel="stylesheet" ...>` of any page you changed, so browsers fetch the new CSS instead of a cached copy.
- Fonts (Fraunces + Inter + JetBrains Mono) load from Google Fonts.

## Notes
- The résumé stays AI-focused; the site routes energy/regulatory and independent-commentary pieces to their own sections.
- Contact is by email (no form): wendyzhang20021111@gmail.com, plus the footer links (LinkedIn, GitHub).
