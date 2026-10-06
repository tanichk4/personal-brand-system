# Tanichka Editorial

Brand basics for @tanii444.ka: colours, type and five signature elements (frosted glass pill, glow, text glow, blur dissolve, handle tag). Use them for posts, carousels, stories, covers, slides and reels.

Last updated: 2026-10-06

This file has no carousel kit on purpose: no templates, header or footer rows, bracket tags, icons, photo cards or voice pill. Each format decides its own layout. The video rules live in `reel-stylebook.md`, built on these colours and fonts. Both files are exported from the design system: change them there first, then export.

## 1. Feel

Minimal fashion-editorial: off-white paper, black type, and real photos or footage doing all the colour work. Calm, airy, a little playful, with one soft pink accent and a few soft depth touches (frosted glass, a glow, a soft text glow, a blur dissolve) used as seasoning. Never a tech dashboard. Leave generous empty space; never fill edge to edge.

Words: short, lowercase, friendly and direct, like texting a friend. Ukrainian or English. Brand names keep their own spelling (Claude, Figma). No all-caps, no underlines, no emoji. The handle is always `@tanii444.ka`.

## 2. Colour

Two themes share one set of names. Pick one theme per post, carousel or reel; never mix them.

| Token | Paper (light, default) | Ink (dark) | Use |
| --- | --- | --- | --- |
| `paper` | #F6F5F1 warm off-white | #151413 warm black | The only background colour. Never pure black |
| `ink` | #111111 | #F3F1EC | All text, icons and lines on paper (17.3:1 / 16.3:1) |
| `muted` | #6E6A64 | #9E9890 | Secondary notes only (4.9:1 / 6.4:1). Never headlines |
| `white` | #FFFFFF | #FFFFFF | Text on photos and video. Never a card, panel, band or frame fill |
| `accent-pink` | #F2A7C3 | #F2A7C3 | The one accent: the pill dot, the glow and the faint halo in the text glow. Never text, never a background or fill |

- Photos and footage carry the colour.
- No other colours, no coloured backgrounds, no neon. The only gradients and soft shadows are the glass fill, the two glows, the text glow, the text haze and the dissolve tint (section 4).
- Switch a whole page or canvas to Ink with `data-theme="ink"`.

```css
:root, [data-theme="paper"] {
  --paper: #f6f5f1;
  --ink: #111111;
  --muted: #6e6a64;
  --white: #ffffff;
  --accent-pink: #f2a7c3;
  --glow-pink-strong: #f2a7c3b3;
  --glow-pink-soft: #f2a7c359;
  --glow-pink-fade: #f2a7c300;
  --glass-dark-top: rgba(34, 34, 36, 0.52);
  --glass-dark-bottom: rgba(14, 14, 16, 0.6);
  --glass-border: rgba(255, 255, 255, 0.3);
  --glass-border-faint: rgba(255, 255, 255, 0.1);
  --glass-highlight: rgba(255, 255, 255, 0.16);
  --glass-lowlight: rgba(255, 255, 255, 0.05);
  --on-glass: #ffffff;
  --paper-tint: rgba(246, 245, 241, 0.3);
  --paper-clear: rgba(246, 245, 241, 0);
  --shadow-pill: 0 10px 26px rgba(17, 17, 17, 0.24);
  --text-glow: 0 0 6px rgba(255,255,255,0.35), 0 0 18px rgba(255,255,255,0.18), 0 0 40px rgba(242,167,195,0.14);
  --text-haze-1: 0 0 14px rgba(17,17,17,0.4), 0 0 36px rgba(17,17,17,0.22);
  --text-haze-2: 0 0 10px rgba(17,17,17,0.55), 0 0 28px rgba(17,17,17,0.35), 0 0 56px rgba(17,17,17,0.18);
}
[data-theme="ink"] {
  --paper: #151413;
  --ink: #f3f1ec;
  --muted: #9e9890;
  --glow-pink-strong: #f2a7c380;
  --glow-pink-soft: #f2a7c340;
  --paper-tint: rgba(21, 20, 19, 0.3);
  --paper-clear: rgba(21, 20, 19, 0);
  --shadow-pill: 0 10px 26px rgba(0, 0, 0, 0.45);
  --text-glow: 0 0 24px rgba(242, 167, 195, 0.22);
}
```

