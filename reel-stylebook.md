# Reel Stylebook: @tanii444.ka

Version 0.8 (2026-10-06: no fixed text positions on footage; text goes where each shot has room, section 3.3). Version 0.7 (2026-10-06: the accent line is left-aligned flush under the display as one title block, never centred or placed like a caption). Version 0.6 (2026-10-06: the design system gained a dark Ink theme; paper layouts can use it, one theme per reel). Version 0.5 (2026-10-06: synced with the current Tanichka Editorial design system: no polaroids, frames or tape (screenshots are plain photo cards), no heart icon, no tilted text). Version 0.4 (2026-10-05: text sizes +20%, no automatic caption pills, no colour grade, after Tetiana's review of IMG_6777). Built from the **Tanichka Editorial** design system, Tetiana's video editing rules, and a frame-by-frame study of her reference reel.

**Where this file lives:** inside the Tanichka Editorial design system (Export group, `assets/Export/reel-stylebook.md`). Whenever the design system changes, this file is updated in the same change so the two never disagree.

**Who reads this:** an AI editor (Claude Code with Whisper, ffmpeg and Remotion) cutting raw iPhone footage into finished vertical reels for Instagram Reels, TikTok, Stories and LinkedIn.

**Precedence when rules conflict:** 1) Tanichka Editorial design system, 2) this file, 3) the reference reel. The older test edit's style (Manrope, Cormorant, mint #9BE7B0) is retired. Never use it.

**Markers:** `⚑ ASSUMPTION` means a reasonable default that Tetiana hasn't confirmed yet. `+ NEW` means a video-only role that the design system doesn't define, built from its tokens.

---

## 0. Quick reference

| Item | Value |
| --- | --- |
| Canvas | 1080×1920, 30 fps, H.264 High, yuv420p, Rec.709 SDR, 16–20 Mbps, AAC 48 kHz 320 kbps |
| Fonts | Onest (400 / 500 / 700) and Playfair Display Italic 400. Nothing else, no fallbacks to Inter, Roboto or Arial |
| Captions | Onest 500, **58px**, lowercase, centred, **phrase chunks of 2–4 words, max 24 characters, 1 line** |
| Caption colour | Picked per shot to suit the picture: white #FFFFFF, porcelain #F6F5F1 or ink #111111 (section 1.2) |
| Caption timing | Min 800 ms on screen, target 1000–1600 ms, max 2400 ms. Soft Focus entrance (140 ms) |
| Text placement | **No fixed positions on footage.** Each shot, text and graphics go where the picture has room: the calmest empty area, never on her face or hands, never on busy detail (section 3.3). Platform safe zones always apply. Paper layouts keep their grid |
| Caption position | Placed per shot by section 3.3. Max width 760px. Fixed for the whole shot, moves only on a cut |
| Keyword | Playfair Display Italic 400 at 115% (67px), same colour as the caption. Max 1 per chunk, 1 per 6 s |
| Hook title | Onest 700, 118px, lh 0.98, ls -0.045em, left-aligned at the 68px side margin, never centred; height chosen per shot (section 3.3). Accent line Playfair Italic 80px, flush left 14px under the display, straight (never rotated) |
| Colours | paper #F6F5F1 · ink #111111 · muted #6E6A64 · white #FFFFFF (text on footage and glass) · accent-pink #F2A7C3 (dots and waveform only) |
| Zoom | Cut-zoom steps 100% ↔ 110%. Max 2 steps per 10 s, min 3.0 s apart. Slow push 100→103% inside a shot |
| Transitions | Hard cut inside a thought. Blur dissolve 240 ms for a new section. Blur dissolve 320 ms for a layout change |
| Easing | Entrances `cubic-bezier(0.22, 1, 0.36, 1)`, exits `cubic-bezier(0.4, 0, 1, 1)`. No springs that overshoot, no bounce |
| Restraint | Max 1 glass element and 1 glow on screen at once. Max 2 graphics plus the caption at once |
| Status pill | Frosted pill with a pulsing pink dot and animated dots ("Claude думає…") while something is in progress, then a soft Pop In of the result (section 6.5) |
| Pauses | Trim any pause over 400 ms down to 200 ms. Keep the last good take |
| Visual change | Something visibly changes every 3–5 s (cut-zoom, card, title, layout) |
| Sound | **No music.** One fixed kit of soft SFX from `@remotion/sfx` + ElevenLabs (pop, whoosh, click, switch, ding), max 1 per 3 s. Voice -14 LUFS integrated, -1 dBTP |
| Interest triggers | Open loop in the hook, status-pill anticipation, re-hook at 40–55%, payoff pop-up, loop ending (section 8.1) |
| Look | **No grade.** Keep the colour she shot; only the HDR → SDR conversion (section 12) |
| Ending | Comment-keyword CTA over footage in the last 3–4 s, then cut 300 ms after the last word so it loops |

---

## 1. Type

All type is lowercase by default. Brand and product names keep their own spelling (Claude, Figma, iPhone, CapCut, ChatGPT). Decided: a capitalised brand name is recognised at a glance and stands out as the one capital in a lowercase line, which works like a free highlight. Everything else stays lowercase.

Nothing is ever rotated or tilted: no tilted titles, accent lines, keywords or cards.

### 1.1 Roles

| Role | Font | Size | Weight | Line height | Letter spacing | Colour | Why |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `reel-caption` + NEW | Onest | 58px | 500 | 1.2 | -0.01em | #FFFFFF / #F6F5F1 / #111111 (section 1.2) | Tetiana found 48px too small (2026-10-05) and asked for +20%; 500 is the heaviest weight the system allows outside the display |
| `reel-caption-keyword` | Playfair Display Italic | 67px (115%) | 400 | 1 | 0 | same as its caption | The system's HighlightWord rule, applied to captions |
| `display` (hook title, section title) | Onest | 118px | 700 | 0.98 | -0.045em | #FFFFFF on footage, #111111 on paper | The system's display; the only bold |
| `accent-line` | Playfair Display Italic | 80px | 400 | 1.1 | 0 | same as display | The title's last line: straight, left-aligned at x 68 under the display |
| `beat-word` + NEW | Playfair Display Italic | 160px | 400 | 1 | 0 | #FFFFFF | One-word punchline moment (L5, section 3.2). Built on the accent line, scaled up |
| `section-label` | Onest | 48px | 400 | 1 | -0.01em | #FFFFFF on footage, #111111 on paper | Names the content below it |
| `meta` | Onest | 36px | 400 | 1 | 0 | #FFFFFF on footage, #111111 / #6E6A64 on paper | Handle, step index, small CTA lead-in |
| `pill` | Onest | 31px | 500 | 1 | -0.01em | #FFFFFF | Text inside a frosted pill or the status pill (+20% on the design system's 26px) |
| `body` (end card CTA) | Onest | 48px | 400 | 1.75 | 0 | #111111 on paper | The system's CTA body |

Load in Remotion with `@remotion/google-fonts/Onest` (weights 400, 500, 700) and `@remotion/google-fonts/PlayfairDisplay` (italic 400, subsets `latin`, `cyrillic`). Block the render until both are loaded (`delayRender`).

### 1.2 Captions

