# CheqPLAY — CLAUDE.md

## Project Overview
**CheqPLAY** (Chequamegon Partners Learning and Aligning for Youth) is a cross-sector community coalition website for the Chequamegon Bay region of Northern Wisconsin.

- **Live site:** cheqplay.org
- **Repo:** github.com/tandemleap/cheqplay
- **Local:** /Users/scottgriffiths/cheqplay
- **Deployed via:** Vercel (auto-deploy from main branch)
- **DNS:** Namecheap — A record @ → 216.198.79.1, CNAME www → cname.vercel-dns.com
- **Formerly known as:** Planet Youth Chequamegon (no longer affiliated)
- **Administered through:** SPARK / Ashland County Health and Human Services

## Files
- `index.html` — entire site (single-page)
- `cheqplay-logo.png` — official logo
- `treat-bike.png` — treat bike illustration

## Stack
Plain HTML/CSS/JS. No framework, no build step. Edit `index.html` directly and push to deploy.

## Design System
**Fonts:** Fredoka One (headings/display) + Nunito (body)

**Colors:**
```
--green:  #4BAF47
--blue:   #4A90D9
--amber:  #F5A623
--orange: #F47B20
--red:    #E03030
--dark:   #1E2B1A
--cream:  #FDF8F2
--warm-white: #FFFDF9
--text:   #2C3A28
--muted:  #6B7B63
```

**SVG wave dividers** separate sections. Each wave uses the background color of the section *below* it as its fill.

## Page Sections (in order)
1. Nav (sticky)
2. Hero — logo, tagline "This is a good place to grow up.", hero-sub
3. Mode bar (reading mode toggle)
4. Why We Exist
5. How We Work (4 steps)
6. Treat Bike
7. What We Focus On (5 focus items)
8. Our Coalition (partner chips + meeting schedule)
9. Where We Work
10. Get Involved (Formspree form)
11. Stay in the Loop (Formspree email signup)
12. Footer

## Reading Mode Toggle
The site has a dual-content reading mode:
- **"Partner or professional"** — current polished/professional language (default)
- **"Neighbor or family"** — 8th grade reading level, plain language

**Implementation:**
- `.v-pro` elements shown by default; hidden when `body.mode-neighbor` is set
- `.v-neighbor` elements hidden by default; shown when `body.mode-neighbor` is set
- CSS: `body:not(.mode-neighbor) .v-neighbor { display: none; }` and `body.mode-neighbor .v-pro { display: none; }`
- Mode preference saved to `localStorage` key `cheqplay-mode`
- Toggle bar sits between the hero section and the first squiggle divider

When editing content, always update **both** the `.v-pro` and `.v-neighbor` versions for any text block that has dual content.

## Forms
- **Get Involved** + **Stay in the Loop** both post to Formspree: `https://formspree.io/f/mojkjzea`

## Key Contacts
- Coalition Coordinator: Rachel — rachel@lightyourspark.org / 715-413-1585
- Program Director: Scott Griffiths — info@lightyourspark.org / 715.600.3001

## Git / Deploy
```bash
git add index.html
git commit -m "description"
git push
```
Vercel auto-deploys on push to main. No build command needed.
