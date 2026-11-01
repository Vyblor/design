# States

A screenshot shows one state. People live in the others. Finishing these is what separates a page that looks designed from a product that is.

## Every control

| State | Note |
|---|---|
| Default | Plain and legible at rest. |
| Hover | Only under `@media (hover: hover)`, or it sticks on touch screens. |
| Focus | `:focus-visible` with a clear ring in 3 to 1 contrast. Never remove the outline without replacing it. |
| Pressed | Immediate, within 100 ms. Slight scale or a tone change. |
| Disabled | Clearly inactive. Better still, leave it enabled and explain the problem on press. |
| Busy | Keeps its width, shows progress and blocks a second submit. |

Tap targets are 44 px at least, even when the visible shape is smaller. Use real `<button>` and `<a>` elements. A clickable `<div>` fails at the keyboard and the screen reader.

## Every list and data view

Test with zero, one, a normal number, and a great many.

- **Empty.** Say what will appear here and give the next step. An empty state is the first thing a new user sees, so it deserves real copy, and not a large grey illustration.
- **Loading.** Skeletons in the shape of the real content when the wait is over about 300 ms, nothing when it is shorter. A centred spinner over a blank page is the last resort.
- **Failure.** Say what happened and offer a retry. Keep the rest of the screen working.
- **Long content.** Try a 40-character name, an unbroken email address, a very large number, and a one-letter name. Decide where each truncates, and show the full value somewhere.

## Forms

- A visible label above every field. Placeholders disappear on typing, so they are never the label.
- Use the right `type`, `inputmode` and `autocomplete`, so phones show the right keyboard and browsers can fill it in.
- Inputs use 16 px text at least on phones, or iOS zooms the page on focus.
- Validate on leaving a field or on submit, not on every keystroke.
- Put the error beside the field, say how to fix it, link it with `aria-describedby`, and keep everything typed.
- After a submit, say clearly what happened and what comes next.

## Dialogs and menus

Use the native `<dialog>` where you can. It gives a focus trap and Escape for free. Return focus to the opener on close. Menus close on outside press and on Escape.

## Whole pages

- Check 360, 390, 768 and 1440 wide, with no sideways scroll at any.
- Respect `prefers-reduced-motion`, and offer dark mode only if you designed one.
- Test a slow connection once. Reserve image space, and do not let web fonts move the layout.
- Semantic headings in order, one `h1`, landmarks, and a skip link on long pages.
