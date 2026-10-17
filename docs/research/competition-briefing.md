# Meta VR Start Developer Competition 2026: Briefing

Distilled from everything in this folder (scraped 2026-10-15). Original text is in the linked files; when in doubt, `rules.md` is the binding contract.

## Key dates (Pacific Time)

| What | When |
|---|---|
| Entry period opened | Sep 24, 2026, 10:00 AM PT |
| **Submission deadline** | **Nov 18, 2026, 12:00 PM PT** (written Oct 15, 2026) |
| Judging | Nov 23 to Dec 9 (dates tab); rules say "on or around Nov 18" |
| Winners announced | ~Dec 11, 2026, 10:00 AM PT |
| **Freeze** | No changes to the build or submission from Nov 18 noon until winners are announced. Changing it can get you disqualified. |

## Eligibility (miss one and you're out)

- 18+ and of legal age where you live. Not a resident of Brazil, Quebec, or a sanctioned region (Crimea, Russia, Cuba, Iran, North Korea, Syria, or anyone OFAC lists).
- Active Meta account with **Developer Access** enabled.
- The person who submits must be a **Meta VR Start member** by the time they submit. Approval isn't instant, so [apply now](https://developers.meta.com/vr/discover/programs/start/). To verify, look for the "Start Member" flair on the [developer forum](https://communityforums.atmeta.com/category/horizon-developer-forum).
- **One entry per person.** You can't be a solo entrant and also a team Representative. Non-Representative membership on other teams is allowed. There's no limit on team size.
- The project can't have received Meta funding (RFPs etc.). If you had 1:1 Start mentorship before, you can't use it on this project during the window.
- No headset required, but **judges play on Quest 3 / 3S**. Optimise for those devices. Builds must be playable on Quest 3/3S, so AI-glasses-only apps don't qualify.

## Pick a track and a division

**Tracks:** Entertainment (lean-back media, spatial cinema, music viz, storytelling, companion apps) · Gaming (seated, controller-free puzzle/strategy/casual/social/narrative) · Productivity (workspaces, tasks, creative tools, routines tied to moments like the morning, commute or wind-down).

**Divisions:**
- *New Experience:* conceived and built on or after Sep 24, 2026. No existing codebase.
- *Adapted / Significantly Updated:* an existing project plus a meaningful new feature, such as hands added, multiplayer, an MR mode, or a UGC tool. Bug fixes, cosmetics and performance-only changes don't count. Ports from other platforms go here. **Keep a changelog from day one.**

## Hard requirements

1. **Hands-first, end to end.** Can someone finish the whole experience without ever pairing a controller?
2. **Policy compliant.** Content must fit a 10+, 13+ or 18+ rating. No real identifiable people, no brand logos or advertising, no third-party IP.
3. **English** (or English subtitles and translations).
4. Use only **publicly released** tools and SDKs. No third-party hardware may be required.
5. **Original.** Third-party assets need valid licences, and Meta may ask for proof.

**Guidelines judges reward:** works seated (the *airplane seat test*, a 2 ft radius) · cold start fast and give a satisfying moment within 10 minutes (the *bus stop test*) · not a thin wrapper around YouTube, ChatGPT and the like (the *take-it-away test*).

## What to submit

1. **Build**
   - Unity / Unreal / Godot / Android: upload the APK to a **new release channel named "Competition"** in the Developer Dashboard and submit the **Invite URL**. FAQ: a raw APK file "will not be considered". Make a new channel even if you used one last year.
   - IWSDK / WebXR: a hosted URL (GitHub Pages, Vercel, etc.).
   - Must stay free and accessible until winners are announced.
2. **Video:** under 3 minutes, public on YouTube or Vimeo, showing footage from a Quest, XR Simulator or an emulator. Put your best material first. Show **real gameplay** and don't rely on AI-generated video.
3. **Devpost form:** name · tagline (140 chars) · track · division · description of inspiration, how you built it and future plans (~500 words) · Adapted only: summary of new features with screenshots or changelog · optional: how hand interactions work · target launch date · team names, emails and roles.

