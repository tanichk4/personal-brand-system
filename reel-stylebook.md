# Reel Stylebook: @tanii444.ka

Version 1.0 (2026-10-06). What changed and why: see the Decisions log at the end. Built from the **Tanichka Editorial** design system, Tetiana's video editing rules, and a frame-by-frame study of her reference reel.

**Where this file lives:** the GitHub repo `tanichk4/personal-brand-system` is the source of truth. Change it here; there is no other design file to export from. When `tanichka-editorial.md` changes, this file is updated in the same change so the two never disagree.

**Who reads this:** an AI editor (Claude Code with Whisper, ffmpeg and Remotion) cutting raw iPhone footage into finished vertical reels for Instagram Reels, TikTok, Stories and LinkedIn.

**Precedence when rules conflict:** 1) Tetiana's own decisions (what she says in the chat or in her CLAUDE.md), 2) Tanichka Editorial design system, 3) this file, 4) the reference reel. The older test edit's style (Manrope, Cormorant, mint #9BE7B0) is retired. Never use it.

**Markers:** `⚑ ASSUMPTION` means a reasonable default that Tetiana hasn't confirmed yet. ★ in the quick reference marks a hard rule. The design system holds colours, type and the five signature elements (frosted glass pill, glow, text glow, blur dissolve, handle tag) plus the caption haze; video-only elements (status pill, screenshots, layouts) are defined here.

**Rules and defaults.** The short list under "Hard rules" below is always true. Everything else in this file is a good default: bend it when a shot needs it, and say what you bent in the edit notes. Numbers are starting points, not quotas; never add something to the screen only to hit a count.

### Hard rules (always true)

1. **Her footage is never moved, shrunk, cropped or covered to make room for text or graphics.** Her framing stays as she shot it; zooms are centred on her face. The one exception: the paper split (L3), only for a real screen recording.
2. **Never add a band, bar, strip, panel, paper area, scrim or box behind or around text on footage.** Text sits straight on the picture, or it isn't shown. (The soft text glow, the caption haze and the pink glow are not bands: they are allowed, sections 1.6 and 2.)
3. If text doesn't fit, in this order: make it smaller (down to the minimum sizes in section 1.1), use fewer words or drop the accent line, put it in another calm area (the lower part of the frame included), or leave it out. Captions alone are a finished reel; a title can live on the cover instead.
4. Never on her face or hands. Never in the platform safe zones (section 3.1).
5. Inter and Playfair Display Italic only. Only the colours in section 2. Nothing tilted. Nothing from the Never list (section 14).
6. No colour grade and no colour matching; only the HDR → SDR conversion (section 12). The one exception: the black-and-white beat moment (L5), max 1 per reel.
7. No music in the file. Sound effects only from the approved kit (section 7).
8. One-go edit: deliver the finished reel without stopping between rounds, unless Tetiana asks for a stop (section 16).
9. **One caption colour for the whole reel.** It never changes between shots, not even for one shot. Bright shots get the soft caption haze instead (section 1.6).

---

## 0. Quick reference

| Item | Value |
| --- | --- |
| ★ Safe zones | Margins top 250 · bottom 480 · left 68 · right 68 (160 from y 900 down): the stricter of Reels and TikTok. Every overlay stays inside (section 3.1) |
| Canvas | 1080×1920, 30 fps, H.264 High, yuv420p, Rec.709 SDR, 16–20 Mbps, AAC 48 kHz 320 kbps |
| ★ Fonts | Inter (400 / 500 / 700) and Playfair Display Italic 400. Nothing else, no fallbacks to Roboto or Arial |
| Captions | Inter 500, **58px**, lowercase, centred, **phrase chunks of 2–4 words, max 24 characters, 1 line** |
| ★ Caption colour | **One colour for the whole reel**, white #FFFFFF by default (porcelain #F6F5F1 or ink #111111 only if they suit every shot). Never changes mid-reel. Bright shots get the soft caption haze (section 1.6) |
| Caption timing | Min 800 ms on screen, target 1000–1600 ms, max 2400 ms. Soft Focus entrance (140 ms). With no hook title, captions start on frame 0 (section 1.7) |
| Text placement | **No fixed positions on footage.** Each shot, text and graphics go where the picture has room: the calmest empty area, never on her face or hands, never on busy detail (section 3.3). Platform safe zones always apply. The split layout keeps its grid |
| Caption position | Placed per shot by section 3.3. Max width 760px. Fixed for the whole shot, moves only on a cut |
| Keyword | Playfair Display Italic 400 at 115% (67px), same colour as the caption. Max 1 per chunk, 1 per 6 s |
| Hook title | **Optional**, only when the shot has room. Inter 700, 72–118px on footage (sized to the room, 118px on paper), lh 0.98, ls -0.045em, left-aligned at the 68px side margin, never centred; height chosen per shot (section 3.3). Accent line Playfair Italic at 68% of the display (80px under a 118px display, 49px under 72px), flush left 14px under it, straight (never rotated) |
| ★ Colours | paper #F6F5F1 · ink #111111 · muted #6E6A64 · white #FFFFFF (text on footage and glass) · accent-pink #F2A7C3 (pill dots and the glow only) |
| Zoom | Cut-zoom steps 100% ↔ 110%. Max 2 steps per 10 s, min 3.0 s apart. Slow push 100→103% inside a shot |
| Transitions | Hard cut inside a thought. Blur dissolve 240 ms for a new section. Blur dissolve 320 ms for a layout change |
| Easing | Entrances `cubic-bezier(0.22, 1, 0.36, 1)`, exits `cubic-bezier(0.4, 0, 1, 1)`. No springs that overshoot, no bounce |
| Restraint | Max 1 glass element (frosted pill or blur dissolve) and 1 glow on screen at once. Max 2 graphics plus the caption at once |
| Status pill | Frosted pill with a pulsing pink dot and animated dots ("Claude думає…") while something is in progress, then a soft Pop In of the result (section 6.5) |
| Pauses | Trim any pause over 400 ms down to 200 ms. Keep the last good take |
| Visual change | About every 4–6 s, mostly from cut-zooms; a strong still shot can hold longer. Never add a graphic just to change something |
| ★ Sound | **No music.** One fixed kit of soft SFX from `@remotion/sfx` + ffmpeg (pop, whoosh, click, switch, ding), max 1 per 3 s. No ElevenLabs (paid). Voice -14 LUFS integrated, -1 dBTP |
| Interest triggers | Use the ones that fit the content: open loop, status-pill anticipation, re-hook, payoff pop-up, loop ending (section 8.1) |
| ★ Look | **No grade.** Keep the colour she shot; only the HDR → SDR conversion (section 12) |
| Ending | Comment-keyword CTA over footage in the last 3–4 s, then cut 300 ms after the last word so it loops |
| Cover | 1080×1920, title and face inside the middle 1080×1440 that the profile grid shows (section 11.2) |

---

## 1. Type

All type is lowercase by default. Brand and product names keep their own spelling (Claude, Figma, iPhone, CapCut, ChatGPT). Decided: a capitalised brand name is recognised at a glance and stands out as the one capital in a lowercase line, which works like a free highlight. Everything else stays lowercase.

Nothing is ever rotated or tilted: no tilted titles, accent lines, keywords or cards.

### 1.1 Roles

| Role | Font | Size | Weight | Line height | Letter spacing | Colour | Why |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `reel-caption` | Inter | 58px (down to 48px only when a shot has no room) | 500 | 1.2 | -0.01em | One per reel: #FFFFFF, #F6F5F1 or #111111 (section 1.2) | Tetiana found 48px too small (2026-10-05) and asked for +20%; 500 is the heaviest weight the system allows outside the display |
| `reel-caption-keyword` | Playfair Display Italic | 67px (115%) | 400 | 1 | 0 | same as its caption | The system's `highlight` rule, applied to captions |
| `display` (hook title, section title) | Inter | 118px on paper; 72–118px on footage, the largest that fits the shot's calm area | 700 | 0.98 | -0.045em | #FFFFFF on footage, #111111 on paper | The system's display; the only bold |
| `accent-line` | Playfair Display Italic | 68% of the display (80px under 118px, 49px under 72px) | 400 | 1.1 | 0 | same as display | The title's last line: straight, left-aligned at x 68 under the display. Scales with the display so it is never bigger than the title |
| `beat-word` | Playfair Display Italic | 160px | 400 | 1 | 0 | #FFFFFF | One-word punchline moment (L5, section 3.2). Built on the accent line, scaled up |
| `section-label` | Inter | 48px | 400 | 1 | -0.01em | #FFFFFF on footage, #111111 on paper | Names the content below it |
| `meta` | Inter | 36px | 400 | 1 | 0 | #FFFFFF on footage, #111111 / #6E6A64 on paper | Handle, step index, small CTA lead-in |
| `pill` | Inter | 31px | 500 | 1 | -0.01em | #FFFFFF | Text inside a frosted pill or the status pill (+20% on the design system's 26px) |

Load in Remotion with `@remotion/google-fonts/Inter` (weights 400, 500, 700, subsets `latin`, `cyrillic`) and `@remotion/google-fonts/PlayfairDisplay` (italic 400, subsets `latin`, `cyrillic`). Block the render until both are loaded (`delayRender`).

### 1.2 Captions

| Rule | Value | Why |
| --- | --- | --- |
| Words on screen | 2–4 words per chunk; a single word only if it is ≥ 10 characters or the whole sentence | Tetiana wants phrase captions, not word-by-word |
| Characters | Max 24 per chunk, including spaces | Keeps one line inside the 760px width at 58px (measured with Onest: typical 24-char Ukrainian lines are 670–730px; re-check with Inter on the first reel) |
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
| Colour | **One colour for the whole reel**, chosen once before placing captions: white #FFFFFF by default. Porcelain #F6F5F1 (white's warm twin) only if every shot is warm; ink #111111 only if white would need haze level 2 in more than half the reel and ink passes the check on every shot (e.g. the whole reel is in front of a white wall). How to pick and check: section 1.6 | Tetiana: a colour that flips for one shot (white → black → white) looks rough. Pro editors keep one caption style for a whole video |
| Colour stability | Never changes between shots, not even for one shot. Readability on a bright shot comes from the caption haze, a calmer area or smaller text, never from a new colour | No flicker |
| Stroke / glow | No stroke, no hard drop shadow, no box. Captions get the soft caption haze when a shot needs it (section 1.6); the caption keyword also gets the soft text glow (section 2) | The haze is for reading; the glow stays special |
| Last resort | If a shot stays under 3:1 even with haze level 2 in every calm area: keep the reel's colour, use haze level 2 in the best area, and list the shot in the edit notes. Never switch colour. **Never put captions in a pill automatically** | Tetiana rejected pills on every caption (2026-10-05). A pill behind a caption only by hand, for one hard shot, if she asks |
| When hidden | While a hook title, section title, beat word or CTA line is on screen, and during full-screen paper layouts that show the same words | The reference does this: one text voice at a time |

### 1.3 Keyword highlight

| Rule | Value | Why |
| --- | --- | --- |
| Style | Playfair Display Italic 400, 115% of the caption (67px), same colour, with the soft text glow (section 2). Never pink, never underlined, never a box | Design system `highlight` |
| How many | At most 1 per chunk and 1 every 6 s | Keeps it a seasoning |
| Which word | In this order: 1) the result or number ("за 5 хвилин", "x2"), 2) the tool or thing being named (Claude, Figma), 3) the contrast word in a "not X but Y" line, 4) the emotional word that carries the point ("красиво", "легко") | Highlights the word you'd stress when speaking |
| Never | Function words (і, в, на, the, a, to), the first word of the reel, two keywords in a row | |

