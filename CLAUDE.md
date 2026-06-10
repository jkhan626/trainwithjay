# Train With Jay — Claude Code Instructions

## What this is
Jamal's **in-person, in-home personal training** business for the Rockaway peninsula (11694). Separate brand from Liftaroo (deliberately). Single-file static site, no build tools.

## The business (decided June 10, 2026)
- **Model:** Jay travels to client homes. 45-minute 1:1 sessions. Client provides dumbbells (~$50 shopping list if needed); Jay brings bands/mat.
- **Pricing:** $75/session standard · **$60 founding rate for first 10 clients, locked for life.** Per-session ONLY — cash/Venmo/Zelle. **No packages, ever** (Jamal's explicit rule). Raise to $90 for new clients at ~70% booked.
- **Target:** gen-pop weight loss, 30–55, Belle Harbor / Neponsit / Rockaway Park / Rockaway Beach / Breezy Point / Broad Channel.
- **Contact CTA:** text (347) 671-2813 — same number as Liftaroo coaching.
- **Liftaroo tie-in:** light. Sessions logged in Liftaroo (mentioned in About + footer). The $249/mo online coaching is a later upsell, not on this site.

## Stack & deploy
- Single `index.html` — all CSS/JS inline. No frameworks, no build.
- **Repo:** github.com/jkhan626/trainwithjay (branch: master)
- **Netlify site:** `trainwithjay` (project id d1b71177-b730-4175-bfc4-2e5db36f908a), live at https://trainwithjay.netlify.app
- **Deploy:** `netlify deploy --prod --dir=.` from this folder (folder is netlify-linked). Repo is NOT wired to auto-deploy — manual deploys.
- **Domain plan:** `trainwithjay.nyc` via Namecheap (trainwithjay.com is taken). Canonical/JSON-LD already point at trainwithjay.nyc.

## Design system
- Palette: sand `#FBF6EC` / deep sand `#F3EAD8` / ink `#16242F` / lifeguard orange `#E2572B` (deep `#C44320`) / seafoam `#7FB6A4`
- Fonts: **Fraunces** (display, variable SOFT/WONK) + **Karla** (body)
- Signature elements: beach-block badges (B. 91st → Breezy), neighborhood ticker, hard offset shadows, paper-grain overlay
- Distinct from Liftaroo's cream/teal on purpose — don't converge them.

## Content rules
- **Never** mention or hint at steroids/PEDs (family privacy — same rule as all Jamal marketing).
- **No CSCS claim** until he passes it. No fake testimonials. Credential is "25 years under the bar" + built Liftaroo.
- Voice: permission, not blame. Anti-gym-intimidation. Same voice as the "[Verb], Dumbass" series.
- Photo placeholder in About section — swap in a real photo when Jamal provides one.

## Key docs
- `MARKETING_PLAN.md` — full launch plan (researched June 2026: pricing data, competitor scan, local channels with phone numbers, legal/insurance, demographics).

## Open manual actions (Jamal, console-side)
1. Register trainwithjay.nyc on Namecheap → connect in Netlify domain settings
2. CPR/AED cert, liability insurance (~$189/yr — verify "cert in progress" eligibility)
3. Google Business Profile (service-area business, hide address)
4. Photos for the site + GBP
5. Waiver + PAR-Q forms (Claude drafts on request; lawyer review)
