# PPA Tour AI Tracker (Pickleball Inc)

This repo is the **PPA Tour / Pickleball Inc AI-initiative tracker** — a single-file
static app (`index.html`, Tailwind CDN + vanilla JS) deployed at
**pickleball-inc.vercel.app** on git push (repo `brycedmorgan/pickleball-inc`).
Bryce = President & CMO of PPA Tour; Connor Pardoe = CEO. This board is how
Connor tracks every AI/software initiative.

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