### 1.4 Hook title and section titles

| Rule | Value | Why |
| --- | --- | --- |
| Style | `display` (Inter 700, 72–118px on footage, 118px on paper) + optional `accent-line` (Playfair Italic at 68% of the display, straight), both with the soft text glow (section 2) | The system's Headline |
| Alignment | Left edge at the 68px side margin (x 68). Never centred | Design system: never centre the display |
| When | Optional. Use it when a shot has a calm area big enough for it; otherwise skip it (the hook can be spoken, with captions) or put the title on the cover | A title must never force a band or a reframe |
| Position | No fixed height. The whole block (display + accent line) goes in the calmest empty area of the shot that fits it at x 68 (section 3.3), upper or lower part of the frame; accent line 14px below the display, flush left at the same x 68. Keep it inside the middle 3:4 area the profile grid shows (y 240–1680) when possible | Text goes where the shot has room, inside the safe zones |
| One title block | Display + accent line are one object: same left edge, built, placed and removed together (Soft Focus Title / Title Out). The accent line is never centred, never moved right or down, never placed in an area of its own, and never treated as a caption by caption detection, placement or Chunk Swap | It must read as part of the title, not as a separate caption |
| Length | Display: max 2 lines, max 14 characters per line. Accent line: max 22 characters | Readable in under 1 s |
| Build | Each line appears when she says it (line by line, not word by word), with Soft Focus Title (section 5) | Keeps the reference's build-up feeling without word-by-word switching |
| Duration | On for 2.5–4.0 s, exit with Soft Focus Out | |
| Where | Hook (0–3 s) and each new section of a tutorial (max 3 per reel); each one only if the shot has room. The CTA has its own block (section 11.1) | |

### 1.5 Accent font use (Playfair Display Italic)

Only for: the caption keyword, the accent line under a display title, the beat word, and the CTA keyword. Never a whole caption, never a paragraph.

### 1.6 Caption readability: one colour + soft haze

