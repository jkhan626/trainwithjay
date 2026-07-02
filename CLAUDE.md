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

## Design system (revamped July 2, 2026 — "de-AI" pass)
- Palette: sand `#FBF6EC` / deep sand `#F3EAD8` / ink `#16242F` / lifeguard orange `#E2572B` (deep `#C44320`)
- Fonts: **Fraunces** (display) + **Karla** (body)
- **July 2, 2026: Jamal asked for the site to look less "AI."** Removed and do NOT reintroduce: scroll-reveal/staggered animations, the neighborhood marquee ticker, rotated badge chips, hard offset "neo-brutalist" shadows, paper-grain overlay, uppercase orange kicker labels, italic-orange accent words inside headlines, punchline-style headlines, bold zingers at the end of FAQ answers. Keep it plain: real photos, simple cards with 1px borders, plain section headers ("How it works", "Pricing", "About me"). Run new copy through the humanizer skill.
- Photos carry the design now: `photos/jamal-inhome-session.jpg` (hero — real session in a client's living room), `photos/jamal-headshot-gym.jpg` (About), `photos/jay-dog.jpg` (equipment strip), `photos/jay-boardwalk.jpg` (Where I train). `jay-race.jpg` currently unused.
- Distinct from Liftaroo's cream/teal on purpose — don't converge them.

## Content rules
- **Never** mention or hint at steroids/PEDs (family privacy — same rule as all Jamal marketing).
- **CSCS: PASSED June 22, 2026 — now claimed on the site.** As of the July 2, 2026 revamp the About copy claims CSCS (NSCA) + CPR/AED only; the earlier "nutrition coach certification on the way" line was DROPPED (cert is deferred until paying clients, so claiming it was iffy — Jamal can veto). No fake testimonials. Credentials are CSCS + CPR/AED + 25 years under the bar + built Liftaroo.
- **No em dashes in site copy** (Jamal's rule, June 10 2026) — use periods, commas, colons, or parentheses.
- **No emojis in site copy** (Jamal's rule, June 10 2026). The orange ✓ CSS list bullets are fine; pictographic emojis are not.
- Voice: permission, not blame. Anti-gym-intimidation. Same voice as the "[Verb], Dumbass" series.
- Real photos now live throughout the site (see Design system).

## Key docs
- `MARKETING_PLAN.md` — full launch plan (researched June 2026: pricing data, competitor scan, local channels with phone numbers, legal/insurance, demographics).

## Marketing preferences (set June 23, 2026 — IMPORTANT, overrides parts of MARKETING_PLAN.md)
- **Jamal will NOT do warm-network solicitation.** No texting friends/neighbors to drum up clients, and **no posting "hire me" to his personal social** (personal IG/FB). This kills the plan's original Phase 1 "ex-wife playbook" (announcement texts) and the personal-social launch post. Do not re-suggest them.
- **Jamal will NOT do in-person cold outreach** ("that's not me," June 24, 2026) — no walking printed flyers into offices/med spas/pharmacies, no cold desk drop-offs. So B2B must be **digital**: email the clinic/partner (attach or link the one-pager) and follow up by email/phone. The flyer is a digital leave-behind (email attachment / linked PDF at rockawaytrainer.com/flyer.html), NOT hand-delivered. Don't re-suggest walk-ins or drop-offs.
- **What he IS fine with:** sharing the CSCS win as a *personal IG story with no ask* (celebration, not a pitch); a separate **business** account (@trainwithjay-style); inbound and B2B channels.
- **So the active strategy is inbound + earned-media + B2B first:** Google Business Profile, Nextdoor, the Rockaway Times "local guy builds app, now trains neighbors" story, and referral partners (Beach NY PT, GLP-1 prescribers/med spas). Honest tradeoff noted to him: this is slower to a first client than warm network, but it's the version he'll actually execute.
- **Bigger-picture (June 23):** Jamal flagged he's been collecting certs instead of getting clients and wants to **make money first**. Don't push more certifications (incl. PN1/nutrition) until he has paying clients — let demand pull the next cert.

## Status & wins — updated July 2, 2026
- **The Wave column is LIVE (recurring earned media).** Jamal writes a **bi-weekly column, "The Rockaway Trainer,"** in The Wave (Rockaway's paper of record). Editor: **Mark C. Healey — mhealey@rockawave.com** (submissions also editor@rockawave.com). Column #1, "Lose the Fat, Keep the Muscle" (GLP-1 muscle preservation, ~560 words + photo), written and sent. **How columns get written: Jamal writes each piece himself in his own voice**; Claude gives bullets/a plain draft and runs the humanizer, then Jamal rewrites it. His hard style rules: **NO em dashes, NO colons, NO emojis**, and he worries about AI detectors (the humanizer skill handles that). Topics banked for future columns: "strength training at home with no equipment" (#2, drafted, points to /homeworkout), "staying strong after 50," "protect your knees at home" (KneesOverToes-style).
- **Beach NY Physical Therapy = warm referral partner.** Nick Vourderis, clinical director, Howard Beach office (**nvourderis@beachnypt.com**), replied to outreach. Jamal is **meeting him in person Wed July 8, 2026** to build a two-way referral pipeline (post-rehab patients who need to keep getting stronger). The differentiator pitched: Jamal **sends short progress notes back** on referred patients. Post-rehab referrals are his #1 channel per the research.
- **In-person nuance:** Jamal WILL do invited/scheduled in-person meetings with warm partners (like this PT meeting). The "no in-person" rule only rules out COLD walk-ins and flyer drops.
- **Public phone = Google Voice (347) 313-8748** everywhere public; personal cell (the Liftaroo number) stays private, off all materials.
- **Site lead form is live** (Netlify Forms "intro" -> emails jamal@rockawaytrainer.com + jamalknyc@gmail.com; ~10-min notification delay). JSON-LD upgraded to HealthClub.
- **/homeworkout page built, NOT yet deployed** (`homeworkout/index.html`): free home-workout landing page (warmup + 5-move circuit: squat, single-leg RDL with a gallon of water, push-up, backpack row, **bird dog** [chosen over plank; McGill Big 3]). Waiting on 6 demo photos (hero + squat/rdl/pushup/row/birddog) dropped into `homeworkout/images/`, then commit + deploy. Column #2 and the desk sign point here.
- **Print materials built** (print-ready PNGs in repo root, generated HTML -> Chrome headless. IMPORTANT: give print shops the **PNGs, not PDFs** — Chrome PDFs have unembedded fonts that Vistaprint rejects): **square double-sided business cards** (`Rockaway-Trainer-card-FRONT/BACK.png`) and a **"Tap or scan" table tent desk sign** (`Rockaway-Trainer-desk-sign.png`) for referral-partner front desks. QR + an NFC tag both point to rockawaytrainer.com. Source HTML in `print/`; QR is `qr-rockawaytrainer.png`. Cards being printed **local** (Rockaway Graphics, 91-19 Rockaway Beach Blvd, rockawaygraphics@verizon.net, (718) 634-1089; or Belle Harbor Cards & More, 442 Beach 129th St, mail@belleharborcards.com, (718) 474-4474). Table tent likely Vistaprint.
- **Humanizer skill installed** at `~/.claude/skills/humanizer` (github.com/blader/humanizer, markdown-only, safe). Run it as the editing pass on any drafted writing.
- **NESTA "GLP-1 Exercise Specialist" (~$149) is the ONE cert worth buying now** — a real, usable title that stays in the exercise (not medical) lane and directly sells the GLP-1 niche. Not yet earned. The day he passes, add "GLP-1 Exercise Specialist (NESTA)" to the flyer, site, and GBP. (Still deferring PN1 and other certs.)

## Open manual actions (Jamal, console-side)
1. ~~Domains~~ ✅ rockawaytrainer.com (primary) + jaytraining.com (redirects in), DNS live, both on Netlify with www aliases. Done.
2. Liability insurance (~$189/yr) — CSCS now in hand (passed June 22), so the "in-progress eligibility" caveat is gone; CPR/AED ✅ done June 2026. Still needed before training a stranger.
3. Google Business Profile (service-area business, hide address) — **in progress June 23**; name "Rockaway Trainer", site rockawaytrainer.com, $75, description must have NO phone/URL (Google rejects those in the description field).
4. Photos for the site + GBP
5. Waiver + PAR-Q forms (Claude drafts on request; lawyer review)