| Rule | Value | Why |
| --- | --- | --- |
| Words on screen | 2–4 words per chunk; a single word only if it is ≥ 10 characters or the whole sentence | Tetiana wants phrase captions, not word-by-word |
| Characters | Max 24 per chunk, including spaces | Keeps one line inside the 760px width at 58px (measured: typical 24-char Ukrainian lines are 670–730px) |
| Lines | 1 line. Never 2 | Keeps the caption a light ribbon, like the reference |
| Line breaks / chunking | Break at meaning: after a comma, before a conjunction (і, а, але, що, бо, and, but, so, that), before a preposition phrase. Never split a number from its unit, a name from its surname, a preposition from its noun | Reads as phrases you'd say in one breath |
| Min on screen | 800 ms. If a chunk would be shorter, merge it with the next one (if ≤ 24 chars) or hold it into the next chunk's start | "A little bit slower" than the reference's 300 ms per word |
| Target on screen | 1000–1600 ms | About 3× the reference's dwell time |
| Max on screen | 2400 ms; also clear the caption if a pause over 600 ms follows | Stale captions feel stuck |
| Sync | Chunk appears 40 ms before its first word starts; next chunk replaces it directly (no empty gap) | Avoids flicker between chunks |
| Position | No fixed position. Placed per shot by section 3.3: the calmest empty area of that shot with room for a 760×90px box; the line is centred in that box | Captions sit on empty space, like Tetiana wants |
| Position stability | The position is chosen once per shot (between two cuts) and never moves mid-shot; it may change only on a cut | Jumping captions look nervous |
| Case | lowercase (brand names excepted); no full stop at the end of a chunk; keep ? and ! only | Design system: lowercase, friendly |
| Language | Caption in the spoken language. English words inside Ukrainian speech stay in English spelling (e.g. "зробила це в Figma за 5 хвилин") | Tetiana's rule |
| Numbers | Digits, not words: "5 хвилин", "3 tips" | Faster to read |
| Filler words | Never captioned (they're cut anyway, section 8) | |
| Colour | Measured once per shot on the chosen area's box (mean of the frames): **ink #111111** if mean luminance > 62%; otherwise **porcelain #F6F5F1** if the picture is warm (mean Lab b* > +6, e.g. lamp light, skin, wood, beige) and **white #FFFFFF** if it is neutral or cool (b* ≤ +6, e.g. grey coat, daylight, screens, black and white). The chosen colour must reach a contrast of ≥ 4.5:1 against the box; if it doesn't, use whichever of the three colours does (e.g. ink on a mid-grey coat, 6.4:1, beats white at 3:1); if none does, try the next calmest area | Colour that matches the warmth and saturation of the picture, as Tetiana asked; only these 3 colours exist in the design system |
| Colour stability | One colour per shot; when the colour changes between shots it changes on the cut, never mid-phrase | No flicker |
| Stroke / shadow | None (design system: shadows only on one raised photo card and the pills) | Design system wins |
| Last resort | If no area passes 4.5:1, use plain text in the empty area with the best contrast. **Never put captions in a pill automatically** | Tetiana rejected pills on every caption (2026-10-05). A pill behind a caption only by hand, for one hard shot, if she asks |
| When hidden | While a hook title, section title, beat word or CTA line is on screen, and during full-screen paper layouts that show the same words | The reference does this: one text voice at a time |

### 1.3 Keyword highlight

| Rule | Value | Why |
| --- | --- | --- |
| Style | Playfair Display Italic 400, 115% of the caption (67px), same colour. Never pink, never underlined, never a box | Design system HighlightWord |
| How many | Max 1 per chunk and max 1 every 6 s (so about 5–9 per 45 s reel) | Keeps it a seasoning |
| Which word | In this order: 1) the result or number ("за 5 хвилин", "x2"), 2) the tool or thing being named (Claude, Figma), 3) the contrast word in a "not X but Y" line, 4) the emotional word that carries the point ("красиво", "легко") | Highlights the word you'd stress when speaking |
| Never | Function words (і, в, на, the, a, to), the first word of the reel, two keywords in a row | |

### 1.4 Hook title and section titles

| Rule | Value | Why |
| --- | --- | --- |
| Style | `display` (Onest 700, 118px) + optional `accent-line` (Playfair Italic 80px, straight) | The system's Headline |
| Alignment | Left edge at the 68px side margin (x 68). Never centred | Design system: never centre the display |
| Position | No fixed height. The whole block (display + accent line) goes in the calmest empty area of the shot that fits it at x 68 (section 3.3); accent line 14px below the display, flush left at the same x 68. Keep it inside the 4:5 crop (y 285–1635) when possible | Text goes where the shot has room, inside the safe zones |
| One title block | Display + accent line are one object: same left edge, built, placed and removed together (Soft Focus Title / Title Out). The accent line is never centred, never moved right or down, never placed in an area of its own, and never treated as a caption by caption detection, placement or Chunk Swap | It must read as part of the title, not as a separate caption |
| Length | Display: max 2 lines, max 14 characters per line. Accent line: max 22 characters | Readable in under 1 s |
| Build | Each line appears when she says it (line by line, not word by word), with Soft Focus Title (section 5) | Keeps the reference's build-up feeling without word-by-word switching |
| Duration | On for 2.5–4.0 s, exit with Soft Focus Out | |
| Where | Hook (0–3 s), each new section of a tutorial (max 3 per reel), the CTA | |

### 1.5 Accent font use (Playfair Display Italic)

Only for: the caption keyword, the accent line under a display title, the beat word, and the CTA keyword. Never a whole caption, never a paragraph.

---

## 2. Colour

Every value comes from the design system tokens.

| Element | Colour | Token | Why |
| --- | --- | --- | --- |
| Captions over footage | #FFFFFF, #F6F5F1 or #111111, chosen per shot (section 1.2) | `on-glass` / `paper` / `ink` | Matches the picture's warmth and brightness |
| Titles, labels, CTA over footage | #FFFFFF (or #111111 when the title area's mean luminance > 62%) | `on-glass` / `ink` | |
| Keyword in captions | same as its caption | — | HighlightWord: same colour |
| Status pill progress line | track rgba(255,255,255,0.18), fill rgba(255,255,255,0.85), 3px | `on-glass` at opacity | Stays inside the pill's white-on-glass palette; pink stays for the dot |
| Paper backgrounds (split layout, end card) | #F6F5F1 | `paper` | The only background colour in the Paper theme |
| Ink theme (paper layouts only) | ground #151413, text and icons #F3F1EC, secondary #9E9890; pink, glass and photos unchanged | `paper` / `ink` / `muted` in Ink (`data-theme="ink"`) | The design system's dark theme. Pick one theme per reel in the brief and use it for every paper layout (L3, end card); never mix. Text over footage is unaffected ⚑ ASSUMPTION |
| Text, icons and lines on paper | #111111 (Ink theme: #F3F1EC) | `ink` | |
| Secondary notes on paper (e.g. "source:") | #6E6A64 | `muted` | Captions/secondary only |
| Dot in pills, waveform bars | #F2A7C3 | `accent-pink` | The one accent; never text, never a fill |
| Frosted pill fill | linear 180°: rgba(34,34,36,0.52) → rgba(14,14,16,0.60) | `glass-dark-*` | |
| Frosted pill rim | 1px, rgba(255,255,255,0.30) at corners → rgba(255,255,255,0.10) on long sides | `glass-border*` | |
| Voice pill fill (end card) | linear 180°: rgba(48,48,50,0.92) → rgba(28,28,30,0.92) | `glass-solid-*` | |
| Voice pill close circle / × | #3A3A3D / #B9B9BE | `voice-close` / `voice-x` | |
| CTA glow (end card only) | radial, #F2A7C3B3 → transparent at 68%, 540px wide | `glow-strong` | |
| Section / layout dissolve tint | rgba(246,245,241,0.30) → 0 | `paper-tint` → `paper-clear` | The dissolve's tint |

