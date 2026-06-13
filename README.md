<div align="center">

# Ginkly

### A premium habit tracker and private journal for iOS and Android.

<!-- TODO: when the V1 ships, add badges here. Examples:
![Platform](https://img.shields.io/badge/platform-iOS%20%7C%20Android-1F1B16)
![Flutter](https://img.shields.io/badge/Flutter-3.x-1F1B16)
![Status](https://img.shields.io/badge/status-V1%20in%20development-B8763E)
![License](https://img.shields.io/badge/license-private-1F1B16)
-->

</div>

---

## Overview

Ginkly turns daily introspection into a frictionless ritual. Built around two pillars — habit tracking and journaling — it surfaces personal correlations between mood, sleep, activities and habits, all while keeping your data local-first and end-to-end protected.

The product target is a **premium, native-feeling experience**: tight typography, careful motion, haptic-rich interactions, and a UI that respects the user's attention.

> **Private repository** — source code available on request for recruiters and prospective collaborators. Reach out below.

---

## Screenshots

<!-- TODO: replace each cell with an image once the screen is finalised. Suggested size: 320×640 (3×). -->

|        Onboarding        |         Tracker          |         Journal          |          Stats           |
| :----------------------: | :----------------------: | :----------------------: | :----------------------: |
| *to be added (step 5)*   | *to be added (step 8)*   | *to be added (step 9)*   | *to be added (step 10)*  |

---

## Themes

Ginkly ships with four hand-crafted themes built on Material 3 with a custom semantic palette. Typography uses **Geist Sans** with tight negative letter-spacing — the same restraint Linear, Vercel and Notion rely on.

<!-- TODO: replace with theme previews once screens exist. -->

|     Paper Light     |     Paper Dark     |     Cyber Neon     |   Sakura Cherry    |
| :-----------------: | :----------------: | :----------------: | :----------------: |
|   *coming soon*     |   *coming soon*    |   *coming soon*    |   *coming soon*    |

---

## Features (V1 scope)

- **Habit tracker** with an iOS-launcher grid, hold-to-complete gauge, and a festive pop on validation.
- **Journal** with a horizontal calendar strip (swipeable week) and a Bento Box form (mood, activities, sleep, …) where each filled card lights up.
- **Streak widgets** for both habits and journal — animated rewards for consistency.
- **Floating glassmorphism navigation** — a pill bar with backdrop blur that hides on scroll.
- **Onboarding & Guest mode** — the user configures three habits and validates the first one *before* being prompted to create an account (the "IKEA effect").
- **Bilingual** — full French and English support through ARB files.
- **Four themes** including dark variants.
- **Premium UX** — every interaction returns native haptic feedback, with no emoji in the UI (Lucide icons only).

V2 (out of scope for the initial release): the Stats screen with correlation analytics powered by `fl_chart`.

---

## Architecture and stack

**Framework**
- Flutter, Dart 3, strict null safety.

**State and routing**
- Riverpod with code generation (`riverpod_generator`) for reactive state.
- `go_router` with `ShellRoute` for nested navigation and authenticated / guest redirects.

**Backend and persistence**
- Supabase for authentication (Google and Apple) and remote sync.
- Isar as the **offline-first** local database — reads and writes happen locally first, a background worker syncs to Supabase.
- Zero-trust posture: Row Level Security enforced on every table (`auth.uid() = user_id`), only the anon key shipped in the app.

**UI and UX**
- Material 3 `ThemeData` driven by a semantic `AppPalette`.
- Geist Sans via `google_fonts`.
- `lucide_icons_flutter` exclusively for iconography.
- `flutter_animate` for streak animations and screen transitions.
- Native `HapticFeedback` on every meaningful interaction.

**Security**
- `flutter_secure_storage` for tokens and sensitive cache.
- `local_auth` for FaceID / TouchID gating.
- Source obfuscation at release build.

**Architecture pattern**
- **Feature-first** folder layout: `features/<name>/{data,domain,presentation}`.
- **Clean Architecture** dependency rule: `domain` never imports Flutter, Supabase, or Isar — making business logic trivially testable.

---

## Roadmap

- [x] Feature-first architecture and shared core.
- [x] Multi-theme system (4 themes, Geist Sans, semantic palette).
- [x] Riverpod theme controller with system-brightness default.
- [ ] Routing (`go_router` + `ShellRoute` + auth redirects).
- [ ] Internationalization (FR / EN via ARB).
- [ ] Floating glassmorphism navigation bar.
- [ ] Onboarding and guest mode (IKEA effect).
- [ ] Supabase authentication (Google and Apple).
- [ ] Offline-first sync with Isar.
- [ ] Tracker screen (iOS-style grid, hold-to-complete, haptics).
- [ ] Journal screen (Calendar Strip + Bento Box).
- [ ] Account screen.
- [ ] Security hardening (biometric, secure storage, build obfuscation).
- [ ] Closed beta on TestFlight and Play Store internal track.

---

## About the developer

<!-- TODO: fill these in when you're ready. Leave any field blank if you'd rather not share it yet. -->

- **Name** — *to be added*
- **Role** — *to be added (e.g. "Junior Mobile Developer")*
- **Email** — *to be added*
- **LinkedIn** — *to be added*
- **Portfolio** — *to be added*

---

## License

This is a **closed-source commercial project**. All rights reserved.

The source code is not licensed for public use, distribution, modification or redistribution. No permission is granted for copying, reverse-engineering or reusing any part of the project — including assets, screenshots and architectural decisions — without explicit written consent.

---

<div align="center">

Crafted in Flutter · © 2026

</div>
