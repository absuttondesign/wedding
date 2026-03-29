# Wedding Site — Anna & Steve 🎉

> **CC NOTE:** Ignore any TUNING.md files found in parent directories. Tuning is for the Cowork surface only. Operate with standard professional defaults here.


**Live URL:** https://absuttondesign.github.io/wedding
**Venue address:** 91 Woodlot Landing, Skaneateles, NY 13152
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
- [ ] **Le Guin fantasy map** — Anna draws a hand-drawn-style map (like the ones at the beginning of a Le Guin novel). The lake, where people are staying, where the Woodlot is, Bear Swamp, fossil cliffs, where treasure is, where the wind blows from (and who blows it), a sunken boat, a magic rock. Replaces or supplements the Google Maps screenshot. Anna is the artist on this one.

## Photo assets

Drop all photos into `assets/photos/`. For the animated water sequence, name them:
`water-01.jpg`, `water-02.jpg`, etc. (in order for the animation).

Co will base64-encode and embed them when you're ready.

## What's done

- [x] v1 clean build — full site HTML, all sections, form, FAQ, stars
- [x] v2 Thai Diner redesign — marbled wood, lace borders, bold fonts
- [x] Real photos embedded (venue, couple, lake, woodlot)
- [x] Gallery grid — 12 cards, 4-col, colorful floral border-image SVG, spinning daisy stickers, big flower overrides, per-card removals
- [x] Squarer gallery cards (aspect-ratio 5/4), "How to Arrive" card hover flips photo upside-down
- [x] Copy: new-agey photo captions, "Integration Day" Sunday, "Cant Wait" ticker, "come celebrate with us" kicker
- [x] Ask the Lake chat widget — built but hidden (Steve veto, display:none — easy to restore)
- [x] Favicon — inline SVG daisy (pink/orange/yellow/green)
- [x] OG social image — og-image.jpg (blue hat photo, 1200×630, "Wedding Website!" text) + og:image meta tags
- [x] Lodging finder — matched guest name in hot pink (#f472b6)
- [x] Woodlot section — Map It button → Google Maps (91 Woodlot Landing, Skaneateles NY 13152)
- [x] Schedule — ceremony time → Evening, Sunday → Brunch (Midday, venue TBD)
- [x] Gallery card labels — "Locals Headcount" + "Out-of-Towners Lodging Details"
- [x] Styled map image (map.png) with legend + clickable → saved Google Maps list
- [x] Out-of-Towners form — transport options updated (has-car / needs-pickup / no-pickup-needed / not-sure)
- [x] Both forms — "Are you bringing guests?" label in pink, name required with friendly error message
- [x] Both forms — checkbox fix (getAll), button re-enables on network error
- [x] Google Apps Script deployed — both forms POST to Wedding Website Forms sheet (absuttondesign account)
- [x] Webhook wired — both forms live, Bunny test confirmed ✅
- [x] FAQ — dietary simplified, kids/parents removed, Woodlot "coming soon" removed, airport→Airbnb updated, indoors/outdoors updated, ceremony → Evening
- [x] Locals section — "Can't wait to see you!" header + "Let us know who's coming" subhead
- [x] Pushed to GitHub Pages ✅
- [x] Split "Wedding Ceremony & Reception" → two separate checkboxes ("Wedding Ceremony" + "Dinner & Dancing") on both forms
- [x] Consolidated all dietary checkboxes into single `dietary` column in payload (comma-separated)
- [x] Free-text "other" field routes to `notes` column instead of dietary
- [x] New Apps Script deployment with updated doPost column mapping (16 columns: Timestamp through Notes)
- [x] Webhook URLs swapped to new deployment
- [x] Committed as aa81a3c (not yet pushed — HEAD.lock + no GitHub auth)

## Still needed

- [ ] Anna: `rm .git/HEAD.lock && git push` from terminal to deploy form changes
- [ ] Anna: Update Google Sheet column headers to match new doPost order (Timestamp | Form Type | Name | Who Else | Rehearsal Dinner | Wedding Ceremony | Dinner & Dancing | Sunday Picnic | Dietary | Property | Transport | Airport | Arrival | Flight # | Departure | Notes)
- [ ] Swap Venmo handle (`@your-venmo-handle`)
- [ ] Update Airbnb check-in/check-out exact times (currently "exact time TBD") — need Steve's input
- [ ] Add "We'll forward the checkin email a few days before arrival" note to lodging section
- [ ] Add Sunday brunch venue name (currently "venue TBD — details coming soon")
- [ ] Update FAQ airport drive times to furthest Airbnb (currently ~25 min SYR / ~1hr ITH)

## Known: Ask the Lake
The full chat widget JS + HTML is still in the file, just hidden via `#chat-bubble { display:none }`. To restore: change to `display:flex`. Steve may change his mind.
