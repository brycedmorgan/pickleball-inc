# PPA Tour AI Tracker (Pickleball Inc) — ⚰️ RETIRED 2026-07-14

**This board is dead.** pickleball-inc.vercel.app now redirects (302 via
`vercel.json`) to **jackalopehq.vercel.app** — the tracker lives on as the
"Bryce Projects" module in the Jackalope app (`~/Documents/ziff`, `tracker.js`).
**Make all tracker updates THERE, not here.** This repo stays as the archive
(`index.html` untouched; restore by deleting `vercel.json`).

Old description: single-file static app (`index.html`, Tailwind CDN + vanilla
JS), repo `brycedmorgan/pickleball-inc`. Bryce = President & CMO of PPA Tour;
Connor Pardoe = CEO. This board was how Connor tracked every AI/software
initiative.

## How the tracker is structured

- Each initiative is an `<article data-project="id">` card (39 cards currently)
  grouped by section, with a status pill, a `stage-bar` progress span, and a
  one-line next-step note under the bar.
- Clicking a card opens a modal driven by the `PROJECTS = {...}` object (same
  `data-project` id) — title, summary, detail rows, checklist, links.
- `PRICING = {...}` maps ids → dollar values; `renderPricing()` injects
  Proposed (amber) / Agreed (green) badges. **Only AGREED dollars roll into the
  header KPIs.** Every card must have a matching PRICING entry.
- Edit conventions: keep straight vs curly apostrophes exactly as found (mixed
  in file); validate with `node --check` after touching `<script>` content.
- Commit as Bryce: `git -c user.email=brycedmorgan@gmail.com -c user.name="Bryce Morgan" commit ...`

## Sibling app

**Ziff** (`~/Documents/ziff`, repo `Gull-Stack/ziff`, live at
**ziff-two.vercel.app**) is the internal web app most tracker initiatives ship
into — single index.html, role-gated modules (login = work email, demo password
"pickleball"). Shipped modules: Travel, Deck Builder, AI Hub, Finance (Claude
Finance preview), Growth, HR hub (Kate), Contractors.

# Session Log

## 2026-07-14 (pt. 5) — BOARD RETIRED → redirects to Jackalope

- Bryce's call: this page is dying; everything moves to the Jackalope app.
- Added `vercel.json` catch-all 302 → jackalopehq.vercel.app (covers /plan-0612
  too — the comp-numbers briefing is no longer reachable, which is a plus).
- Firefight card ported to Jackalope's tracker (ziff `fcee818`) — Jackalope now
  has all 40 projects incl. economics ($3.11M proposed) and dilution flag.
- index.html untouched (archive); un-kill by deleting vercel.json.
- Future tracker edits go to `~/Documents/ziff/tracker.js` (PROJECTS + PRICING
  + TRACKER_META), not this repo.

## 2026-07-14 (pt. 4) — NEW PROJECT: Firefight ad platform (from Connor/Bryce/Braden meeting)

- Bryce recorded the meeting; transcript analyzed → new tracker card `firefight`
  under the PPA Tour pillar (commit `caef377`, pushed/live).
- The idea, three layers: (1) native ad server replacing AdButler across
  pickleball.com / PT.com / newsletters; (2) Braden-run managed program —
  endemic brands hand over their pickleball budget ("80% with us, 20% Meta/
  Google run through us"), biweekly throttle calls, real ROI dashboards;
  (3) Taylor's self-serve module for tournament directors (geo-target players,
  budget → impressions from our CPMs).
- Scope guardrails agreed in the meeting: paid display, programmatic,
  email/retargeting only — NO social posting, NO SEO, NO client websites.
- Reframes sponsorship sales ("$50k blackout title vs $100k in Firefight") and
  gives Pickleball Central leverage (Gamma: spend through Firefight or delist).
