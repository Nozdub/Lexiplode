# Lexiplode

## General game idea
A competitive, turn-based word game on a 15×15 board. Players place letter tiles to form valid words, scoring via classic **double/triple letter/word** multipliers. New twist: **Catalyst (bomb) tiles**. Use a Catalyst in a played word to detonate it and **steal the points from linked words** (words sharing letters with the detonated word). Detonations also **refresh** the destroyed board area with random new tiles (regular, multipliers, or more Catalysts). Win by **highest score at time end** or (future mode) by **dominating tiles** via smart detonations.

---

## Detailed / rules / elements
- **Board:** 15×15. Start from one of several **predefined, balanced templates** (randomly chosen each match).
- **Tiles in rack:** Start with **7** (we may test 6–9).
- **Placement:** Horizontal/vertical; must connect to existing tiles; must be valid per chosen dictionary.
- **Multipliers:** 
  - **x2/x3 Letter**, **x2/x3 Word** (standard multipliers; our own layouts).
- **Catalyst (bomb) tile:**
  - Acts as a **wildcard** letter for the played word.
  - After scoring, detonates the **played word** and **all linked words** (any word sharing tiles with it).
  - **Scoring (fluid):** The detonator **does not** gain points for the trigger word, but **does** gain points for all **linked words** destroyed. Those points are **subtracted** from the opponent’s total and **added** to the detonator’s total.
  - **Tile returns:** Only **linked-word tiles** destroyed are added to the detonator’s **bag**; letters used to form the trigger word are **not returned** (prevents easy farming).
  - **Board refresh:** Destroyed squares repopulate with **random tiles** (could be plain, multiplier, or Catalyst).
- **Bags:** Each player has a **personal bag**. Normal play draws from your bag. Detonations can **replenish** your bag with captured letters from linked words.
- **Bonuses & penalties:**
  - **Full rack bonus:** +40 when using all 7 tiles.
  - **End penalty:** Unused rack tiles subtract from score (applies to timed modes at match end).
- **Timers (starting point):**
  - **Standard:** 5 minutes total; **30s turn timer** (tune after testing).
  - **Modes (later):** Blitz (shorter), Casual (no global timer), Domination (win by emptying opponent’s rack).
- **Anti-frustration:**
  - Weighted refill to avoid **vowel starvation** (ensure vowel/consonant balance in bags).

---

## Tech & tools
**Frontend (App)**
- **Flutter (Dart)** for one codebase Android + iOS.  
  Docs: https://flutter.dev/  
  Learn: https://docs.flutter.dev/ , https://flutter.dev/learn

**Ads**
- **Google AdMob** with `google_mobile_ads` (Interstitial after match; Adaptive Banner on leaderboard).  
  Quick start: https://developers.google.com/admob/flutter/quick-start  
  Cookbook: https://docs.flutter.dev/cookbook/plugins/google-mobile-ads  
  Interstitial guidance (placements): https://support.google.com/admob/answer/6066980

**Backend**
- **Supabase** (Auth, Postgres DB, Realtime) — **Free tier** to start.  
  Flutter quickstart: https://supabase.com/docs/guides/getting-started/quickstarts/flutter  
  Getting started hub: https://supabase.com/docs/guides/getting-started  
  Pricing (Free tier limits): https://supabase.com/pricing

**Project tools**
- GitHub (repo, Issues, Actions).  
- Testing: `flutter test`.  
- Design/PM: Figma / Notion (free plans).

---

## Security elements
- **Server-side validation:** All word validation and scoring re-checks on backend to prevent client tampering.
- **Rate limiting:** Throttle matchmaking and turn submissions.
- **Auth:** Supabase Auth (email/OTP/social later). Store minimal PII.
- **Transport security:** HTTPS everywhere; secure WebSocket for realtime.
- **Anti-cheat:** Hash & sign turn payloads; reject impossible moves; keep an audit trail.
- **RNG integrity:** Seeded, server-driven randomness for tile generation/refills.
- **Privacy/consent (EU/iOS):**
  - GDPR consent dialog (offer **non-personalized ads**).
  - Follow AdMob policies for banner/interstitial placements.
- **Not a kids app:** set appropriate store age ratings.

---

## Monetization strategy
- **Interstitial ad** shown **after the match result screen** (skippable after a few seconds).
- **Adaptive banner** only on **Leaderboard** (never during play).
- **No ads during gameplay** (board view, placements, animations).
- **Future (optional):** Rewarded ads for **cosmetics only** (no pay-to-win).

---

## Learning resources (official docs)
- **Flutter (framework & language)**
  - Flutter site: https://flutter.dev/
  - Docs hub: https://docs.flutter.dev/
  - API reference: https://api.flutter.dev/
- **Flutter + Firebase (optional later)**
  - FlutterFire setup: https://firebase.google.com/docs/flutter/setup
- **AdMob for Flutter**
  - Quick start: https://developers.google.com/admob/flutter/quick-start
  - Cookbook: https://docs.flutter.dev/cookbook/plugins/google-mobile-ads
  - Interstitial guidance: https://support.google.com/admob/answer/6066980
  - AdMob policies: https://support.google.com/admob/answer/6128543
- **Supabase (backend)**
  - Flutter quickstart: https://supabase.com/docs/guides/getting-started/quickstarts/flutter
  - Getting started: https://supabase.com/docs/guides/getting-started
  - Pricing (Free tier): https://supabase.com/pricing

Copyright
