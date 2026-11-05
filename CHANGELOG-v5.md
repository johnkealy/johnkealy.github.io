# Changelog v4 → v5 (November 5, 2026)

For Zed: v5 supersedes the v4 package. **No page content changed** — all ten HTML files are byte-identical to v4. This release adds the design-system assets and records decisions made after v4 shipped.

## Added

1. **`lumentity-color-palette.md`** — color system of record (published Nov 3). 9 tokens with roles, WCAG contrast ratios computed and verified for 13 pairings (all pass AA; `--muted` on `--bg` is narrow at 4.55:1 — body-size+ only), 8 usage rules, and §4 "Instructions for AI agents" (tokens-only, no new hex, no dark mode, no gradient additions, gold buttons use ink text). **Follow §4 before writing any page code.**
2. **`icons/` folder** — favicon/icon set (published Oct 28): `icon.svg`, `favicon.ico` (16/32/48), PNGs 512/180/64/48/32/16. Gold chaos star on `--hero-dark` #0b2545, rounded square. The favicon head-tag snippet is in HANDOFF-v5 §4.
3. **`sitemap-v4.csv`** retained (unchanged from v4).

## Recorded decisions

4. **Theme reconfirmed with Eric via Slack, Oct 29, 2026: the build uses UI Suite DaisyUI 5.0.x.** A "mercury" theme that appeared in a repo scan was confusion, not a change of plan. Do not treat mercury as a theme decision.
5. **Git workflow:** John merges a completed content chunk to master first, then Eric merges his config branch (Eric does conflict resolution and flags any resolution that touches content files). New clean Pantheon site **lumentity3** created for the build.

## Open items (updated)

6. Same gates as v4: CHCF sign-off (~70% WAF figure), Zoho form build, Eric's page review — plus one new hygiene item for Eric's config branch: gitignore `settings.ddev.php` or move Mailpit dev-mail config to a committed include; drop stale Symfony Mailer 1.x keys after the 2.x transition.

## Unchanged

- All 10 HTML pages, `logo-chaos-star.svg`, the 10 content rules (now §5 of the handoff), the page inventory, and the not-launching list. The handoff's section numbering shifted by one (assets are the new §4; rules moved from §4 to §5) — references to "rule N" remain valid since rule numbers are unchanged.
