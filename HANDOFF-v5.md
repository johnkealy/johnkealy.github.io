# Lumentity Website — Build Handoff v5

**Date:** November 5, 2026
**Supersedes:** v4 package (Oct 28). Content files are unchanged from v4 — this release adds the design-system assets (color palette rules, icon set) and records the theme reconfirmation. Read `CHANGELOG-v5.md` for the diff.

**Status:** All ten pages remain content-final pending Eric Davila's review. Open items: CHCF sign-off (~70% WAF figure), Zoho contact form build, and one config-hygiene fix (see §6). None of these block starting the theme build.

---

## 1. Project context

- **Client:** Lumentity — a two-founder digital agency (John Kealy, Eric Davila) serving universities, healthcare organizations, and nonprofits.
- **Positioning:** Senior-only team; plain-spoken; real numbers over marketing claims; open-source (Drupal/WordPress) and self-hosted AI ("AI you actually own"); long-term partnership over launches.
- **Tagline:** "Digital Solutions to Help Mission-Driven Organizations Succeed in a Rapidly Changing World."
- **Founders:** John Kealy (strategy, governance, AI; ex-UCSF Website Services Manager, current BADCamp President) and Eric Davila (24+ years web platforms, UX/governance; **Product Owner of UCSF's PAWS platform**).

## 2. Target stack

- **CMS:** Drupal, hosted on **Pantheon**; domain **lumentity.com**. A clean site (lumentity3) has been created on Pantheon for the build.
- **Theme:** **UI Suite DaisyUI 5.0.x** — **reconfirmed with Eric Oct 29, 2026 (Slack)**. A "mercury" theme seen in a repo scan was confusion, not a plan change. Fallback: Artisan base theme.
- **Contact form:** built in **Zoho** and integrated — the draft form in `contact.html` is the prototype (fields, copy, structure). Requirements that survive the Zoho build: spam protection, opt-in feeding a mailing list with consent timestamps.
- **Division of labor:** Eric site-builder/strategy; John code.

## 3. Page inventory (10 files)

| File | Page | Status |
|---|---|---|
| `homepage.html` | Home | Content-final, in review |
| `about.html` | About Us (incl. Our People + Mission & Values — no separate pages at launch) | Content-final |
| `services.html` | Services overview (cards link to subpages) | Content-final |
| `services/ai.html` | AI & Automation | Content-final |
| `services/strategy.html` | Digital Strategy | Content-final |
| `services/web.html` | Digital Solutions | Content-final (h1 is pre-workshop copy, accepted) |
| `services/support.html` | Support & Maintenance | Content-final |
| `work.html` | Our Work: UCSF → Eric/PAWS → CHCF → Sierra Club | Content-final |
| `faq.html` | FAQ (18 questions, 5 groups) | Content-final; CHCF figure pending sign-off |
| `contact.html` | Contact | Content-final; Zoho form build pending |

**Not launching:** Blog (absent — and there are **no links to /blog anywhere**; do not re-add), individual case-study pages (work page carries them), Request-a-Free-Audit page (CTAs point to /contact), Resources, Careers.

## 4. Design assets (NEW in v5)

- **`lumentity-color-palette.md`** — the color system of record: 9 tokens with roles, verified WCAG ratios for 13 pairings, 8 usage rules, and **§4 "Instructions for AI agents"** — read that section before generating or editing any page code. Highlights: tokens never raw hex; no new colors; gold buttons use ink text; no dark mode; hero gradient is the only gradient.
- **`icons/`** — the favicon/icon set: gold chaos star on `--hero-dark` (#0b2545), rounded square (rx 22). Contents: `icon.svg` (scalable master), `favicon.ico` (16/32/48), PNGs at 512/180/64/48/32/16. Theme-build integration:
  ```html
  <link rel="icon" href="/favicon.ico" sizes="any">
  <link rel="icon" type="image/svg+xml" href="/icon.svg">
  <link rel="apple-touch-icon" href="/apple-touch-icon.png">  <!-- rename icon-180.png -->
  ```
  Known caveat: at 16px the diagonal arrowheads are near the legibility floor; if it reads muddy at tab size, the fallback is a simplified 4-arrow variant.
- **`logo-chaos-star.svg`** — the full logo mark (unchanged from v4).

## 5. Content rules — do not regress these

1. **No unverifiable claims.** No "100% compliance," "zero downtime," "99.95% uptime." Real numbers only, sources in the copy ("happy to walk through the math").
2. **CHCF wording is client-confirmed** (Oct 23): "markedly improved pace of delivered improvements, at a lower cost than the previous vendor." Do not soften, embellish, or attribute to John's subcontracting.
3. **UCSF figures:** ~1,800 starter-kit sites + ~200 custom; ~$1M/yr savings (2013 analysis). Not "2,000+ sites" or "350+."
4. **PAWS claims:** Eric is Product Owner (public on it.ucsf.edu). The 50% maintenance-cost reduction is a **published UCSF target, not a delivered result** — keep the word "targeted." PAWS ≠ John's starter-kit platform; don't conflate.
5. **WordPress maintenance workflow (verified):** updates tested in development and staging, with client review of staging before production deploy. This wording is approved.
6. **Vocabulary:** "communities" for the people clients serve (not "audiences"/"stakeholders" — except one deliberate use describing clients' internal reality). "Digital Solutions" (not "Web Development"); "Support & Maintenance" (not "Website Support & Maintenance"); "Our Work" (not "Our Experience") in nav and copy.
7. **AI positioning:** "AI you actually own"; hero lede ends "answers to your organization — not the tech giants."
8. **No hero CTA button pairs** on services pages (removed as buggy/unnecessary Oct 28). Pages convert via the header pill and closing CTA band.
9. **Footer service names are plain text in the drafts** — in the theme build, LINK them to the four subpages (they launch now). Homepage service cards stay linkless by design.
10. **Case-study order** on the work page: UCSF (John) → Eric's track record/PAWS → CHCF → Sierra Club. Homepage "Our Work" previews the top three (no Sierra Club card).

## 6. Open items

- **CHCF sign-off** on the ~70% WAF reduction figure (appears: homepage card, work page, FAQ).
- **Zoho form build** + spam protection + consent-timestamped opt-in.
- **Eric's review** of all ten pages — the gate before theme build.
- **Config hygiene (Eric's config branch):** gitignore `settings.ddev.php` or move shared dev mail config (Mailpit) to a committed include; drop the stale Symfony Mailer 1.x keys after the 2.x transition.
- Blog, case-study subpages, Resources, Free-Audit page: all post-launch.
