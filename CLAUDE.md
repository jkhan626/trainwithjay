# Rockaway Trainer — Claude Code Instructions

## What this is
Jamal's **in-person, in-home personal training** business for the Rockaway peninsula (11694). Separate brand from Liftaroo (deliberately). Single-file static site, no build tools.

**Brand history (June 23, 2026):** rebranded from "Train With Jay" to **Rockaway Trainer**, and the public-facing name switched from "Jay" to **Jamal** (his real name). The exact-match name was chosen to fit the inbound/local-search strategy (see Marketing preferences below). The folder/repo/Netlify site are all still named `trainwithjay` — that's fine, nobody sees those; only the live copy + domain changed. "Train With Jay" is kept as the JSON-LD `alternateName` for search continuity.

## The business (decided June 10, 2026)
- **Model:** Jamal travels to client homes. 45-minute 1:1 sessions. Client provides dumbbells (~$50 shopping list if needed); Jamal brings bands/mat.
- **Pricing:** **flat $75/session** (the live site shows $75 in all four spots — this is the real price; an earlier $60 in these docs was stale and was corrected June 23, 2026). Per-session ONLY — cash/Venmo/Zelle. **No packages, ever** (Jamal's explicit rule). Raise path for new clients to ~$90 when ~70% booked lives in MARKETING_PLAN.md.
- **Target:** gen-pop weight loss, 30–55, Belle Harbor / Neponsit / Rockaway Park / Rockaway Beach / Breezy Point / Broad Channel.
- **Spearhead niche (June 10):** GLP-1 users (Ozempic/Wegovy/Zepbound) — "lose the fat, keep the muscle." Hero flag + dedicated section + FAQ on the site. Honest claim only: 25–40% of GLP-1 weight loss can be lean mass without resistance training ("studies show"). NEVER advise on meds (dosing/side effects/start/stop) — "ask your prescriber." Cert plan: NESTA GLP-1 Exercise Specialist ($149) + ACE anti-obesity-meds course ($69.95); add the NESTA title to the site only after he earns it.
- **Contact CTA:** text (347) 313-8748 — a **dedicated Google Voice number** (set up June 24, 2026) for Rockaway Trainer that forwards calls + texts to Jamal's cell. His personal cell (= the Liftaroo coaching number) now stays **private** and is kept off all public materials (site, flyer, GBP, signatures). Use the Google Voice number everywhere public.
- **Liftaroo tie-in:** light. Sessions logged in Liftaroo (mentioned in About + footer). The $249/mo online coaching is a later upsell, not on this site.

## Stack & deploy
- Single `index.html` — all CSS/JS inline. No frameworks, no build.
- **Repo:** github.com/jkhan626/trainwithjay (branch: master)
- **Netlify site:** `trainwithjay` (project id d1b71177-b730-4175-bfc4-2e5db36f908a), live at https://trainwithjay.netlify.app
- **Deploy:** `netlify deploy --prod --dir=.` from this folder (folder is netlify-linked). Repo is NOT wired to auto-deploy — manual deploys.
- **Domain:** `rockawaytrainer.com` (**primary** as of June 23, 2026) + `jaytraining.com` (now 301-redirects *into* rockawaytrainer.com via `_redirects`). Both registered on Namecheap, both set on the Netlify site with www aliases, DNS live (A `@` → 75.2.60.5). Canonical/JSON-LD point at rockawaytrainer.com. Netlify primary domain = rockawaytrainer.com (set via `netlify api updateSite`; flipping it is required *before* deploying any redirect change or you get a redirect loop).
- **Email — `jamal@rockawaytrainer.com` (set up June 23, 2026, free).** Receives via **ImprovMX** (free forwarding → `jamalknyc@gmail.com`; MX `mx1/mx2.improvmx.com`, SPF `v=spf1 include:spf.improvmx.com ~all`, DNS at Namecheap). Sends via **Gmail "Send mail as"** using **Gmail's own SMTP** (`smtp.gmail.com:587`, username = full Gmail address, password = a Google App Password) — NOT ImprovMX SMTP (that's premium). Same method as `support@liftaroo.app`. Full reusable recipe in the master `Claude/CLAUDE.md` → "Setting Up Free Custom-Domain Email."