How pro editors solve this: Netflix, the BBC and most social captions keep one text colour for the whole video and get readability from a box, an outline or a shadow behind the letters. Switching the text colour per shot is not the usual practice: the flip pulls the eye away from her face. Hard rule 2 rules out the box and her style rules out outlines, so the tool here is the **caption haze**: a soft, wide, dark blur behind the letters, with no offset and no edges. It darkens the picture just around the words and reads as depth, not as a shape.

| Level | When (contrast without haze) | White or porcelain captions | Ink captions |
| --- | --- | --- | --- |
| 0 | ≥ 4.5:1 | none | none |
| 1 | 3:1 to 4.5:1 | `text-shadow: 0 0 14px rgba(17,17,17,0.40), 0 0 36px rgba(17,17,17,0.22)` | `0 0 14px rgba(246,245,241,0.45), 0 0 36px rgba(246,245,241,0.25)` |
| 2 | under 3:1 | `0 0 10px rgba(17,17,17,0.55), 0 0 28px rgba(17,17,17,0.35), 0 0 56px rgba(17,17,17,0.18)` | `0 0 10px rgba(246,245,241,0.60), 0 0 28px rgba(246,245,241,0.38), 0 0 56px rgba(246,245,241,0.20)` |

| Rule | Value |
| --- | --- |
| Never a shape | No edge, no offset, no rounded corners: on a still frame you can't tell where the haze ends. If you can, it is too strong |
| Changes | The level is chosen per shot. It changes only at a cut, together with the Chunk Swap (140 ms fade), so it never pops on or off mid-phrase |
| Keyword | Haze underneath, the soft text glow on top |
| Also for | Titles, beat word, CTA and pill-less labels over footage: they keep their colour and get the same haze when a shot is bright |

**Contrast check** (run for every shot after placing the caption, on the SDR render, i.e. what the viewer sees):

1. Take every 2nd frame of the shot. In each, crop the caption's real box: the text's width × 90px, plus 16px padding.
2. Turn the pixels into relative luminance (the WCAG sRGB formula).
3. Take the **brightest 10% of pixels** in the box for white or porcelain captions (the darkest 10% for ink). An average hides the bright window or white shirt that eats the letters.
4. The **worst frame** of the shot decides. Contrast = (lighter + 0.05) / (darker + 0.05).
5. With haze, recompute with the background darkened by 40% (level 1) or 60% (level 2); lightened by the same for ink.
6. If the box is busy (edge density over 8% with a Sobel filter, or visible motion), treat the result as one level worse.
7. Decide: ≥ 4.5:1 → level 0. 3:1 to 4.5:1 → level 1. Under 3:1 → first try the next calm area; if none passes, level 2. (58px is "large text", where 3:1 is the readable minimum; 4.5:1 is our target.)
8. Write a one-line contrast report per shot in the edit notes: shot, area, worst contrast, haze level.

**Picking the reel's colour:** run steps 1–4 for white on every shot. Stay with white unless white needs level 2 in more than half the reel and ink passes at level 0–1 on every shot.

### 1.7 Captions in the first 3 seconds

Most viewers decide in the first 1–3 s, and many watch with the sound off. So when there is no hook title, the captions are the hook.

| Rule | Value |
| --- | --- |
| Start | With no hook title, captions start on frame 0; the first chunk is fully visible by frame 3 (100 ms) |
| Say the point first | The first chunk carries the promise, the result or who it's for, never context ("привіт", "отже", "so today"). If her first words are context, cut them (section 8) so the first caption is the hook |
| Read as one hook | The captions in the first 3 s together read as a complete hook of about 5–10 words: what you get, or who it's for, plus a reason to stay |
| One keyword | Highlight the strongest word of the hook (the number, result or tool) in Playfair Italic with the text glow; not the very first word (section 1.3) |
| Place near her eyes | The first captions go in a calm area close to her eye line (above or beside her head when there is room), inside the middle 3:4 area (y 240–1680), so one look takes in her face and the words |
| Calm screen | Nothing else animates in the first 3 s except the slow push, the caption swaps and, if used, the handle tag; no pill or pop-up competes with the hook |

---

## 2. Colour

Every value comes from the design system tokens.

| Element | Colour | Token | Why |
| --- | --- | --- | --- |
| Captions over footage | One per reel: #FFFFFF (default), #F6F5F1 or #111111 (section 1.2) | `on-glass` / `paper` / `ink` | One steady colour; bright shots get the caption haze |
| Titles, labels, CTA over footage | #FFFFFF, with the caption haze when a shot is bright (section 1.6) | `on-glass` | Same steady colour as the captions |
| Keyword in captions | same as its caption | — | `highlight`: same colour |
| Status pill progress line | track rgba(255,255,255,0.18), fill rgba(255,255,255,0.85), 3px | `on-glass` at opacity | Stays inside the pill's white-on-glass palette; pink stays for the dot |
| Paper background (split layout) | #F6F5F1 | `paper` | The only background colour in the Paper theme |
| Ink theme (split layout only) | ground #151413, text #F3F1EC, secondary #9E9890; pink, glass and photos unchanged | `paper` / `ink` / `muted` in Ink (`data-theme="ink"`) | The design system's dark theme. Pick one theme per reel in the brief and use it for every split layout (L3); never mix. Text over footage is unaffected ⚑ ASSUMPTION |
| Text and lines on paper | #111111 (Ink theme: #F3F1EC) | `ink` | |
| Secondary notes on paper (e.g. "source:") | #6E6A64 | `muted` | Captions/secondary only |
| Dot in pills | #F2A7C3 | `accent-pink` | The one accent; never text, never a fill |
| Frosted pill fill | linear 180°: rgba(34,34,36,0.52) → rgba(14,14,16,0.60) | `glass-dark-*` | Smoky see-through glass |
| Frosted pill rim | 1px, rgba(255,255,255,0.30) at corners → rgba(255,255,255,0.10) on long sides | `glass-border*` | |
| Glow | radial, #F2A7C3B3 → transparent at 68%, about 540px wide | `glow-strong` | One soft pink glow behind the focal point; it may sit behind a title or the CTA |
| Text glow | white text: `text-shadow: 0 0 6px rgba(255,255,255,0.35), 0 0 18px rgba(255,255,255,0.18), 0 0 40px rgba(242,167,195,0.14)`; ink text on paper: `0 0 24px rgba(242,167,195,0.22)` | `text-glow` | A light bloom with a hint of pink halation, so accent text feels softly lit, a little wet, never flat. On accent text only: display title, accent line, caption keyword, pill text, beat word, CTA keyword. Never on every word or on regular captions |
| Caption haze | #111111 at 18–55% (light #F6F5F1 version for ink captions), blurred, no offset | `text-haze-1` / `text-haze-2` | Readability on bright shots without a box (section 1.6) |
| Section / layout dissolve tint | rgba(246,245,241,0.30) → 0 | `paper-tint` → `paper-clear` | The blur dissolve's tint |

Not allowed: any other colour, coloured backgrounds, pink text, mint, neon, any gradient or shadow other than the pill fill, the glow, the text glow, the caption haze and the dissolve tint above.

---

## 3. Layout

