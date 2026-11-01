# Motion

Motion is the easiest way to look busy and the hardest to get right, so the default answer is no.

## Should it move at all

Ask how often someone sees it. A once-only welcome can be slow and lovely. Something seen every minute should be instant, and anything triggered by a keyboard shortcut should not animate. Then ask what it explains: where something came from, what changed, that a press was received. If the answer is "it looks nice", it is decoration, so allow one such thing per page and spend it well.

The signature mistake of generated pages is fade-and-rise on every section as it scrolls in. It delays reading, and it hides content if a script fails. Leave content visible by default.

## One signature

Pick the single motion this page is remembered for, drawn from the material: a split-flap board settling, a pencil line drawing itself, a number rolling once. Make it good, then leave the rest alone.

## Numbers

| What | Duration |
|---|---|
| Press feedback, hover, toggles | 80 to 150 ms |
| Small things appearing: tooltip, menu, dropdown | 150 to 220 ms |
| Larger things: dialog, drawer, panel | 200 to 320 ms |
| A once-only entrance, a hero | 400 to 800 ms |

- Leaving is faster than arriving, about two-thirds of the time.
- Arriving things ease out, so they respond at once and settle: something like `cubic-bezier(0.2, 0.8, 0.2, 1)`. Things moving across the screen ease in and out. `linear` is for loops, progress and marquees.
- Avoid bounce and overshoot in interfaces unless the voice of the page is playful and it is one element.
- Stagger lists only slightly, 30 to 50 ms a step, and cap the total. Nobody should wait for the tenth item.

## Mechanics

- Animate `transform` and `opacity`. Animating `width`, `height`, `top` or `box-shadow` makes the browser redo layout or paint on every frame.
- Use CSS transitions for things a person can interrupt, because they retarget from the current position. Keyframes restart.
- Press effects should scale very slightly, about 0.97. Hover lift is a cliché; change a colour or a line instead.
- Honour `prefers-reduced-motion`: swap travel for a short fade or nothing, and stop anything that loops.

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

- Make sure the page is correct and readable with scripts off and with the animation at its first frame.
- Add a heavy animation library only for what CSS cannot do. If a piece needs one, tell the user the dependency and its licence.