## 3. Type

Two free Google fonts (OFL), both with Cyrillic. Never Roboto or Arial, not even as a fallback. Inter replaced Onest on 2026-10-06.

`https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&family=Playfair+Display:ital,wght@1,400&display=swap`

| Role | Font | Size on a 1080-wide canvas | Notes |
| --- | --- | --- | --- |
| `display` | Inter 700, lh 0.98, ls -0.045em | 118px on paper (smaller on photos and video, to fit the space) | Left-aligned, max 2 lines. The only bold. Never centred |
| `accent-line` | Playfair Display Italic 400, lh 1.1 | 68% of the display, so it scales with it | Optional last line of a title, flush left under it, 14px gap |
| `highlight` | Playfair Display Italic 400 | 115% of its sentence | One key word in a line, same colour. Brand names like Claude |
| `body` | Inter 400, lh 1.75 | 40px | Short lines, never dense blocks |
| `label` / `meta` | Inter 400 (500 for small text on photos) | 30–40px | Handles, small labels, page numbers |

- Everything sits straight: no tilted or rotated text.
- Sizes scale with the canvas width. Other formats (9:16 story, square, 16:9) keep the same proportions.

## 4. Signature elements

Five touches that make it look like you. Restraint: at most one glass element (frosted pill or blur dissolve) and one glow per slide, page or screen. Most get none.

### Frosted glass pill

A smoky, see-through glass pill on a photo or video, for one short fact or a status ("Claude думає…", "6 категорій поз").

- Fill: `glass-dark-top` → `glass-dark-bottom` (linear 180°), over a 24px backdrop blur + saturate 120%, so the picture behind melts into smooth colour. Fully rounded.
- Rim: 1px, brightest at the top-left and bottom-right (`glass-border`), dimmer along the long sides (`glass-border-faint`). Inner top highlight `glass-highlight`, inner bottom edge `glass-lowlight`. Shadow `shadow-pill`.
- Pink dot on the left (0.32em, own soft glow), then the text in Inter 500, `on-glass` white, 22–26px on a 1080 canvas (larger on video).
- Proportions in em of the text: height about 2.8em, padding 0.9em 1.55em 0.9em 0.95em, dot to text 0.72em.
- Only on photos or video, never on paper. No fixed spot: the calmest empty area, never on a face or hands.

### Glow

One large soft pink radial circle behind the single focal point.

- `glow-soft`: `glow-pink-soft` → transparent by 66%, about 85% of the canvas width, behind a focal photo.
- `glow-strong`: `glow-pink-strong` → transparent by 68%, about 50% of the canvas width, behind a call to action.
- It may sit behind a title or a call to action. Never more than one at a time.

### Text glow

A very soft, slightly wet-looking light around accent text, so it doesn't feel flat. In motion-design terms: a light **bloom** (a soft haze of the text's own colour) with a hint of warm **halation** (a faint pink fringe).

- Use on accent text only: display titles, the accent line, the highlight (keyword) word, pill text, a one-word beat and the CTA keyword. Never on every word, never on body text or regular captions, so it stays special.
- On white text over photos or video: `text-glow` = `0 0 6px rgba(255,255,255,0.35), 0 0 18px rgba(255,255,255,0.18), 0 0 40px rgba(242,167,195,0.14)`.
- On ink text over paper: only the faint pink halo, `0 0 24px rgba(242,167,195,0.22)`.
- It must stay subtle: the letters stay sharp, and the haze is barely visible on a phone.

### Text haze (for reading, not a signature)

When white text sits on a bright photo or video, it keeps its colour and gets a soft dark haze behind the letters instead: a wide blur with no offset and no edges, never a box or a band. Text never switches colour to fit one picture.

