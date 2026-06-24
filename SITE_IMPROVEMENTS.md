# Rockaway Trainer — Website Upgrades (review, then deploy together)
*Staged June 24, 2026. I did NOT edit your live index.html unsupervised — everything here is ready-to-apply code. We apply + `netlify deploy --prod --dir=.` together so nothing on the live site breaks while you're asleep.*

Priority order: **(1) lead-capture form** (stops inquiries from leaking), **(2) JSON-LD upgrade** (SEO), **(3) the small SEO/indexing checklist**.

---

## 1. Lead-capture form (Netlify Forms — no backend needed)
Right now the site only offers text/call/email. A simple form captures people who won't pick up the phone. Netlify auto-detects the form and stores submissions (no server). `thanks.html` is already built in this folder.

**Add this form** into the final CTA section of `index.html` (near the "Text Jamal" buttons). Keep it to 4 fields:

```html
<form name="intro" method="POST" data-netlify="true" netlify-honeypot="bot-field" action="/thanks.html" style="max-width:520px;margin:24px auto 0;text-align:left;">
  <input type="hidden" name="form-name" value="intro" />
  <p hidden><label>Leave blank: <input name="bot-field" /></label></p>

  <label style="display:block;font-weight:700;margin:10px 0 4px;">Name
    <input type="text" name="name" required style="width:100%;padding:12px;border-radius:10px;border:1px solid rgba(22,36,47,.25);font-size:16px;" />
  </label>
  <label style="display:block;font-weight:700;margin:10px 0 4px;">Phone or email
    <input type="text" name="contact" required placeholder="Best way to reach you" style="width:100%;padding:12px;border-radius:10px;border:1px solid rgba(22,36,47,.25);font-size:16px;" />
  </label>
  <label style="display:block;font-weight:700;margin:10px 0 4px;">Which part of Rockaway?
    <input type="text" name="area" placeholder="e.g. Belle Harbor" style="width:100%;padding:12px;border-radius:10px;border:1px solid rgba(22,36,47,.25);font-size:16px;" />
  </label>
  <label style="display:block;font-weight:700;margin:10px 0 4px;">Your goal (optional)
    <textarea name="goal" rows="2" placeholder="e.g. keep muscle on Wegovy" style="width:100%;padding:12px;border-radius:10px;border:1px solid rgba(22,36,47,.25);font-size:16px;"></textarea>
  </label>

  <button type="submit" class="btn inverse" style="margin-top:14px;width:100%;cursor:pointer;border:none;">Book my free intro session</button>
</form>
```

**After deploying, in the Netlify dashboard:**
- Site configuration → Forms → confirm the `intro` form is detected.
- Forms → Notifications → add an **email notification to jamal@rockawaytrainer.com** on every submission (optionally an SMS via Zapier). **Speed-to-lead is the #1 conversion lever — reply within 5–15 min.**

**Reply text that books the session (paste-ready):**
> Hi [NAME], it's Jamal from Rockaway Trainer — thanks for reaching out! I'd love to set up your free 20-min intro. I've got [DAY] at [TIME] or [DAY] at [TIME] open — which works? (And what part of Rockaway are you in?)

---

## 2. JSON-LD upgrade (better local SEO for a service-area business)
Your current `index.html` has a basic `LocalBusiness` block with a street address. For a service-area business, the cleaner approach is `HealthClub` + `areaServed` (no public home address). **Replace the existing `<script type="application/ld+json"> … </script>` block in `<head>` with:**

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "HealthClub",
  "name": "Rockaway Trainer",
  "image": "https://rockawaytrainer.com/og-image.jpg",
  "url": "https://rockawaytrainer.com",
  "telephone": "+1-347-671-2813",
  "email": "jamal@rockawaytrainer.com",
  "priceRange": "$$",
  "description": "In-home personal training on the Rockaway Peninsula. CSCS-certified strength coaching and GLP-1 muscle-preservation programs. $75 per session.",
  "areaServed": [
    { "@type": "City", "name": "Rockaway Beach, Queens, NY" },
    { "@type": "City", "name": "Rockaway Park, Queens, NY" },
    { "@type": "City", "name": "Belle Harbor, Queens, NY" },
    { "@type": "City", "name": "Neponsit, Queens, NY" },
    { "@type": "City", "name": "Breezy Point, Queens, NY" },
    { "@type": "City", "name": "Broad Channel, Queens, NY" },
    { "@type": "City", "name": "Arverne, Queens, NY" },
    { "@type": "City", "name": "Far Rockaway, Queens, NY" }
  ],
  "openingHoursSpecification": [{
    "@type": "OpeningHoursSpecification",
    "dayOfWeek": ["Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"],
    "opens": "06:00", "closes": "20:00"
  }],
  "makesOffer": [
    { "@type": "Offer", "itemOffered": { "@type": "Service", "name": "In-Home Personal Training" }, "price": "75", "priceCurrency": "USD" },
    { "@type": "Offer", "itemOffered": { "@type": "Service", "name": "GLP-1 Muscle-Preservation Training" } }
  ],
  "founder": { "@type": "Person", "name": "Jamal Khan", "hasCredential": "CSCS — NSCA Certified Strength and Conditioning Specialist" },
  "sameAs": [
    "https://www.google.com/maps/place/?cid=YOUR_GBP_CID",
    "https://nextdoor.com/pages/your-page"
  ]
}
</script>
```
Validate at Google's **Rich Results Test** before pushing. Update the two `sameAs` URLs once your GBP and Nextdoor pages exist. (`og-image.jpg` is a placeholder — point it at a real share image, e.g. the boardwalk shot, or remove the line.)

---

## 3. `/review` redirect (for the review-ask system)
Once your GBP is verified and you have your Google review link, add this line to the `_redirects` file so `rockawaytrainer.com/review` jumps straight to the review screen:

```
/review   https://search.google.com/local/writereview?placeid=YOUR_PLACE_ID   302
```
Find your Place ID via Google's Place ID Finder. Then `rockawaytrainer.com/review` is short, textable, and goes on your email signature, post-session cards, and a QR code. (See MARKETING_PLAYBOOK §2.)

---

## 4. Quick SEO checklist
Your title tag is already strong ("Personal Trainer Rockaway Beach NY | In-Home + GLP-1 Weight Loss Training | Rockaway Trainer"). Remaining:
- [ ] **Footer NAP block** identical to GBP: "Rockaway Trainer · (347) 671-2813 · jamal@rockawaytrainer.com · Serving the Rockaway Peninsula." (Matching site NAP to GBP NAP is a ranking factor.)
- [ ] A short **"Where I train"** section listing every neighborhood by name (Belle Harbor, Neponsit, Rockaway Park, Rockaway Beach, Breezy Point, Broad Channel, Arverne, Far Rockaway) — this is your stand-in for per-neighborhood pages.
- [ ] **Google Search Console**: verify the domain, submit `sitemap.xml`, Request Indexing on the homepage.
- [ ] **Citations** with byte-identical NAP: Bing Places, Apple Business Connect, Yelp, a Facebook *business* page, Yellow Pages.
- [ ] Don't bother geotagging photos — Google strips EXIF on upload. Fresh photos uploaded steadily is what matters.

*Full detail + sources: MARKETING_PLAYBOOK.md §4 and §6.*
