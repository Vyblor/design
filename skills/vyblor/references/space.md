# Space and composition

## Scale

Pick one base unit, usually 4 px, and a short scale such as 4, 8, 12, 16, 24, 32, 48, 64, 96, 128. Use `gap` over margins.

The rule that does most of the work: **things that belong together sit at about half the distance of things that do not.** A heading sits closer to its paragraph than to the section above it. If every gap is 24 px, nothing belongs to anything.

Sections on marketing pages need more room than feels safe: 96 to 160 px on a desktop, 64 to 96 px on a phone. Then vary it. Identical section padding down a whole page is itself a tell.

## Composition

The default page is one centred column of stacked bands. Break it at least once, on purpose.

- Offset the content on a 12-column grid: heading in columns 1 to 5, text in 7 to 12.
- Let one thing run full-bleed, or cross the edge of the screen and crop.
- Replace a card row with a table, a timeline, a ruled list or a single long sentence.
- Overlap two elements, once, with intent.
- Change density between sections: an airy statement, then a tight data block.

Keep alignment strict while doing this. Odd placement reads as designed only when the edges still line up.

## Cards

Most cards should not exist. A card says "these are comparable, separate objects". Products in a shop are. Three selling points are not.

Before adding a box, try a line, or space alone. Never put a card inside a card. Boxes around everything flatten the hierarchy, because everything has the same frame.

## Radii, borders, shadows

- Decide one radius language for the whole page. Sharp, 0 to 4 px, reads printed and editorial. Soft, 8 to 12 px, reads like a product. Pills are for tags and nothing else, unless a very round voice is the idea.
- A nested corner should be the outer radius minus the padding, or it will look pinched.
- Use a border or a shadow, not both. A shadow belongs only on something truly above the page: a menu, a dialog, a dragged item.

## Hierarchy

One primary action per view. Everything else looks secondary, and most things need no button at all. Size, weight, colour and position are one budget: use two to mark something important, because all four shouts.

## Images

- Real product first. Show the actual interface, photograph or object.
- With no images available, build from type, rules and colour, or draw a specific SVG for this subject. Do not fill the gap with gradient blobs, abstract 3D shapes or dot grids.
- Set `width` and `height` or `aspect-ratio` so nothing jumps, and write alt text that says what the image shows.

## Phones

Design the phone version as its own layout. Stacking the desktop version in order is usually wrong: the most useful thing may need to come first. Use `100dvh` rather than `100vh`, keep tap targets at 44 px at least, and check 360 and 390 wide for sideways scroll.
