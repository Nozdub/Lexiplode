# Wordblast – Project Management Notes

## 🎯 Core Vision
A free-to-play player vs player mobile word game that combines **Scrabble/Wordfeud word-building** with **Bomberman/Candy Crush style explosions**.  
Players place words on a shared board, trigger bombs to clear tiles, and compete across a set number of turns. The player with the highest score wins.

---

## 🛠️ Tech & Tools (Zero-Cost First)
We will keep development and hosting 100% free until the game generates revenue.

- **Frontend (Game App)**  
  - **Option A: React Native (JS/TS)** – Huge ecosystem, easy Firebase/Supabase integration, AdMob support.  
  - **Option B: Flutter (Dart)** – Great performance, consistent cross-platform UI, first-class Firebase & AdMob plugins.  

- **Backend (Free tiers only)**  
  - **Firebase** → Auth, Firestore DB, Hosting, Analytics.  
  - **Supabase** → SQL database, authentication, realtime features.  
  - **Alternative fallback:** Render / Railway (free tiers).  

- **Project Tools**  
  - GitHub (repo, issues, CI/CD with Actions – free tier).  
  - Figma (free design).  
  - Trello/Notion (project tracking, free plans).  

---

## 📐 Key Game Design Notes
- **Core Loop:** Place words → trigger bombs → clear tiles → score points.  
- **Bomb Tiles:** Work as wildcards, explode when part of a valid word, reshuffle surrounding tiles.  
- **Game Modes:** Start with **1v1 turn-based**.  
- **Scoring System:** To be defined (word length, rare letters, explosion bonuses).  
- **Accessibility:** Easy for casual players, with strategic depth for long-term play.  

---

## 🔒 Security & Reliability
- Word validation must be done **server-side** to prevent cheating.  
- Rate limiting to block spam or fake accounts.  
- Ensure **turn persistence** so progress isn’t lost if a player closes the app.  

---

## 💰 Monetization Strategy
- **Phase 1:** No ads (prototype, internal testing).  
- **Phase 2:** **Post-match ads only** (Mimo-style: short, skippable ad after a game ends, before returning to main menu).  
- **Phase 3 (optional):** Rewarded ads for **cosmetic bonuses** (never pay-to-win).  
- **Phase 4 (later, if revenue):** Consider optional cosmetic IAPs (skins, themes).  

---

## 📚 Learning Resources

### React Native (JavaScript / TypeScript)
- [React Native Docs – Getting Started](https://reactnative.dev/docs/getting-started)  
- [React Native Environment Setup Guide](https://reactnative.dev/docs/environment-setup)  
- [React Native + Firebase (official docs)](https://firebase.google.com/docs/react-native/setup)  
- [React Native + Supabase (Expo guide)](https://supabase.com/docs/guides/getting-started/tutorials/with-expo-react-native)  
- [React Native Google Mobile Ads](https://rntester.app/examples/AdMob)  

### Flutter (Dart)
- [Flutter Documentation](https://docs.flutter.dev/)  
- [Codelab: Write Your First Flutter App](https://docs.flutter.dev/get-started/codelab)  
- [Flutter for Mobile](https://docs.flutter.dev/get-started/flutter-for/mobile)  
- [FlutterFire (Firebase for Flutter)](https://firebase.google.com/docs/flutter/setup)  
- [Supabase Flutter Quickstart](https://supabase.com/docs/guides/getting-started/tutorials/with-flutter)  
- [Google Mobile Ads for Flutter](https://developers.google.com/admob/flutter/quick-start)  

### Firebase & Supabase (General)
- [Firebase Auth Overview](https://firebase.google.com/docs/auth)  
- [Supabase Docs](https://supabase.com/docs)  

---

## ✅ Next Steps
1. **Finalize the app name** → update repo name & branding.  
2. **Choose framework** (React Native vs Flutter, based on learning preference).  
3. **Define scoring system** (word values, bomb effects, bonuses).  
4. **Build local prototype** (no backend, single-device testing).  
5. **Integrate backend (Firebase or Supabase)** for auth + matchmaking.  
6. **Add ads (AdMob) after match completion.**  
7. **Implement leaderboards & friend system.**  
8. **Playtest & refine gameplay loop.**  

---
