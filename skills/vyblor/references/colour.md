# Colour

## Starting

Take the main hue from the material, not from a framework's palette. The first colours that come to mind for any tech product are indigo, violet and a blue-to-purple blend; if the subject does not demand them, they are off the table. The same goes for Tailwind's default ramps used as they come: `indigo-500`, `slate-900`, `gray-500` read as "nobody chose this".

Decide how loud the page is, then commit:

- **Quiet:** paper and ink plus one accent, used for the primary action and little else. Under a tenth of the surface.
- **Loud:** one strong colour taking a large share of the page, a third or more, with type set straight on it.
- **In between** is the danger zone: pale tints in every section and a medium accent on everything. That is the template look.

## Tokens

Write these before the first component, as CSS custom properties, and use nothing else:

```css
:root {
  --bg: ...;        /* the page */
  --surface: ...;   /* raised or set-apart areas */
  --ink: ...;       /* main text */
  --muted: ...;     /* secondary text, must still pass contrast */
  --line: ...;      /* rules and borders */
  --accent: ...;    /* the one colour */
  --on-accent: ...; /* text on the accent */
}
```

Any hex in a component is a bug, unless the piece is a picture.

## Neutrals

Pure `#fff` and `#000` with pure grey between them is the coldest possible start. Tint every neutral a few degrees toward the main hue. In OKLCH this is a chroma of about 0.005 to 0.02 at the same hue, which is invisible as a colour and very visible as warmth or coolness. Off-white backgrounds and very dark inks that are not black do more than any accent.

Use OKLCH for ramps, because equal steps in lightness look equal.

## Contrast

- Body text 4.5 to 1 at least. Large text and interface edges 3 to 1.
- Check `--muted` and text on the accent specifically. These are the ones that fail.
- Grey text on a coloured background usually looks dirty. Use a darker or lighter tone of that background instead.

## Meaning

Keep error, warning and success apart from the brand colour. A red brand needs a different way to say "error": an icon and words, not colour alone. Never carry meaning by colour alone in any case.

## Dark mode

A dark theme is another palette, not an inversion.

- Page background around 12 to 18 percent lightness, not black, tinted like the light neutrals.
- Depth comes from lighter surfaces. Shadows barely show on dark.
- Lower the chroma of the accent a little so it does not vibrate.
- Body text slightly off-white, and slightly heavier than feels necessary if the font is thin.