## Design system
- Palette: sand `#FBF6EC` / deep sand `#F3EAD8` / ink `#16242F` / lifeguard orange `#E2572B` (deep `#C44320`) / seafoam `#7FB6A4`
- Fonts: **Fraunces** (display, variable SOFT/WONK) + **Karla** (body)
- Signature elements: beach-block badges (B. 91st → Breezy), neighborhood ticker, hard offset shadows, paper-grain overlay
- Distinct from Liftaroo's cream/teal on purpose — don't converge them.

## Content rules
- **Never** mention or hint at steroids/PEDs (family privacy — same rule as all Jamal marketing).
- **CSCS: PASSED June 22, 2026 — now claimed on the site.** The About copy reads "a CSCS (Certified Strength and Conditioning Specialist) through the NSCA and CPR/AED certified, with a nutrition coach certification on the way." Nutrition cert is still in progress (PN1 under consideration, but **deferred until he has paying clients** — see Marketing preferences). No fake testimonials. Credentials are now CSCS + CPR/AED + 25 years under the bar + built Liftaroo.
- **No em dashes in site copy** (Jamal's rule, June 10 2026) — use periods, commas, colons, or parentheses.
- **No emojis in site copy** (Jamal's rule, June 10 2026). The orange ✓ CSS list bullets are fine; pictographic emojis are not.
- Voice: permission, not blame. Anti-gym-intimidation. Same voice as the "[Verb], Dumbass" series.
- Photo placeholder in About section — swap in a real photo when Jamal provides one.

## Key docs
- `MARKETING_PLAN.md` — full launch plan (researched June 2026: pricing data, competitor scan, local channels with phone numbers, legal/insurance, demographics).

## Marketing preferences (set June 23, 2026 — IMPORTANT, overrides parts of MARKETING_PLAN.md)
- **Jamal will NOT do warm-network solicitation.** No texting friends/neighbors to drum up clients, and **no posting "hire me" to his personal social** (personal IG/FB). This kills the plan's original Phase 1 "ex-wife playbook" (announcement texts) and the personal-social launch post. Do not re-suggest them.
- **Jamal will NOT do in-person cold outreach** ("that's not me," June 24, 2026) — no walking printed flyers into offices/med spas/pharmacies, no cold desk drop-offs. So B2B must be **digital**: email the clinic/partner (attach or link the one-pager) and follow up by email/phone. The flyer is a digital leave-behind (email attachment / linked PDF at rockawaytrainer.com/flyer.html), NOT hand-delivered. Don't re-suggest walk-ins or drop-offs.
- **What he IS fine with:** sharing the CSCS win as a *personal IG story with no ask* (celebration, not a pitch); a separate **business** account (@trainwithjay-style); inbound and B2B channels.
- **So the active strategy is inbound + earned-media + B2B first:** Google Business Profile, Nextdoor, the Rockaway Times "local guy builds app, now trains neighbors" story, and referral partners (Beach NY PT, GLP-1 prescribers/med spas). Honest tradeoff noted to him: this is slower to a first client than warm network, but it's the version he'll actually execute.
- **Bigger-picture (June 23):** Jamal flagged he's been collecting certs instead of getting clients and wants to **make money first**. Don't push more certifications (incl. PN1/nutrition) until he has paying clients — let demand pull the next cert.

## Open manual actions (Jamal, console-side)
1. ~~Domains~~ ✅ rockawaytrainer.com (primary) + jaytraining.com (redirects in), DNS live, both on Netlify with www aliases. Done.
2. Liability insurance (~$189/yr) — CSCS now in hand (passed June 22), so the "in-progress eligibility" caveat is gone; CPR/AED ✅ done June 2026. Still needed before training a stranger.
3. Google Business Profile (service-area business, hide address) — **in progress June 23**; name "Rockaway Trainer", site rockawaytrainer.com, $75, description must have NO phone/URL (Google rejects those in the description field).
4. Photos for the site + GBP
5. Waiver + PAR-Q forms (Claude drafts on request; lawyer review)