Not allowed: any other colour, coloured backgrounds, pink text, mint, neon, gradients other than the five defined in the design system.

---

## 3. Layout

### 3.1 Canvas and safe zones

| Item | Value | Why |
| --- | --- | --- |
| Canvas | 1080×1920, 30 fps (convert 24/60 fps footage to 30) | Reels/TikTok/Stories native |
| Top unsafe band | 0–250px: no text | Platform header, Stories progress bar |
| Bottom unsafe band | 1440–1920px (bottom 480px): no text | Reels/TikTok caption, username, audio row |
| Right unsafe band | x 920–1080 from y 900 down: no text | Like/comment/share buttons |
| Side margin | 68px | `margin-side` |
| LinkedIn / profile grid crop | Keep hook title and key text inside y 285–1635 (centre 1080×1350) | LinkedIn and the Instagram grid may crop to 4:5 / 3:4 ⚑ ASSUMPTION |

### 3.2 Layouts

Positions for text and graphics on footage in this table are examples of a good spot, not rules: on footage, section 3.3 decides each shot. Paper areas (L3's top half, the end card) keep their grid, since there is no footage to avoid there.

| Code | Name | Composition | Use when |
| --- | --- | --- | --- |
| L1 | Full face | Footage fills 1080×1920; eyes at y 760 ± 60 | Default for talking-head speech |
| L2 | Card over face | Footage full frame; one photo card (screenshot, result, photo: a plain rectangle, radius 0, no frame, straight, `shadow-lift`), max 760×560, placed by section 3.3 (e.g. above her head when that area is empty); never over her face or hands | She mentions something visual for 1.5–6 s: an app, a result, a before/after |
| L3 | Paper split | Top 0–1000: paper #F6F5F1, `meta` header row at y 260 (left: step index `[2]`, centre: `@tanii444.ka`), screen recording as a photo (radius 0, no shadow) at x 68–1012, y 320–980. Bottom 1000–1920: footage, cropped so her face centres at y 1300 | Tutorials: a screen recording or UI shown for more than 6 s |
| L4 | Full screen + face card | Screen recording fills the frame (or sits on paper, x 68–1012); her face in a 300×370 photo card (radius 0, no frame, straight, `shadow-lift`) in the calmest corner of the recording (e.g. lower right, outside the right unsafe band) | Long screen walk-through where her face isn't needed but her voice is |
| L5 | Beat moment | Footage in black and white (saturation 0), beat word in the calmest empty area of the shot (e.g. lower middle), never on her face | One punchline or "no" moment per reel, 600–1200 ms |
| L6 | CTA over footage | Footage full frame; `meta` lead-in with the `accent-line`-style keyword under it, as one block placed by section 3.3 (e.g. upper third when it is empty) (section 11) | Last 3–4 s |

| Switch rule | Value | Why |
| --- | --- | --- |
| Min time in a layout | 2.0 s (L5 excepted) | Prevents choppy jumping |
| Max layout changes | 1 per 6 s | Calm pacing |
| Transition between layouts | Blur Dissolve, 320 ms (section 5) | |
| Horizontal footage, talking head | Crop to 9:16 around her face (eyes at y 760); requires ≥ 1080px source height after crop, else use L3 | |
| Horizontal footage, screen or scenery | Place as a photo on paper (L3) or as a photo card (L2). Never stretch, never blurred-copy background | Blurred-fill backgrounds look cheap |

### 3.3 Text placement on footage

There are no fixed positions for text or graphics on footage. For each shot, text goes where the picture has room.

| Rule | Value | Why |
| --- | --- | --- |
| Where | The calmest empty area of the shot: never on her face or hands, never on busy detail (edge density over 8% of pixels with a Sobel filter, or visible movement), with room for the whole element's box | Text sits on empty space and never covers her |
| How to choose | Analyse every frame of the shot (between two cuts). Mask her face and hands with a 40px margin plus the safe zones below, then pick the free area with the least detail and motion that fits the box for the whole shot | A spot that is empty in one frame can be covered a second later |
| Stability | Chosen once per shot; it never moves mid-shot and may change only on a cut | Moving text looks nervous |
| Several elements | Place the most important first (title or CTA, then a pop-up card, then a pill, then the caption), each in its own calm area, at least 40px apart, never overlapping. One text voice at a time still applies (section 1.2) | |
| Alignment | The display title block always has its left edge at the 68px side margin (never centred); only its height changes. Other elements are centred in their area | Design system: display left-aligned |
| Contrast | After choosing, the colour rule in section 1.2 must reach ≥ 4.5:1; if it can't, use the next calmest area | |
| No room | If no area fits: shorten the text or leave out the non-essential graphic (pill, handle tag); never fall back to her face or hands | |
| Safe zones | Always: no text in the top 250px, the bottom 480px, or right of x 920 from y 900 down (section 3.1) | The app's own buttons and captions cover those |
| Paper layouts | Split screen (L3's paper half) and the end card keep their grid; there is no footage to avoid there | |

---

## 4. Zooms

The reference alternates two framings at each jump cut (about 100% and 110–115%), once every 4.1 s on average (20 framing jumps in 82 s). We copy that, slightly calmer.

| Rule | Value | Why |
| --- | --- | --- |
| Cut-zoom (on a jump cut) | Alternate 100% and 110% scale, anchored on her face (eyes stay at the same y) | Hides jump cuts; the reference's main motion device |
| Emphasis punch-in | 115%, only on the keyword of the strongest line, max 2 per reel; hard cut in, return on the next cut | |
| Animated punch-in (no cut available) | 100→108% over 400 ms, `cubic-bezier(0.22, 1, 0.36, 1)` | |
| Slow push inside a shot | 100→103% linear across the shot (scale only, centre on face) | Keeps a still shot alive |
| Triggers | A new sentence after a jump cut; the keyword of a key claim; the payoff line | |
| Max | 2 zoom changes per 10 s; min 3.0 s between two | Calmer than the reference's ~2.4 per 10 s |
| Never during | A title build, a card entrance, the beat moment, L3/L4 screen layouts, the CTA, the first 600 ms | One movement at a time |
| Max scale ever | 115% (check sharpness: 4K source only above 110%) | Beyond that iPhone 1080p goes soft |

---

## 5. Animations and motion

All motion is ease-out, short, and soft. No bounce, no shake, no spin, no rotation, no typewriter on captions. The only overshoot allowed is Pop In's 2% settle on pop-ups.

Easing tokens:
- `ease-enter`: `cubic-bezier(0.22, 1, 0.36, 1)` (Remotion: `Easing.bezier(0.22, 1, 0.36, 1)`)
- `ease-exit`: `cubic-bezier(0.4, 0, 1, 1)`
- `ease-move`: `cubic-bezier(0.65, 0, 0.35, 1)`

Named animations. CapCut equivalents are given only as the closest feel; the names below are what this stylebook uses.

| Name | Applies to | Properties | Duration | Easing | Closest CapCut feel |
| --- | --- | --- | --- | --- | --- |
| Soft Focus In | Captions | opacity 0→1, blur 8→0px, scale 0.96→1, y +8→0px | 140 ms | ease-enter | Fade In + Blur |
| Soft Focus Out | Captions (only when no chunk follows) | opacity 1→0, blur 0→6px | 100 ms | ease-exit | Fade Out |
| Chunk Swap | Caption → next caption | old: Soft Focus Out 100 ms; new: Soft Focus In 140 ms, starting at the same frame | 140 ms | — | — |
| Soft Focus Title | Display lines, accent line, section label | opacity 0→1, blur 12→0px, scale 0.92→1, y +16→0px; each next line starts 120 ms after the previous one's start | 220 ms per line | ease-enter | Blur In |
| Title Out | Titles | opacity 1→0, blur 0→10px, y 0→-8px, all lines together | 180 ms | ease-exit | Fade Out |
| Card Drop | Photo cards (L2, L4) | y +40→0, opacity 0→1; shadow fades in with it. No rotation | 360 ms | ease-enter | Slide Up + Fade |
| Card Lift | Photo card exit | y 0→-24, opacity 1→0 | 220 ms | ease-exit | — |
| Pill Rise | Frosted pill | y +24→0, opacity 0→1, backdrop blur 0→24px | 260 ms | ease-enter | Slide Up |
| Icon Fade | Bookmark, arrow | opacity 0→1, scale 0.9→1 | 200 ms | ease-enter | Fade In |
| Blur Dissolve (section) | Cut between sections | outgoing: blur 0→16px + opacity 1→0; incoming: scale 1.04→1, blur 16→0px; paper tint 0.30 peak at midpoint | 240 ms | ease-move | Blur (transition) |
| Blur Dissolve (layout) | Layout changes | same as above | 320 ms | ease-move | Blur |
| Pop In + NEW | Pop-ups: result card, UI card after a status pill, fact pill | scale 0.90→1.02→1.00, opacity 0→1, blur 6→0px. Remotion: `spring({fps, config: {damping: 18, stiffness: 170, mass: 1}})` mapped to scale 0.90→1 (≈ 2% overshoot); check it never exceeds 1.025 | 320 ms | spring | Pop / Zoom In |
| Pop Out | Pop-ups | scale 1→0.96, opacity 1→0, blur 0→4px | 180 ms | ease-exit | — |
| Status Pulse | Status pill dot | opacity 0.55→1→0.55 and glow 0.3em→0.6em, loop | 1200 ms per loop | ease-move | — |
| Thinking Dots | "…" after the status text | 3 dots, each fades 0.25→1 in turn, 200 ms apart, loop | 900 ms per loop | ease-move | — |
| Status Swap | Status text → next status text | old text: y 0→-12px, opacity 1→0; new text: y +12→0px, opacity 0→1, blur 4→0px; pill width animates to the new text | 260 ms | ease-enter | — |
| Status Done | Last state of the status pill | dot cross-fades into a 0.9em thin outline check (stroke 2.2px, #FFFFFF), progress line fills to 100% | 240 ms | ease-enter | — |
| Beat Cut | Into and out of L5 | hard cut to saturation 0 + beat word Soft Focus Title; hard cut back | 0 ms cut, word 220 ms | ease-enter | — |

| Rule | Value | Why |
| --- | --- | --- |
| Elements entering at once | Max 1 (stagger 120 ms if two must enter) | One movement at a time reads as calm |
| Idle motion | Only the slow push (section 4). Graphics don't float, pulse or wiggle; the pink dot may glow-pulse at 0.8→1.0 opacity over 1600 ms | |
| Springs (Remotion) | `damping: 200` (no overshoot) for everything except Pop In | |
| Pop-ups at once | Max 1 pop-up on screen; a new one replaces the old with Pop Out → Pop In, 80 ms apart | |

---

## 6. Graphics

### 6.1 Allowed elements

| Element | Spec | Position | Max |
| --- | --- | --- | --- |
| Hook / section title | Section 1.4 | Left edge x 68; height by section 3.3 | 1 at a time |
| Section label | `section-label`, lowercase, e.g. "крок 2", "результат" | On footage: by section 3.3, left edge x 68, directly above what it names; on paper: the field's left edge | 1 |
| Step index | BracketTag `[2]` in `meta` | L3 paper header, left (paper grid) | 1 |
| Handle tag | `@tanii444.ka` in `meta`, #FFFFFF on footage / #111111 on paper | On footage: by section 3.3, in any calm area; on the L3 paper header: centred. Shown 0.6–3.0 s in the hook and on the L3 header | 1 |
| Screenshot / UI card | Photo card: a plain rectangle, radius 0, no frame, no tape, never tilted, `shadow-lift` (0 22px 44px rgba(17,17,17,0.18)) | By section 3.3 (L2 in section 3.2 is an example) | 1 on screen (2 only as a before/after pair, side by side with a 14px gap) |
| Frosted pill | Section 6.4 | On footage only, by section 3.3: its own calm area near what it describes, never touching the caption | 1 glass element per screen |
| Status pill | Section 6.5 | By section 3.3: a calm area with room below or beside it for the result | 1; counts as the glass element |
| Icons | Outline only: bookmark 24×30, arrow 104×22 (stroke 2.2–2.4px, round caps). Ink on paper, white on footage | In CTA and L3 header/footer | 2 |
| Voice pill | Design system VoicePill | End card only (section 11) | 1 |
| Glow | `glow-strong`, 540px | Behind end card CTA only | 1 |

### 6.2 Not allowed

Full-width progress or timeline bars across the video, emoji, stickers, hearts, arrows that point at things, circles around things, filled or 3D icons, polaroids, photo frames, tape strips, tilted or rotated text or cards, rounded cards, borders, boxes, drop shadows (except one raised photo card and the pills), subscribe/like animations, logo bugs, countdown timers. Progress is shown only inside the status pill (6.5) or with the BracketTag step index `[1]`, `[2]`, `[3]`.

### 6.3 Screen recordings

| Rule | Value |
| --- | --- |
| Capture | Native resolution, 30 fps, cursor visible, light mode, notifications off |
| Crop | Crop to the region that matters; text in the UI must render ≥ 22px tall on the 1080 canvas, else zoom the recording (Ken Burns 100→115% over the shot, `ease-move`) |
| Frame | No device mockups. On paper (L3) as a radius-0 photo; on footage (L2) as a photo card |

### 6.4 Frosted pill on video

Design system FrostedPill: fill `glass-dark`, backdrop blur 24px + saturate 120%, radius 999px, 1px gradient rim, inner highlight, `shadow-pill` (0 10px 26px rgba(17,17,17,0.24)), pink dot 0.32em with its glow. Proportions in em: height ≈ 2.8em, padding 0.9em 1.55em 0.9em 0.95em, gap 0.72em.

| Use | Text size | Content |
| --- | --- | --- |
| Fact pill | 31px (`pill`) | 2–4 words stating one fact: "6 категорій поз", "за 5 хвилин" |
| Caption in a pill | 58px (`reel-caption`), dot omitted | Only by hand, when Tetiana asks for it on a shot (never automatic, section 1.2) |

### 6.5 Status pill + NEW

The "work in progress" pill from the earlier test edit, which Tetiana liked, rebuilt in the design system. Use it whenever something is happening that the viewer waits for: Claude thinking, an app generating, a render, an upload, a search.

| Part | Spec |
| --- | --- |
| Shell | FrostedPill (6.4): `glass-dark` fill, 24px backdrop blur + saturate 120%, 1px gradient rim, `shadow-pill`, radius 999px, height 2.8em at 31px text (≈ 87px) |
| Dot | `accent-pink` #F2A7C3, 0.32em, own glow, Status Pulse |
| Text | `pill` style (Onest 500, 31px, #FFFFFF), lowercase except brand names, max 26 characters, then Thinking Dots. Examples: "Claude думає", "збирає дизайн", "шукає референси", "готово" |
| Progress line (optional) | 3px line inside the pill, 0.95em from the left, 1.55em from the right, 10px above the bottom edge; track rgba(255,255,255,0.18), fill rgba(255,255,255,0.85), radius 999px. Fills with `ease-move` across the whole status sequence, never resets |
| Position | No fixed spot: placed by section 3.3 in a calm empty area of the shot; its pop-up result lands in the next calm area beside or below it, never over her face or hands |
| Sequence | 1) Pill Rise as she starts the action ("я питаю Claude…"). 2) 1–3 status texts, each on screen ≥ 1200 ms, changed with Status Swap. 3) Status Done ("готово" + check) for 600 ms. 4) Pill Rise reversed (180 ms), and 80 ms later the result pops up with Pop In (photo or UI card) |
| Length | 1.8–4.5 s from Pill Rise to Done. If the real process took longer, speed up the screen recording (up to 8×) or cut it; never make the viewer wait over 4.5 s |
| Max | 3 status sequences per reel, at least 8 s apart; never while a title, handle tag or CTA is on screen (one text voice at a time) |
| Sound | `switch-soft` on each Status Swap, `ding-soft` on Done, `pop-soft` on the result Pop In (section 7) |

