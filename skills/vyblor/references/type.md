# Type

Type is most of what a page looks like, so choose it first. If there is Korean on the page, read [korean.md](korean.md) too.

## Choosing

Find the display voice in the material from the brief. A freight company's container markings suggest a stencil or a condensed grotesque. A law office suggests a text serif set with care. A children's clinic suggests a rounded face with real warmth, not a geometric sans in a pastel. A serif is not a shortcut to taste: on a page with no reason for one, it reads as the same default as Inter, only warmer.

Ask of any font: what would this have been printed on? If the answer is "a slide deck", keep looking.

- Inter, Roboto, Arial and the system stack are good text faces and poor voices. Use one for body text if you like, never as the only idea.
- Fonts that became the second reflex (Space Grotesk, Poppins, Outfit, DM Sans, Playfair over a sans) are not banned, but picking one must be a decision. Name why it fits this subject.
- Two families are enough. A third is allowed for numbers or code when the page is about numbers or code.
- Check the licence before you ship a font, and self-host when you can. A blocked font service leaves you with fallback metrics and a jumping page.

## Size

Set body text at 16 to 18 px for reading pages, 14 to 15 px for dense tools. Then make contrast between levels obvious. A timid scale is the commonest reason a page looks flat.

- Marketing pages: a ratio around 1.5 between steps, with the hero at three to six times the body. Use `clamp()` so it scales between phone and desktop, and test the phone size on the real headline.
- App screens: a ratio around 1.2. Hierarchy comes from weight, colour and position more than size.
- Use fewer sizes than you think. Five is usually enough for a whole site.

## Details

- Line length 55 to 75 characters for Latin text.
- Line height falls as size rises: 1.5 to 1.7 for body, 1.0 to 1.2 for large display.
- Tighten tracking only at large sizes, and only a little: about -0.01em to -0.03em. Leave body text alone.
- Two or three weights. If headings are 700 and everything else is 400, nothing else needs to exist.
- `font-variant-numeric: tabular-nums` wherever numbers line up: prices, tables, timers.
- `text-wrap: balance` on headings, `text-wrap: pretty` on paragraphs.
- Load only the weights you use, and use `font-display: swap` with a fallback of similar width.
- Do not fake a weight or a slant the font lacks. Set `font-synthesis: none` and check.