### 3.1 Canvas and safe zones

One safe zone for every vertical video, built from the stricter edge of Instagram Reels and TikTok (Stories fits inside it too). The apps cover these edges with their own buttons, captions and tabs, so text, titles, pills and key graphics stay inside the safe area. Her footage itself still fills the whole frame; only overlays keep to the margins.

| Edge | Margin on 1080×1920 | What covers it | Reels / TikTok on their own (approx.) |
| --- | --- | --- | --- |
| Top | 250px | App header, tabs ("Reels", "Following / For You"), search, Stories progress bar | Reels ~220px · TikTok ~200px |
| Bottom | 480px | Username, caption, audio row, nav bar | Reels ~420px · TikTok ~480px |
| Right | 160px from y 900 down (68px above it) | Like, comment, share, save, profile buttons | Reels ~140px · TikTok ~160px |
| Left | 68px (`margin-side`) | Edge of the phone | Reels ~60px · TikTok ~60px |

- **Safe area:** x 68–1012 above y 900; x 68–920 from y 900 down; y 250–1440. When one simple rectangle is easier, use x 68–920, y 250–1440 (852×1190).
- Apps change their layouts now and then, so these margins keep a little extra room on purpose. Check new UI against them about once a year, on a real phone, with a long post caption: Instagram's caption grows upwards when expanded, and some 2026 guides use a bottom margin of up to ~670px.
- **Profile grid:** since January 2025 the Instagram grid shows reels cropped to 3:4, the middle 1080×1440 (y 240–1680). Keep the hook title and key text inside that area when possible; the cover must be (section 11.2).
- LinkedIn covers the edges with its own buttons; the safe area above covers them.
- Canvas: 1080×1920, 30 fps (convert 24/60 fps footage to 30).

For code (Remotion or any renderer), use these as the margins of every overlay layer:

```ts
// reel-safe-zones: stricter of Instagram Reels and TikTok, 1080×1920
export const CANVAS = {width: 1080, height: 1920};
export const SAFE = {
  top: 250,
  bottom: 480,          // safe area ends at y 1440
  left: 68,
  right: 68,            // above y 900
  rightLower: 160,      // from y 900 down (like/comment/share buttons)
  rightLowerFromY: 900,
};
// One-rectangle version: x 68–920, y 250–1440
export const SAFE_BOX = {x: 68, y: 250, width: 852, height: 1190};
```

In Remotion, wrap every text and graphic layer in an `AbsoluteFill` with `padding: '250px 160px 480px 68px'` (or the two-step right margin above), and render a QA preview with a semi-transparent overlay of these bands (section 16).

### 3.2 Layouts