---

## 7. Sound

No music in the file. Soft, popular sound effects only, from one fixed **sound kit** so every reel sounds like the same editor made it.

### 7.1 Where the sounds come from

Think before picking. Ask of every sound: would a premium app (Apple, Linear, Notion) make this sound on this event? If it sounds like a meme, a cartoon or a game, it's out. Sources, in this order:

| # | Source | What it is | Use it for |
| --- | --- | --- | --- |
| 1 | **`@remotion/sfx`** (Remotion's own sound package, MIT, files peak-normalised to -3 dB) | Install once inside her Remotion project (`Claude/video-tools/remotion`): `npx remotion add @remotion/sfx`. Import the URL in code: `import {whoosh} from '@remotion/sfx'` | whoosh, click, switch, page turn, shutter, ding (table 7.2) |
| 2 | **ElevenLabs Sound Effects** (text-to-sound AI; the tool power users pair with Remotion) | Official agent skill: `npx skills add elevenlabs/skills` (includes `sound-effects` and `setup-api-key`). Needs an `ELEVENLABS_API_KEY` on a paid plan. API: `POST /v1/sound-generation` with `text`, `duration_seconds` (0.5–30), `prompt_influence` (0–1), model `eleven_text_to_sound_v2` | Sounds Remotion doesn't have: the soft pop, the air swell, quiet typing (prompts in 7.2) |
| 3 | **ffmpeg synthesis** (works offline, no account) | Recipes in 7.2, tested | Fallback for the pop and the whoosh if there's no ElevenLabs key |

Never use from `@remotion/sfx`: `whip` and every meme sound (`bruh`, `vineBoom`, `windowsXpError`, `fah`, `spongebobFail`, `omgHellNah`, `priceIsRightFail`, `romanceMeme`, `boneCrack`, `animeWow`, `yippee`, `loadingLag`, `wilhelmScream`, `macQuack`, `skedaddle`, `snapchatNotification`, `nellyAhh`, `sanctuaryGuardianWhat`, `minecraftHurt`, `ohMyGodVine`, `illuminatiConfirmed`, `dramaticBoomer`, `triggered`, `recordScratch`). They're the cheap "dopamine" style.

### 7.2 The kit (event → sound)

Kit files live in `Claude/video-tools/remotion/public/sfx/` (Remotion loads them with `staticFile('sfx/<name>.wav')`). That folder is created in Round 0 (section 16). Remotion volume = 10^((target peak + 3) / 20), because every kit file is normalised to a -3 dB peak.

| Kit file | Event | Source | Treatment | Target peak | Remotion `volume` |
| --- | --- | --- | --- | --- | --- |
| `pop-soft.wav` | Pop-up appears (Pop In: result card, UI card, fact pill) | ElevenLabs: "a single soft bubble pop, short and rounded, gentle UI pop-up, no click, no reverb", `duration_seconds` 0.5, `prompt_influence` 0.7; generate 4, keep the roundest. Fallback (ffmpeg): `ffmpeg -f lavfi -i "aevalsrc='0.8*sin(2*PI*(260*t+2400*t*t))*exp(-34*t)':s=48000:d=0.16" -af "afade=t=in:d=0.004,lowpass=f=3500,afade=t=out:st=0.13:d=0.03" pop-soft.wav` | low-pass 3.5 kHz | -22 dBFS | 0.11 |
| `whoosh-soft.wav` | Layout change, section change (Blur Dissolve) | `@remotion/sfx` `whoosh` (https://remotion.media/whoosh.wav) | low-pass 6 kHz, trim to 300–400 ms | -24 dBFS | 0.09 |
| `switch-soft.wav` | Status Swap (status pill text changes) | `@remotion/sfx` `uiSwitch` (https://remotion.media/switch.wav) | low-pass 6 kHz | -26 dBFS | 0.07 |
| `click-soft.wav` | UI click in a screen recording (only clicks that change the screen) | `@remotion/sfx` `mouseClick` (https://remotion.media/mouse-click.wav) | none | -24 dBFS | 0.09 |
| `page-soft.wav` | Tutorial step change (`[1]` → `[2]`) | `@remotion/sfx` `pageTurn` (https://remotion.media/page-turn.wav) | low-pass 7 kHz, trim to ≤ 500 ms | -26 dBFS | 0.07 |
| `ding-soft.wav` | Status Done, payoff (max 2 per reel) | `@remotion/sfx` `ding` (https://remotion.media/ding.wav). If it sounds bright or like a notification, use ElevenLabs: "one soft glass bell tap, warm, short decay, minimal", `duration_seconds` 1.0, `prompt_influence` 0.7 | low-pass 5 kHz | -24 dBFS | 0.09 |
| `shutter-soft.wav` | Screenshot first shown (max 1 per reel) | `@remotion/sfx` `shutterModern` (https://remotion.media/shutter-modern.wav) | low-pass 7 kHz | -24 dBFS | 0.09 |
| `air-soft.wav` | Hook title, first line only | ElevenLabs: "very short soft breathy air swell, subtle, no whoosh tail", `duration_seconds` 0.5, `prompt_influence` 0.6. Fallback: `whoosh-soft.wav` at volume 0.045 | low-pass 5 kHz | -28 dBFS | 0.056 |
| `keys-soft.wav` | A prompt or text typing on screen | ElevenLabs: "quiet close laptop keyboard typing, soft keys, steady", `duration_seconds` 2.0. No fallback: skip the sound | low-pass 6 kHz, trim to the typing length | -28 dBFS | 0.056 |
| — | Beat moment (L5) | Room tone only | — | — | — |
| — | Caption change, keyword, zoom | No sound (a sound on every word is the "dopamine" style she doesn't want) | — | — | — |

### 7.3 Rules

| Rule | Value | Why |
| --- | --- | --- |
| Music | **None in the file.** Tetiana adds audio in the app herself if she wants it | Her decision |
| One kit | Build the kit once (Round 0), get Tetiana's OK, then never swap or add sounds per video. Changes go through this file | Same sounds every time = a recognisable style |
| Local copies | Download the Remotion sounds into `public/sfx/` instead of streaming the URLs at render time | Renders work offline and the kit can't change under us |
| Kit processing | For each file: trim leading silence, 3 ms fade in, 20 ms fade out, the low-pass in 7.2, mono, 48 kHz, 24-bit WAV, peak-normalised to -3 dBFS | All kit files behave the same in the mix |
| Kit manifest | `public/sfx/kit.json`: for each file its event, source (package export or ElevenLabs prompt + settings, or ffmpeg recipe), date | Anyone can rebuild or audit the kit |
| SFX density | Max 1 per 3 s, max 12 per reel; never 2 within 400 ms | Noticeable but calm |
| SFX timing | Sound starts on the same frame as the visual event (Pop In: 1 frame before) | Sync is what makes it feel professional |
| SFX level | Target peaks in 7.2, i.e. 8–14 dB under the voice peaks | Soft, never harsh |
| Room tone | Fill every cut and every removed pause with 0.5 s of her own room tone at its natural level, crossfaded 30 ms | Without music, pure digital silence between words sounds broken |
| Voice chain (ffmpeg) | `highpass=f=80, afftdn=nr=10, deesser=i=0.4, acompressor=threshold=-20dB:ratio=3:attack=10:release=120, loudnorm=I=-14:TP=-1:LRA=7` | Clean, even voice at platform loudness (the reference measures -14.4 LUFS) |
| Master | -14 LUFS integrated, -1 dBTP | |

---

## 8. Pacing and cutting

The reference is cut almost gap-free (only 4 pauses longer than 120 ms in 82 s) with framing jumps every ~4.1 s. We keep the flow but give it a little more air.

| Rule | Value | Why |
| --- | --- | --- |
| Dead air | Any pause over 400 ms is trimmed to 200 ms | Tight but not breathless |
| Between sentences | 150–250 ms of silence | Lets each line land |
| Before a payoff line | Keep up to 400 ms | A beat before the punchline |
| Breaths | Remove breaths louder than -35 dBFS between sentences; keep quiet ones inside a sentence | Removing all breaths sounds robotic |
| Takes | Keep the **last** complete take of a line. Use an earlier take only if the last one has a stumble, and say so in the edit notes | Her final take is usually the intended one |
| Repeats | Remove false starts and repeated words ("це… це"), keep the clean repeat | |
| Filler words | Cut: ну, ее, ем, типу, короче, так от, um, uh, like (as filler), you know. Keep if cutting breaks the sentence | |
| Cut point | On a word boundary, with 2 frames (66 ms) of handle after the last phoneme; 30 ms audio crossfade on every cut | No clipped consonants or clicks |
| Visual change | Every 3–5 s (cut-zoom, card, title, layout); never more than 6 s without one; never two within 1.5 s | Reference average: one framing change every 4.1 s |
| Speed | Never speed up speech. ⚑ ASSUMPTION: no 1.1× speed-ups | Keeps her voice natural |
| Target length | 30–60 s; flag any reel over 60 s | |

### 8.1 Interest triggers (motion design)

Retention devices, all built from the motion and graphics in this file. Use at least 4 per reel.

| Trigger | What it looks like | When | Max |
| --- | --- | --- | --- |
| Open loop | Hook shows the result for 0.8–1.2 s as a Pop In photo card (or says it in the hook title), then it Pops Out; the full result returns at the payoff | 0–3 s | 1 |
| Anticipation | Status pill sequence (6.5): the viewer watches something "work" before the result pops up | Any time a process happens | 3 |
| Pattern interrupt | Cut-zoom, layout change, pop-up or title: something changes every 3–5 s | Throughout | (section 8) |
| Progress signal | Step index `[1]` → `[2]` → `[3]` in tutorials, or the status pill's progress line | Tutorials, processes | — |
| Re-hook | A section title with a new promise ("а тепер найцікавіше", "the best part") + whoosh, at 40–55% of the reel | Middle | 1 |
| Contrast | L5 beat moment: black and white + one big Playfair word | The surprising line | 1 |
| Payoff | Result Pop In + `ding-soft`, held 2.0–3.0 s, captions hidden | Last third | 1–2 |
| Direct address | Cut to 110% framing on lines that say "ти / you" | When she addresses the viewer | — |
| Loop | Last line flows into the hook, framing matches (section 11) | End | 1 |

---

## 9. Hook (first 0–3 s)

| Time | What happens |
| --- | --- |
| Frame 0 | She is already mid-energy and speaking (cut any lead-in). Framing at 110% (tight), Full face. No black frames, no logo |
| 0–150 ms | Nothing animates yet except the slow push |
| 150 ms – 1.2 s | Hook title (placed by section 3.3, left edge x 68) line 1 builds (Soft Focus Title), line 2 120 ms later, accent line last. Captions hidden while the title is on |
| 0.6 – 3.0 s | Handle tag `@tanii444.ka` in `meta`, placed by section 3.3 in a calm area away from the title |
| ≈ 3.0 s | First cut-zoom to 100% on the first jump cut; Title Out; captions start |

Hook title = the promise in max 2 short lines + an accent line. Tetiana talks about general topics, so these templates are formulas that work for any subject; fill in the brackets.

| # | Formula | Example (display / accent line) | Why it works |
| --- | --- | --- | --- |
| 1 | [result] за [time] | "пост за / 5 хвилин" · *без дизайнера* | Concrete payoff and effort |
| 2 | [common belief] не працює | "ранкові рутини / не працюють" · *ось що працює* | Contrarian claim opens a loop |
| 3 | [N] речі, які [result] | "3 речі, які / змінили мій день" · *третя найпростіша* | Numbers promise a clear end |
| 4 | я [did X] — ось що вийшло | "я тиждень / не брала телефон" · *ось що вийшло* | Personal story, outcome withheld |
| 5 | як [result] без [pain] | "як вчити англійську / без підручників" · *по 10 хвилин* | Desire plus removed obstacle |

English versions: "[result] in [time]" · "[common belief] doesn't work" · "[N] things that [result]" · "I [did X] for [time]: here's what happened" · "how to [result] without [pain]".

Rule for the spoken hook: the first sentence states the result, not the context. Never start with "привіт", "отже" or "in this video".

---

## 10. Structure (beat sheets)

### 10.1 Talking-head tip (30–45 s)

| Time | Beat | Visual |
| --- | --- | --- |
| 0–3 s | Hook: the result or claim | L1 + hook title |
| 3–8 s | Why it matters / the problem | L1, cut-zooms |
| 8–30 s | 2–3 points, one idea each | L1; L2 card per point if there is something to show; 1 keyword per point |
| 30–35 s | Payoff / proof | L2 result card or L5 beat moment |
| last 3–4 s | CTA | L6 |

### 10.2 Tutorial with screen recording (45–60 s)

| Time | Beat | Visual |
| --- | --- | --- |
| 0–3 s | Hook: the finished result first | L2 photo card of the result + hook title |
| 3–7 s | What you need (tool, 1 line) | L1 + fact pill |
| 7–45 s | Steps 1–3 (max 4), ≈ 8–12 s each | L3 paper split with `[1]`, `[2]`, `[3]` + section label; cut back to L1 for 1–2 s between steps |
| 45–52 s | Result again | L2 or L3 |
| last 3–4 s | CTA (keyword for the prompt / link) | L6 |

### 10.3 Story (30–60 s)

| Time | Beat | Visual |
| --- | --- | --- |
| 0–3 s | Hook: the moment of tension or surprise | L1 tight (110%), hook title |
| 3–15 s | Setup: where/when/who | L1, B-roll as L2 photo cards |
| 15–40 s | Turn: what happened, the problem | L1, max 1 L5 beat moment |
| 40–52 s | Lesson in one line | Section title (display) |
| last 3–4 s | CTA | L6 |

---

## 11. Ending

| Item | Value | Why |
| --- | --- | --- |
| Default CTA | Comment keyword, as in the reference: `meta` line "напиши в коментарях" (EN: "comment") with the keyword in Playfair Display Italic 80px directly under it, straight, the two lines centred on each other as one block, #FFFFFF. No fixed position: the block goes where the shot has room (section 3.3) | Comment CTAs drive reach; the reference's strongest graphic, made lowercase per the system |
| CTA wording | Max 2 lines. Patterns: "напиши «промпт» в коментарях" · "збережи, щоб не загубити" · "comment «guide» and I'll send it" | Design system: CTA 1–2 lines, imperatives |
| CTA timing | Appears with the first word of her spoken CTA, stays to the end; captions hidden meanwhile | |
| End card (optional, tutorials and carousels-to-video) | 1.2 s paper card: design system FinalSlide in 1080×1920 (`.te-canvas--story`): voice pill + 2 body lines with 1 highlight word, strong glow behind, footer bookmark + "збережи". Enters with Blur Dissolve 320 ms | Reuses the CTABlock exactly |
| Loop rule | No end card by default. Cut 300 ms after her last word; the last frame should match the first frame's framing (both 110%), and the last line should lead into the hook where possible ("…і саме тому" → "пост за 5 хвилин") | Instagram replays automatically; a seamless loop adds watch time |

Default: comment-keyword CTA with a seamless loop; the paper end card only when a reel needs it.

---

## 12. Footage look

| Item | Value | Why |
| --- | --- | --- |
| Input | iPhone 17 Pro HEVC; if HDR (HLG / Dolby Vision), tone-map to SDR Rec.709 first: `zscale=t=linear:npl=100,format=gbrpf32le,zscale=p=bt709,tonemap=hable:desat=0,zscale=t=bt709:m=bt709:r=tv,format=yuv420p` | HDR looks washed out or blown on many phones once overlays are added |
| Grade | **None.** Don't change saturation, contrast, curves or colour balance | Tetiana: the soft warm grade made her footage look awful (2026-10-05). Her iPhone colour is the look |
| Skin | Never push saturation above 100%; no beauty filter, no skin smoothing | Natural and premium |
| Mixed light | Match all clips in a reel to the first clip's white balance (±200 K) | One continuous look |
| Sharpening | `unsharp=5:5:0.4` only when the source is 1080p and zoomed above 105% | |
| Framing (vertical) | Eyes at y 760 ± 60, headroom above for titles; the face never crosses x 920 (right buttons) | Leaves calm space around her for text |
| Framing (horizontal) | See section 3.2 switch rules | |
| Crop | Never crop above the hairline or through the chin; at 110% the eyes must still be at y 700–820 | |
| Stabilisation | Only for handheld outdoor shots: `deshake` or `vidstab`, max 5% crop | |
| Black and white | Only in L5 beat moments | |

---

## 13. References

### 13.1 Reference reel (reference-reel.mp4, 82.5 s, 720×1280, 30 fps)

Measured: one continuous talking-head setup, hard jump cuts with framing alternating ≈ 100% / 112% every 4.1 s on average; captions change every 0.30 s (median, word by word), visible 59% of the time; almost no pauses (4 over 120 ms); loudness -14.4 LUFS.

| Copy | Exactly what | How it changes for us |
| --- | --- | --- |
| Small, quiet captions low in the frame | One line, white, medium-weight sans, ≈ 48px at y ≈ 1340, no box | **Slower:** 2–4 word chunks, min 800 ms instead of single words at 300 ms; and placed where each shot has room, not at a fixed height |
| Captions soften into focus | Each word fades in over ~3 frames with a slight blur and scale-up | Same feel as Soft Focus In (140 ms), applied per chunk |
| Mixed-font titles | Sans title lines with one word in a serif italic ("*Claude* може робити", "*закономірності*") | Onest 700 display + Playfair Italic accent line, left-aligned and straight (the reference centres them; our system forbids centred display and tilted text) |
| Titles replace captions | When a title is on, captions disappear | Same rule (1.2) |
| Title builds as she speaks | Words add one at a time | Line by line, not word by word |
| Cut-zoom jump cuts | Alternating framing hides every jump cut | 100% / 110%, max 2 per 10 s |
| UI shown as small cards above her head | Screenshots and app panels at the top third with a tiny label above ("settings → connectors → add") | As photo cards (radius 0, no frame, straight, `shadow-lift`) with a `section-label` above. Breadcrumb arrows "→" are fine in labels |
| B&W punchline moment | Hard cut to black and white with one big serif italic word ("Нет") | L5 beat moment, max 1 per reel |
| CTA with keyword | Small caps lead-in + big serif italic keyword ("телеграм") | Same, but lowercase lead-in |

| Don't copy | Why |
| --- | --- |
| Word-by-word captions at 300 ms | Tetiana dislikes the fast switching |
| Centred bold titles | Design system: display is always left-aligned |
| UPPERCASE lead-in ("ПИШИТЕ В КОММЕНТАРИЯХ") | Design system: no caps |
| Rounded white UI cards with shadows | Design system: radius 0, no white frames; a shadow only on one raised photo card |
| The "x2" circle badge in the top right | Unclear meaning, extra element |
| Gap-free delivery (no pauses at all) | Slightly breathless; we keep 150–250 ms between sentences |
| Warm, soft colour look | No grade: her own iPhone colour (section 12) |

### 13.2 Earlier test edit (IMG_6777_edit_v1)

Keep: soft blur dissolves, gentle zoom steps, frosted pills, the "Claude працює…" status pill with its pulsing dot and animated dots (Tetiana's favourite, now section 6.5 with a pink dot), one accent, restraint. Drop: Manrope, Cormorant Garamond, mint #9BE7B0, uppercase labels, dark bottom gradient, word-by-word light-up, the warm grade.

### 13.3 Where to find more references

For the professional, animated, pop-up feel Tetiana likes. Save the ones she likes into `04 Resources/Motion references` in the vault with one line on what to copy, then add them to 13.1's table format here.

| Where | What to look for |
| --- | --- |
| Product launch videos by software companies (Apple keynotes and product pages, Linear, Raycast, Arc, Notion, Framer, Figma Config) | UI pop-ups, status states, soft blur transitions, sound design on clicks |
| Savee and Pinterest | Search "ui motion", "kinetic typography minimal", "editorial motion design", "app launch video" |
| Dribbble and Behance (Motion / Animation filters) | Status pills, loaders, notification pop-ups, card reveals |
| LottieFiles | Ready animated loaders and status icons to study the timing |
| Remotion Showcase (remotion.dev/showcase) | Videos made with the same tool we use, so anything there is buildable |
| Screen Studio videos | How smooth, auto-zoomed screen recordings look in tutorials |
| Instagram and TikTok search | "AI tools tutorial", "productivity app review", "ui animation", "motion designer reel"; save reels into a "style" collection and send them over |

When sending a reference, a 3–10 s screen recording plus one line ("I like how the card pops in") is enough.

---

## 14. Do / don't

| Do | Don't |
| --- | --- |
| Onest + Playfair Display Italic only | Any other font, Inter/Roboto/Arial even as fallback |
| lowercase captions and titles | ALL CAPS, underlines, emoji |
| 2–4 word caption chunks, ≥ 800 ms | Word-by-word, karaoke colour fills, bouncing words |
| One keyword in Playfair Italic, same colour | Pink, yellow or boxed keywords |
| Captions on empty space, in white, porcelain or ink matched to the shot | Text strokes, drop shadows, black boxes behind text, captions on her face |
| Everything straight: titles, accent lines, cards | Tilted or rotated text or cards |
| Cut-zoom on jump cuts, 100% ↔ 110% | Whip zooms, shakes, spins, glitch, RGB split, flash frames |
| One glass element and one glow at a time | Glass and glow on every screen |
| Screenshots as plain photo cards (radius 0, no frame) | Device mockups, polaroids, tape, white frames, rounded cards, floating 3D icons |
| Soft pop, click and whoosh mapped to events | A sound on every word or zoom; music baked into the file |
| Status pill while something is in progress, then the result pops in | Loading spinners, full-width progress bars, countdowns |
| Her own iPhone colour, no grade | Any grade or LUT, teal-orange looks, heavy contrast, beauty filters |
| Something visibly changes every 3–5 s | 6+ s with no visual change; or changes under 1.5 s apart |
| Left-aligned display titles at x 68 | Centred display titles, more than 2 display lines |
| Paper #F6F5F1, or Ink #151413 for a whole reel, for any full background | Coloured backgrounds, pure black, mixing Paper and Ink in one reel, blurred-video fill backgrounds |

---

## 15. Per-video brief template

Copy into `02 Scripts/<video>.md` in the Obsidian vault.

```markdown
# <working title>

| Field | Answer |
| --- | --- |
| Reel type | talking-head tip / tutorial with screen recording / story |
| Language | uk / en |
| Theme for paper layouts | paper / ink |
| Audience | who exactly (e.g. "creators who post carousels and hate Canva") |
| Hook (spoken, first sentence) | |
| Hook title (display, max 2 × 14 chars) | |
| Accent line (max 22 chars) | |
| Key points (max 3, one line each) | 1. 2. 3. |
| Visuals to show (screenshots, recordings, B-roll) + timestamps or file names | |
| Keywords to highlight (optional) | |
| Beat moment (optional, 1 word) | |
| Target length | 30 / 45 / 60 s |
| CTA (what the viewer does at the end) | e.g. comment «промпт» |
| Platforms | Reels / TikTok / Stories / LinkedIn |
| Footage files | |
```

---

## 16. Edit-in-rounds checklist

Work in `Claude/videos/<video>/`. Wait for Tetiana's go-ahead before touching the folder. Each round ends with a render or file she reviews; don't start the next round without her OK.

### Round 0: build the sound kit (once, before the first edit)

- [ ] In `Claude/video-tools/remotion`: `npx remotion add @remotion/sfx`; create `public/sfx/`.
- [ ] Download the 6 Remotion sounds in 7.2 into `public/sfx/` under the kit names.
- [ ] If `ELEVENLABS_API_KEY` is set (skill: `npx skills add elevenlabs/skills`), generate `pop-soft`, `air-soft`, `keys-soft` (and `ding-soft` if Remotion's ding is too bright) with the prompts in 7.2, 4 candidates each. If there is no key, use the ffmpeg fallbacks and tell Tetiana which sounds are fallbacks.
- [ ] Process every file (7.3) and write `kit.json`.
- [ ] Render `sfx-preview.mp4`: paper background, each kit name shown in `section-label` while its sound plays, 1 s apart. Tetiana listens and approves before any reel uses the kit.

### Round 1: captions only

- [ ] Convert HDR to SDR, conform to 30 fps (section 12).
- [ ] Whisper transcript with word-level timestamps (language set from the brief, never auto-detect), model from `Claude/video-tools/whisper-models`.
- [ ] Fix spelling; keep English words in English spelling; lowercase (brand names excepted).
- [ ] Chunk into 2–4 words, ≤ 24 chars, ≥ 800 ms (section 1.2). Mark keywords (section 1.3). Pick the caption position (section 3.3) and colour per shot.
- [ ] Deliver `captions.json` + `captions.srt` and a readable list of chunks with times.

### Round 2: cut dead air

- [ ] Trim pauses > 400 ms to 200 ms; keep last takes; remove repeats and fillers (section 8).
- [ ] 2-frame handles, 30 ms audio crossfades.
- [ ] Re-time captions to the new cut.
- [ ] Deliver `cut_v1.mp4` (no graphics) + `edl.txt` listing every removed range and which take was kept.

### Round 3: first 15 s for review

- [ ] HDR → SDR conversion (no grade), hook title, captions, cut-zooms, layouts, sound for 0–15 s only (Remotion).
- [ ] Check safe zones with an overlay of the Reels/TikTok UI.
- [ ] Deliver `preview_15s.mp4`. Tetiana approves or lists changes.

### Round 4: full edit

- [ ] Apply everything to the whole reel: photo cards, pills, status pills, beat moment, CTA, SFX, room tone (sections 3–11). No music.
- [ ] QA: fonts loaded (no fallback), captions never under 800 ms, caption position and colour fixed per shot with contrast ≥ 4.5:1, no text on her face, hands or busy detail, at least 4 interest triggers (8.1), max 1 glass + 1 glow on screen, nothing tilted, no text in unsafe bands, max 2 zooms / 10 s, visual change every 3–5 s, -14 LUFS / -1 dBTP, no black first frame, loop point checked.
- [ ] Export 1080×1920, 30 fps, H.264 High, 16–20 Mbps, AAC 48 kHz 320 kbps → `<video>_final.mp4`; plus a cover frame `<video>_cover.png` (1080×1920, hook title visible, key content inside the centre 1080×1440).

---

## Decisions log

| Date | Decision |
| --- | --- |
| 2026-10-05 | Captions sit directly on video in empty space; colour white, porcelain or ink, matched to the picture's warmth and brightness |
| 2026-10-05 | Hook templates are topic-agnostic formulas; she talks about general topics |
| 2026-10-05 | No music in the file; soft popular SFX only (click, whoosh, pop) |
| 2026-10-05 | Brand names keep their own spelling (Claude decided); everything else lowercase |
| 2026-10-05 | Add the status pill and pop-ups she liked in the test edit; add interest triggers expressed as motion design |
| 2026-10-05 | Ending default: comment-keyword CTA with a seamless loop; paper end card optional |
| 2026-10-05 | Text sizes +20% (caption 58px, keyword 67px, pill 31px, label 48px, meta 36px, body 48px). Display title, accent line and beat word unchanged, already large |
| 2026-10-05 | No automatic caption pills; plain text in the best slot |
| 2026-10-05 | No colour grade; only HDR → SDR conversion |
| 2026-10-05 | Sound sources: `@remotion/sfx` first, ElevenLabs Sound Effects for what Remotion lacks, ffmpeg synthesis as the offline fallback; one fixed kit built in Round 0 and approved by Tetiana |
| 2026-10-06 | Synced with the design system: polaroids, white frames and tape removed (screenshots and face cards are plain photo cards with `shadow-lift`); heart icon removed; nothing is ever tilted, the accent line included |
| 2026-10-06 | Design system added a dark Ink theme; reels may use it for paper layouts (L3, end card), one theme per reel, chosen in the brief |
| 2026-10-06 | Accent line is left-aligned flush under the display as one title block (same x 68), never centred or placed like a caption |
| 2026-10-06 | No fixed text positions on footage; text goes where the shot has room |
| 2026-10-06 | This file now lives in the design system's Export group and is updated in the same change as the system |
