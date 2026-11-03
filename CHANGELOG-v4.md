# Changelog v3 → v4 (October 28, 2026)

For Zed: v4 supersedes the v3 package entirely. Everything below is client-approved as of Oct 28; remaining open items are listed at the end.

## Site-wide

1. **Service subpages now launch with the site.** Decision Oct 28: /services/ai, /services/strategy, /services/web, /services/support go live for SEO/AEO value. `services.html` has been split: overview at `services.html`, subpages in the `services/` folder mirroring the URL map.
2. **No hero CTA button pairs on any services page.** The "What We Offer" / "Discuss Your Situation" (etc.) pairs were removed from the overview and all four subpages as buggy and unnecessary. Each page keeps the header's "Get in Touch" pill and its closing CTA band. **Do not re-add.**
3. **Footer service lists are plain text in the drafts.** Because the subpages now launch, the footer service names SHOULD be links to the subpages in the theme build — the drafts show them as text only because they were neutralized mid-review. Link them.
4. **No /blog link anywhere.** Blog launches absent; all footer Blog links were removed. Do not re-add until /blog exists.
5. **Footer naming fixed:** "Web Development" footer label corrected to "Digital Solutions" on all pages (11 stale instances).
6. **Homepage and services overview service cards:** bullets removed from homepage cards (keep the one-paragraph descriptions); services overview cards keep their bullet lists AND now carry "Explore →" links to the subpages.

## Homepage

7. **New PAWS case card; Sierra Club card removed.** "Our Work" band is now UCSF → UCSF PAWS (Eric as Product Owner, 50% targeted maintenance-cost reduction) → CHCF. Sierra Club remains on the work page only.
8. **FAQ preview band: five items** — WordPress maintenance question added after the Drupal 11 item.

## Services pages

9. **AI subpage lede:** "…answers to your organization — not the tech giants." (was "not to a vendor's terms of service").
10. **Strategy subpage, Assessment & Optimization card:** "An in-depth review of your current platforms, spending, and assets. What's underused, what's missing, and what's costing you more than it should — with a prioritized plan to fix it." (removed "staffing"/"redundant" wording — it read as a critique of client staff).

## FAQ page

11. **WordPress maintenance answer updated with verified workflow:** "test every update in development and staging — with your review of staging before anything is deployed." Verified by John Oct 28; safe to publish.
12. First answer ("Is our data safe if we use AI?") rewritten for flow; "Why would we want a custom AI agent" now opens "To give staff their time back — and better serve your community."

## Open items (not blockers for review)

- **CHCF sign-off on the ~70% WAF figure** (homepage card + work page + FAQ). Confirmed internally, pending client's explicit sign-off.
- **Contact form:** to be built in Zoho and integrated; draft form is the prototype. Spam protection and mailing-list opt-in with consent timestamps remain engineering requirements.
- **Web subpage naming:** content updated to Digital Solutions; h1 ("Platforms built for the long haul") is pre-workshop copy that survived review — fine for launch, revisit later.
- **Eric's review** of all pages is the next gate before theme build.
