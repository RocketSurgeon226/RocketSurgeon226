<!--
# jerms226 — portfolio

Adam "Jerms" Smith's personal portfolio: a static, multi-page site (no build step) covering background, projects, the home lab build, résumé, and contact info. Dark terminal-inspired design that matches the home lab documentation style.

## Pages
- `index.html` — home / about
- `projects.html` — Home Lab, Cr8r Soul, SalesDataAnalyzer
- `homelab.html` — home lab overview (stack, topology, notable fixes)
- `roadmap.html` — full home lab build log (imported from your existing doc)
- `topology.html` — detailed network topology map (imported from your existing doc)
- `resume.html` — résumé summary + PDF download
- `contact.html` — email, phone, LinkedIn, GitHub
- `assets/style.css` — shared stylesheet
- `assets/resume/Adam_Smith_Resume.pdf` — downloadable résumé

## Deploy on GitHub Pages

**Option A — user site (recommended, gives you `https://RocketSurgeon226.github.io`):**

1. On GitHub, create a new repo named exactly `RocketSurgeon226.github.io` (public, no README/license — this folder already has one).
2. From this folder, run:
   ```bash
   git remote add origin https://github.com/RocketSurgeon226/RocketSurgeon226.github.io.git
   git add -A
   git commit -m "Initial portfolio site"
   git branch -M main
   git push -u origin main
   ```
3. Go to the repo's **Settings → Pages**. Under "Build and deployment," set Source to **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. Site goes live at `https://RocketSurgeon226.github.io` within a minute or two.

**Option B — project site (e.g. `https://RocketSurgeon226.github.io/portfolio`):**

Same steps, but name the repo anything you like (e.g. `portfolio`) and use that repo's URL for `git remote add origin`. The live URL will be `https://RocketSurgeon226.github.io/<repo-name>`.

## Updating later
Edit the HTML/CSS locally, then:
```bash
git add -A
git commit -m "describe the change"
git push
```
GitHub Pages redeploys automatically within a minute or two of a push to `main`.

## Notes
- All copy references your Dec 2026 graduation, current Service Desk Analyst role at MOREnet, and Network+ → Security+ → CCNA path — update `index.html` and `resume.html` as your status changes.
- `roadmap.html` and `topology.html` are snapshots of your home lab docs as of 8/25/26 — swap in newer versions any time by replacing those files (keep the filenames the same so links elsewhere in the site keep working).
- Custom domain (e.g. pointing `jerms226.net` here instead of/alongside the homelab tunnel) can be added later via Settings → Pages → Custom domain, plus a CNAME record at your DNS provider.
-->
