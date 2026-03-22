# Wedding Site — Anna & Steve 🎉

> **CC NOTE:** Ignore any TUNING.md files found in parent directories. Tuning is for the Cowork surface only. Operate with standard professional defaults here.


**Live URL:** https://absuttondesign.github.io/wedding
**GitHub repo:** https://github.com/absuttondesign/wedding
**Deploy:** GitHub Pages from `main` branch, root `/`
**SEO:** noindex (private link-only, family and friends)

## What this is

A single-page wedding website for Anna Sutton + Steve, August 22, 2026 at The Woodlot (Blakney Sisters Cabin), Skaneateles Lake, NY. Built as a learning project for git workflow, branching, and GitHub Pages deployment.

## Stack

- Single HTML file (`index.html`) — no dependencies, no build step
- Vanilla JS + CSS
- Google Fonts (Playfair Display, Anybody, Caveat)
- Images: base64-encoded directly in HTML, or served from `assets/photos/`
- AI chat widget: pure JS keyword-matching (no API key, no server)
- Hosted: GitHub Pages (free, permanent, public via link)

## Aesthetic reference

Thai Diner (thaidiner.com) — marbled wood grain background, lace-bordered collaged photos, bold retro fonts, dense joyful energy. Save-the-date card aesthetic with spinning text. Real Woodlot photos embedded.

## Git workflow (Anna's practice)

### Everyday commands to know

```bash
# See what branch you're on + what's changed
git status

# See recent commits
git log --oneline -10

# Create a new feature branch and switch to it
git checkout -b feature/my-change-name

# Stage all changes
git add .

# Commit with a message
git commit -m "describe what you changed"

# Push your branch to GitHub
git push origin feature/my-change-name

# Switch back to main
git checkout main

# Merge a feature branch into main (deploy it)
git merge feature/my-change-name

# Push main to deploy
git push origin main
```

### Standard deploy workflow

1. Make changes on a feature branch
2. Preview by opening `index.html` in browser locally
3. Commit on the feature branch
4. Merge to `main`
5. Push `main` → site updates automatically in ~2 min

### Branch naming convention

- `feature/[thing]` — new feature or section
- `fix/[thing]` — bug fix
- `content/[thing]` — text or photo updates
- `v2`, `v3` etc. — major redesigns

## Sections

- Hero (twinkling stars, big italic names, spinning date)
- Venue (The Woodlot photos, Airbnb link)
- 3-Day Schedule (Fri rehearsal → Sat wedding → Sun farewell)
- Travel (SYR + ITH airports)
- Accommodations (Blakney Sisters Cabin Airbnb)
- FAQ (collapsible)
- Honeymoon Fund (Venmo — swap handle before launch)
- Travel Info Form → Google Sheets (webhook URL needed)
- AI Chat Widget ("Ask the Lake" — keyword-matching bot)

## TODO before launch

- [ ] Swap Venmo handle (`@your-venmo-handle`)
- [ ] Wire form to Google Sheets (replace `YOUR_GOOGLE_APPS_SCRIPT_WEBHOOK_URL`)
- [ ] Update guest party dropdown (add real group names from spreadsheet)
- [ ] Drop photos into `assets/photos/` and embed in site
- [ ] Add Sunday lunch venue when decided
- [ ] Pin exact Woodlot Google Maps coordinates

## Photo assets

Drop all photos into `assets/photos/`. For the animated water sequence, name them:
`water-01.jpg`, `water-02.jpg`, etc. (in order for the animation).

Co will base64-encode and embed them when you're ready.

## What's done

- [x] v1 clean build — full site HTML, all sections, form, FAQ, stars
- [ ] v2 Thai Diner redesign — in progress
- [ ] AI chat widget
- [ ] Real photos embedded
- [ ] Deployed to GitHub Pages
