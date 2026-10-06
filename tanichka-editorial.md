# Tanichka Editorial

Design system for @tanii444.ka: posts, carousels, stories, covers, landing pages and presentations.

Last updated: 2026-10-06

## 1. Brand book

### Export

Two files to download and use anywhere, both kept current on every change to this system. Find them under **Assets → Export** (the first group in Assets):

- `tanichka-editorial.md`: the whole design system in one file (brand book, tokens for both themes, components, icons, code).
- `reel-stylebook.md`: the video editing rules for @tanii444.ka reels, built on this system.

**Markdown export.** The whole system is also kept as one Markdown file, `assets/Export/tanichka-editorial.md`, in the Export group. Whenever you change anything in this system, regenerate it in the same update: read the icon uploads into `assets/Icons/`, run `python3 tools/export-md.py` from the `project/` folder, and publish the new export with your other changes.

**Reel stylebook.** The video rules for @tanii444.ka reels live beside it as `assets/Export/reel-stylebook.md`. It is written by hand, so no script rebuilds it: whenever you change this system, read the stylebook, rewrite every place that mentions what changed (token names and values, components, icons, rules), bump its version line, add a dated row to its Decisions log, and publish it in the same update. The design system wins any conflict.

### Mood

Minimal fashion-editorial, like a Pinterest moodboard printed as a zine page. Off-white paper, black type, and real photos doing all the colour work. Calm, airy, a little playful, with one soft pink accent and a few soft depth touches (frosted glass, one glow) used as seasoning. It should never look like a tech dashboard.

Fonts, colours, shapes and the Don't list are fixed. Sizes and positions are the default for the 4:5 paper canvas; other formats and video adapt them to the space they have (see Video). The system works for any format: social posts, carousels, stories, covers, landing pages, presentations and reels.

### Content fundamentals

- Write short, lowercase, friendly and direct, like texting a friend. Ukrainian or English.
- Navigation words are imperatives: "збережи" (save), "гортай" (swipe).
- The handle is always `@tanii444.ka`.
- Lowercase by default everywhere. No all-caps, no underlines, no emoji.
- Real copy: "пози, які працюють" · "без фотографа" · "хочеш такі ж *кадри*?" · "6 категорій поз" · "[ пози ]".
- No dense text blocks. One idea per slide; a CTA is 1–2 lines at most.

### Colour

Two themes share one set of token names, so every component works in both without changes:

| Token | Paper (light, default) | Ink (dark) |
| --- | --- | --- |
| `paper` (ground) | #F6F5F1 warm off-white | #151413 warm black |
| `ink` (text, icons, lines) | #111111 | #F3F1EC |
| `muted` | #6E6A64 | #9E9890 |
| `accent-pink` | #F2A7C3 | #F2A7C3 (unchanged) |

