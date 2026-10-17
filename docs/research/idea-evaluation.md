# Idea evaluation: Meta VR Start Developer Competition 2026

Researched 2026-10-15. Constraints: student team, no headset, no budget, 34 days left, and the goal is the most expected prize money.

## 1. Data: where the competition is

- **Registrations this year:** 3,126 participants so far. Last year had ~2,900 participants and 653 submissions (scraped in full: `gallery25.json`, `list.txt`).
- **Last year's mix** (keyword pass plus a manual read of all 653 taglines): roughly **55 to 60% games, ~20% lifestyle/productivity, ~15 to 18% entertainment**.
- **This year's prizes:** Gaming and Entertainment each pay $100k + $50k per division. Productivity pays $70k + $35k.
- **Conclusion:** Entertainment has the same $100k top prize as Gaming with about a quarter of the competitors. **Entertainment, New Experience division, is the best expected value.** The Adapted division is where studios with shipped titles compete.

**Saturated last year (avoid):** MR room shooters and tower defense, rhythm and music makers (15+), meditation and wellness (15+), language learning (10+), AI cooking and kitchen assistants, AI companions, interior and room redesign, fitness.

## 2. Scoring rubric (weighted to 100)

Prize expected value 25 · Novelty 20 · Fit to judging criteria 20 · Buildable with no headset, $0, 34 days, by students 15 · Demo in a 3-minute video 10 · Extra special-award chances 10

| # | Idea | EV | Novelty | Fit | Build | Demo | Stack | **Total** | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| A | Colour-blind AI assistant (original idea) | 3 | 3 | 4 | 1 | 5 | 6 | **34** | DROP. Needs a headset and camera. Prior art: Hue4U, Hue4True, Animal Vision MR (LUT), Echo Eyes, cAIne, Meta's own Detailed Responses |
| B | Memory palace study app | 5 | 3 | 7 | 8 | 5 | 6 | **56** | DROP. FlipSpace, FocusSphere, Ouron VR and 10+ learning apps already exist |
| C | "Don't look away" gaze horror game | 2 | 4 | 7 | 8 | 8 | 5 | **52** | DROP. Gaming is the most crowded track. Dungeon Anomaly and SleepWatch already exist |
| D | Pop-up storybook diorama | 8 | 5 | 7 | 6 | 7 | 5 | **65** | Backup. Dioramas were common (Pocket Lands, Tactical Quest, Curious Tale of the Stolen Pets) |
| E | Evening wind-down ritual | 5 | 2 | 6 | 6 | 4 | 5 | **47** | DROP. The wellness category is saturated |
| **F** | **"Overheard": gaze-to-listen dollhouse mystery drama** | 8 | 8 | 9 | 6 | 9 | 8 | **80** | **PICK** |

## 3. The pick: "Overheard" (Entertainment, New Experience)

A miniature mansion (dollhouse) sits on the table in front of you. A dinner party plays out over 8 minutes, with four guests in three rooms all talking at once. **Whoever you look at comes into focus**: their voices get clear and everyone else is muffled. Lean in to hear whispers. Pinch and drag the grandfather clock's hand to rewind and follow a different thread. Pinch clue objects to pocket them. At the end, pinch the person you think did it.

### Why it scores
- **Innovation:** gaze becomes your ear. No shipped product does this. Prior art covers parts of it: The Invisible Hours (2017) lets you follow characters on foot but isn't seated and has no gaze-controlled audio, and The Dinner Party (GGJ 2015) used eye contact. There's a research basis (Vinnikov et al., ACM TOCHI, on gaze-contingent audio), and **Meta holds a patent on "gaze-directed audio enhancement"**, which plays well with Meta judges.
- **Experience design:** seated by design, the table is the stage, everything sits in a narrow field of view (glasses-ready), there's no menu, and the core interaction is understood in about 20 seconds.
- **Technical:** gaze interactions and spatial audio are both named in the judging criteria and the track text. IWSDK 1.0 has gaze + pinch and positional audio built in, and the same build runs on Meta VR Glasses.
- **Polish:** a dollhouse looks great in a trailer, and the core moment ("look and the voice comes into focus") is easy to show on video.
- **Special-award chances:** Best First Five Minutes (you teach the mechanic with a whisper, no text), Boldest Original Concept, and Judge's Choice. Reason to Come Back is weaker; episodes and replaying to hear the other threads help.