## How judging works

- **Stage 1, pass/fail:** does the entry fit the theme and use the required tools and features?
- **Stage 2:** four criteria, **25% each**. AI may assist; humans decide.

| Criterion | What scores high |
|---|---|
| Innovation & Creativity | Original, fits the track, uses Meta device features (spatial depth, hands, gaze, passthrough, scene understanding, persistent anchors) **to drive repeat usage** |
| Experience Design | Intuitive from the first second, clear onboarding, a habit-forming purpose. Passthrough must be *purposeful*: the real room changes the experience. **FoV-aware**: keep essential UI in a narrower FoV that works across devices |
| Technical Implementation | **≥60 fps on Quest**, no bugs, gaze interactions (ISDK v207+), hand tracking, passthrough, spatial anchors. If you use MR: MRUK scene understanding, anchoring to real planes, and it still works in rooms you never tested |
| Polish & Presentation | Cohesive UI/UX, art and sound. The submission text, images and video all clearly communicate the value |

Judge listed: **Dilmer V** (Dilmer Valecillos, Meta developer advocate). He presents the VR 101 / VR 102 tutorials (transcripts in `videos/`) and co-hosts the Oct 20 "Agentic Workflows" session.

## Prizes ($1M total, max one prize per entry, you get the highest one)

| | New | Adapted |
|---|---|---|
| Gaming | $100k / $50k runner-up | $100k / $50k |
| Entertainment | $100k / $50k | $100k / $50k |
| Productivity | $70k / $35k | $70k / $35k |

**Special awards ($25k each, any track or division):** Social & Multiplayer · **Agentic Interaction** (AI as core: spatial agents, voice-first, procedural, context-aware) · Reason to Come Back (progression, growth between sessions) · **First Five Minutes** (teaches controller-free play without a wall of text and pays off fast) · Accessibility Forward (voice alternatives, eyes-only navigation, high contrast) · Boldest Original Concept (would fall apart on any other platform). **Judge's Choice:** 2 × $20k.

## Suggested stack

- **Unity:** Meta XR SDK v81+ (v207) All-in-One + Interaction SDK. XRIT + XR Hands is allowed, but judges value Meta ISDK features.
- **Unreal:** UE 5.8 + Oculus/Meta XR integration v207+
- **Android:** React Native via Expo, or Jetpack Compose with the Meta VR Android Studio plugin
- **WebXR:** IWSDK (`npm create @iwsdk@latest`, Node ≥20.19). This is the quickest route to a shareable link.
- **AI tooling:** Meta VR CLI, [meta-quest/agentic-tools](https://github.com/meta-quest/agentic-tools), Meta XR Operator, Unity CLI

## Upcoming events (see `webinars-office-hours.md`)

- **Tue Oct 20, 10 AM PT:** Agentic Workflows for New & Existing Apps (Dilmer + Yuchan). Registration not open yet.
- Recordings of past sessions get posted about a week later. The kickoff recording is on the forum and needs a Start login.

## Things I noticed that could cost points or prizes

- The overview says "Meta VR Glasses and Meta Quest", but the FAQ says builds **must be playable on Quest 3/3S** and that's what judges use. Target Quest 3/3S.
- The **First Five Minutes** and **Reason to Come Back** special awards map directly onto main criteria (onboarding, habit-forming). Designing for them improves your main score at the same time.
- The judging text repeatedly uses "drive repeat usage", "habit-forming" and "comes back tomorrow". A retention loop matters even for a hackathon build.
- If you use passthrough, it must change the experience. Decorative passthrough will hurt your score.
- Keep the release channel invite URL working through Dec 11. Test it from a second account before you submit.

## Contacts

- Hackathon manager: keshya@devpost.com
- Sponsor: MetaHorizonStart@meta.com
- Devpost tech issues: support@devpost.com
- Start membership issues: https://developers.meta.com/vr/support/