Positions for text and graphics on footage in this table are examples of a good spot, not rules: on footage, section 3.3 decides each shot. Paper areas (L3's top half) keep their grid, since there is no footage to avoid there.

| Code | Name | Composition | Use when |
| --- | --- | --- | --- |
| L1 | Full face | Footage fills 1080×1920, framed as she shot it | Default for talking-head speech |
| L2 | Screenshot over footage | Footage full frame; one screenshot (or result, or photo) shown plain: sharp corners, no frame, no shadow, straight, max 760×560, placed by section 3.3 (e.g. above her head when that area is empty); never over her face or hands | She mentions something visual for 1.5–6 s: an app, a result, a before/after |
| L3 | Paper split | Top 0–1000: paper #F6F5F1, optional step number `[2]` in `meta` at x 68, y 260; screen recording (sharp corners, no shadow) at x 68–1012, y 320–980. Bottom 1000–1920: footage, cropped so her face centres at y 1300 (the one allowed exception to Hard rule 1) | **Only** when there is a real screen recording or UI to show for more than 6 s. Never as a fallback, never to make room for text, never with an empty or text-only paper half |
| L4 | Full screen recording | Screen recording fills the frame (or sits on paper, x 68–1012); her voice carries it | Long screen walk-through where her face isn't needed |
| L5 | Beat moment | Footage in black and white (saturation 0; the one allowed exception to Hard rule 6), beat word in the calmest empty area of the shot (e.g. lower middle), never on her face | One punchline or "no" moment per reel, 600–1200 ms |
| L6 | CTA over footage | Footage full frame; `meta` lead-in with the `accent-line`-style keyword under it, as one block placed by section 3.3 (e.g. upper third when it is empty) (section 11) | Last 3–4 s |

| Switch rule | Value | Why |
| --- | --- | --- |
| Min time in a layout | 2.0 s (L5 excepted) | Prevents choppy jumping |
| Max layout changes | 1 per 6 s | Calm pacing |
| Transition between layouts | Blur Dissolve, 320 ms (section 5) | |
| Horizontal footage, talking head | Crop to 9:16 centred on her face. If the source is under 1080px tall after the crop, keep it full frame anyway and accept it a little softer; never switch to L3 for this | A paper band is worse than a slightly soft picture |
| Horizontal footage, screen or scenery | Place it on paper (L3) or as a plain screenshot (L2). Never stretch, never blurred-copy background | Blurred-fill backgrounds look cheap |

### 3.3 Text placement on footage

There are no fixed positions for text or graphics on footage. For each shot, text goes where the picture has room. The picture is never changed to make room: no moving, shrinking or reframing her, and no band, bar, panel, paper strip, gradient or box behind text (Hard rules 1–3).

| Rule | Value | Why |
| --- | --- | --- |
| Where | The calmest empty area of the shot: never on her face or hands, never on busy detail (edge density over 8% of pixels with a Sobel filter, or visible movement), with room for the whole element's box | Text sits on empty space and never covers her |
| How to choose | Analyse every frame of the shot (between two cuts). Mask her face and hands with a 40px margin plus the safe zones below, then pick the free area with the least detail and motion that fits the box for the whole shot | A spot that is empty in one frame can be covered a second later |
| Stability | Chosen once per shot; it never moves mid-shot and may change only on a cut | Moving text looks nervous |
| Several elements | Place the most important first (title or CTA, then a screenshot, then a pill, then the caption), each in its own calm area, at least 40px apart, never overlapping. One text voice at a time still applies (section 1.2) | |
| Alignment | The display title block always has its left edge at the 68px side margin (never centred); only its height changes. Other elements are centred in their area | Design system: display left-aligned |
| Contrast | After choosing, run the contrast check (section 1.6): ≥ 4.5:1 plain, or with the caption haze; if a shot is under 3:1, try the next calmest area first | |
| No room | If no area fits, in this order: 1) make it smaller (display down to 72px, caption down to 48px), 2) fewer words, or drop the accent line, 3) another calm area, lower part included, 4) leave it out (pill, handle tag, even the title; captions alone are fine). Never add a band or box, never move her, never fall back to her face or hands | The white-band edit on IMG_6777 came from forcing a title in |
| Safe zones | Always inside the safe area of section 3.1: no text in the top 250px, the bottom 480px, or right of x 920 from y 900 down. In code, use the `SAFE` margins | The apps' own buttons and captions cover those |
| Paper layouts | Split screen (L3's paper half) keeps its grid; there is no footage to avoid there | |

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
| Card Drop | Screenshots (L2) | y +40→0, opacity 0→1. No rotation | 360 ms | ease-enter | Slide Up + Fade |
| Card Lift | Screenshot exit | y 0→-24, opacity 1→0 | 220 ms | ease-exit | — |
| Pill Rise | Frosted pill | y +24→0, opacity 0→1, backdrop blur 0→24px | 260 ms | ease-enter | Slide Up |
| Blur Dissolve (section) | Cut between sections | outgoing: blur 0→16px + opacity 1→0; incoming: scale 1.04→1, blur 16→0px; paper tint 0.30 peak at midpoint | 240 ms | ease-move | Blur (transition) |
| Blur Dissolve (layout) | Layout changes | same as above | 320 ms | ease-move | Blur |
| Pop In | Pop-ups: result screenshot after a status pill, fact pill | scale 0.90→1.02→1.00, opacity 0→1, blur 6→0px. Remotion: `spring({fps, config: {damping: 18, stiffness: 170, mass: 1}})` mapped to scale 0.90→1 (≈ 2% overshoot); check it never exceeds 1.025 | 320 ms | spring | Pop / Zoom In |
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
| Step number | `[2]` in `meta` | L3 paper half, top left | 1 |
| Handle tag | `@tanii444.ka` in `meta`, #FFFFFF on footage / #111111 on paper | On footage: by section 3.3, in any calm area; Shown 0.6–3.0 s in the hook only | 1 |
| Screenshot | Shown plain: sharp corners, no frame, no shadow, never tilted | By section 3.3 (L2 in section 3.2 is an example) | 1 on screen (2 only as a before/after pair, side by side with a 14px gap) |
| Frosted pill | Section 6.4 | On footage only, by section 3.3: its own calm area near what it describes, never touching the caption | 1 glass element per screen |
| Glow | `glow-strong` (section 2), soft pink, behind one focal point: the CTA keyword or the payoff result | Centred on what it lights, never on her face | 1 at a time, max 2 per reel |
| Status pill | Section 6.5 | By section 3.3: a calm area with room below or beside it for the result | 1; counts as the glass element |

### 6.2 Not allowed

Everything in the Never list (section 14). Progress is shown only inside the status pill (6.5) or with the step number `[1]`, `[2]`, `[3]`.

### 6.3 Screen recordings

| Rule | Value |
| --- | --- |
| Capture | Native resolution, 30 fps, cursor visible, light mode, notifications off |
| Crop | Crop to the region that matters; text in the UI must render ≥ 22px tall on the 1080 canvas, else zoom the recording (Ken Burns 100→115% over the shot, `ease-move`) |
| Frame | No device mockups. On paper (L3) or over footage (L2), shown plain: sharp corners, no shadow |

### 6.4 Frosted pill on video

Design system frosted glass pill: fill `glass-dark` (section 2), backdrop blur 24px + saturate 120%, fully rounded, 1px gradient rim, inner top highlight, `shadow-pill` (0 10px 26px rgba(17,17,17,0.24)), pink dot 0.32em with its glow. Proportions in em: height ≈ 2.8em, padding 0.9em 1.55em 0.9em 0.95em, gap 0.72em.

| Use | Text size | Content |
| --- | --- | --- |
| Fact pill | 31px (`pill`) | 2–4 words stating one fact: "6 категорій поз", "за 5 хвилин" |
| Caption in a pill | 58px (`reel-caption`), dot omitted | Only by hand, when Tetiana asks for it on a shot (never automatic, section 1.2) |

### 6.5 Status pill

The "work in progress" pill from the earlier test edit, which Tetiana liked, built on the design system's frosted glass pill. Use it whenever something is happening that the viewer waits for: Claude thinking, an app generating, a render, an upload, a search.

| Part | Spec |
| --- | --- |
| Shell | Frosted pill (6.4): same fill, blur, rim and shadow, fully rounded, height 2.8em at 31px text (≈ 87px) |
| Dot | `accent-pink` #F2A7C3, 0.32em, own glow, Status Pulse |
| Text | `pill` style (Inter 500, 31px, #FFFFFF, soft text glow), lowercase except brand names, max 26 characters, then Thinking Dots. Examples: "Claude думає", "збирає дизайн", "шукає референси", "готово" |
| Progress line (optional) | 3px line inside the pill, 0.95em from the left, 1.55em from the right, 10px above the bottom edge; track rgba(255,255,255,0.18), fill rgba(255,255,255,0.85), radius 999px. Fills with `ease-move` across the whole status sequence, never resets |
| Position | No fixed spot: placed by section 3.3 in a calm empty area of the shot; its pop-up result lands in the next calm area beside or below it, never over her face or hands |
| Sequence | 1) Pill Rise as she starts the action ("я питаю Claude…"). 2) 1–3 status texts, each on screen ≥ 1200 ms, changed with Status Swap. 3) Status Done ("готово" + check) for 600 ms. 4) Pill Rise reversed (180 ms), and 80 ms later the result pops up with Pop In (a plain screenshot) |
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
| 2 | **ffmpeg synthesis** (works offline, no account) | Recipe in Appendix A, tested | Sounds Remotion doesn't have: the soft pop |