### Weaknesses
1. **The content is the product.** Weak writing or flat voices lose, whatever the tech. You need someone who can write.
2. **Track reassignment risk.** If it plays like a game, Meta can move it into the crowded Gaming track. Keep it lean-back: no fail states, no score, and an optional accusation at the end.
3. **Quest 3/3S has no eye tracking.** "Gaze" is head direction on the judges' devices. That works naturally (people turn toward voices), but say so honestly in the pitch.
4. **Mysteries are one-and-done.** Reason to Come Back is weak, so mitigate with episodes.
5. **No passthrough or MR mode** means some Technical Implementation points go to MR entries. Add "place the dollhouse on your real table" only if you can borrow a headset.
6. **AI voices can sound cheap.** Record friends for the main characters and use Kokoro-82M (reported Apache-2.0; check the model card) only for extras.
7. **You can't verify 60 fps or how the spatial audio feels on the device.** Keep geometry low-poly and borrow a Quest for 1 to 2 days before submitting.
8. **The Quest Store isn't fully searched.** Check it manually for "eavesdrop", "dinner party mystery" and "audio drama".

### Honest prize estimate (rough)
Guess: 70 to 110 entries in Entertainment New. With excellent execution: about 8 to 15% chance of the winner or runner-up spot, and about 15 to 20% chance of any prize including special awards and Judge's Choice. Expected value is roughly $10 to 20k. That's far better than the same effort in Gaming, but it's not a likely win. Execution decides it.

## Sources
- Last year's gallery: https://start-developer-competition.devpost.com/project-gallery
- Winners: https://developers.meta.com/horizon/blog/meta-horizon-start-developer-competition-meet-the-winners/
- IWSDK 1.0: https://developers.meta.com/vr/blog/immersive-web-sdk-1-0/
- Meta patent, gaze-directed audio enhancement: https://patents.justia.com/patent/10555106
- Gaze-contingent audio in VR (Vinnikov et al.): https://percept.eecs.yorku.ca/papers/vinnikiv%20auditory.pdf
- Virtual café gaze/attention study: https://www.frontiersin.org/journals/human-neuroscience/articles/10.3389/fnhum.2019.00386/pdf
- The Invisible Hours: https://blog.playstation.com/?p=195358
- The Dinner Party (GGJ): https://v3.globalgamejam.org/node/23361
- Curious Tale of the Stolen Pets: https://gematsu.com/2019/06/fast-travel-games-announces-the-curious-tale-of-the-stolen-pets-for-virtual-reality-platforms
- Hue4U: https://research.utwente.nl/en/publications/hue4u-real-time-personalized-color-correction-in-augmented-realit/
- Kokoro-82M: https://featherless.ai/models/hexgrad/Kokoro-82M

---

## Round 2: emotionally driven concepts (2026-10-15)

Correction: entrants choose their own track. The rules (§4.3) still let the Sponsor reassign an entry "at its sole discretion", so a clear fit to the track matters.

**Last year's emotional entries:** about 10 of 653 (The Forgotten War, Nowhere to Belong, Memory Garden, Third Seat, Becoming the Unborn, Landscape Lab, Lemo). None won a main prize; Into the Mind got Judge's Choice. Emotion is an open lane, but it isn't enough on its own.

| Concept | Emotion | Novelty | Judge fit | Buildable without headset | Verdict |
|---|---|---|---|---|---|
| **Unsaid**: one family's dinner table across decades. Look at someone to hear what isn't said; pinch the clock to replay; small hand moments at the end of each chapter; final chapter cooks Grandma's recipe | High | High (only a student proposal found) | High | Medium | **PICK** |
| Her Hands: learn a late grandmother's craft by following her ghost hands | Very high | High (only Ultraleap's tutorial ghost hands found) | Very high | Low (needs pose matching) | Only with a borrowed Quest |
| Fading: dementia from the patient's point of view | Very high | Medium (Embodied Labs exists) | Medium | Medium | Drop |
| Colour-blindness empathy | Medium | Low (Through Their Eyes) | Low | Low | Drop |

**Risks for Unsaid:** melodrama, a mechanic that has to feel great, a weak "Reason to Come Back", scope (maximum 2 chapters plus the finale), voices (record real people), and you still need a Quest for 1 to 2 days of testing.

**Sources:**
- Student proposal: https://desginimmersiveexperienceyao.myblog.arts.ac.uk/?p=36
- Embodied Labs: https://www.embodiedlabs.com/industries/family-caregiving-homebased-care
- Ultraleap Aurora: https://www.leapmotiontechnology.com/gallery-sub/aurora
- Meta gaze-audio patent: https://patents.justia.com/patent/10555106

---

## Round 3: no headset, ever (2026-10-15)

Constraint: only interactions the emulator can reproduce (pinch, grab, poke, point, gaze). Nothing that depends on real rooms or custom hand poses.

