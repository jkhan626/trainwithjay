# Train With Jay — Claude Code Instructions

## What this is
Jamal's **in-person, in-home personal training** business for the Rockaway peninsula (11694). Separate brand from Liftaroo (deliberately). Single-file static site, no build tools.

## The business (decided June 10, 2026)
- **Model:** Jay travels to client homes. 45-minute 1:1 sessions. Client provides dumbbells (~$50 shopping list if needed); Jay brings bands/mat.
- **Pricing:** **flat $60/session** (founding-rate framing removed June 10 per Jamal — site shows one price, no crossed-out anchor). Per-session ONLY — cash/Venmo/Zelle. **No packages, ever** (Jamal's explicit rule). Raise path for new clients when ~70% booked lives in MARKETING_PLAN.md.
- **Target:** gen-pop weight loss, 30–55, Belle Harbor / Neponsit / Rockaway Park / Rockaway Beach / Breezy Point / Broad Channel.
- **Spearhead niche (June 10):** GLP-1 users (Ozempic/Wegovy/Zepbound) — "lose the fat, keep the muscle." Hero flag + dedicated section + FAQ on the site. Honest claim only: 25–40% of GLP-1 weight loss can be lean mass without resistance training ("studies show"). NEVER advise on meds (dosing/side effects/start/stop) — "ask your prescriber." Cert plan: NESTA GLP-1 Exercise Specialist ($149) + ACE anti-obesity-meds course ($69.95); add the NESTA title to the site only after he earns it.
- **Contact CTA:** text (347) 671-2813 — same number as Liftaroo coaching.
- **Liftaroo tie-in:** light. Sessions logged in Liftaroo (mentioned in About + footer). The $249/mo online coaching is a later upsell, not on this site.

## Stack & deploy
- Single `index.html` — all CSS/JS inline. No frameworks, no build.
- **Repo:** github.com/jkhan626/trainwithjay (branch: master)
- **Netlify site:** `trainwithjay` (project id d1b71177-b730-4175-bfc4-2e5db36f908a), live at https://trainwithjay.netlify.app
- **Deploy:** `netlify deploy --prod --dir=.` from this folder (folder is netlify-linked). Repo is NOT wired to auto-deploy — manual deploys.
- **Domain:** `jaytraining.com` (primary, registered on Namecheap June 2026) + `rockawaytrainer.com` (301 redirect via `_redirects`). Both set on the Netlify site with www aliases. Canonical/JSON-LD point at jaytraining.com.

## Design system
- Palette: sand `#FBF6EC` / deep sand `#F3EAD8` / ink `#16242F` / lifeguard orange `#E2572B` (deep `#C44320`) / seafoam `#7FB6A4`
- Fonts: **Fraunces** (display, variable SOFT/WONK) + **Karla** (body)
- Signature elements: beach-block badges (B. 91st → Breezy), neighborhood ticker, hard offset shadows, paper-grain overlay
- Distinct from Liftaroo's cream/teal on purpose — don't converge them.

## Content rules
- **Never** mention or hint at steroids/PEDs (family privacy — same rule as all Jamal marketing).
- **No "CSCS certified" claim** until he passes it. Site currently says "CSCS and nutrition coach certifications on the way" (his certs are in progress, June 2026) — flip to "certified" the day he passes. No fake testimonials. Credential is "25 years under the bar" + CPR/AED + built Liftaroo.
- **No em dashes in site copy** (Jamal's rule, June 10 2026) — use periods, commas, colons, or parentheses.
- **No emojis in site copy** (Jamal's rule, June 10 2026). The orange ✓ CSS list bullets are fine; pictographic emojis are not.
- Voice: permission, not blame. Anti-gym-intimidation. Same voice as the "[Verb], Dumbass" series.
- Photo placeholder in About section — swap in a real photo when Jamal provides one.

## Key docs
- `MARKETING_PLAN.md` — full launch plan (researched June 2026: pricing data, competitor scan, local channels with phone numbers, legal/insurance, demographics).

## Open manual actions (Jamal, console-side)
1. ~~Domains~~ ✅ jaytraining.com + rockawaytrainer.com registered and added to Netlify — pending: Jamal pastes DNS records into Namecheap (A @ → 75.2.60.5, CNAME www → trainwithjay.netlify.app, on both domains)
2. Liability insurance (~$189/yr — verify CSCS-"in progress" eligibility; CPR/AED ✅ done June 2026)
3. Google Business Profile (service-area business, hide address)
4. Photos for the site + GBP
5. Waiver + PAR-Q forms (Claude drafts on request; lawyer review)