- `text-haze-1` (a little help) and `text-haze-2` (bright spots). For ink text on a dark picture, use the same values in `paper` colour.
- You must not be able to see where it ends. If you can, it is too strong.
- The video rules decide when to use it (`reel-stylebook.md` section 1.6).

### Blur dissolve

A blur that melts upward from the bottom of one photo, as if it dissolves into the paper. Also the soft blur transition between video sections.

- Bottom 45% of the photo: 16px backdrop blur plus a faint paper tint (`paper-tint` → `paper-clear`), masked `linear-gradient(to top, #000 35%, transparent)`.
- One photo only; counts as the glass element, so never alongside a frosted pill.
- On video it is only the transition between sections, never a blurred strip left over the footage.

### Handle tag

`@tanii444.ka` in Inter 400 (`meta`), lowercase, `ink` on paper or white on photos and video. Small and quiet, in a calm spot. It is the signature, not a logo bug.

```css
:root {
  --glow-strong: radial-gradient(circle, var(--glow-pink-strong) 0%, var(--glow-pink-fade) 68%);
  --glow-soft: radial-gradient(circle, var(--glow-pink-soft) 0%, var(--glow-pink-fade) 66%);
  --glass-dark: linear-gradient(180deg, var(--glass-dark-top), var(--glass-dark-bottom));
  --dissolve-tint: linear-gradient(to top, var(--paper-tint), var(--paper-clear));
}
.te-frost {
  position: relative; display: inline-flex; align-items: center; gap: 0.72em;
  font: 500 24px/1 Inter, sans-serif; letter-spacing: -0.01em; color: var(--on-glass);
  padding: 0.9em 1.55em 0.9em 0.95em; border-radius: 999px; background: var(--glass-dark);
  -webkit-backdrop-filter: blur(24px) saturate(120%); backdrop-filter: blur(24px) saturate(120%);
  box-shadow: inset 0 1px 0 var(--glass-highlight), inset 0 -1px 0 var(--glass-lowlight), var(--shadow-pill);
  white-space: nowrap;
}
.te-frost::before {
  content: ""; position: absolute; inset: 0; border-radius: inherit; padding: 1px; pointer-events: none;
  background: linear-gradient(115deg, var(--glass-border) 0%, var(--glass-border-faint) 38%, var(--glass-border-faint) 68%, var(--glass-border) 100%);
  -webkit-mask: linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0);
  -webkit-mask-composite: xor; mask-composite: exclude;
}
.te-dot { flex: none; width: 0.32em; height: 0.32em; border-radius: 50%; background: var(--accent-pink); box-shadow: 0 0 0.45em var(--accent-pink); }
.te-glow { position: absolute; pointer-events: none; aspect-ratio: 1; transform: translate(-50%, -50%); background: var(--glow-soft); width: 918px; }
.te-glow--strong { background: var(--glow-strong); width: 540px; }
.te-text-glow { text-shadow: var(--text-glow); } /* accent text only: titles, accent line, keyword, pill text */
.te-text-haze { text-shadow: var(--text-haze-1); } /* readability on bright pictures; --text-haze-2 for the brightest */
.te-dissolve {
  position: absolute; left: 0; right: 0; bottom: 0; height: 45%; pointer-events: none;
  background: var(--dissolve-tint);
  -webkit-backdrop-filter: blur(16px); backdrop-filter: blur(16px);
  -webkit-mask-image: linear-gradient(to top, #000 35%, transparent); mask-image: linear-gradient(to top, #000 35%, transparent);
}
```

## 5. Never

- Cards, frames, polaroids, tape, borders, boxes, rounded panels or bands behind text.
- Moving, shrinking or cropping a photo or video to make room for text. If text doesn't fit, make it smaller, use fewer words, move it, or leave it out.
- The voice-message pill with the waveform, header and footer rows, bracket tags, icons, photo grids, slide templates.
- Hearts, emoji, filled or 3D icons, heavy 3D renders.
- Pink text or pink fills.
