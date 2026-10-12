# True North Interactive — company site spec (Oct 12, 2026)

## 1. Objective
Company landing page for True North Interactive, indie app studio. Page type:
company site with two product sections. Quality bar: type-first, dark,
premium, TCG-collector aesthetic matching ScanVault's midnight theme.
One page (index.html) + privacy.html. No placeholders — every fact real.

## 2. Design tokens
- bg: #0b0e1a (midnight); bg2: #10162e (card); text: #eef1ff; muted: #9aa3c7;
  line: rgba(255,255,255,.09)
- accent gold: #f2b73c (ScanVault Pro gold — CTAs only)
- accent cyan: #53dbff (Pro diamond — links, live signals only)
- Fonts: display "Sora" (700/800, tight -0.03em), body "Inter" (400/500/600).
  Google Fonts with display=swap. Never Inter as display.
- 8px base unit; radius 16–22px cards; one shadow: 0 18px 50px rgba(0,0,0,.45)
- Buttons: gold filled primary (dark text #1a1405), ghost secondary (1px line)

## 3. Sections (in order)
1. **Nav** (sticky, blur): wordmark "True North Interactive" (Sora 700) +
   diamond glyph; links: Apps, Studio, Contact. Mobile: links collapse to
   anchors row (no hamburger needed for 3 links).
2. **Hero**: kicker "INDEPENDENT APP STUDIO — AJAX, ONTARIO" (mono caps,
   cyan). H1 (clamp(3rem,9vw,7.5rem), balance): "Apps worth collecting."
   Sub (16–18px, pretty, max 60ch): "True North Interactive is an independent
   studio building ScanVault, the trading-card scanner that respects
   collectors — and Hollowreign, a dark-fantasy saga where every victory
   earns a card." Primary CTA "Explore the apps" (scrolls to #apps).
   Secondary "Follow the journey" (scrolls to #contact socials).
   Signature interaction: a holographic trading-card visual (CSS-built,
   5:7 ratio, gold border, diamond emblem, "SCANVAULT" label) that tilts in
   3D following the pointer (transform-only, rAF, disabled on touch and
   prefers-reduced-motion). No stock photos.
3. **Trust strip** (directly under hero, 3 honest signals): "6 TCG series
   supported" · "One-time pricing — no subscriptions" · "Collector-first:
   free scans are unlimited". Real facts from the shipped app.
4. **#apps — ScanVault** (id scanvault): kicker "NOW IN BETA"; H2 "ScanVault".
   Copy: "Scan any trading card and know what it's worth. Unlimited free
   single-card scans, live market prices across six TCG series, pull-rate
   odds, and a $24.99 one-time Pro — never a subscription."
   Feature list (4, real): unlimited free scans · 45 cards per series on
   Free · graded-value estimates & full price history on Pro · eBay deal
   alerts. Status pill: "Coming soon to Google Play". Include 2 REAL app
   screenshots (~/workspace/card-scanner-app/price-history-sheet.png,
   confetti-burst.png — phone screenshots, shown in phone frames).
   CTA: none fake — no dead "download" button. Text: "Launching on Google
   Play. Follow along for the release date."
5. **#apps — Hollowreign** (id hollowreign): kicker "IN DEVELOPMENT"; H2
   "Hollowreign". Copy: "A dark-fantasy tower-defense saga. Collect
   guardian cards as towers, name your Warden, hold the breach — every
   victory earns a card." Status pill: "Coming soon". Visual: CSS art card
   (dark, ember accent #ff7a3c) — no fake screenshots.
6. **#studio — About**: H2 "The studio". Copy (real, no invented team):
   "True North Interactive is an independent app studio in Ajax, Ontario.
   We build collectible-first apps with a simple creed: respect the
   collector. Free tiers that are actually useful. One-time pricing instead
   of subscriptions. No dark patterns." (All verifiable from the products.)
7. **#contact**: H2 "Follow the journey." Social row (5, real URLs):
   YouTube https://www.youtube.com/@truenorthinteractive (LIVE);
   Instagram/TikTok/X/Facebook — wire when the account task reports URLs;
   until then render ONLY live ones (never dead links). Each 44px touch
   target with label.
8. **Footer (destination)**: giant CTA type "Have cards? Scan them."
   (viewport-scale, links to #scanvault). Legal row: Privacy Policy
   (/privacy.html) · Terms (/terms.html — brief honest terms) ·
   "© 2026 True North Interactive. All rights reserved." plus the eBay
   Partner disclosure line (real, from the app footer).

## 4. Copy rules
- Real content only. No invented stats, reviews, awards, download counts.
- Headlines: benefit-led, <15 words, middle-school reading level.
- CTA verbs: Explore, Follow, See. Forbidden: Elevate/Unlock/Seamless/Delve,
  "Learn More", "Click Here", "Submit".
- "True North Interactive", never bare "True North".

## 5. Trust elements
- Trust strip under hero (3 real signals). No fake testimonials/ratings
  (product is pre-launch — inventing them would be fraud).

## 6. Motion
- Hero card: pointer tilt (rotateX/rotateY max 10deg, 120ms ease-out),
  holographic sheen via --mx/--my custom props. Entrance: y:60→0, 700ms.
- Reveal-on-scroll: single IntersectionObserver, opacity/translateY only,
  60ms stagger. prefers-reduced-motion: everything static.
- No scroll-hijack, no parallax, no preloader.

## 7. Signature interaction
The holographic tilting card in the hero (named above). One per page.

## 8. Placeholder audit (pre-ship)
- [ ] All 5 social URLs live (or only live ones rendered)
- [ ] No lorem ipsum; screenshots are the real app
- [ ] "Coming soon" labels where nothing shippable exists
- [ ] privacy.html real policy (adapt from scanvault-data/privacy.html)

## 9. Performance
- Single HTML file + 2 fonts + 2 screenshots. <1MB total. LCP <1.5s.
- transform/opacity animations only. No frameworks.

## 10. SEO/OG/a11y
- Title: "True North Interactive — Apps Worth Collecting" (54 chars)
- Description: "True North Interactive is an independent app studio building ScanVault, the trading-card scanner collectors deserve, and Hollowreign, a dark-fantasy card saga." (~160)
- OG + Twitter card tags. JSON-LD Organization (name, url, sameAs).
  Skip link, focus-visible rings, one H1, semantic sections, alt text.
