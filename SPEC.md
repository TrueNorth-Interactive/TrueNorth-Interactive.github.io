# True North Interactive — company site spec (Nov 24, 2026)

Rebuilt Nov 24, 2026 (real visuals + premium interactions): every product
now shows real screenshots or real footage instead of icons/key art, the
dead holographic-card code is gone, and the tilt + scroll-glow interactions
are live. The Oct 12 spec described the two-product launch version; the
site has grown to six products since, and the spec below is the current
truth.

## 1. Objective
Company landing page for True North Interactive, indie app studio. Page type:
company site with six product sections. Quality bar: type-first, dark,
premium, TCG-collector aesthetic matching ScanVault's midnight theme.
One page (index.html) + privacy.html + terms.html. No placeholders — every
fact real, every visual a real screenshot, real footage, or the product's
own key art already in use. No stock photos, no AI art standing in for a
product.

## 2. Design tokens
- bg: #0b0e1a (midnight); bg2: #10162e (card); text: #eef1ff; muted: #9aa3c7;
  line: rgba(255,255,255,.09)
- accent gold: #f2b73c (ScanVault Pro gold — CTAs only)
- accent cyan: #53dbff (Pro diamond — links, live signals only)
- accent ember: #ff7a3c (Hollowreign / OUTBREAK); accent magenta: Point Fingers
- Fonts: display "Sora" (700/800, tight -0.03em), body "Inter" (400/500/600).
  Google Fonts with display=swap. Never Inter as display.