No ElevenLabs or any other paid sound service (Tetiana's decision, 2026-10-06).

Never use from `@remotion/sfx`: `whip` and every meme sound (`bruh`, `vineBoom`, `windowsXpError`, `fah`, `spongebobFail`, `omgHellNah`, `priceIsRightFail`, `romanceMeme`, `boneCrack`, `animeWow`, `yippee`, `loadingLag`, `wilhelmScream`, `macQuack`, `skedaddle`, `snapchatNotification`, `nellyAhh`, `sanctuaryGuardianWhat`, `minecraftHurt`, `ohMyGodVine`, `illuminatiConfirmed`, `dramaticBoomer`, `triggered`, `recordScratch`). They're the cheap "dopamine" style.

### 7.2 The kit (event → sound)

Kit files live in `Claude/video-tools/remotion/public/sfx/` (Remotion loads them with `staticFile('sfx/<name>.wav')`). That folder is created once when the kit is built (Appendix A). Remotion volume = 10^((target peak + 3) / 20), because every kit file is normalised to a -3 dB peak.

| Kit file | Event | Source | Treatment | Target peak | Remotion `volume` |
| --- | --- | --- | --- | --- | --- |
| `pop-soft.wav` | Pop-up appears (Pop In: result screenshot, fact pill) | ffmpeg synthesis (recipe in Appendix A) | low-pass 3.5 kHz | -22 dBFS | 0.11 |
| `whoosh-soft.wav` | Layout change, section change (Blur Dissolve) | `@remotion/sfx` `whoosh` (https://remotion.media/whoosh.wav) | low-pass 6 kHz, trim to 300–400 ms | -24 dBFS | 0.09 |
| `switch-soft.wav` | Status Swap (status pill text changes) | `@remotion/sfx` `uiSwitch` (https://remotion.media/switch.wav) | low-pass 6 kHz | -26 dBFS | 0.07 |
| `click-soft.wav` | UI click in a screen recording (only clicks that change the screen) | `@remotion/sfx` `mouseClick` (https://remotion.media/mouse-click.wav) | none | -24 dBFS | 0.09 |
| `page-soft.wav` | Tutorial step change (`[1]` → `[2]`) | `@remotion/sfx` `pageTurn` (https://remotion.media/page-turn.wav) | low-pass 7 kHz, trim to ≤ 500 ms | -26 dBFS | 0.07 |
| `ding-soft.wav` | Status Done, payoff (max 2 per reel) | `@remotion/sfx` `ding` (https://remotion.media/ding.wav) | low-pass 5 kHz | -24 dBFS | 0.09 |
| `shutter-soft.wav` | Screenshot first shown (max 1 per reel) | `@remotion/sfx` `shutterModern` (https://remotion.media/shutter-modern.wav) | low-pass 7 kHz | -24 dBFS | 0.09 |
| `air-soft.wav` | Hook title, first line only | `whoosh-soft.wav` played at volume 0.045 (no separate file) | low-pass 5 kHz | -28 dBFS | 0.056 |
| — | Beat moment (L5) | Room tone only | — | — | — |
| — | Caption change, keyword, zoom | No sound (a sound on every word is the "dopamine" style she doesn't want) | — | — | — |

### 7.3 Rules

| Rule | Value | Why |
| --- | --- | --- |
| Music | **None in the file.** Tetiana adds audio in the app herself if she wants it; then the music sits well under her voice so every word stays clear | Her decision |
| One kit | Build the kit once (Appendix A), get Tetiana's OK, then never swap or add sounds per video. Changes go through this file | Same sounds every time = a recognisable style |
| Local copies | Download the Remotion sounds into `public/sfx/` instead of streaming the URLs at render time | Renders work offline and the kit can't change under us |
| Kit processing | For each file: trim leading silence, 3 ms fade in, 20 ms fade out, the low-pass in 7.2, mono, 48 kHz, 24-bit WAV, peak-normalised to -3 dBFS | All kit files behave the same in the mix |
| Kit manifest | `public/sfx/kit.json`: for each file its event, source (package export or ffmpeg recipe), date | Anyone can rebuild or audit the kit |
| SFX density | Max 1 per 3 s, max 12 per reel; never 2 within 400 ms | Noticeable but calm |
| SFX timing | Sound starts on the same frame as the visual event (Pop In: 1 frame before) | Sync is what makes it feel professional |
| SFX level | Target peaks in 7.2, i.e. 8–14 dB under the voice peaks | Soft, never harsh |
| Room tone | Fill every cut and every removed pause with 0.5 s of her own room tone at its natural level, crossfaded 30 ms | Without music, pure digital silence between words sounds broken |
| Voice chain | High-pass, light denoise, de-ess, gentle compression, loudness to -14 LUFS (ffmpeg chain in Appendix A) | Clean, even voice at platform loudness (the reference measures -14.4 LUFS) |
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
| Visual change | About every 4–6 s, mostly cut-zooms; a strong still shot may hold longer; never two within 1.5 s. Never add a card, title or pill only to create a change | Reference average: one framing change every 4.1 s; minimal beats busy |
| Speed | Never speed up speech. ⚑ ASSUMPTION: no 1.1× speed-ups | Keeps her voice natural |
| Target length | 30–60 s; flag any reel over 60 s | |

### 8.1 Interest triggers (motion design)

Retention devices, all built from the motion and graphics in this file. A menu, not a quota: use the ones the content earns (a loop ending and a strong spoken hook are often enough).

| Trigger | What it looks like | When | Max |
| --- | --- | --- | --- |
| Open loop | Hook shows the result for 0.8–1.2 s as a Pop In screenshot (or says it in the hook title), then it Pops Out; the full result returns at the payoff | 0–3 s | 1 |
| Anticipation | Status pill sequence (6.5): the viewer watches something "work" before the result pops up | Any time a process happens | 3 |
| Pattern interrupt | Cut-zoom, layout change, pop-up or title: something changes about every 4–6 s; a strong shot may hold longer | Throughout | (section 8) |
| Progress signal | Step index `[1]` → `[2]` → `[3]` in tutorials, or the status pill's progress line | Tutorials, processes | — |
| Re-hook | A section title with a new promise ("а тепер найцікавіше", "the best part") + whoosh, at 40–55% of the reel | Middle | 1 |
| Contrast | L5 beat moment: black and white + one big Playfair word | The surprising line | 1 |
| Payoff | Result Pop In + `ding-soft`, optionally with the glow behind it, held 2.0–3.0 s, captions hidden | Last third | 1–2 |
| Direct address | Cut to 110% framing on lines that say "ти / you" | When she addresses the viewer | — |
| Loop | Last line flows into the hook, framing matches (section 11) | End | 1 |

---

## 9. Hook (first 0–3 s)

| Time | What happens |
| --- | --- |
| Frame 0 | She is already mid-energy and speaking (cut any lead-in). Framing at 110% (tight), Full face. No black frames, no logo |
| 0–150 ms | Nothing animates yet except the slow push |
| 150 ms – 1.2 s | If the shot has room: hook title (placed by section 3.3, left edge x 68) line 1 builds (Soft Focus Title), line 2 120 ms later, accent line last. Captions hidden while the title is on |
| 0.6 – 3.0 s | Handle tag `@tanii444.ka` in `meta`, placed by section 3.3 in a calm area away from the title |
| ≈ 3.0 s | First cut-zoom to 100% on the first jump cut; Title Out; captions start. With no hook title, captions run from frame 0 (section 1.7) |

Hook title (optional) = the promise in max 2 short lines + an optional accent line. Tetiana talks about general topics, so these templates are formulas that work for any subject; fill in the brackets.

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
| 8–30 s | 2–3 points, one idea each | L1; an L2 screenshot per point if there is something to show; 1 keyword per point |
| 30–35 s | Payoff / proof | L2 result screenshot or L5 beat moment |
| last 3–4 s | CTA | L6 |

### 10.2 Tutorial with screen recording (45–60 s)

| Time | Beat | Visual |
| --- | --- | --- |
| 0–3 s | Hook: the finished result first | L2 screenshot of the result + hook title (if room) |
| 3–7 s | What you need (tool, 1 line) | L1 + fact pill |
| 7–45 s | Steps 1–3 (max 4), ≈ 8–12 s each | L3 paper split with `[1]`, `[2]`, `[3]` + section label. Stay in L3 between steps: the step number changes (with `page-soft`), the layout doesn't. Go back to L1 only for a part longer than 6 s where her face matters |
| 45–52 s | Result again | L2 or L3 |
| last 3–4 s | CTA (keyword for the prompt / link) | L6 |

### 10.3 Story (30–60 s)

| Time | Beat | Visual |
| --- | --- | --- |
| 0–3 s | Hook: the moment of tension or surprise | L1 tight (110%), hook title |
| 3–15 s | Setup: where/when/who | L1, B-roll as plain L2 inserts |
| 15–40 s | Turn: what happened, the problem | L1, max 1 L5 beat moment |
| 40–52 s | Lesson in one line | Section title (display) |
| last 3–4 s | CTA | L6 |

---

## 11. Ending and cover

### 11.1 Ending

| Item | Value | Why |
| --- | --- | --- |
| Default CTA | Comment keyword, as in the reference: `meta` line "напиши в коментарях" (EN: "comment") with the keyword in Playfair Display Italic 80px directly under it, straight, the two lines centred on each other as one block, #FFFFFF (with the caption haze when the shot is bright). No fixed position: the block goes where the shot has room (section 3.3) | Comment CTAs drive reach; the reference's strongest graphic, made lowercase per the system |
| CTA wording | Max 2 lines. Patterns: "напиши «промпт» в коментарях" · "збережи, щоб не загубити" · "comment «guide» and I'll send it" | Design system: CTA 1–2 lines, imperatives |
| CTA timing | Appears with the first word of her spoken CTA, stays to the end; captions hidden meanwhile | |
| Loop rule | No end card. Cut 300 ms after her last word; the last frame should match the first frame's framing (both 110%), and the last line should lead into the hook where possible ("…і саме тому" → "пост за 5 хвилин") | Instagram replays automatically; a seamless loop adds watch time |

Default: comment-keyword CTA with a seamless loop. No end card.

### 11.2 Cover

The cover is what people see in the profile grid and when the reel is shared. It is made with every reel.

| Rule | Value | Why |
| --- | --- | --- |
| Size | 1080×1920 PNG. Everything that matters inside the middle 1080×1440 (y 240–1680); face and title ideally inside the centre 1080×1080 | The Instagram grid crops reels to 3:4; other places crop tighter |
| Frame | A real frame from the reel: her face clear, eyes open, a readable expression, mouth not mid-word, no motion blur. No grade, same colour as the reel | Faces get taps; a mid-word frame looks odd |
| Title | 3–5 words: the hook promise, or a shorter version of the hook title. Lowercase, brand names excepted | It is read at thumbnail size in under a second |
| Style | The title block: Inter 700 display + optional Playfair Italic accent line (68% of the display), left edge x 68, soft text glow, caption haze if the frame is bright | Same look as the reel, so the cover feels like part of it |
| Size of the title | As large as fits, at least 96px. If it doesn't fit, Hard rule 3 applies: smaller (not under 96px), fewer words, another calm area, or a different frame | Small or thin text disappears in the grid |
| Placement | By section 3.3 on that frame: never on her face or hands, never a band or box | Same rules as the reel |
| Consistency | Same layout, type and colour on every cover, so the profile grid reads as one set | A steady grid tells new visitors this is a real brand |
| Keep off | Handle tag, pills, glow, emoji, arrows | One message per cover |
| Check | Look at it at 1/4 size (about one grid tile). If the title can't be read in 1 s, make it bigger or shorter | |

---

## 12. Footage look

| Item | Value | Why |
| --- | --- | --- |
| Input | iPhone 17 Pro HEVC; if HDR (HLG / Dolby Vision), tone-map to SDR Rec.709 first (filter in Appendix A) | HDR looks washed out or blown on many phones once overlays are added |
| Grade | **None.** Don't change saturation, contrast, curves or colour balance | Tetiana: the soft warm grade made her footage look awful (2026-10-05). Her iPhone colour is the look |
| Skin | Never push saturation above 100%; no beauty filter, no skin smoothing | Natural and premium |
| Mixed light | Leave each clip as shot. No white-balance matching | Tetiana: no colour change beyond HDR → SDR |
| Sharpening | `unsharp=5:5:0.4` only when the source is 1080p and zoomed above 105% | |
| Framing (vertical) | Keep her framing as shot. Never move or shrink the footage to make room for text | Text adapts to the shot, never the other way round |
| Framing (horizontal) | See section 3.2 switch rules | |
| Crop | Never crop above the hairline or through the chin; zooms stay centred on her face | |
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
| Mixed-font titles | Sans title lines with one word in a serif italic ("*Claude* може робити", "*закономірності*") | Inter 700 display + Playfair Italic accent line, left-aligned and straight (the reference centres them; our system forbids centred display and tilted text) |
| Titles replace captions | When a title is on, captions disappear | Same rule (1.2) |
| Title builds as she speaks | Words add one at a time | Line by line, not word by word |
| Cut-zoom jump cuts | Alternating framing hides every jump cut | 100% / 110%, max 2 per 10 s |
| UI shown as small cards above her head | Screenshots and app panels at the top third with a tiny label above ("settings → connectors → add") | As plain screenshots (sharp corners, no frame, no shadow, straight) with a `section-label` above. Breadcrumb arrows "→" are fine in labels |
| B&W punchline moment | Hard cut to black and white with one big serif italic word ("Нет") | L5 beat moment, max 1 per reel |
| CTA with keyword | Small caps lead-in + big serif italic keyword ("телеграм") | Same, but lowercase lead-in |

| Don't copy | Why |
| --- | --- |
| Word-by-word captions at 300 ms | Tetiana dislikes the fast switching |
| Centred bold titles | Design system: display is always left-aligned |
| UPPERCASE lead-in ("ПИШИТЕ В КОММЕНТАРИЯХ") | Design system: no caps |
| Rounded white UI cards with shadows | Screenshots are shown plain: sharp corners, no frame, no shadow |
| The "x2" circle badge in the top right | Unclear meaning, extra element |
| Gap-free delivery (no pauses at all) | Slightly breathless; we keep 150–250 ms between sentences |
| Warm, soft colour look | No grade: her own iPhone colour (section 12) |

### 13.2 Earlier test edit (IMG_6777_edit_v1)

Keep: soft blur dissolves, gentle zoom steps, frosted pills, the "Claude думає…" status pill with its pulsing dot and animated dots (Tetiana's favourite, now section 6.5 with a pink dot), one accent, restraint. Drop: Manrope, Cormorant Garamond, mint #9BE7B0, uppercase labels, dark bottom gradient, word-by-word light-up, the warm grade.

---

## 14. Never

One list for everything that stays out of a reel. The Hard rules at the top are the short version; the design system's own Never list says the same for all formats.

- **Her footage:** moving, shrinking, cropping or reframing her to fit text (only L3 crops her, for a real screen recording); text on her face or hands; any grade, LUT, teal-orange look, heavy contrast, beauty filter or white-balance matching (only L5 goes black and white).
- **Behind text:** bands, bars, strips, panels, paper areas, scrims, boxes, outlines or strokes, hard drop shadows, automatic caption pills. Allowed: the soft caption haze, the text glow and the pink glow.
- **Type:** fonts other than Inter and Playfair Display Italic (no Roboto or Arial, not even as fallback); ALL CAPS; underlines; centred display titles; more than 2 display lines; word-by-word or karaoke captions; bouncing words; pink, yellow or boxed keywords; a glow on every word; a caption colour that changes mid-reel.
- **Colour:** any colour outside section 2; coloured backgrounds; pure black; pink text or pink fills; mixing Paper and Ink in one reel.
- **Graphics:** emoji, stickers, hearts, arrows that point at things, circles around things, icons of any kind, polaroids, photo frames, tape, white frames, rounded or shadowed cards (the pill's own shadow is fine), device mockups, face cards, voice-message pills with a waveform, end cards, bracket tags, logo bugs, subscribe or like animations, countdowns, loading spinners, full-width progress or timeline bars, blurred-video fill backgrounds.
- **Motion:** tilted or rotated text or cards; whip zooms, shakes, spins, glitch, RGB split, flash frames; bounce or overshoot (except Pop In's 2%); more than 1 glass element and 1 glow on screen; visual changes under 1.5 s apart; more than 6 s that feels stuck.
- **Sound:** music in the file; a sound on every word or zoom; meme sounds (list in 7.1); ElevenLabs or any paid sound service.
- **Retired style:** Onest (replaced by Inter, 2026-10-06); Manrope, Cormorant Garamond, mint #9BE7B0 (the old test edit).

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
| Caption colour for the whole reel (optional) | white (default) / porcelain / ink |
| Audience | who exactly (e.g. "creators who post carousels and hate Canva") |
| Hook (spoken, first sentence) | |
| Hook title (optional; display, max 2 × 14 chars) | |
| Cover title (3–5 words) | |
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

Work in `Claude/videos/<video>/`. **One go by default:** run every round below without stopping and deliver the finished reel, then show her. Stop between rounds only when she asks for it. The rounds are the order of work, not review gates.

### Round 0: the sound kit

- [ ] Built once before the first edit (steps in Appendix A). Skip if `public/sfx/kit.json` exists.

### Round 1: captions only

- [ ] Convert HDR to SDR, conform to 30 fps (section 12).
- [ ] Whisper transcript with word-level timestamps (language set from the brief, never auto-detect), model from `Claude/video-tools/whisper-models`.
- [ ] Fix spelling; keep English words in English spelling; lowercase (brand names excepted).
- [ ] Chunk into 2–4 words, ≤ 24 chars, ≥ 800 ms (section 1.2); make the first 3 s a hook (section 1.7). Mark keywords (section 1.3). Pick the reel's caption colour once (section 1.6), then the position (section 3.3) and haze level per shot.
- [ ] Write `captions.json` + `captions.srt` and a readable list of chunks with times (shown to her only if she asked for a stop).

### Round 2: cut dead air

- [ ] Trim pauses > 400 ms to 200 ms; keep last takes; remove repeats and fillers (section 8).
- [ ] 2-frame handles, 30 ms audio crossfades.
- [ ] Re-time captions to the new cut.
- [ ] Write `cut_v1.mp4` (no graphics) + `edl.txt` listing every removed range and which take was kept (shown to her only if she asked for a stop).

### Round 3: first 15 s

- [ ] Hook title, captions, cut-zooms, layouts, sound for 0–15 s only (Remotion). No grade.
- [ ] Check safe zones with an overlay of the section 3.1 margins (or the Reels/TikTok UI) on the render.
- [ ] Self-check the first 15 s (hook, safe zones, captions) and fix before going on. Deliver `preview_15s.mp4` only if she asked for a stop here.

### Round 4: full edit

- [ ] Apply everything to the whole reel: screenshots, pills, status pills, beat moment, CTA, SFX, room tone (sections 3–11). No music.
- [ ] QA: her face is where it was in the raw clip and no band, bar, panel or box was added behind text; fonts loaded (no fallback), captions never under 800 ms, one caption colour for the whole reel, caption position fixed per shot, contrast report done with every shot ≥ 3:1 at its haze level (section 1.6), the haze never visible as a shape, no text on her face, hands or busy detail, max 1 glass + 1 glow on screen, nothing tilted, no text in unsafe bands, max 2 zooms / 10 s, no stretch over about 6 s that feels stuck, -14 LUFS / -1 dBTP, no black first frame, loop point checked.
- [ ] Export 1080×1920, 30 fps, H.264 High, 16–20 Mbps, AAC 48 kHz 320 kbps → `<video>_final.mp4`; plus the cover `<video>_cover.png` (section 11.2).

---

## 17. Review loop

The rules get better from real numbers, not guesses.

| When | What |
| --- | --- |
| 3–7 days after a reel is posted | Tetiana sends a screenshot of the reel's insights (views, average watch time, the retention graph, skip rate or 3-second hold, shares, saves, comments with the keyword). Claude notes the date, reel, type, hook formula, length, the numbers, and where the retention graph drops (time and what was on screen then) |
| Every 5 reels | Claude compares the notes: which hooks, lengths, layouts and first-3-second captions kept people longest, and where they leave. It proposes at most 2 rule changes, each with the numbers behind it |
| A change | Only after Tetiana says yes. It goes into this file and the Decisions log with the reason (e.g. "formula 3 held twice as long in 4 of 5 reels") |

- Never change a rule because of one reel. Change one or two things at a time, so the next reels show what worked.
- Her taste wins over the numbers when they disagree.

---

## Appendix A: pipeline recipes

Tool commands the rules above refer to. They also live in `make-reel.sh` and `kit.json` on the Mac; keep them in sync.

**HDR → SDR (section 12):**
`zscale=t=linear:npl=100,format=gbrpf32le,zscale=p=bt709,tonemap=hable:desat=0,zscale=t=bt709:m=bt709:r=tv,format=yuv420p`

**Voice chain (section 7.3):**
`highpass=f=80, afftdn=nr=10, deesser=i=0.4, acompressor=threshold=-20dB:ratio=3:attack=10:release=120, loudnorm=I=-14:TP=-1:LRA=7`

**Soft pop (section 7.2):**
`ffmpeg -f lavfi -i "aevalsrc='0.8*sin(2*PI*(260*t+2400*t*t))*exp(-34*t)':s=48000:d=0.16" -af "afade=t=in:d=0.004,lowpass=f=3500,afade=t=out:st=0.13:d=0.03" pop-soft.wav`

**Building the sound kit (once, before the first edit):**

- [ ] In `Claude/video-tools/remotion`: `npx remotion add @remotion/sfx`; create `public/sfx/`.
- [ ] Download the 6 Remotion sounds in 7.2 into `public/sfx/` under the kit names.
- [ ] Make `pop-soft` with the recipe above.
- [ ] Process every file (7.3) and write `kit.json`.
- [ ] Render `sfx-preview.mp4`: paper background, each kit name shown in `section-label` while its sound plays, 1 s apart. Tetiana listens and approves before any reel uses the kit.

---