- Open: Taylor's deck (get it from Connor), fee model (agency % vs inventory
  margin vs pure funnel-through), name ("Firefight" is placeholder), UTM/pixel
  attribution standards, ad-ops capacity (Braden's sour-relationship risk).
- Next: inventory audit (every slot/newsletter/segment + real CPMs), then
  Phase 1 MVP scope = ad server + reporting dashboard.

## 2026-07-14 (pt. 3) — Board renamed to "Bryce Projects"

- Renamed the tracker everywhere (commit `cd57857`): page title, header pill
  ("PPA Tour · Pickleball Inc · AI Initiatives"), and h1 now "Bryce Projects"
  (yellow/sky two-tone). Pushed → live at pickleball-inc.vercel.app.
- Same rename shipped in Jackalope (ziff `7c38eb1`): module label, tracker h1,
  Feed project tag — ids stay `tracker` so stored entries/localStorage keep working.
- Notion page renamed to "Bryce Projects" too (same page/URL). Memory updated —
  future sessions log there under the new name.

## 2026-07-14 (pt. 2) — Ziff is now JACKALOPE (Connor: "Prove it")

- Bryce floated "Jackalope" for the internal app; Connor loved it but doubted
  one app could serve everyone → Bryce pitched role-based access → "Prove it."
- **Proved it, same day:** app rebranded Jackalope (login glyph + Bungee Shade
  wordmark, tagline "One login. You get your stuff, Dylan gets his — admins
  see it all"), **Dylan added** (dylan@ppatour.com, role ops → lands on Order
  of Play, also sees Travel), non-exec homes show a **locked-modules strip**
  (other teams' tools listed but inaccessible) — the visible proof of the
  one-app model. Connor's exec login sees all 11 modules.
- **New canonical URL: jackalopehq.vercel.app** (claimed via Vercel domain on
  project `the-kitchen` — that's the real Vercel project behind the repo;
  the old ziff-two.vercel.app project no longer exists, so any old links are
  dead). Verified live. Login: connor@ppatour.com / pickleball.
- Tracker card renamed Jackalope + all URLs updated (commit in
  pickleball-inc). Ziff repo commit `dfbd427`.
- ALSO this session: **Australian Pickleball Cup sponsorship deck rebuilt**
  (the old 17-slide one was unacceptable — TBDs, typos, wrong event name, no
  tiers/ask). New 12-slide dark deck on PPA Australia brand: Desktop
  "…Sponsorship — v2.pptx/.pdf/.html" + artifact. Placeholders: contact
  name/email, AUS broadcast partner. LibreOffice installed for deck QA.

## 2026-07-14 — Card sweep + Dylan/Parker emails (from the GullStack Claude instance)

- Applied the /goal sweep: **Finance card** flipped VENDOR SIGNED → **BUILDING
  IN-HOUSE** (Claude Finance in Ziff; Specter runs its paid year, don't renew;
  bar 45%), **Ziff card** bumped to 55% with all shipped modules listed +
  "Connor/Kate/Jennifer logins next", **PPA Website** confirmed current
  ("bigger review end of week — NOT shipping yet", 85%). Commit `02c8057`, pushed.
- **Dylan email SENT** (Teamworks daily-use breakdown + ideal Order-of-Play
  workflow, reply by Wed) — his answers drive the Teamworks-replacement build.
- **Parker/Tanner email drafted** (events-bible exec dashboard: what numbers
  get asked repeatedly, where data lives, thoughts by Thursday, sit-down
  Thu/Fri to hammer next stages). Send from the PPA inbox.
- Bryce's open action list (top items): incognito-check ziff-two.vercel.app
  deployment protection → unblocks Connor/Kate/Jennifer logins; send
  Kate + Jennifer emails; read-only Stripe + Sage Intacct access for Finance;
  ticketing docs (Tixr replacement); Jason Aspes intro (results/rankings MCP).
- This PPA Claude instance (`claude-ppa`, CLAUDE_CONFIG_DIR=~/.claude-ppa) was
  set up today so PPA email sends come from the PPA account, not GullStack.
