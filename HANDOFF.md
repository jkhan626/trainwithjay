# Rockaway Trainer — Session Handoff (START HERE)
*Last updated July 2, 2026. Read this first, then dive into the linked docs as needed. This is the fast catch-up for a fresh session.*

## Read these (in this order)
1. **CLAUDE.md** — project instructions + the "Status & wins" section (kept current). Auto-loads.
2. **GROWTH_PLAN.md** — the master strategy and 30/60/90 sequence.
3. **MARKETING_PLAYBOOK.md** — the how-to systems (GBP, reviews, Nextdoor, referrals, lead capture) with copy/paste templates.
4. **MARKETING_OUTREACH.md** — the target list and who has been contacted.
5. **MARKETING_PLAN.md** — original positioning, offer, and phases.

---

## The business in a nutshell
- **What:** Rockaway Trainer, in-home personal training on the Rockaway peninsula, Queens NY. Trainer comes to the client's home.
- **Owner:** Jamal Khan. CSCS (NSCA), MPA, doctoral student in public health at Johns Hopkins, 25 years lifting, built the Liftaroo fitness app.
- **Offer:** 45-minute one-on-one in-home sessions. Flat **$75/session**, per-session only, no packages. Target: adults roughly 30 and up who want to lose weight, get strong, and stay independent.
- **Niche and edge:** **GLP-1 muscle preservation** ("lose the fat, keep the muscle") for people on Ozempic, Wegovy, Zepbound, Mounjaro. This is the #1 channel and differentiator.
- **Brand:** rebranded from "Train With Jay" to **Rockaway Trainer** (June 2026), and uses his real name Jamal (not "Jay").
- **Public phone:** Google Voice **(347) 313-8748**. **Email:** jamal@rockawaytrainer.com. Personal cell stays private, off all materials.
- **Site:** rockawaytrainer.com. Static single-page site, folder/repo is `trainwithjay`, hosted on Netlify (manual deploy: `netlify deploy --prod --dir=.`).

## Marketing strategy (and it's working)
Inbound + earned media + B2B referrals. He does **NOT** do warm-network solicitation or personal-social pitching. Channels:
- **Inbound:** Google Business Profile, Nextdoor, the website + lead form.
- **Earned media:** a recurring column in The Wave.
- **B2B referrals:** physical therapists, chiropractors, and GLP-1 prescribers / med spas. Post-rehab and GLP-1 referrals are the highest-ceiling channels.

## Current state / in flight (July 2, 2026)
- **The Wave column is live.** Recurring bi-weekly, called "The Rockaway Trainer." Editor **Mark C. Healey (mhealey@rockawave.com)**. Column #1 (GLP-1 muscle preservation) sent. Column #2 ("strength training at home, no equipment") in progress, points to /homeworkout.
- **Beach NY PT referral meeting.** Clinical director **Nick Vourderis (nvourderis@beachnypt.com)**, meeting in person **Wed July 8, 2026**. Hook: Jamal sends progress notes back on referred patients.
- **Business cards + "tap or scan" table-tent desk sign** being printed (local shops / Vistaprint). QR + NFC point to rockawaytrainer.com.
- **/homeworkout page** built but NOT deployed. Waiting on 6 demo photos in `homeworkout/images/`, then deploy.
- **Site lead form** live (Netlify Forms).
- **GBP** in progress (needs verification + photos).

## Next actions (his to pace)
- Finish and verify the **Google Business Profile** + add photos (biggest inbound lever).
- Shoot the 6 workout photos, then deploy **/homeworkout**.
- Follow up with non-responders, especially **Nicole Frontera** (he's a customer).
- Set up **Nextdoor** business page.
- Earn the **NESTA GLP-1 Exercise Specialist** cert (~$149), then add "GLP-1 Exercise Specialist (NESTA)" to the flyer, site, and GBP.
- More **PT/chiro** and **GLP-1 med-spa** referral outreach.

## How Jamal works (IMPORTANT for the assistant)
- Learns by discussion, conversational, not walls of text. Be direct and give a recommendation, not a survey.
- **Writing style rules: no em dashes, no colons, no emojis.** He worries about AI detectors.
- **Column workflow:** Claude gives bullets or a plain draft and runs the **humanizer** skill, then Jamal rewrites it in his own voice, then humanize once more. (Humanizer installed at `~/.claude/skills/humanizer`.)
- **Won't do:** cold-text friends, post "hire me" to personal social, cold walk-in or flyer drops. **Will do:** invited/scheduled in-person meetings with warm partners.
- **Certs:** deferring everything except the NESTA GLP-1 Exercise Specialist.
- **Outreach emails:** Claude drafts, Jamal reviews and sends himself. Do not auto-send. He sends from jamal@rockawaytrainer.com (watch the Gmail From dropdown, it defaults to jamalknyc@gmail.com).

## Setup and assets
- **Domain:** rockawaytrainer.com is primary; jaytraining.com 301-redirects in. Netlify site `trainwithjay`.
- **Email:** ImprovMX forwards to Gmail (jamalknyc@gmail.com); Gmail "send as" jamal@rockawaytrainer.com via a Google app password.
- **Repo:** github.com/jkhan626/trainwithjay. Not auto-deploy; manual `netlify deploy --prod --dir=.`.
- **Collateral in repo:** flyer (`Rockaway-Trainer-flyer.pdf`), neighborhood poster (`Rockaway-Trainer-poster.pdf`), business cards + table-tent sign (`Rockaway-Trainer-card-FRONT/BACK.png`, `Rockaway-Trainer-desk-sign.png`, source in `print/`), QR (`qr-rockawaytrainer.png`).

## Key contacts
- **Mark C. Healey** — The Wave, editor — mhealey@rockawave.com
- **Nick Vourderis** — Beach NY Physical Therapy, clinical director (Howard Beach) — nvourderis@beachnypt.com
- **Nicole Frontera** — Nicole Frontera Beauty (Rockaway Park med spa, GLP-1 partner) — nicole@nicolefronterabeauty.com
- **Dr. Vincent Esposito** — Rockaway Family Chiropractic — rockawayfamilychiro@gmail.com
- **Print:** Rockaway Graphics (718) 634-1089 / rockawaygraphics@verizon.net; Belle Harbor Cards (718) 474-4474 / mail@belleharborcards.com