- 8px base unit; radius 16–22px cards; one shadow: 0 18px 50px rgba(0,0,0,.45)
- Buttons: gold filled primary (dark text #1a1405), ghost secondary (1px line)

## 3. Sections (in order)
1. **Nav** (sticky, blur): wordmark "True North Interactive" (Sora 700) +
   diamond glyph; links: Apps, Studio, Contact. Mobile: links collapse to
   anchors row (no hamburger needed for 3 links).
2. **Hero**: kicker "Independent app studio — Ajax, Ontario" (mono caps,
   cyan). H1 (clamp(3rem,9vw,7.5rem), balance): "Apps worth collecting."
   Sub (16–18px, pretty, max 60ch): names all six products in one sentence —
   ScanVault, Hollowreign, MorningMission, OUTBREAK, Point Fingers, On This
   Day. Primary CTA "Explore the apps" (scrolls to #apps).
   Secondary "Follow the journey" (scrolls to #contact socials).
   Hero tiles (replaces the Oct 12 holographic card — see §7): six tiles,
   one per product, each with kicker, name, one-line pitch and status:
   ScanVault "Now in beta" · Hollowreign "In development" · OUTBREAK
   "Live on Roblox" · MorningMission "In testing" · Point Fingers "Play now
   on the web" · On This Day "Watch on YouTube". No stock photos.
   A `.hero-glow` layer drifts with scroll (see §6).
3. **Trust strip** (directly under hero, 3 honest signals): "Six products,
   one studio" · "One-time pricing — no subscriptions" · "Independent —
   Ajax, Ontario". Real facts from the shipped products.
4. **#apps — intro**: kicker "The lineup"; H2 "Six apps. One studio."
   Sub: "One in beta, one in testing, two playable now, one in development,
   one new every day — each built around collecting something: cards,
   guardians, missions, survival, bragging rights, or a story worth
   remembering."
5. **#apps — ScanVault** (id scanvault): kicker "NOW IN BETA"; H2 "ScanVault".
   Copy: "Scan any trading card and know what it's worth — then shelve it
   in your digital binder. One binder per TCG series, your whole collection
   organized, valued, and always with you. 7 days free with everything
   unlocked, then a $24.99 one-time purchase — yours forever, never a
   subscription. Cards you earn in our other games are always free to add,
   even after the trial ends."
   Feature list (5, real): digital binders per series · 7 days free,
   everything unlocked · your binder stays yours after the trial ·
   graded values & full price history · eBay deal alerts.
   "How it's built" (3, real): on-device ML Kit OCR (photos never leave
   the phone) · live prices from TCGdex, PriceCharting and more · card
   database and pull rates updated weekly.
   Status pill: "Coming soon to Google Play". 2 REAL app screenshots in
   phone frames (screenshots/sv-binder.webp — the binder, CA$2,129, nine
   cards with live prices; screenshots/sv-home.webp — the FULL Home tab,
   412x2660, scrolling inside the frame with a fixed tab-bar strip
   screenshots/sv-tabbar.webp and a Scroll cue that hides once scrolled).
   Both frame images use object-fit:fill — object-fit:none painted them at
   natural size (cropped/zoomed); the caption is two lines at
   bottom:-44px so it clears the pinned tab bar (a 4-line caption at
   bottom:-34px grew upward into the frame and covered it).
   Home captured Nov 24 from the real app (fresh profile, country set to
   Canada via Settings so prices read CA$; sample card used so Hot products
   shows; live Pokémon 100 ticker 988.4). Portfolio reads CA$0.00 — the
   local run's binder is empty; no values fabricated. Binder flip NOT built
   (Dan, Nov 24): the real binder is a single 9-pocket page — verified in
   the app (1 page dot, prev/next hidden) and the local binder is empty
   (0 cards, also 1 page) — so there are no real extra pages to flip
   through; no pages fabricated. The old CSS "illustrated scan moment" figure and
   its CSS are gone (removed Nov 24); the price-history sheet and confetti
   shots (price-history-sheet.png, confetti-burst.png) stay in the repo but
   are no longer on the page.
   CTA: none fake — no dead "download" button. Text: "Launching on Google
   Play. Follow along for the release date."
6. **#apps — Hollowreign** (id hollowreign): kicker "IN DEVELOPMENT"; H2
   "Hollowreign". Copy: "A dark-fantasy tower-defense saga. Collect
   guardian cards as towers, name your Warden, hold the breach — every
   victory earns a card." 3 points: guardian cards are your towers (twelve
   guardians) · a Warden you name and drive · every victory earns a card.
   Status pill: "Coming soon". Visual: 2 REAL gameplay screenshots —
   screenshots/hr-level2-battle.webp — a real Level 2 (Dark Forest) night-1
   battle in a LANDSCAPE phone frame (.phone.land, 915x412, sideways like
   the battle plays; the .phones stack vertically for this block), Nov 24,
   captured headless from the ship file with the Warden + Mauler/Archer/
   Spark holding the campfire against the horde, an enemy ON the fire and
   damage numbers visible (re-shot Nov 24 — Dan: the first capture read as
   a quiet camp, enemies far from the fire); and screenshots/hr-level1-
   battle.webp — a real Level 1 (Vault Keep) wave-1 battle, Nov 24, enemies
   on the torch-lit road with HP bars, a guardian engaged and damage
   numbers (-29/-18/-34) visible. The Level 1 frame stays PORTRAIT: the
   vault chapter is portrait-only in the game (code-proven rotate gate —
   landscape shows a rotate screen, waves never play), so a portrait frame
   is the honest one, not a letterbox. It replaces the saga map (hr-saga.
   webp, a menu, removed from the repo Nov 24 — Dan: show Level 1 playing,
   not the map). The modes-screen shot (hr-modes.webp) was replaced Nov 24
   — Dan: the two shots were menus, not gameplay. Nov 24, Dan: NO black
   camera pill on any phone frame — the .phone::after and .phone.land::
   after rules are deleted site-wide; every phone frame (all products)
   shows its image edge to edge inside the frame bezel. The key art
   (screenshots/hollowreign-keyart.webp) stays in the repo and is still
   the OG image, but is no longer on the page.
7. **#apps — OUTBREAK** (id outbreak): kicker "LIVE NOW ON ROBLOX"; H2
   "OUTBREAK". Copy: zombie survival extraction — cross a massive living
   city, scavenge weapons, fight to the helicopter; die and you respawn as
   infected, hunting your friends. 4 points: die and you join them · 7
   zombie variants with real senses (sight, smell, hearing) · pets that
   fight beside you · helicopter extraction.
   Status pill: "Play now on Roblox". Play link (real, live):
   https://www.roblox.com/games/119609872282173/OUTBREAK
   Visual: official poster (screenshots/outbreak-poster.png) — the ONLY
   product still shown with key art instead of a real screenshot: every
   real OUTBREAK gameplay frame in the workspace is defaced by QA
   annotation boxes or a giant DIAGNOSTICS panel. A clean shot needs a
   fresh capture from Dan's phone with diagnostics off.
   KNOWN GAP (Nov 24): the poster art itself has "COMING SOON TO ROBLOX"
   baked into the image, which contradicts the "Live now on Roblox" copy
   and caption. Do not edit the art; the poster needs replacing when new
   art exists.
8. **#apps — MorningMission** (id morningmission): kicker "IN TESTING"; H2
   "Morning<wbr>Mission" (the <wbr> break is load-bearing — see §9).
   Copy: "An alarm that only turns off when you finish a mission. No snooze
   trap — dance, push-ups, maths, a photo match, or a wolf howl, and you
   are actually out of bed." 4 points: **40 missions** — move, brain,
   camera, voice and tap, each under 60 seconds · Surprise me (random pick)
   · never trapped (a kind timeout always lets you out) · every mission
   earns a collector card.
   Spotify block: "Wake up to Spotify" — MorningMission Mornings playlist
   (https://open.spotify.com/playlist/45L098TnGzIuAn0O8SBVBh); a basic
   Spotify account plays a playlist shuffled, so no Premium is required.
   Status pill: "In testing". Text: "In testing. Launching on Google Play.
   Follow along for the release date." Visual: 2 REAL app screenshots in
   phone frames (screenshots/mm-home.webp — home, next alarm 7:00 AM;
   screenshots/mm-mission-crop.webp — a Tic-Tac-Toe mission ringing).
   mm-mission-crop is the Tester capture with the bottom cropped and padded
   to phone aspect so the "Stop test alarm" label never shows. The app icon
   (screenshots/morningmission-icon.webp) stays as the small section logo
   only.
9. **#apps — Point Fingers** (id pointfingers): kicker "PLAY NOW ON THE
   WEB"; H2 "Point Fingers". Copy: "The who's-most-likely-to party game.
   A question drops, everyone points at who fits best — the most-pointed-at
   player takes the roast, and the night ends with an Awards Show. Pass the
   phone, no install needed." 8 editions: Kids, Family, Sports, Teens,
   Friends, Work, Adults, Spicy — host picks one sealed edition per room.
   4 points: Know Me, Twists and Stakes · Awards Show to close the night ·
   guests join free (any phone browser, no install, no account) · earnable
   ScanVault cards.
   Status pill: "Play now — free on the web". Play link (real, live):
   https://point-fingers.pages.dev. Pricing line: Kids is free to host; a
   one-time Host Pass ($4.99 at launch, $9.99 after) unlocks hosting the
   other seven editions. No subscription, ever. Visual: 2 REAL game
   screenshots in phone frames (screenshots/pf-game.webp — a live Kids
   round, Round 1 of 12; screenshots/pf-create.webp — the Create Game
   screen with all eight editions). Captured from the local v31 build
   (same build as live; the live site was verified booting, the shots were
   taken locally because the VM egress proxy stalls the live site). The app
   icon (screenshots/pointfingers-icon.png) stays as the small section logo
   only. NOT captured: the Awards Show — driving a full 12-round game
   headless stalls on the vote-tally screen (room sync to the worker hangs
   through the proxy); needs a real phone.
10. **#apps — On This Day** (id onthisday): kicker "NEW EVERY DAY"; H2
    "On This Day". Copy: "History happened today. Every day, something
    incredible happened on this date — and we tell its story in under 60
    seconds. Verified facts, beautiful animation, zero fluff. A new story
    every day." 3 points: a new story every day (wars, technology, sad
    stories, epic stories, under a minute) · verified facts, real footage
    first (public-domain archives where they exist, animation where nothing
    was filmed) · ends with a question (every story closes on the debate it
    still starts).
    Status pill: "Watch now — free on YouTube". Watch link (real, live):
    https://www.youtube.com/@thisdaydaily. Also on TikTok
    @truenorthinteractive and Instagram @truenorth.interactive.
    Visual: REAL footage, not channel art — two looping clips in phone
    frames, both muted autoplay loop with posters: otd-loop.mp4 (5s,
    1.2 MB — Ep 63, Blackbeard, cannon deck) and otd-nuremberg.mp4
    (7s, 0.86 MB, poster otd-nuremberg.webp — Ep 61, Nuremberg: real
    1948 public-domain courtroom footage from "Nuremberg: Its Lesson
    for Today", defendants in the dock). Fixed Nov 24: the Ep 64
    Stalingrad still (otd-stalingrad.webp) was captioned "Real footage"
    but was a picture, not footage — replaced with the Ep 61 clip,
    which is actual motion footage shipped in the episode. The Ep 64
    "Battle of Russia" clip was NOT used: real footage, but never in
    the episode. The channel art (screenshots/onthisday-banner.webp)
    stays in the repo but is no longer on the page.
11. **#studio — About**: H2 "Small studio, six ways to play." Copy (real,
    no invented team): the six-product rundown in one paragraph, then the
    linked list — ScanVault (collect and value your cards) · Hollowreign
    (collect guardians and hold the breach) · MorningMission (earn a card by
    finishing a morning mission) · OUTBREAK (survive the city, extract, or
    join the infected) · Point Fingers (point at who fits, take the roast)
    · On This Day (a new history story every day). Closing creed: "The same
    creed runs through all six: try it free first, one-time pricing instead
    of subscriptions, no dark patterns. Every feature ships only if we'd
    want it ourselves."
12. **#contact**: H2 "Follow the journey." Sub: "New studio, new channels.
    YouTube, Instagram and TikTok are live — more on the way." Social row
    (3, real URLs): YouTube https://www.youtube.com/@truenorthinteractive ·
    Instagram https://www.instagram.com/truenorth.interactive/ · TikTok
    https://www.tiktok.com/@truenorthinteractive. X and Facebook are
    commented out in the source until their URLs go live — never render a
    dead link. Each 44px touch target with label.
13. **Footer (destination)**: studio stamp image (tni-stamp.png), giant CTA
    type "Follow the journey." (links to #contact). Legal row: Privacy
    Policy (/privacy.html) · Terms of Service (/terms.html) ·
    "© 2026 True North Interactive. All rights reserved." plus the eBay
    Partner disclosure line (real, from the app footer).

## 4. Copy rules
- Real content only. No invented stats, reviews, awards, download counts.
- Headlines: benefit-led, <15 words, middle-school reading level.
- CTA verbs: Explore, Follow, See. Forbidden: Elevate/Unlock/Seamless/Delve,
  "Learn More", "Click Here", "Submit".
- "True North Interactive", never bare "True North".
- Statuses must match reality: OUTBREAK "Live on Roblox" (published Nov 22),
  Point Fingers "Play now on the web", MorningMission "In testing" with
  **40 missions**, ScanVault "Now in beta" / "Coming soon to Google Play",
  Hollowreign "In development", On This Day "New every day". When a status
  changes, update the hero tile, the app block, the meta description and
  this spec together — the Nov 23 refresh missed the spec, which is why
  this rewrite exists.

## 5. Trust elements
- Trust strip under hero (3 real signals). No fake testimonials/ratings
  (products are pre-launch or in testing — inventing them would be fraud).

## 6. Motion
- Reveal-on-scroll: single IntersectionObserver, opacity/translateY only,
  60ms stagger. prefers-reduced-motion: everything static.
- Hero glow: a `.hero-glow` layer translates at 0.25x scroll and fades to
  transparent by 900px scroll — transform/opacity only, rAF-throttled,
  disabled under reduced motion.
- No scroll-hijack, no heavy 3D library, no preloader.

## 7. Signature interaction
- Pointer tilt on the real visuals: every `.phone` figure and the OUTBREAK
  poster carry `data-tilt` (11 elements). Pointermove drives a rAF-lerped
  rotateX/rotateY, max ~6deg, transform-only; pointerleave eases back to
  flat. Binds only on pointer:fine devices and never under
  prefers-reduced-motion. Verified Nov 24 in headless Chrome by exercising
  the handler directly (rotateX 2.97deg / rotateY 3.56deg at the 0.8/0.2
  pointer position); the gate correctly keeps it off under touch emulation.
- The Oct 12 holographic card and its dead `#holoCard` script are GONE —
  removed Nov 24 along with the unused `.holo-card` CSS and the CSS
  scan-moment figure. Do not re-add a tilt target without a real element.

## 8. Placeholder audit (pre-ship)
- [ ] All live social URLs rendered; X/Facebook still commented out
- [ ] No lorem ipsum; visuals are real screenshots / real footage / the
      product's own key art (OUTBREAK poster only — see §3.7)
- [ ] Status pills match §4 (beta / testing / live / playable / new daily)
- [ ] privacy.html real policy; terms.html real terms

## 9. Layout guard — mobile overflow (Nov 23 fix, commit 7a5c0a3)
The page once laid out ~415px wide at a 412px viewport and clipped at the
right edge. Causes, all fixed and all must stay fixed:
- Product tiles must be allowed to shrink (grid min-width: 0) — the long
  unbroken word "MorningMission" forced the whole layout wider.
- "MorningMission" breaks cleanly between the two words via
  `Morning<wbr>Mission` in the hero tile and the app-block H2.
- The Spotify link wraps instead of pushing out; phone frames are slightly
  narrower.
- Verify after any layout change in a real render at 360px and 412px:
  scrollWidth must equal innerWidth at both, and the hero, tiles, OUTBREAK
  and MorningMission sections must be eyeballed, not just measured.
- Re-verified Nov 24 after the real-visuals rebuild (headless Chrome 157,
  CDP): 412px and 360px both scrollWidth == innerWidth, the only element
  past the edge is the intentional off-screen skip link. All 18 images load
  (complete + naturalWidth), the OTD video reaches readyState 4 and plays.
- Capture gotcha: `loading="lazy"` images render BLANK in
  captureBeyondViewport full-page screenshots unless the page is scrolled
  through first — that is a capture artifact, not a site bug. Force `.rv`
  visible AND scroll through the page before a full-page capture; the
  sticky nav may paint mid-page in the composite (also an artifact — it
  sits correctly at the top in real viewport shots).

## 10. Performance
- Single HTML file + fonts + screenshots. transform/opacity animations only.
  No frameworks.
- Media budget (Nov 24): the eight new visual files total ~630 KB
  (sv-binder 63 KB, sv-home 85 KB, sv-tabbar 3 KB, hr-modes 39 KB, hr-saga 88 KB,
  mm-home 69 KB, mm-mission-crop 63 KB, pf-game 64 KB, pf-create 116 KB)
  plus hr-level2-battle.webp 35 KB (Nov 24, re-shot — replaces the 41 KB
  first capture on the page) and hr-level1-battle.webp 37 KB (Nov 24,
  replaces hr-saga.webp on the page — hr-saga removed from the repo;
  hr-modes stays in the repo) plus two looping clips: otd-loop.mp4 at 1.23 MB and otd-nuremberg.mp4
  at 0.86 MB (replaced the 67 KB otd-stalingrad.webp still Nov 24 —
  it was a picture captioned as footage). Below-fold images are
  loading="lazy"; the videos are preload="metadata" with posters.
  Nothing multi-MB.

## 11. SEO/OG/a11y
- Title: "True North Interactive — Apps Worth Collecting" (54 chars)
- Description (names all six products): "True North Interactive is an
  independent app studio building ScanVault, the trading-card scanner
  collectors deserve, Hollowreign, a dark-fantasy card saga, MorningMission,
  an alarm that only turns off when you finish a mission, OUTBREAK, a zombie
  survival game live now on Roblox, and Point Fingers, a who's-most-likely-to
  party game you can play right now on the web — plus On This Day, a new
  animated history story every day."
- OG + Twitter card tags (title "True North Interactive — Apps Worth
  Collecting", OG image screenshots/hollowreign-keyart.webp). JSON-LD
  Organization (name, url, sameAs).
  Skip link, focus-visible rings, one H1, semantic sections, alt text.