- Switch a whole canvas or page with `data-theme="ink"` on it (or on `<html>`); `data-theme="paper"` or no attribute is the light theme. Never mix the two themes inside one carousel, post or page.
- Ink is the same system turned over: warm black paper with off-white type, never pure #000 and never pure white text. Photos, the pink accent and the frosted pill stay exactly the same; glows are softer, the voice pill a little lighter, placeholders and shadows deeper.
- `paper` is the only background in each theme. No coloured backgrounds.
- `ink` is used for all text, icons and lines. `muted` is only for captions and secondary notes.
- `white` (#FFFFFF) is for small details only, never a card, panel or frame.
- `accent-pink` (#F2A7C3) is the one accent: glowing dots and waveform bars. `accent-pink-85` is the same pink at 85%. Never use pink as a background fill or for text.
- Photos carry the colour. Until a real photo goes in, use the placeholders `photo-1`…`photo-5`, labelled in `photo-label`.
- The only gradients allowed are the two glows, the two glass fills and the dissolve (all defined in `components/bundle.css` as `--glow-strong`, `--glow-soft`, `--glass-dark`, `--glass-solid`, `--dissolve-tint`). Use no other colours and no other gradients.

### Type

Both families are free on Google Fonts (OFL) and cover Latin and Cyrillic, including Ukrainian. Load them with a `<link rel="stylesheet">` in `<head>`, not only through `components/bundle.css` (its `@import` is ignored once the CSS is pasted after other rules):
`https://fonts.googleapis.com/css2?family=Onest:wght@400;500;700&family=Playfair+Display:ital,wght@1,400&display=swap`

| Role | Style token | Spec on a 1080-wide canvas |
| --- | --- | --- |
| Display | `display` | Onest 700, 118px, lh 0.98, ls -0.045em. Left-aligned, 2 lines max |
| Accent line | `accent-line` | Playfair Display Italic 400, 80px, lh 1.1, left-aligned flush with the display, straight. The last line of the title block, 14px under the display; never centred or pushed right, so it never reads as a caption |
| Highlight word | `highlight` | Playfair Display Italic 400 at 115% of its sentence, same colour. One per line at most |
| Section label | `section-label` | Onest 400, 40px, lh 1, ls -0.01em. Always lowercase |
| Meta / UI | `meta` | Onest 400, 30px, lh 1. Handle, page index, navigation words |
| Pill | `pill` | Onest 500, 22–26px, `on-glass` white, ls -0.01em |
| Body / CTA | `body` | Onest 400, 40px, lh 1.75, centred |

- Bold is used only on the display headline. Never centre the display.
- Never use Inter, Roboto or Arial, not even as a fallback.

### Layout and spacing

The base canvas is 1080×1350 (4:5). Every size scales proportionally with canvas width: in CSS, set `--u` to (canvas width ÷ 1080) px on the canvas and the `.te-*` classes follow.

- Header: `header-top` 60px from the top. Footer: `footer-bottom` 52px from the bottom. Both rows sit `margin-side` 68px in from each side and are `bar-height` 36–40px tall.
- Section label top: `label-top` 146px. Content field: `field-top` 223px to `field-bottom` 1201px.
- The content field is centred, between `field-width-min` 70% and `field-width-max` 90% of the canvas width. The section label aligns to the field's left edge, not to the margin.
- Photo gap: `photo-gap` 14px.
- Leave generous empty paper around everything. Never fill edge to edge.
- Other formats: a 9:16 story is 1080×1920 (`.te-canvas--story`) and a square post is 1080×1080 (`.te-canvas--square`). For a 16:9 slide or a landing page, keep the same proportions to width.

### Shape, depth and effects

- Corner radius is `radius-none` (0) for photos and everything else. Only pills are fully rounded (`radius-pill`).
- Shadows only on one raised photo per slide (`shadow-lift`), the frosted pill (`shadow-pill`) and the voice pill (`shadow-voice`). Nothing else casts a shadow.
- Nothing is ever rotated or tilted: no tilted text (the accent line included), no tilted photos. Everything sits straight on the grid.
- No polaroids, photo frames, tape strips or stacked/tilted photo piles, anywhere. Photos are plain, sharp-cornered rectangles, alone or in the photo grid.
- Frosted glass (for pills over photos): a smoky, see-through `--glass-dark` fill over a soft backdrop blur (`blur-glass`, 24px + saturate 120%), so the photo behind melts into smooth colour. A thin 1px rim, brightest at the top-left and bottom-right (`glass-border`) and dimmer along the long sides (`glass-border-faint`), plus a faint inner top highlight (`glass-highlight`). Proportions are tied to the text size: height about 2.8× the text, generous padding, more on the right than the left.
- Blur dissolve: on ONE photo, the bottom 45% gets a 16px backdrop blur and a faint paper tint (`paper-tint` → `paper-clear`), masked `linear-gradient(to top, #000 35%, transparent)` so the blur melts upward.
- Glow: one large soft pink radial circle behind the single focal point. Use `--glow-soft` (about 85% of canvas width) behind a cover's focal photo, or `--glow-strong` (about 50%) behind the CTA. Never put a glow behind body text anywhere else.
- Text and pills on a photo or on video have no fixed position: each goes where that picture has room, in the calmest empty area, never on a face, hands or busy detail. A display headline always keeps its left edge on the side margin; only its height changes. Paper areas keep their grid.
- The picture is never changed to make room for text: never move, shrink or crop a photo or video for it, and never add a band, bar, strip, panel, paper area, gradient or box behind text. If text doesn't fit, make it smaller, use fewer words, move it, or leave it out.
- **Restraint rule:** at most one glass/frosted/blur element and one glow per slide or page. Most slides get none. The 3D touches are seasoning, never the dish.

### Motion

All motion is short, soft and ease-out. No bounce, shake, spin, rotation or typewriter text. One thing moves at a time (stagger 120 ms if two must).

| Token | Value | Use |
| --- | --- | --- |
| `ease-enter` | `cubic-bezier(0.22, 1, 0.36, 1)` | Anything appearing |
| `ease-exit` | `cubic-bezier(0.4, 0, 1, 1)` | Anything leaving |
| `ease-move` | `cubic-bezier(0.65, 0, 0.35, 1)` | Transitions, loops, slow pushes |
| `dur-fast` | 140 ms | Small text in (captions, labels) |
| `dur-base` | 220 ms | Titles in, exits |
| `dur-slow` | 320 ms | Cards, layout changes, blur dissolve |

- Text comes in with a soft focus: opacity 0→1, blur 8–12px→0, scale 0.92–0.96→1, a few px upward.
- Pop-ups may settle with at most 2% overshoot; nothing else overshoots.
- The reel stylebook names the full set of animations (Soft Focus, Pop In, Blur Dissolve and the rest) and builds them from these tokens.

### Video

For reels and stories (1080×1920). Full rules in `reel-stylebook.md`; these are the parts that belong to the system:

- Text sits straight on the footage, with no band, panel, box, stroke or shadow behind it. Her footage stays framed as shot.
- On footage, text is white #FFFFFF (or ink #111111 on bright areas); the reel stylebook also allows paper #F6F5F1 on warm shots.
- The display headline on footage is 72–118px, the largest that fits the calm area; it keeps its left edge on the side margin. 118px on paper.
- Keep text out of the platform zones: top 250px, bottom 480px, and right of x 920 from y 900 down.
- Paper or Ink panels appear in video only to hold real content (a screen recording, an end card), never to make room for text.

### Components

Header, Footer, BracketTag, Headline, HighlightWord, SectionLabel, PhotoGrid, FrostedPill, BlurDissolve, VoicePill and CTABlock, plus three full-canvas templates (CoverSlide, GridSlide, FinalSlide). All are plain HTML + `components/bundle.css` classes prefixed `te-`; each card's README gives the markup.

- A carousel runs CoverSlide → GridSlides (or single-photo slides) → FinalSlide.
- Cover footer: icons only. Inner footer: "збережи" + bookmark, "гортай" + arrow. Final footer: no arrow.

### Iconography

- Thin outline icons only: stroke 2.2–2.4px, round caps and joins. Use `ink` (so icons flip with the theme), and `voice-x` grey inside dark pills. No hearts.
- The set lives in `assets/Icons/`: bookmark (24×30), arrow (104×22) and close ×. The preview cards carry the same paths inline with `stroke="currentColor"`.
- No filled icons, no emoji, no chrome or 3D icons.

### Don't

- No rounded cards, borders or boxes around content. Pills are the only rounded shapes.
- No extra accent colours, no neon, no pink background fills.
- No glass, glow or blur on every slide, and never more than one of each per slide.
- No drop shadows except on one raised photo and the pills.
- No centred display headlines or accent lines, and no dense text blocks.
- No bands, panels or paper strips added behind text on a photo or video, and never move or shrink a photo to make room for text.
- No heavy 3D renders.

## 2. Tokens

### Colour

Themes: Paper (`data-theme="paper"`), Ink (dark) (`data-theme="ink"`). The first is the default.

| Token | Paper | Ink (dark) | Usage |
| --- | --- | --- | --- |
| `paper` | `#f6f5f1` | `#151413` | The ground of every canvas, page and slide. Paper: warm off-white. Ink: warm black, never pure #000. |
| `ink` | `#111111` | `#f3f1ec` | All text, icons and lines, on paper. Paper: 17.3:1. Ink theme: warm off-white, 16.3:1. |
| `muted` | `#6e6a64` | `#9e9890` | Captions and secondary notes only, on paper (Paper 4.9:1, Ink 6.4:1). Never for headlines or navigation. |
| `paper-tint` | `rgba(246, 245, 241, 0.3)` | `rgba(21, 20, 19, 0.3)` | paper at 30%: the bottom of the blur dissolve's faint tint. |
| `paper-clear` | `rgba(246, 245, 241, 0)` | `rgba(21, 20, 19, 0)` | paper at 0%: the top of the blur dissolve's tint. |
| `white` | `#ffffff` | `#ffffff` | Pure white, for small details. Never a card, panel, border or frame fill. |
| `accent-pink` | `#f2a7c3` | `#f2a7c3` | The one accent: glowing dots and waveform bars. Never a background fill, never text on paper (1.7:1). |
| `accent-pink-85` | `#f2a7c3d9` | `#f2a7c3d9` | accent-pink at 85% opacity, for a softer pink detail. Never a background fill. |
| `glow-pink-strong` | `#f2a7c3b3` | `#f2a7c380` | Centre stop of the strong glow (radial, transparent by 68%). Behind the CTA only. Softer in Ink, where pink reads brighter on black. |
| `glow-pink-soft` | `#f2a7c359` | `#f2a7c340` | Centre stop of the soft glow (radial, transparent by 66%). Behind a cover's focal photo only. Softer in Ink. |
| `glow-pink-fade` | `#f2a7c300` | `#f2a7c300` | Outer stop of both glows: accent-pink at 0%. |
| `glass-dark-top` | `rgba(34, 34, 36, 0.52)` | `rgba(34, 34, 36, 0.52)` | Top stop of the frosted pill fill (linear 180deg): smoky and see-through, so the blurred photo shows. Over photos only. |
| `glass-dark-bottom` | `rgba(14, 14, 16, 0.6)` | `rgba(14, 14, 16, 0.6)` | Bottom stop of the frosted pill fill. |
| `glass-solid-top` | `rgba(48, 48, 50, 0.92)` | `rgba(66, 66, 70, 0.92)` | Top stop of the voice pill fill (linear 180deg), on paper. Lighter in Ink so the pill still lifts off the black ground. |
| `glass-solid-bottom` | `rgba(28, 28, 30, 0.92)` | `rgba(44, 44, 48, 0.92)` | Bottom stop of the voice pill fill. |
| `glass-border` | `rgba(255, 255, 255, 0.3)` | `rgba(255, 255, 255, 0.3)` | Brightest part of the frosted pill's 1px rim (top-left and bottom-right). |
| `glass-border-faint` | `rgba(255, 255, 255, 0.1)` | `rgba(255, 255, 255, 0.1)` | Dimmest part of the frosted pill's 1px rim, along the long sides. |
| `glass-highlight` | `rgba(255, 255, 255, 0.16)` | `rgba(255, 255, 255, 0.16)` | Inner top highlight of the frosted pill (inset 0 1px 0). |
| `glass-lowlight` | `rgba(255, 255, 255, 0.05)` | `rgba(255, 255, 255, 0.05)` | Faint inner bottom edge of the frosted pill (inset 0 -1px 0). |
| `voice-border` | `rgba(255, 255, 255, 0.14)` | `rgba(255, 255, 255, 0.2)` | Hairline border of the voice pill. Stronger in Ink to outline the pill on black. |
| `on-glass` | `#ffffff` | `#ffffff` | Pill text on glass-dark or glass-solid fills. |
| `voice-close` | `#3a3a3d` | `#4a4a4e` | The 56px circle at the right end of the voice pill. |
| `voice-x` | `#b9b9be` | `#c4c4c9` | The thin × inside voice-close (Paper 5.8:1, Ink 5.1:1), and any grey icon inside a dark pill. |
| `photo-1` | `#dcd7cf` | `#3a3733` | Photo placeholder, lightest in Paper / darkest in Ink. Stand-in until a real photo goes in. |
| `photo-2` | `#cfc9c0` | `#45413c` | Photo placeholder. |
| `photo-3` | `#c4bdb3` | `#504b45` | Photo placeholder. |
| `photo-4` | `#b9b2a8` | `#5c5650` | Photo placeholder. |
| `photo-5` | `#a8a197` | `#6a645d` | Photo placeholder. |
| `photo-label` | `#2e2b27` | `#f3f1ec` | Label text on any photo placeholder (at least 5.2:1 in both themes). |

### Composite effects

Built from the colour tokens above (defined in `bundle.css`):

```css
--glow-strong: radial-gradient(circle, var(--glow-pink-strong) 0%, var(--glow-pink-fade) 68%);
--glow-soft: radial-gradient(circle, var(--glow-pink-soft) 0%, var(--glow-pink-fade) 66%);
--glass-dark: linear-gradient(180deg, var(--glass-dark-top), var(--glass-dark-bottom));
--glass-solid: linear-gradient(180deg, var(--glass-solid-top), var(--glass-solid-bottom));
--dissolve-tint: linear-gradient(to top, var(--paper-tint), var(--paper-clear));
```

### Typography

Font stacks:

- `sans`: `Onest, "Helvetica Neue", Helvetica, sans-serif`
- `serif`: `"Playfair Display", Georgia, "Times New Roman", serif`

| Style | Family | Size | Line height | Weight | Letter spacing | Sample | Usage |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `display` | sans | 118px | 0.98 | 700 | -0.045em | пози, які працюють | The headline. Left-aligned, 2 lines max, about 11% of canvas width. The only bold text in the system. |
| `accent-line` | serif italic | 80px | 1.1 | 400 | 0 | без фотографа | The last line of the title block: right under the display, left-aligned flush with it at the same x, 14px gap, perfectly straight. Never centred, never pushed right, never apart from the display, so it is never read as a caption. About 68% of the display size. |
| `highlight` | serif italic | 46px | 1 | 400 | 0 | кадри | ONE key word inside an Onest sentence at 115% of the surrounding size (46px inside 40px body), same colour. Max one per line. |
| `section-label` | sans | 40px | 1 | 400 | -0.01em | пози сидячи | Lowercase label above the content field, aligned to the field's left edge. |
| `body` | sans | 40px | 1.75 | 400 | 0 | хочеш такі ж кадри? | Body and CTA lines, centred. Short; never dense blocks. |
| `meta` | sans | 30px | 1 | 400 | 0 | [2]  @tanii444.ka  [ пози ] | Handle, page index, navigation words, bracket tags. In muted for captions. |
| `pill` | sans | 24px | 1 | 500 | -0.01em | 6 категорій поз | Text inside a frosted pill, in on-glass. 22–26px range. |

### Spacing and layout

Base canvas 1080×1350 (4:5). Every value scales with canvas width / 1080.

| Token | Value | Usage |
| --- | --- | --- |
| `margin-side` | `68px` | Left and right margin of the header and footer rows. |
| `header-top` | `60px` | Header row distance from the top edge. |
| `footer-bottom` | `52px` | Footer row distance from the bottom edge. |
| `bar-height` | `38px` | Height of the header and footer rows (36–40px). |
| `label-top` | `146px` | Top of the section label. |
| `field-top` | `223px` | Top of the content / photo field. |
| `field-bottom` | `1201px` | Bottom of the content field, measured from the top (149px of paper below it). |
| `field-width-min` | `70%` | Narrowest content field, centred. |
| `field-width-max` | `90%` | Widest content field, centred. |
| `photo-gap` | `14px` | Gap between photos in a grid. |

### Radius

| Token | Value | Usage |
| --- | --- | --- |
| `radius-none` | `0` | Photos and everything else that is not a pill. |
| `radius-pill` | `999px` | Frosted pill and voice pill only (plus their dots and the close circle). |

### Shadows

Ink uses deeper, pure-black shadows; the Paper ones disappear on a black ground.

| Token | Value | Usage |
| --- | --- | --- |
| `shadow-lift` | `0 22px 44px rgba(17, 17, 17, 0.18)` / `0 22px 44px rgba(0, 0, 0, 0.5)` | Soft lift for one raised photo per slide at most (the cover photo). Nothing else. |
| `shadow-pill` | `0 10px 26px rgba(17, 17, 17, 0.24)` / `0 10px 26px rgba(0, 0, 0, 0.45)` | Frosted pill on a photo. |
| `shadow-voice` | `0 16px 36px rgba(17, 17, 17, 0.22)` / `0 16px 36px rgba(0, 0, 0, 0.5)` | Voice pill on paper. |

### Blur

| Token | Value | Usage |
| --- | --- | --- |
| `blur-glass` | `24px` | Frosted pill backdrop blur (with saturate 120%): soft enough that the photo behind turns to smooth colour. |
| `blur-dissolve` | `16px` | Blur dissolve layer over the bottom 45% of one photo. |

## 3. Components

Plain HTML with the `te-` classes from `bundle.css` (section 5). Set `--u` on the canvas to (canvas width ÷ 1080) px and every size scales.

### Header

The top row of every slide: page index left, handle centred, an optional bracket tag right.

- Markup: `.te-header.te-meta` with exactly three children; the third may be empty.
- Sits `header-top` (60px) from the top, `margin-side` (68px) in from each side, `bar-height` (38px) tall.
- Left: the page index in brackets, `[2]`. Centre: always `@tanii444.ka`. Right: empty, or a bracket tag like `[ пози ]`.
- Set in `meta` (Onest 400, 30px), `ink`. Never bold, never caps.

### Footer

The bottom row: a save prompt on the left, a swipe prompt on the right.

- Markup: `.te-footer.te-meta` with two `.te-footer__side` groups.
- Left: bookmark outline icon (24×30, stroke 2.4) + "збережи". Right: "гортай" + the long thin arrow (104×22, stroke 2.2, round caps).
- Sits `footer-bottom` (52px) from the bottom, `margin-side` (68px) in from each side.
- Cover: drop both words, keep only the bookmark and the arrow. Final slide: drop the arrow (and "гортай").
- Icons in `ink`; use the inline SVGs or `assets/Icons/`.

### BracketTag

Text in square brackets with a space inside each bracket: `[ пози ]`. Used for the header's right slot and topic tags.

- Set in `meta` (`.te-meta`), `ink`, lowercase. A page index is the one exception with no inner spaces: `[2]`.
- No pill, no box, no border around it: the brackets are the container.

### Headline

The display headline with its optional accent line: the loudest type on a slide.

- `.te-display`: Onest Bold 700, 118px on 1080 wide, line-height 0.98, letter-spacing -0.045em. Left-aligned, 2 lines max. Never centred.
- `.te-accent`: Playfair Display Italic 400, 80px (about 68% of the display), line-height 1.1, left-aligned flush with the display, straight (never rotated). One short line right under the display.
- Always wrap both in one `<hgroup class="te-headline">` (display as `<h1>`, accent line as `<p>`): one title block, one left edge at x 68, 14px gap. The accent line is the title's last line, never a separate caption: never centred, never pushed right, never placed apart from the display.
- Bold appears nowhere else in the system. Lowercase by default.
- Consumer provides: the two lines (break with `<br>` where the meaning breaks) and the accent phrase.

### HighlightWord

One key word inside an Onest sentence set in Playfair Display Italic 400 at 115% of the surrounding size, same colour.

- Markup: `<span class="te-hl">кадри</span>` inside any Onest text; it sizes itself at `1.15em`.
- At most one highlighted word per line. Never on the display headline itself (the accent line does that job there).
- Same colour as its sentence: never pink, never underlined.

### SectionLabel

One lowercase word or phrase that names the content below it.

- `.te-label`: Onest Regular 400, 40px, line-height 1, letter-spacing -0.01em, always lowercase.
- Top at `label-top` (146px). It aligns to the content field's left edge, not to the header margin. `.te-field` handles both.

### PhotoGrid

Two rows of photos with deliberately uneven columns and rows, sharp corners, 14px gaps.

- Markup: `.te-grid` (set `--rows`, e.g. `2fr 3fr` for a 40/60 split) holding two `.te-grid__row`s (set `--cols`, e.g. `130fr 138fr 96fr` over `78fr 143fr`).
- Rows are 3 over 2 or 2 over 3. Never equal columns, never equal rows.
- Gap is `photo-gap` (14px). Corners `radius-none`. No borders, no shadows.
- Each cell is a `.te-photo`: put the real photo in as `background-image` (cover), or an `<img>` with `object-fit: cover`. Placeholders use `photo-1`…`photo-5` with a `.te-photo__label` in `photo-label`.
- Place it inside `.te-field` so it runs from `field-top` (223px) to `field-bottom` (1201px).

<details><summary>Example markup</summary>

```html
<div style="width:calc(907*var(--u));height:calc(978*var(--u))"><div class="te-grid" style="--rows:2fr 3fr">
  <div class="te-grid__row" style="--cols:130fr 138fr 96fr">
    <div class="te-photo" style="--ph:var(--photo-2)"><span class="te-photo__label">фото 1</span></div>
    <div class="te-photo" style="--ph:var(--photo-4)"><span class="te-photo__label">фото 2</span></div>
    <div class="te-photo" style="--ph:var(--photo-1)"><span class="te-photo__label">фото 3</span></div>
  </div>
  <div class="te-grid__row" style="--cols:78fr 143fr">
    <div class="te-photo" style="--ph:var(--photo-3)"><span class="te-photo__label">фото 4</span></div>
    <div class="te-photo" style="--ph:var(--photo-5)"><span class="te-photo__label">фото 5</span></div>
  </div>
</div></div>
```

</details>

### FrostedPill

A frosted glass pill that sits on a photo and states one key fact in 2–4 words.

- Markup: `<span class="te-frost"><span class="te-dot"></span>6 категорій поз</span>`, placed as a child of a `.te-photo`. It has no fixed spot: put it where that photo has room, in the calmest empty area, never on a face, hands or busy detail. Always set its spot with `--pill-x` (horizontal centre) and `--pill-y` (distance from the bottom); the bottom-centre the CSS falls back to is only a placeholder for previews, not a position to use.
- Fill: smoky glass-dark (`glass-dark-top` → `glass-dark-bottom`), see-through, over a soft backdrop blur `blur-glass` (24px) + saturate 120%. Fully rounded (`radius-pill`), `shadow-pill`.
- Rim: a thin 1px gradient line, brightest at the top-left and bottom-right (`glass-border`), dimmer along the long sides (`glass-border-faint`). Inner edges: `glass-highlight` on top, `glass-lowlight` at the bottom.
- Proportions, all in em of the text so they hold at any size: height about 2.8em, padding 0.9em 1.55em 0.9em 0.95em, dot 0.32em, gap from dot to text 0.72em.
- Dot: `accent-pink` with a soft glow of its own. Text: `pill` style (Onest 500, 22–26px) in `on-glass`.
- Only on photos, never on paper. One glass element per slide at most; most slides get none.

### BlurDissolve

A blur that melts upward from the bottom of one photo, like the picture is dissolving into the paper.

- Markup: `<div class="te-dissolve"></div>` as the last child of a `.te-photo`.
- Covers the bottom 45%: backdrop blur `blur-dissolve` (16px), a faint paper tint (rgba of `paper` at 0.30 → 0), masked with `linear-gradient(to top, #000 35%, transparent)` so the blur fades out going up.
- On ONE photo per slide, and counts as that slide's glass element: never alongside a frosted pill.

### VoicePill

A dark glass pill shaped like a voice message. It sits on paper, above the CTA text.

- Fill: glass-solid (`glass-solid-top` → `glass-solid-bottom`), hairline `voice-border`, inner top highlight, `shadow-voice`, `radius-pill`.
- Left: a 14px glowing `accent-pink` dot. Middle: `.te-wave`, about 8 rounded pink bars (`<span class="te-wave__bar" style="--h:24">`, 5px wide, `--h` from 18 to 36) trailing into 3 fading pink dots (`<span class="te-wave__dot" style="--o:.75">`, then `.45`, `.2`). Right: `.te-voice__close`, a 56px `voice-close` circle with a thin × in `voice-x`.
- Decorative: give it `role="img"` and an `aria-label`. Use it only inside the CTA block, once.

### CTABlock

The closing call to action: voice pill, then 1–2 centred lines with one highlight word, on a strong pink glow.

- Markup: `.te-cta` holding `.te-glow.te-glow--strong` (about 50% of canvas width), the voice pill, then a `.te-body` paragraph.
- Body: Onest 400, 40px, line-height 1.75, centred. One `.te-hl` word. No icon after the text.
- This glow and this voice pill are the slide's one glow and one glass element. Usually on the final slide only.
- Consumer provides: the two lines and the highlight word.

<details><summary>Example markup</summary>

```html
<div class="te-cta">
  <div class="te-glow te-glow--strong"></div>
  <div class="te-voice" role="img" aria-label="voice message"><span class="te-dot"></span><span class="te-wave"><span class="te-wave__bar" style="--h:18"></span><span class="te-wave__bar" style="--h:30"></span><span class="te-wave__bar" style="--h:36"></span><span class="te-wave__bar" style="--h:24"></span><span class="te-wave__bar" style="--h:32"></span><span class="te-wave__bar" style="--h:20"></span><span class="te-wave__bar" style="--h:28"></span><span class="te-wave__bar" style="--h:18"></span><span class="te-wave__dot" style="--o:.75"></span><span class="te-wave__dot" style="--o:.45"></span><span class="te-wave__dot" style="--o:.2"></span></span><span class="te-voice__close"><svg viewBox="0 0 18 18" aria-hidden="true"><path d="M3 3l12 12M15 3L3 15"/></svg></span></div>
  <p class="te-body">хочеш такі ж <span class="te-hl">кадри</span>?<br>пиши «пози» в директ</p>
</div>
```

</details>

### Templates (full 1080×1350 canvases)

#### CoverSlide

The first slide of a carousel, as a full 1080×1350 canvas.

- Header with `[1]`, the handle and an optional tag. One title block top-left (`.te-headline`): display headline with its accent line directly under it, both left-aligned at x 68.
- Focal point: one photo, set off-centre to the right with sharp corners and `shadow-lift`, over the soft glow (the slide's one glow). No glass elements, no frames, no stacks.
- Footer: icons only, no words.
- Scale the whole canvas with `--u` (canvas width / 1080, in px).

<details><summary>Example markup</summary>

```html
<div class="te-canvas">
  <div class="te-header te-meta"><span>[1]</span><span>@tanii444.ka</span><span>[ пози ]</span></div>
  <div style="position:absolute;left:calc(68*var(--u));right:calc(68*var(--u));top:calc(168*var(--u))">
    <hgroup class="te-headline">
      <h1 class="te-display">пози, які<br>працюють</h1>
      <p class="te-accent">без фотографа</p>
    </hgroup>
  </div>
  <div class="te-glow" style="left:calc(640*var(--u));top:calc(900*var(--u))"></div>
  <div class="te-photo te-photo--lift" style="--ph:var(--photo-3);position:absolute;left:calc(380*var(--u));top:calc(600*var(--u));width:calc(520*var(--u));height:calc(600*var(--u))"><span class="te-photo__label">фото</span></div>
  <div class="te-footer te-meta"><span class="te-footer__side"><svg class="te-icon te-icon--bookmark" viewBox="0 0 24 30" aria-hidden="true"><path d="M2.2 2.2h19.6v25.6L12 20.8l-9.8 7z"/></svg></span><span class="te-footer__side"><svg class="te-icon te-icon--arrow" viewBox="0 0 104 22" aria-hidden="true"><path d="M1.6 11h100.8M92 1.6l10.4 9.4L92 20.4"/></svg></span></div>
</div>
```

</details>

#### GridSlide

An inner carousel slide: section label over an uneven photo grid.

- Header with the page index and tag; section label at 146px, aligned to the field's left edge; grid from 223px to 1201px inside `.te-field` (set `--field` between 70% and 90%).
- At most one glass touch: here a frosted pill on the largest photo. Most inner slides should have none.
- Footer: "збережи" + bookmark, "гортай" + arrow.

<details><summary>Example markup</summary>

```html
<div class="te-canvas">
  <div class="te-header te-meta"><span>[2]</span><span>@tanii444.ka</span><span>[ пози ]</span></div>
  <div class="te-field" style="--field:84%">
    <p class="te-label">пози сидячи</p>
    <div class="te-grid" style="--rows:2fr 3fr">
  <div class="te-grid__row" style="--cols:130fr 138fr 96fr">
    <div class="te-photo" style="--ph:var(--photo-2)"><span class="te-photo__label">фото 1</span></div>
    <div class="te-photo" style="--ph:var(--photo-4)"><span class="te-photo__label">фото 2</span></div>
    <div class="te-photo" style="--ph:var(--photo-1)"><span class="te-photo__label">фото 3</span></div>
  </div>
  <div class="te-grid__row" style="--cols:78fr 143fr">
    <div class="te-photo" style="--ph:var(--photo-3)"><span class="te-photo__label">фото 4</span></div>
    <div class="te-photo" style="--ph:var(--photo-5)"><span class="te-photo__label">фото 5</span><span class="te-frost"><span class="te-dot"></span>6 категорій поз</span></div>
  </div>
</div>
  </div>
  <div class="te-footer te-meta"><span class="te-footer__side"><svg class="te-icon te-icon--bookmark" viewBox="0 0 24 30" aria-hidden="true"><path d="M2.2 2.2h19.6v25.6L12 20.8l-9.8 7z"/></svg><span>збережи</span></span><span class="te-footer__side"><span>гортай</span><svg class="te-icon te-icon--arrow" viewBox="0 0 104 22" aria-hidden="true"><path d="M1.6 11h100.8M92 1.6l10.4 9.4L92 20.4"/></svg></span></div>
</div>
```

</details>

#### FinalSlide

The last slide: lots of paper and the CTA block in the middle.

- Header with the final index and the handle. The CTA block centred, its strong glow as the slide's one glow and the voice pill as its one glass element.
- Footer: bookmark + "збережи" only. No arrow, nothing left to swipe to.

<details><summary>Example markup</summary>

```html
<div class="te-canvas">
  <div class="te-header te-meta"><span>[8]</span><span>@tanii444.ka</span><span></span></div>
  <div style="position:absolute;left:0;right:0;top:calc(500*var(--u))"><div class="te-cta">
  <div class="te-glow te-glow--strong"></div>
  <div class="te-voice" role="img" aria-label="voice message"><span class="te-dot"></span><span class="te-wave"><span class="te-wave__bar" style="--h:18"></span><span class="te-wave__bar" style="--h:30"></span><span class="te-wave__bar" style="--h:36"></span><span class="te-wave__bar" style="--h:24"></span><span class="te-wave__bar" style="--h:32"></span><span class="te-wave__bar" style="--h:20"></span><span class="te-wave__bar" style="--h:28"></span><span class="te-wave__bar" style="--h:18"></span><span class="te-wave__dot" style="--o:.75"></span><span class="te-wave__dot" style="--o:.45"></span><span class="te-wave__dot" style="--o:.2"></span></span><span class="te-voice__close"><svg viewBox="0 0 18 18" aria-hidden="true"><path d="M3 3l12 12M15 3L3 15"/></svg></span></div>
  <p class="te-body">хочеш такі ж <span class="te-hl">кадри</span>?<br>пиши «пози» в директ</p>
</div></div>
  <div class="te-footer te-meta"><span class="te-footer__side"><svg class="te-icon te-icon--bookmark" viewBox="0 0 24 30" aria-hidden="true"><path d="M2.2 2.2h19.6v25.6L12 20.8l-9.8 7z"/></svg><span>збережи</span></span><span></span></div>
</div>
```

</details>

## 4. Icons

Thin outline, round caps and joins. Inline them with `stroke="currentColor"` to change the ink.

**bookmark.svg**

```svg
<svg xmlns="http://www.w3.org/2000/svg" width="24" height="30" viewBox="0 0 24 30" fill="none" stroke="#111111" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="M2.2 2.2h19.6v25.6L12 20.8l-9.8 7z"/></svg>
```

**arrow.svg**

```svg
<svg xmlns="http://www.w3.org/2000/svg" width="104" height="22" viewBox="0 0 104 22" fill="none" stroke="#111111" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M1.6 11h100.8M92 1.6l10.4 9.4L92 20.4"/></svg>
```

**close.svg**

```svg
<svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 18 18" fill="none" stroke="#B9B9BE" stroke-width="2.2" stroke-linecap="round"><path d="M3 3l12 12M15 3L3 15"/></svg>
```

## 5. Code

Load the fonts with a `<link>` in `<head>`, then the token variables, then `bundle.css`.

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Onest:wght@400;500;700&family=Playfair+Display:ital,wght@1,400&display=swap">
```

Token variables:

```css
:root, [data-theme="paper"] {
  --paper: #f6f5f1;
  --ink: #111111;
  --muted: #6e6a64;
  --paper-tint: rgba(246, 245, 241, 0.3);
  --paper-clear: rgba(246, 245, 241, 0);
  --white: #ffffff;
  --accent-pink: #f2a7c3;
  --accent-pink-85: #f2a7c3d9;
  --glow-pink-strong: #f2a7c3b3;
  --glow-pink-soft: #f2a7c359;
  --glow-pink-fade: #f2a7c300;
  --glass-dark-top: rgba(34, 34, 36, 0.52);
  --glass-dark-bottom: rgba(14, 14, 16, 0.6);
  --glass-solid-top: rgba(48, 48, 50, 0.92);
  --glass-solid-bottom: rgba(28, 28, 30, 0.92);
  --glass-border: rgba(255, 255, 255, 0.3);
  --glass-border-faint: rgba(255, 255, 255, 0.1);
  --glass-highlight: rgba(255, 255, 255, 0.16);
  --glass-lowlight: rgba(255, 255, 255, 0.05);
  --voice-border: rgba(255, 255, 255, 0.14);
  --on-glass: #ffffff;
  --voice-close: #3a3a3d;
  --voice-x: #b9b9be;
  --photo-1: #dcd7cf;
  --photo-2: #cfc9c0;
  --photo-3: #c4bdb3;
  --photo-4: #b9b2a8;
  --photo-5: #a8a197;
  --photo-label: #2e2b27;
  --margin-side: 68px;
  --header-top: 60px;
  --footer-bottom: 52px;
  --bar-height: 38px;
  --label-top: 146px;
  --field-top: 223px;
  --field-bottom: 1201px;
  --field-width-min: 70%;
  --field-width-max: 90%;
  --photo-gap: 14px;
  --radius-none: 0;
  --radius-pill: 999px;
  --shadow-lift: 0 22px 44px rgba(17, 17, 17, 0.18);
  --shadow-pill: 0 10px 26px rgba(17, 17, 17, 0.24);
  --shadow-voice: 0 16px 36px rgba(17, 17, 17, 0.22);
  --blur-glass: 24px;
  --blur-dissolve: 16px;
  --font-sans: Onest, "Helvetica Neue", Helvetica, sans-serif;
  --font-serif: "Playfair Display", Georgia, "Times New Roman", serif;
}

[data-theme="ink"] {
  --paper: #151413;
  --ink: #f3f1ec;
  --muted: #9e9890;
  --paper-tint: rgba(21, 20, 19, 0.3);
  --paper-clear: rgba(21, 20, 19, 0);
  --glow-pink-strong: #f2a7c380;
  --glow-pink-soft: #f2a7c340;
  --glass-solid-top: rgba(66, 66, 70, 0.92);
  --glass-solid-bottom: rgba(44, 44, 48, 0.92);
  --voice-border: rgba(255, 255, 255, 0.2);
  --voice-close: #4a4a4e;
  --voice-x: #c4c4c9;
  --photo-1: #3a3733;
  --photo-2: #45413c;
  --photo-3: #504b45;
  --photo-4: #5c5650;
  --photo-5: #6a645d;
  --photo-label: #f3f1ec;
  --shadow-lift: 0 22px 44px rgba(0, 0, 0, 0.5);
  --shadow-pill: 0 10px 26px rgba(0, 0, 0, 0.45);
  --shadow-voice: 0 16px 36px rgba(0, 0, 0, 0.5);
}
```

Component styles (`bundle.css`):

```css
@import url("https://fonts.googleapis.com/css2?family=Onest:wght@400;500;700&family=Playfair+Display:ital,wght@1,400&display=swap");
/* The @import only works while this file is its own stylesheet. If you paste it into a
   <style> after other rules, the browser ignores it: add the same URL as a <link> in <head>. */

/* Tanichka Editorial — component styles.
   Every size is written in canvas units: calc(N * var(--u)), where N is the px value
   on the 1080px-wide base canvas. Set --u to (canvas width / 1080) px:
   1080 wide → 1px, 540 wide → 0.5px, 1920-wide 16:9 → 1.7778px. */

:root {
  --u: 1px;
  --glow-strong: radial-gradient(circle, var(--glow-pink-strong) 0%, var(--glow-pink-fade) 68%);
  --glow-soft: radial-gradient(circle, var(--glow-pink-soft) 0%, var(--glow-pink-fade) 66%);
  --glass-dark: linear-gradient(180deg, var(--glass-dark-top), var(--glass-dark-bottom));
  --glass-solid: linear-gradient(180deg, var(--glass-solid-top), var(--glass-solid-bottom));
  --dissolve-tint: linear-gradient(to top, var(--paper-tint), var(--paper-clear));
}

/* ---------- canvas ---------- */
.te-canvas {
  position: relative; overflow: hidden; box-sizing: border-box;
  width: calc(1080 * var(--u)); height: calc(1350 * var(--u));
  background: var(--paper); color: var(--ink);
  font-family: var(--font-sans); text-transform: none;
  -webkit-font-smoothing: antialiased;
}
.te-canvas *, .te-canvas *::before, .te-canvas *::after { box-sizing: border-box; }
.te-canvas--story { height: calc(1920 * var(--u)); }
.te-canvas--square { height: calc(1080 * var(--u)); }

/* ---------- type ---------- */
.te-display {
  margin: 0; font-family: var(--font-sans); font-weight: 700;
  font-size: calc(118 * var(--u)); line-height: 0.98; letter-spacing: -0.045em;
  text-align: left; text-wrap: balance;
}
.te-headline { margin: 0; display: flex; flex-direction: column; align-items: flex-start; gap: calc(14 * var(--u)); }
.te-accent {
  display: block; margin: 0; font-family: var(--font-serif); font-style: italic; font-weight: 400;
  font-size: calc(80 * var(--u)); line-height: 1.1; text-align: left;
}
.te-hl {
  font-family: var(--font-serif); font-style: italic; font-weight: 400;
  font-size: 1.15em; line-height: 1; letter-spacing: 0; color: inherit;
}
.te-label {
  margin: 0; font-family: var(--font-sans); font-weight: 400;
  font-size: calc(40 * var(--u)); line-height: 1; letter-spacing: -0.01em; text-transform: lowercase;
}
.te-meta { font-family: var(--font-sans); font-weight: 400; font-size: calc(30 * var(--u)); line-height: 1; white-space: nowrap; }
.te-body { margin: 0; font-family: var(--font-sans); font-weight: 400; font-size: calc(40 * var(--u)); line-height: 1.75; text-align: center; }
.te-muted { color: var(--muted); }

/* ---------- header & footer ---------- */
.te-header, .te-footer {
  position: absolute; left: calc(68 * var(--u)); right: calc(68 * var(--u));
  height: calc(38 * var(--u));
}
.te-header { top: calc(60 * var(--u)); display: grid; grid-template-columns: 1fr auto 1fr; align-items: center; }
.te-header > :nth-child(3) { justify-self: end; }
.te-footer { bottom: calc(52 * var(--u)); display: flex; align-items: center; justify-content: space-between; }
.te-footer__side { display: flex; align-items: center; gap: calc(16 * var(--u)); }
.te-icon { display: block; flex: none; fill: none; stroke: currentColor; stroke-linecap: round; stroke-linejoin: round; }
.te-icon--bookmark { width: calc(24 * var(--u)); height: calc(30 * var(--u)); stroke-width: 2.4; }
.te-icon--arrow { width: calc(104 * var(--u)); height: calc(22 * var(--u)); stroke-width: 2.2; }

/* ---------- content field ---------- */
.te-field {
  position: absolute; left: 50%; transform: translateX(-50%);
  width: var(--field, 84%); top: calc(146 * var(--u)); bottom: calc(149 * var(--u));
  display: grid; grid-template-rows: calc(40 * var(--u)) 1fr; row-gap: calc(37 * var(--u));
}

/* ---------- photos ---------- */
.te-photo {
  position: relative; overflow: hidden; border-radius: 0; min-width: 0; min-height: 0;
  background: var(--ph, var(--photo-2)); background-size: cover; background-position: center;
}
.te-photo__label {
  position: absolute; left: calc(16 * var(--u)); top: calc(14 * var(--u));
  font: 400 calc(22 * var(--u))/1 var(--font-sans); color: var(--photo-label);
}
.te-photo--scene { /* placeholder with tonal blocks so glass and blur have something to bend */
  background:
    linear-gradient(90deg, transparent 0 58%, var(--photo-5) 58% 80%, transparent 80%) bottom/100% 62% no-repeat,
    linear-gradient(0deg, var(--photo-3) 0 38%, var(--photo-1) 38%);
}
.te-grid { display: grid; gap: calc(14 * var(--u)); height: 100%; grid-template-rows: var(--rows, 2fr 3fr); min-height: 0; }
.te-grid__row { display: grid; gap: calc(14 * var(--u)); grid-template-columns: var(--cols, 1fr 1fr); min-height: 0; }

.te-photo--lift { box-shadow: var(--shadow-lift); } /* one raised photo per slide at most */

/* ---------- glow (one per slide) ---------- */
.te-glow {
  position: absolute; pointer-events: none; aspect-ratio: 1; transform: translate(-50%, -50%);
  background: var(--glow-soft); width: var(--gw, calc(918 * var(--u)));
}
.te-glow--strong { background: var(--glow-strong); width: var(--gw, calc(540 * var(--u))); }

/* ---------- frosted pill (one glass element per slide) ---------- */
/* Proportions are in em of the pill text, so the shape holds at any size:
   height ≈ 2.8em, left pad 0.95em, dot 0.32em, dot→text 0.72em, right pad 1.55em. */
.te-frost {
  position: relative; display: inline-flex; align-items: center; gap: 0.72em;
  font: 500 calc(24 * var(--u))/1 var(--font-sans); letter-spacing: -0.01em;
  padding: 0.9em 1.55em 0.9em 0.95em;
  border-radius: var(--radius-pill); background: var(--glass-dark);
  -webkit-backdrop-filter: blur(calc(24 * var(--u))) saturate(120%);
  backdrop-filter: blur(calc(24 * var(--u))) saturate(120%);
  box-shadow: inset 0 1px 0 var(--glass-highlight), inset 0 -1px 0 var(--glass-lowlight), var(--shadow-pill);
  color: var(--on-glass); white-space: nowrap;
}
/* thin 1px rim: brightest at the top-left, fading along the sides, catching light again at the bottom-right */
.te-frost::before {
  content: ""; position: absolute; inset: 0; border-radius: inherit; padding: 1px; pointer-events: none;
  background: linear-gradient(115deg, var(--glass-border) 0%, var(--glass-border-faint) 38%, var(--glass-border-faint) 68%, var(--glass-border) 100%);
  -webkit-mask: linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0);
  -webkit-mask-composite: xor; mask-composite: exclude;
}
.te-frost .te-dot { width: 0.32em; height: 0.32em; box-shadow: 0 0 0.45em var(--accent-pink); }
/* on a photo: no fixed spot. Default is bottom-centre; set --pill-x / --pill-y to put it in the calmest empty area of that photo */
.te-photo > .te-frost { position: absolute; left: var(--pill-x, 50%); bottom: var(--pill-y, calc(28 * var(--u))); transform: translateX(-50%); }
.te-dot {
  flex: none; width: calc(12 * var(--u)); height: calc(12 * var(--u)); border-radius: 50%;
  background: var(--accent-pink); box-shadow: 0 0 calc(10 * var(--u)) var(--accent-pink);
}

/* ---------- blur dissolve (one photo) ---------- */
.te-dissolve {
  position: absolute; left: 0; right: 0; bottom: 0; height: 45%; pointer-events: none;
  background: var(--dissolve-tint);
  -webkit-backdrop-filter: blur(calc(16 * var(--u))); backdrop-filter: blur(calc(16 * var(--u)));
  -webkit-mask-image: linear-gradient(to top, #000 35%, transparent); mask-image: linear-gradient(to top, #000 35%, transparent);
}

/* ---------- voice pill ---------- */
.te-voice {
  display: inline-flex; align-items: center; gap: calc(24 * var(--u));
  padding: calc(12 * var(--u)) calc(12 * var(--u)) calc(12 * var(--u)) calc(30 * var(--u));
  border-radius: var(--radius-pill); background: var(--glass-solid);
  border: 1px solid var(--voice-border);
  box-shadow: inset 0 1px 0 var(--voice-border), var(--shadow-voice);
}
.te-voice .te-dot { width: calc(14 * var(--u)); height: calc(14 * var(--u)); }
.te-wave { display: flex; align-items: center; gap: calc(7 * var(--u)); height: calc(40 * var(--u)); }
.te-wave__bar { display: block; flex: none; width: calc(5 * var(--u)); height: calc(var(--h, 24) * var(--u)); border-radius: var(--radius-pill); background: var(--accent-pink); }
.te-wave__dot { display: block; flex: none; width: calc(6 * var(--u)); height: calc(6 * var(--u)); border-radius: 50%; background: var(--accent-pink); opacity: var(--o, 0.7); }
.te-voice__close {
  flex: none; display: grid; place-items: center; width: calc(56 * var(--u)); height: calc(56 * var(--u));
  border-radius: 50%; background: var(--voice-close); color: var(--voice-x);
}
.te-voice__close svg { width: calc(18 * var(--u)); height: calc(18 * var(--u)); fill: none; stroke: currentColor; stroke-width: 2.2; stroke-linecap: round; }

/* ---------- CTA block ---------- */
.te-cta { position: relative; display: flex; flex-direction: column; align-items: center; gap: calc(44 * var(--u)); }
.te-cta > .te-glow { left: 50%; top: 50%; z-index: 0; }
.te-cta > :not(.te-glow) { position: relative; z-index: 1; }
```
