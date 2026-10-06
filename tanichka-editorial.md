# Tanichka Editorial

Brand basics for @tanii444.ka: colours and type. Nothing else. Use them for posts, carousels, stories, covers, slides and reels.

Last updated: 2026-10-06

This file has no components, templates, cards, icons or effects on purpose. Each format decides its own layout. The video rules live in `reel-stylebook.md`, built on these colours and fonts. Both files are exported from the design system: change them there first, then export.

## 1. Feel

Minimal fashion-editorial: off-white paper, black type, and real photos or footage doing all the colour work. Calm, airy, a little playful, with one soft pink accent. Never a tech dashboard. Leave generous empty space; never fill edge to edge.

Words: short, lowercase, friendly and direct, like texting a friend. Ukrainian or English. Brand names keep their own spelling (Claude, Figma). No all-caps, no underlines, no emoji. The handle is always `@tanii444.ka`.

## 2. Colour

Two themes share one set of names. Pick one theme per post, carousel or reel; never mix them.

| Token | Paper (light, default) | Ink (dark) | Use |
| --- | --- | --- | --- |
| `paper` | #F6F5F1 warm off-white | #151413 warm black | The only background colour. Never pure black |
| `ink` | #111111 | #F3F1EC | All text, icons and lines on paper (17.3:1 / 16.3:1) |
| `muted` | #6E6A64 | #9E9890 | Secondary notes only (4.9:1 / 6.4:1). Never headlines |
| `white` | #FFFFFF | #FFFFFF | Text on photos and video. Never a card, panel, band or frame fill |
| `accent-pink` | #F2A7C3 | #F2A7C3 | The one accent: small dots and the voice waveform. Never text, never a background or fill |

- Photos and footage carry the colour.
- No other colours, no coloured backgrounds, no gradients, no neon.
- Switch a whole page or canvas to Ink with `data-theme="ink"`.

```css
:root, [data-theme="paper"] {
  --paper: #f6f5f1;
  --ink: #111111;
  --muted: #6e6a64;
  --white: #ffffff;
  --accent-pink: #f2a7c3;
}
[data-theme="ink"] {
  --paper: #151413;
  --ink: #f3f1ec;
  --muted: #9e9890;
}
```

## 3. Type

Two free Google fonts (OFL), both with Cyrillic. Never Inter, Roboto or Arial, not even as a fallback.

`https://fonts.googleapis.com/css2?family=Onest:wght@400;500;700&family=Playfair+Display:ital,wght@1,400&display=swap`

| Role | Font | Size on a 1080-wide canvas | Notes |
| --- | --- | --- | --- |
| `display` | Onest 700, lh 0.98, ls -0.045em | 118px on paper (smaller on photos and video, to fit the space) | Left-aligned, max 2 lines. The only bold. Never centred |
| `accent-line` | Playfair Display Italic 400, lh 1.1 | about 68% of the display | Optional last line of a title, flush left under it, 14px gap |
| `highlight` | Playfair Display Italic 400 | 115% of its sentence | One key word in a line, same colour. Brand names like Claude |
| `body` | Onest 400, lh 1.75 | 40px | Short lines, never dense blocks |
| `label` / `meta` | Onest 400 (500 for small text on photos) | 30–40px | Handles, small labels, page numbers |

- Everything sits straight: no tilted or rotated text.
- Sizes scale with the canvas width. Other formats (9:16 story, square, 16:9) keep the same proportions.

## 4. Never

- Cards, frames, polaroids, tape, borders, boxes, rounded panels or bands behind text.
- Moving, shrinking or cropping a photo or video to make room for text. If text doesn't fit, make it smaller, use fewer words, move it, or leave it out.
- Hearts, emoji, filled or 3D icons, heavy 3D renders.
- Pink text or pink fills.