**Pick: "Mend"**, kintsugi stories (Entertainment, New Experience), overall about 8.4.
- **Core loop:** grab and turn the shards of a broken object; forgiving snap; each snap plays a fragment of the owner's memory as spatial audio from the object; pinch-drag along the cracks to pour glowing gold; the finished object goes on your shelf; one new object daily; the objects together tell one family's story.
- **Prior art:** none in VR (last year's 653 entries, plus web searches of Quest Store, App Lab and itch.io; verify the Quest Store manually). Assemble with Care (ustwo, flat screen) validates the concept. Le Dino Labo (assembly) won an honourable mention last year.
- **Scores:** EV 8.5 · Novelty 8 · Innovation 8.5 · Experience Design 9 · **Technical 7.5** · Polish 9 · Winner-pattern fit 8.5 · Buildable 8 · Demo 9 · Emotion 8.5 · Special awards 8.5.
- **Honest ceiling:** Technical Implementation can't reach 8 without a headset, because the criterion rewards passthrough, MRUK and verified 60 fps. Mitigations: gaze + pinch, spatial audio, glasses-ready, strict performance budget, a remote teammate who owns a Quest, Start mentor office hours.
- **Risks:** snap and turn feel is untested on a device; writing quality (5 monologues, ~1,500 words); being read as a puzzle game (keep it gentle, lead with the stories); respectful treatment of kintsugi.
- **Other round 3 candidates:** Unsaid + grabbed thoughts 6.5 to 7, paper theatre 6, clay stop-motion 6.5 (Mindshow/Quill prior art), constellation stories 5 (CONSTELLATIONS existed last year).

**Sources:**
- Assemble with Care: https://www.creativereview.co.uk/assemble-with-care/
- Assemble with Care free relaunch: https://toucharcade.com/2023/10/02/ustwos-assemble-with-care-now-available-for-free-with-premium-unlock-iap-following-its-removal-from-apple-arcade-last-month/
- Le Dino Labo: https://devpost.com/software/realcast-game-working-title

---

## Round 4: with a Quest 2 (2026-10-16)

Mend / Golden Seams still works, and the Quest 2 lifts the Technical ceiling from 7.5 to about 8.5. New overall estimate: **about 8.8**.

| Feature Meta is pushing | Works on Quest 2? | Use it in Mend? |
|---|---|---|
| Hand tracking (grab, turn, pinch) | Yes | Core |
| Gaze + pinch (IWSDK 1.0 / ISDK v207) | **No eye tracking on Quest 2, 3 or 3S.** IWSDK gaze is eye gaze and does not fall back to head pose in production | Build our own head-direction "look to listen" instead; use IWSDK gaze only as an extra on eye-tracked devices |
| Passthrough | Yes, but **greyscale** | Yes: repair on your real table. Check the gold colour on a Quest 3 |
| Plane detection / MRUK room setup | Manual Space Setup only, no automatic scene mesh | Yes: place the bowl on a real table |
| Persistent spatial anchors | Yes | **Yes: the shelf of mended objects stays in your real room (Reason to Come Back)** |
| Spatial audio | Yes | Core |
| Glasses FoV mask (IWSDK `fieldOfViewMask`) | Docs say "Quest 3, 3S, or another supported Quest" | Yes |
| Microgestures | Yes (Unity/Unreal docs list Quest 2) | Optional |
| Meta VR CLI / agentic-tools | Not device-bound | Use for building |
| Depth API (occlusion) | **No.** Quest 3/3S/Glasses only | Skip |
| Passthrough Camera API | **No.** Quest 3/3S only | Skip |
| VR CLI glasses-FoV simulation | No (Quest 3/3S/Pro only) | Use the IWSDK mask instead |

- **Performance:** Quest 2's XR2 Gen 1 is weaker than the XR2 Gen 2 in Quest 3/3S. Hitting 60 fps on Quest 2 gives you headroom on the judges' devices.
- **Rule:** don't add features just to tick boxes. Passthrough must change the experience, or it scores negatively.
- **Still needed:** a few hours on a Quest 3/3S before submitting, to check colour passthrough, the gold look and the final frame rate.
- **Sources:**
  - Depth API prerequisites: https://developers.meta.com/horizon/documentation/unity/unity-depthapi-overview
  - Passthrough Camera API: https://developers.meta.com/vr/documentation/spatial-sdk/spatial-sdk-pca-overview/
  - Phanto sample (scene mesh is Quest 3 only): https://developers.meta.com/horizon/documentation/unity/unity-sample-phanto
  - Local docs: linked-pages/038, 042, 053

- **Correction (2026-10-17):** the IWSDK gaze docs (iwsdk.dev/concepts/xr-input/gaze.html) say gaze is a single eye-gaze ray and "IWSDK does not silently replace missing production gaze with head pose". Quest 3/3S judges will not get eye gaze.
- **New prior art (2026-10-17):** Kintsugi: Scars of Gold (Kageori Lab, TUM-XR, 2026), a 10-minute Quest 3 hand-tracking festival piece about repairing your own heart. Not public. Novelty lowered from 8 to 7.5.
