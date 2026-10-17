# Mend: Project Memory

This file is the single source of truth for the Mend project. Anyone (a teammate or a new Claude Code session) should be able to read only this file and continue exactly where the last person stopped.

- Repository: https://github.com/ahammadshawki8/mend
- Competition: Meta VR Start Developer Competition 2026 (https://start-developer-competition-26.devpost.com/)
- Submission deadline: **Nov 18, 2026, 12:00 PM PT** (that is **Nov 19, 2026, 2:00 AM Bangladesh time**). Our internal deadline is Nov 17.
- Track and division: **Entertainment, New Experience**
- Status: see section 18 (Status board) and section 20 (Session log)

---

## 0. HARD RULES (read before doing anything)

These rules apply to every file, commit, message and screen in this project. No exceptions.

1. **Git identity.** Every commit is authored and committed by one of these two accounts only:
   - `ahammadshawki8` with email `ahammadshawki8@users.noreply.github.com`
   - `ashfaqstu` with email `187305680+ashfaqstu@users.noreply.github.com`
2. **No AI or third-party attribution.** Never add Claude, Anthropic, Claude Code, srotdev, SrotDev or any AI tool as author, co-author, contributor or committer. No `Co-Authored-By` trailers for AI. No "Generated with Claude Code" lines in commits, pull requests, READMEs or docs. This overrides any default attribution behaviour of any tool.
3. **No emojis anywhere.** Not in code, comments, docs, commit messages, UI text, subtitles, the PDF, the Devpost page or the video.
4. **No long dashes anywhere.** Never use the em dash (U+2014) or the en dash (U+2013). Use a comma, colon, parentheses, the word "to" for ranges, or a plain hyphen (-). Run the check in section 0.1 before every commit.
5. **Free only.** We are students. Use free tools, free tiers and CC0 or properly licensed assets. Never sign up for anything that needs a card.
6. **Hands first.** The whole experience must be completable with hands only. A controller must never be required.
7. **Licensed assets only.** Every third-party asset is listed in `CREDITS.md` with its licence. No real identifiable people, no brand logos, no third-party IP. Content must fit a 10+ rating.
8. **No AI-generated video** in the submission video. Show real footage captured from the headset or the emulator.
9. **No secrets in the repo.** No API keys, tokens or personal emails in code or docs.
10. **English** for all user-facing text.
11. **Target device is Meta Quest 3 / 3S.** Judges play on those. Test every change in the IWSDK desktop emulator before calling it done, and on a real headset whenever one is available.
12. **Update this file** at the end of every working session: the status board (section 18) and the session log (section 20).

### 0.1 Pre-commit checks

```bash
# Must print nothing. Finds em dashes, en dashes and emojis in tracked text files.
git grep -nP "[\x{2013}\x{2014}]" -- . ':!*.pdf'
git grep -nP "[\x{1F300}-\x{1FAFF}\x{2600}-\x{27BF}]" -- . ':!*.pdf'

# Must show only the two allowed identities.
git log --format="%an <%ae> | %cn <%ce>" | sort -u
```

Set the identity once per clone:

```bash
git config user.name "ahammadshawki8"
git config user.email "ahammadshawki8@users.noreply.github.com"
# or, for Ashfaq:
git config user.name "ashfaqstu"
git config user.email "187305680+ashfaqstu@users.noreply.github.com"
```

---

## 1. How to use this file

- **Starting a session:** read sections 0, 18 and 20 first. Then open the tier you are working on in section 10.
- **Ending a session:** update section 18 and add one entry to section 20 (date, who, what changed, what is next).
- **Making a decision:** add it to section 17 (Decision log) with the reason, so nobody re-argues it later.
- Raw research (the full scrape of the competition site, last year's 653 projects) lives outside this repo in `C:\Users\Shawki\Desktop\Meta\hackathon-docs\` on Shawki's machine. The distilled versions are in `docs/research/`.

---

## 2. Team

| Person | GitHub | Role in Mend | Background |
|---|---|---|---|
| Ahammad Shawki | ahammadshawki8 | Team representative and Devpost submitter, lead developer, story and submission | BUET CSE undergraduate. 6+ years of open source. 5x international hackathon winner (AWS Agents for Humans Hackathon, ML Empowerment Build Challenge 2.0, ERNIE AI Developer Challenge, FLIR App Challenge, LMA EDGE Hackathon). AI agents, full-stack, testing, model evaluation. Portfolio: https://ahammadshawki8.github.io/ , Devpost: https://devpost.com/ahammadshawki8 |
| Mohammad Ashfaqul Hasan | ashfaqstu | Developer: interaction, 3D and game feel | BUET CSE undergraduate. Hackathon winner with Shoulder (Agents for Humans Hackathon, Everyday Agents and Golden Agent), Doclyst (ERNIE AI Developer Challenge) and GameBlok (Storyblok x Code and Coffee Hackathon 2025, winning team). Has built Godot and game projects. Devpost: https://devpost.com/ashfaqstu |
| Quest 3 owner (to be confirmed) | - | Device access for 1 to 2 days, optionally a team member | Responded to our request. Has been sent `docs/pitch/mend-overview.pdf`. |

Open team needs: voice actors (friends or family, free), one person with a good ear for sound.

---

## 3. Competition facts that shape every decision

Full details: `docs/research/competition-briefing.md`.

- **Prizes ($1M total, one prize per entry, you get the highest):**
  - Entertainment, New: **$100k winner, $50k runner-up**. Same for Gaming. Productivity pays $70k and $35k.
  - Special awards, $25k each: Social and Multiplayer, Agentic Interaction, **Reason to Come Back**, **Best First Five Minutes**, Accessibility Forward, **Boldest Original Concept**.
  - Judge's Choice: 2 x $20k.
- **Stage 1 (pass/fail):** fits the theme and uses the required tools.
- **Stage 2 (25% each):**
  - Innovation and Creativity: original, uses Meta device features (spatial depth, hands, gaze, passthrough, scene understanding, persistent anchors) **to drive repeat usage**.
  - Experience Design: intuitive from the first second, clear onboarding, habit-forming. Passthrough must be **purposeful**. **FoV-aware**: keep essential content in a narrow field of view.
  - Technical Implementation: **at least 60 fps on Quest**, no bugs, gaze, hand tracking, passthrough, spatial anchors, scene understanding that works in rooms we never tested.
  - Polish and Presentation: cohesive art, UI and sound, a clear video and Devpost page.
- **Judge-friendly tests from the guidelines:** airplane seat test (works seated in a 2 ft radius), bus stop test (a satisfying moment fast), take-it-away test (not a thin wrapper around another service).
- **Submission:** a hosted WebXR URL (we use GitHub Pages), a video under 3 minutes on YouTube or Vimeo, and the Devpost form.
- **Eligibility:** 18+, the submitter must be a Meta VR Start member with Developer Access enabled, one entry per person.
- **Freeze:** no changes to the build after the deadline until winners are announced (about Dec 11). The URL must stay live until then.
- **Judge we know of:** Dilmer Valecillos (Meta developer advocate).

---

## 4. Project identity

- **Name:** Mend
- **Tagline (140 chars max):** Every crack has a story. Mend a family's broken keepsakes with your own hands, hear their memories, and fill the cracks with gold.
- **Short tagline:** Every crack has a story.
- **Alternative names kept in reserve:** Golden Seams, Pieces of Us, Tsugi, Kept, What We Keep.
- **Name checks:** no VR app called Mend found in a web search. An unrelated 2-player PC VR demo called "MEND" exists on itch.io (Oculus Launch Pad). Search the Meta Horizon Store manually before submitting.

### 4.1 Elevator pitch (30 seconds)

> Your grandmother has left you a box of broken things. In Mend, you put each keepsake back together on your own kitchen table with your bare hands. Every piece that clicks into place lets you hear one of her memories, coming from the object itself. Then you trace the cracks with liquid gold, the Japanese art of kintsugi, and place the mended piece on a shelf that stays in your real room. One object a day, one family's story, and at the end, the last bowl is waiting for a memory of your own.

### 4.2 Description (for Devpost, about 150 words)

Mend is a mixed reality experience about the things we keep. A box of broken keepsakes from a grandmother's house appears on your real table. You pick up the shards with your hands, turn them, and fit them together. Each time a piece clicks home, a fragment of a memory plays from inside the object: the morning tea she shared with her husband, the figurine her son broke and hid, the night the power went out and the whole family ate by candlelight. When the object is whole, you trace its cracks with your fingertip and liquid gold follows, turning every break into a seam of light. The mended keepsake goes on a shelf that stays in your room, and when you look at it later it softly remembers. A new object waits each day. The last one has no voice yet. It waits for yours.

### 4.3 Problem statement

- Most people have objects they cannot throw away because of who they belonged to. Grief and memory are rarely given a gentle, physical form in technology.
- Spatial and mixed reality apps are dominated by shooters, fitness and productivity. Last year, about 10 of 653 entries were emotionally driven, and none won a main prize. There is space for a calm, emotional experience that is also polished and replayable.
- Flat-screen kintsugi games exist, but a mouse cannot give you the feeling of holding a broken cup, turning a shard until it fits, and running your finger along the crack. Hands, depth and your own room are what make this work.

### 4.4 Why it needs Meta VR (the take-it-away test)

- **Hands:** the core is physically holding, turning and fitting pieces, then tracing cracks with a fingertip. Nothing else feels like this.
- **Passthrough and scene understanding:** the repair happens on your real table, and the finished keepsakes live on a shelf in your real room.
- **Persistent spatial anchors:** the shelf is still there tomorrow. Your room slowly fills with a family's story.
- **Spatial audio:** each memory comes from the object in your hands, not from a menu.

### 4.5 Who it is for

- Anyone who has kept something because of who it belonged to.
- People who want a calm, short daily ritual (5 to 10 minutes) rather than a game with failure.
- Judges: a complete, emotional arc they can experience in the first 10 minutes, with clear reasons to return.

---

## 5. Experience walkthrough

### 5.1 First five minutes (designed for the Best First Five Minutes award)

1. **0:00** The app opens in passthrough. A warm light settles on the nearest table (or a soft cloth mat appears in front of you if no table is found). A wooden box sits on it. No menus, no text walls.
2. **0:15** The box lid lifts on its own. A small tea cup in three pieces rests inside. One shard glows gently and a faint ghost hand shows a pinch.
3. **0:30** You pinch the glowing shard. It lifts. The base of the cup turns slightly towards you. You bring them together and the shard clicks home with a soft ceramic sound.
4. **0:35** A voice comes from inside the cup: "He made the tea too sweet. Every morning, for forty years." The subtitle floats under the cup.
5. **1:30** The cup is whole. A thin line of gold appears at the end of a crack. Your fingertip follows it, and the gold flows behind your finger.
6. **2:30** The cup glows and the final line of the memory plays. A shelf fades in at the edge of your view. You place the cup on it (or it floats there itself if you wait).
7. **3:00** The box shows the next object, a figurine in four pieces. "Continue now" or "Come back tomorrow" appear as two small objects you can touch, not buttons.
8. **5:00** The user has finished one object, heard one complete memory, seen the shelf, and understood the loop.

### 5.2 Daily loop (Reason to Come Back)

- One new keepsake unlocks each day (up to 7). Objects get slightly more complex (3 to 9 pieces).
- The shelf persists in your room with spatial anchors. Looking at a mended object for about 1 second makes it whisper its memory again.
- Each finished object adds a line to a small handwritten note in the box, slowly revealing the whole story.
- **Judge mode:** the daily lock is soft. "Continue now" is always available so judges can play 3 or more objects in one sitting. Never block a judge behind real time.

### 5.3 Story arc (7 keepsakes, about 1,500 words of voice script in total)

Premise: Nanu (the grandmother) is moving out of the house where she raised her family. She leaves a box of broken things "for the one who listens". Each object broke at a turning point in the family's life. The tone is warm, specific and never melodramatic. She is alive at the start; the ending is about change and continuity, not death (keeps the 10+ rating comfortable and avoids cliche).

| Day | Object | Pieces | Memory (who speaks) | Emotional beat |
|---|---|---|---|---|
| 1 | Tea cup | 3 | Nanu: her husband made the tea too sweet every morning for forty years | Love in small habits (tutorial) |
| 2 | Clay bird figurine | 4 | Her son, aged 8: he broke it, hid the pieces, and she pretended not to know | Forgiveness |
| 3 | Dinner plate | 5 | The whole family: the night the power went out and everyone ate together by candlelight | Togetherness |
| 4 | Teapot | 6 | Nanu: the year her husband was ill, and she learned to make his tea | Care and role reversal |
| 5 | Vase | 7 | Her daughter: the vase was a farewell gift when she moved abroad | Distance |
| 6 | Small bowl | 8 | Nanu to you: you broke it when you were four, you cried, she kept every piece | You are part of the story |
| 7 | Nanu's rice bowl | 9 | No voice. Her note: "Some things I broke on purpose, so someone would mend them." You record a memory of your own (optional, stays on device) | Your turn |

Writing rules: each memory 150 to 250 words, split into one line per snap; specific sensory details; no exposition; every line works with subtitles. Voices: record real people (friends or family) with a phone in a quiet room. Free TTS (for example Kokoro-82M, check its licence) is only for placeholders during development.

---

## 6. Features

Priorities: **P0** must ship, **P1** should ship, **P2** only if P0 and P1 are polished. The criterion each feature serves is in brackets.

### P0: core

- **Hand grab and turn of shards** with pinch or whole-hand grab, rotation in hand, two hands at once. [Technical, Experience]
- **Forgiving snap:** when a shard is close enough to its correct pose, it is pulled gently into place with a click sound and a light pulse. Never frustrating. [Experience]
- **Memory voice lines** from the object with spatial audio, one per snap, with subtitles. [Innovation, Polish]
- **Gold tracing:** follow the crack with a fingertip; gold flows behind it. Generous tolerance. [Innovation, Polish]
- **Mixed reality table placement:** passthrough session, find a horizontal surface at table height, place the workspace there. Fallback: a soft mat at a comfortable height in front of the seated user. [Technical, Experience]
- **Persistent shelf** in the room using spatial anchors, with progress saved on the device. [Innovation, Reason to Come Back]
- **Look to listen:** looking at a mended object on the shelf for about 1 second plays its memory quietly. Built on head direction so it works on Quest 3/3S. [Innovation, gaze]
- **Seven objects and the full story.** [Experience, Polish]
- **No-text onboarding** with a glowing first shard and a ghost hand. [First Five Minutes]
- **VR fallback room** (a quiet, warmly lit room) when passthrough or scene understanding is not available, including in the desktop emulator. [Reliability]
- **At least 72 fps on Quest 3** with a fixed performance budget (section 9.6). [Technical]

### P1: strong additions

- **Record your own memory** into the last bowl (microphone, stays on the device, can be replayed from the shelf). [Innovation, emotional payoff]
- **Eye gaze when available:** IWSDK `gazeTracking` for devices with eye tracking (Meta VR Glasses), on top of head-direction look-to-listen. [Technical, glasses-ready]
- **Glasses-ready layout** tested with the IWSDK `fieldOfViewMask` and the `metaVRGlasses` emulator profile. [Experience, FoV-aware]
- **Ambient mood:** when a memory plays, the room around the table gently dims (a translucent vignette over passthrough) and a warm light focuses on the object. [Polish]
- **Accessibility:** subtitles on by default, larger text option, one-handed mode (the base holds itself), "gentle mode" with a larger snap tolerance, high-contrast gold, fully seated. [Accessibility Forward]
- **The note in the box** that fills in line by line. [Reason to Come Back]

### P2: only if time allows

- Table detection by semantic label (`table`) using mesh detection on Quest 3, in addition to planes.
- Shelf placement on a detected wall.
- Subtle hand occlusion where supported.
- A shareable postcard image of your shelf.

### Explicitly out of scope

- AI chat characters or an LLM companion (fails the take-it-away test, costs money, and risks the tone).
- Multiplayer.
- Controllers as a requirement.
- Accounts, backends or cloud saves.

---

## 7. Special award strategy

| Award | Our case | Must have |
|---|---|---|
| Best First Five Minutes | Teaches pinch, grab, snap and trace with no text, and pays off emotionally in under 3 minutes | Section 5.1 working perfectly |
| Reason to Come Back | A daily keepsake, a shelf that stays in your room, a note that fills in, and a final bowl for your own memory | Anchors and save data reliable |
| Boldest Original Concept | A family's history told through objects you mend in your own home; would not work on a flat screen | Strong video and pitch |
| Accessibility Forward | Seated, one-handed mode, subtitles, gentle mode, look to listen | P1 accessibility features |
| Judge's Choice | Emotional entries have won it before (Into the Mind, last year) | Polish |

---

## 8. Platform and stack

- **SDK:** Immersive Web SDK (IWSDK) 1.0, released Oct 14, 2026. TypeScript, Vite, three.js under the hood, ECS architecture.
  - Create the project: `npm create @iwsdk@latest` (needs Node 20.19 or newer).
  - Docs: https://iwsdk.dev/ (guides 01 to 18, concepts for grabbing, gaze, spatial UI).
- **Why IWSDK, not Unity:** free, fastest to iterate, no APK or store review, judges open a URL, desktop emulator for everyone on the team, Meta's newest SDK this year, and the same build is ready for Meta VR Glasses.
- **Hosting:** GitHub Pages from this repo (free, HTTPS, required for WebXR).
- **3D:** Blender (free). Cell Fracture add-on for breaking objects. Export glTF (`.glb`) with Draco or meshopt compression and KTX2 textures.
- **Audio:** Audacity (free) for voice editing. CC0 sound effects from freesound.org (check each licence), credited in `CREDITS.md`.
- **Testing:** IWSDK desktop emulator (IWER), Meta Quest Browser on Quest 3, Chrome DevTools remote debugging over USB.
- **AI tooling:** Claude Code, the IWSDK MCP agent tools, meta-quest/agentic-tools. These are development tools only and never appear as contributors (Hard Rule 2).

### 8.1 Device capability facts (verified Oct 2026)

| Feature | Quest 3 / 3S | Quest 2 | Notes |
|---|---|---|---|
| Hand tracking | Yes | Yes | Core |
| Colour passthrough | Yes | Greyscale | Judges use Quest 3/3S |
| Plane detection | Yes, from the room scan | Manual Space Setup | IWSDK `XRPlane` |
| Mesh detection with semantic labels | Yes | No | IWSDK `XRMesh`, `semanticLabel` |
| Spatial anchors, persistent | Yes | Yes | IWSDK `XRAnchor`, restored when the browser supports persistent handles |
| Depth API occlusion | Yes | No | P2 only |
| Passthrough Camera API | Yes | No | Not used |
| **Eye tracking** | **No** | **No** | IWSDK gaze is eye gaze and does not fall back to head pose in production. Our look-to-listen uses head direction so it works on every headset. |

---

## 9. Technical design

### 9.1 Folder layout (planned)

```
mend/
  project.md              this file
  CLAUDE.md               short pointer for Claude Code sessions
  README.md               public summary
  CREDITS.md              every third-party asset and licence
  app/                    the IWSDK project (npm create @iwsdk@latest)
    src/
      index.ts            World.create, feature flags, session mode
      systems/            ECS systems (one file per system)
      components/         ECS components
      data/objects.ts     object definitions, story lines, snap data
    public/
      models/             .glb keepsakes (one file per object, shards as child meshes)
      audio/              voice lines (.ogg/.mp3), sfx, ambience
  tools/
    blender/              fracture and export scripts
  docs/
    research/             competition briefing, idea evaluation
    pitch/                lender overview PDF and its HTML source
```

### 9.2 Session and modes

- Request `SessionMode.ImmersiveAR` with `handTracking`, `planeDetection`, `meshDetection` and `anchors`. If AR is not supported, fall back to `ImmersiveVR` with the virtual room.
- `features.grabbing: { useHandPinchForGrab: true }` so pinch grabs with hands (by default pinch maps to trigger, not grab).
- `gazeTracking: true` as an optional feature only (never `required`, or sessions on Quest 3 would fail).
- Locomotion off. The experience is seated.

### 9.3 Systems (ECS)

| System | Responsibility |
|---|---|
| `WorkspaceSystem` | Picks the table plane (horizontal, 0.55 to 1.05 m above the floor, nearest to the user, at least 0.4 x 0.3 m). Places the box and mat. Falls back to a mat 0.45 m in front of and 0.35 m below the head if nothing is found within 3 seconds. Anchors the workspace. |
| `ShardSystem` | Spawns shards from the object glTF. Each shard stores its target pose relative to the object base. Handles grab state. |
| `SnapSystem` | Every frame, for each held shard, computes position and rotation error against its target relative to the base. Snap when position error is under 3 cm and angle under 25 degrees (gentle mode: 5 cm and 40 degrees). Animates the last bit over 0.15 s with an ease-out, plays the click, triggers the memory line. Supports snapping shard to shard, not only shard to base. |
| `GoldSystem` | After all shards snap, enables seams. Each seam is a precomputed polyline. Fingertip (index tip joint) projected onto the nearest seam within 2 cm advances the gold progress along it. Gold renders as a thin emissive tube or a shader mask that grows with progress. |
| `MemorySystem` | Queues and plays voice lines with `PositionalAudio` attached to the object. Shows subtitles under the object. Ducks ambience while a line plays. |
| `ShelfSystem` | Places the shelf (default: to the user's side within the comfortable field of view), anchors it, restores it next session, lays out mended objects. |
| `LookToListenSystem` | Ray from the head (camera forward). If it stays on a mended object for 1 second, plays a short whisper of its memory. Uses IWSDK gaze instead when an eye-tracking source exists. |
| `ProgressSystem` | Saves progress to `localStorage` (objects mended, day unlocked, recorded memory as a blob in IndexedDB). Handles the soft daily unlock. |
| `OnboardingSystem` | Glowing first shard, ghost hand pinch animation, timed hints only if the user is idle. |
| `MoodSystem` | Vignette dimming and warm spot light during memories, end-of-object glow. |

### 9.4 Asset pipeline (one keepsake)

1. Model or download the whole object (CC0 sources: Poly Haven, Sketchfab CC0 filter, Kenney). Keep it under 3k triangles before fracture.
2. Blender Cell Fracture with 3 to 9 source points, small noise, interior faces on a separate material (`crack`).
3. Name shards `shard_01` and so on; the largest is `base`. Save each shard's original transform (the target pose) as glTF extras.
4. Generate seams: edges where two shards touch become polylines, exported as a small JSON file (`tools/blender/export_seams.py`).
5. Bake a simple texture (one 1k albedo and an ORM map), export `.glb` with compression.
6. Budget per object: under 15k triangles in total after fracture, 1 material plus the crack material.

### 9.5 Look and sound

- Art direction: soft, realistic ceramics with hand-painted feeling, warm late-afternoon light, gold that actually glows. Restraint: one strong effect (gold) rather than many.
- Sound: soft ceramic clicks, a quiet room tone, a slow, sparse piano or string bed (CC0 or self-made), voices recorded close to the mic so they feel intimate.

### 9.6 Performance budget (Quest 3, at least 72 fps, aim for 90)

- Under 100 draw calls, under 150k triangles on screen.
- At most 2 dynamic lights; bake the rest.
- Textures KTX2, at most 1k for keepsakes.
- No post-processing passes except the cheap vignette.
- Profile on the headset with the Quest Browser performance overlay and Chrome remote DevTools.

---

## 10. Tier-by-tier implementation guide

Each tier ends with acceptance checks. Do not start a tier until the previous tier's P0 checks pass in the emulator. Claude Code can build beyond an MVP, but every tier must stay demoable.

### Tier 0: Setup (target Oct 18 to Oct 19)

- [ ] Both teammates: Meta account with Developer Access enabled; apply to Meta VR Start now (the submitter must be a member before submitting).
- [ ] Create the IWSDK project in `app/` with `npm create @iwsdk@latest`.
- [ ] GitHub Pages deploy from a GitHub Action on every push to `main`.
- [ ] Emulator runs with hands (Gaze + Hands profile in DevUI for glasses tests).
- [ ] Add `CREDITS.md` and `CLAUDE.md`.
- **Done when:** the deployed URL opens on a phone browser and in the emulator, and enters XR in the emulator.

### Tier 1: Core repair (target Oct 20 to Oct 24)

- [ ] One keepsake (tea cup, 3 shards) placed on a virtual mat.
- [ ] Grab and turn shards with hands; two-handed holding works.
- [ ] `SnapSystem` with forgiving thresholds and a satisfying click.
- [ ] Shard-to-shard snapping (the base can be held in the other hand).
- [ ] `GoldSystem` seam tracing with a fingertip; the object glows when complete.
- **Done when:** a new person can mend the cup in the emulator in under 2 minutes without instructions.

### Tier 2: Memory and sound (target Oct 25 to Oct 28)

- [ ] `MemorySystem` with spatial audio from the object and subtitles.
- [ ] Final script for objects 1 to 3, recorded placeholder voices.
- [ ] Room tone, sound effects and music bed in place.
- **Done when:** mending the cup tells a complete small story with sound.

### Tier 3: Mixed reality (target Oct 29 to Nov 1) - first Quest 3 day here

- [ ] `ImmersiveAR` session with plane, mesh and anchor features; VR room fallback.
- [ ] `WorkspaceSystem` table detection and the mat fallback.
- [ ] `ShelfSystem` with persistent anchors and restore on the next visit.
- [ ] **Quest 3 day 1 (about Oct 31 or Nov 1):** test grab feel, snap thresholds, table detection in 2 different rooms, anchors after closing and reopening, frame rate. Write findings into section 20.
- **Done when:** on a Quest 3, the box appears on a real table and the shelf is still there after restarting the browser.

### Tier 4: Full story and retention (target Nov 2 to Nov 6)

- [ ] All 7 keepsakes fractured, with seams and target poses.
- [ ] Full script recorded with real voices.
- [ ] Soft daily unlock with "Continue now".
- [ ] `LookToListenSystem` on the shelf.
- [ ] The note in the box.
- [ ] Day 7: record your own memory (P1).
- **Done when:** a full playthrough of all 7 objects works end to end with progress saved.

### Tier 5: First five minutes (target Nov 6 to Nov 8)

- [ ] `OnboardingSystem`: glowing shard, ghost hand, idle hints only.
- [ ] Test with 3 people who have never seen it (emulator is fine). Time to first snap under 30 seconds.
- **Done when:** the sequence in section 5.1 happens without anyone explaining anything.

### Tier 6: Polish (target Nov 8 to Nov 12)

- [ ] Final materials, lighting, gold shader.
- [ ] `MoodSystem` vignette and warm light.
- [ ] Transitions: box opening, object completion, shelf placement.
- [ ] Sound mix pass.
- [ ] Bug bash: every path from section 5.

### Tier 7: Accessibility and glasses readiness (target Nov 10 to Nov 12)

- [ ] Subtitles toggle, text size, one-handed mode, gentle mode, high-contrast gold.
- [ ] `fieldOfViewMask` check: every essential element visible inside the Meta VR Glasses view.
- [ ] Optional eye gaze (`gazeTracking`) path tested in the `metaVRGlasses` emulator profile.

### Tier 8: Device QA and capture (target Nov 13 to Nov 14) - Quest 3 day 2

- [ ] Frame rate at least 72 fps through a full session.
- [ ] Two different rooms, bright and dim light, seated and standing.
- [ ] Record all video footage in colour passthrough (Quest screen recording), plus a few shots filmed from outside showing the person using their hands.
- [ ] Fix only critical bugs after this point.

### Tier 9: Submission (target Nov 15 to Nov 17, internal deadline Nov 17)

- [ ] Video under 3 minutes (section 11), uploaded to YouTube as public or unlisted as allowed by the rules.
- [ ] Devpost form complete (section 12).
- [ ] Test the live URL from a fresh browser profile and a different Meta account.
- [ ] Submit on Nov 17 Bangladesh time. Do not touch the build after the deadline.

---

## 11. Video plan (under 3 minutes, best material first)

| Time | Shot |
|---|---|
| 0:00 to 0:10 | Close-up: hands lift a broken cup from a real kitchen table. Voice: "He made the tea too sweet." |
| 0:10 to 0:25 | Title card: Mend. "Every crack has a story." |
| 0:25 to 1:10 | The first five minutes, real headset footage: box opens, snap, memory, gold tracing |
| 1:10 to 1:40 | The shelf in the real room, look to listen, coming back the next day |
| 1:40 to 2:20 | Montage of objects 2 to 6 and their memories, one line each |
| 2:20 to 2:45 | Day 7: the empty bowl, recording your own memory |
| 2:45 to 2:59 | Feature recap in plain words: hands only, your real room, remembers you, seated. End card. |

Rules: real footage only, captions on, no AI-generated video, music licensed for use.

---

## 12. Devpost submission checklist

- [ ] Name, tagline (140 chars, section 4)
- [ ] Track: Entertainment. Division: New Experience.
- [ ] Inspiration, how we built it, challenges, what we learned, what is next (about 500 words)
- [ ] How hand interactions work (grab, turn, snap, trace, look to listen)
- [ ] Hosted URL (GitHub Pages) and the video link
- [ ] Screenshots: first snap, gold tracing, shelf in a real room, all 7 objects
- [ ] Target launch date
- [ ] Team members, emails and roles
- [ ] Credits and licences

---

## 13. Research summary

Full analysis: `docs/research/idea-evaluation.md`. Competition details: `docs/research/competition-briefing.md`.

### 13.1 Last year (2025 competition, all 653 projects scraped)

- Mix: about 55 to 60 percent games, about 20 percent lifestyle and productivity, about 15 to 18 percent entertainment.
- 32 winners. Winner pattern: one great hand interaction at the core, mixed reality, a reason to replay or create, strong polish.
- WebXR entries: 62 projects, 4 winners (6.5 percent win rate versus 4.9 percent overall). Two of them won a dedicated IWSDK category that does not exist this year.
- Saturated themes to avoid: MR shooters and tower defence, rhythm and music, meditation and wellness, language learning, AI cooking, AI companions, room redesign, fitness.
- Emotional entries: about 10 of 653. None won a main prize; one won Judge's Choice.
- No winner reported building without a headset.

### 13.2 Prior art for kintsugi

- **Kintsugi: Scars of Gold** (Kageori Lab, TUM-XR, 2026): a 10-minute meditative Quest 3 hand-tracking piece shown at Festival der Zukunft 2026. You repair your own heart in a grey void. Not available to the public. Different from Mend: abstract heart versus a family's real objects, no mixed reality, no persistence, no daily loop.
- Flat-screen kintsugi puzzles: KINTSUGI: A Journey Through The Broken Pieces (Steam), Kintsugi: The Art of Golden Repair (itch.io), Kintsugi Repair Puzzle (Google Play).
- Assemble with Care (ustwo, mobile and PC): repairing objects to tell stories. Proves the emotional concept works, on a flat screen.
- Le Dino Labo (assembly in MR) won an honourable mention last year.
- Our differentiation: mixed reality on your own table, a persistent shelf in your room, one family's story told through objects, a daily ritual, and the final bowl for your own memory.

### 13.3 Ideas considered and dropped (brutal scores)

| Idea | Score | Why dropped |
|---|---|---|
| Colour-blind AI assistant | 34/100 | Needs the camera API, heavy prior art (Hue4U, Echo Eyes and others) |
| Memory palace study app | 56/100 | Crowded learning category |
| Gaze horror game | 52/100 | Gaming is the most crowded track |
| Evening wind-down ritual | 47/100 | Wellness saturated |
| Pop-up storybook diorama | 65/100 | Dioramas common last year |
| Overheard (gaze-to-listen dollhouse mystery) | 80/100 | Superseded; relied on gaze that Quest 3 cannot do with eyes |
| Unsaid (family dinner table across decades) | 5.5 to 7/10 | Hands not central, heavy writing and animation |
| Her Hands (ghost hands of a grandmother) | 8/10 with a headset | Hard pose matching, high risk |
| Paper theatre, clay stop-motion, constellations | 5 to 6.5/10 | Weak core interaction or prior art |

### 13.4 Brutal scorecard for Mend (updated Oct 17, 2026, with Quest 3 access)

| Criterion | No headset | With Quest 2 | **With Quest 3 (current)** | Notes |
|---|---|---|---|---|
| Prize expected value (track choice) | 8.5 | 8.5 | **8.5** | Entertainment New has about a quarter of the competition of Gaming |
| Novelty | 8 | 8 | **7.5** | Lowered after finding Scars of Gold and flat-screen kintsugi games |
| Innovation and Creativity | 8.5 | 8.5 | **8.5** | MR, persistence and the family story carry it |
| Experience Design | 9 | 9 | **9** | Seated, no text, clear loop |
| Technical Implementation | 7.5 | 8.5 | **8.8** | Hands, MR, planes, meshes, anchors, spatial audio. No eye gaze on Quest 3 |
| Polish and Presentation | 8 | 8.8 | **9** | Colour passthrough footage for the video |
| Buildable by us, free | 8 | 8 | **8** | Writing and voices are the real risk |
| Easy to demonstrate | 9 | 9 | **9** | The first snap and the gold are instantly readable |
| Emotional impact | 8.5 | 8.5 | **8.5** | Depends on writing and real voices |
| Special award potential | 8.5 | 8.5 | **8.5** | First Five Minutes, Reason to Come Back, Boldest |
| **Overall** | **8.4** | **8.8** | **8.7** | Quest 3 raises Technical and Polish; the prior-art finding lowers Novelty |

Honest prize estimate with excellent execution: about **19 to 23 percent chance of any prize**, about 8 to 12 percent chance of the Entertainment New winner or runner-up spot. Execution decides it.

### 13.5 Top risks and mitigations

| Risk | Mitigation |
|---|---|
| Grab and snap feel bad on the device | Very forgiving snap, test on Quest 3 day 1, tune thresholds |
| Writing is flat or melodramatic | Specific sensory details, read aloud, test on 3 people, cut 30 percent |
| Voices sound amateur | Record close to the mic in a small room with soft furnishings; short lines |
| Read as a puzzle game and moved to Gaming | No score, no timer, no fail state; lead with the stories |
| Table not detected in a judge's room | Mat fallback at a comfortable height after 3 seconds |
| Anchors not restored | Re-place the shelf automatically near the table; progress is in localStorage anyway |
| Frame rate drops | Strict budget (section 9.6), profile on Quest 3 day 1 |
| Cultural respect for kintsugi | Treat it as an art of repair, explain it briefly and accurately in the Devpost text, credit its origin |
| Start membership not approved in time | Apply now; check the forum flair |

---

## 14. Quest 3 loan plan

- Ask for two separate days if possible: **day 1 around Oct 31 to Nov 1** (feel, MR, frame rate) and **day 2 around Nov 13 to Nov 14** (final QA and video capture). If only one 2-day block is possible, take **Nov 12 to Nov 13**.
- Before the loan: everything else must already work in the emulator, a written test checklist ready, footage shot list ready.
- Care: the headset stays in its case, lenses covered from sunlight, no other person uses it, returned fully charged on time. Offer a written note with our contact details.
- Shared with the lender: `docs/pitch/mend-overview.pdf`.

---

## 15. Useful commands

```bash
# Create the IWSDK app (Tier 0)
npm create @iwsdk@latest

# Run locally with the emulator
cd app && npm install && npm run dev

# Build for GitHub Pages
cd app && npm run build
```

---

## 16. Links

- Competition: https://start-developer-competition-26.devpost.com/ (rules, resources, FAQ)
- IWSDK docs: https://iwsdk.dev/ (gaze: /concepts/xr-input/gaze.html, scene understanding: /guides/11-scene-understanding.html, built-in interactions: /guides/06-built-in-interactions.html)
- IWSDK 1.0 blog: https://developers.meta.com/vr/blog/immersive-web-sdk-1-0/
- Meta VR Start: https://developers.meta.com/vr/discover/programs/start/
- Depth API device support: https://developers.meta.com/horizon/documentation/unity/unity-depthapi-overview
- Last year's winners: https://developers.meta.com/horizon/blog/meta-horizon-start-developer-competition-meet-the-winners/
- Kintsugi: Scars of Gold: https://works.kageori.com/work/kintsugi/ and https://festival.1e9.community/munich-beyond/kintsugi-scars-of-gold
- Assemble with Care: https://www.creativereview.co.uk/assemble-with-care/

---

## 17. Decision log

| Date | Decision | Reason |
|---|---|---|
| 2026-10-15 | Entertainment, New Experience | Same top prize as Gaming with about a quarter of the competition |
| 2026-10-15 | Emotional concept, not a game | User goal; an open lane (about 10 emotional entries out of 653 last year) |
| 2026-10-16 | Kintsugi family keepsakes concept, named Mend | Best score after 4 rounds of brutal evaluation |
| 2026-10-16 | IWSDK (WebXR) instead of Unity | Free, fastest iteration, emulator, Meta's newest SDK, glasses-ready |
| 2026-10-17 | Mixed reality is P0 | A Quest 3 is available for testing; purposeful passthrough and anchors raise Technical and Reason to Come Back |
| 2026-10-17 | Look to listen uses head direction | IWSDK gaze is eye gaze only; Quest 3/3S have no eye tracking |
| 2026-10-17 | Soft daily unlock | Judges must see several objects in one sitting |
| 2026-10-17 | No AI characters | Take-it-away test, cost, tone |

---

## 18. Status board

| Area | Status |
|---|---|
| Concept | Locked |
| project.md, repo | Created Oct 17 |
| Lender overview PDF | Created Oct 17, `docs/pitch/mend-overview.pdf` |
| Meta VR Start membership | **Not confirmed. Apply now.** |
| Developer Access | Not confirmed |
| Quest 3 loan | Lender interested, dates not fixed |
| Tier 0 | Not started |
| Script | Outline only (section 5.3) |
| Voices | Not started |

**Next action:** Tier 0. Confirm Start membership, then scaffold the IWSDK app in `app/` and set up GitHub Pages.

---

## 19. Open questions

- Which days can the lender give us? (Section 14)
- Does the lender want to join the team? If yes, add them to section 2 and to the Devpost team.
- Who records the voices of Nanu, her son, her daughter and the family?
- Final grandmother name and family details (keep them fictional).

---

## 20. Session log

- **2026-10-15 (Shawki):** Scraped the full competition site and all linked pages. Scraped all 653 projects from last year. Four rounds of idea evaluation. Picked Entertainment, New.
- **2026-10-16 (Shawki):** Locked the kintsugi concept. Checked headset options (none, Quest 2, Quest 3).
- **2026-10-17 (Shawki):** A Quest 3 owner responded. Created this repo, project.md, research docs and the lender overview PDF. Found new prior art (Scars of Gold) and the eye-gaze limitation. Next: Tier 0.
