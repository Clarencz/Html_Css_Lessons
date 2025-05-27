The position Property in CSS
What Does position Do?
The position property in CSS determines how an element is placed in the document — whether it flows naturally with other elements, or is pulled out of the normal flow and placed exactly where you want it. It changes how and where an element is rendered on the page.

The 5 Main Values of position:
static Default position — normal flow
relative Offset relative to its normal position
absolute Removed from flow, positioned relative to nearest positioned ancestor
fixed Stuck to viewport, stays even when scrolling
sticky Scrolls with page, but sticks when reaching a position

We'll now explain each in depth, with clear examples.

1. position: static (The Default)
   This is the default position for every element. The element stays in the normal document flow — meaning it appears in order, one after the other, based on the HTML. You cannot use top, left, right, or bottom with it.
   Example:
   div {
   position: static;
   }
   The element will sit wherever it naturally lands based on the HTML structure and block/inline rules.

2. position: relative
   Element stays in the document flow, but you can move it visually using top, left, right, or bottom. The space it originally occupied is not taken away — it stays reserved. Positioning is relative to its normal spot.
   Example:
   .box {
   position: relative;
   top: 20px;
   left: 40px;
   }
   This moves the element down 20px and right 40px, but it still "holds" its original space in the layout. Useful for making small shifts or defining a reference point for absolutely positioned children.

3. position: absolute
   Removed from normal document flow — doesn’t affect surrounding elements.
   Positioned relative to the nearest ancestor that is positioned (not static). If no such ancestor exists, it's positioned relative to the html document (viewport).
   Example:
   .container {
   position: relative;
   }
   .box {
   position: absolute;
   top: 0;
   left: 0;
   }
   This places .box at the top-left of the .container. If .container wasn’t relatively positioned, .box would be positioned relative to the entire page.
   Use this for popups, tooltips, badges, or elements that should "float" inside a container.

4. position: fixed
   Completely removed from the document flow. Positioned relative to the browser viewport (not any element). Doesn’t move when the page scrolls.
   Useful for headers, sidebars, floating buttons, or sticky navbars.
   Example:
   .floating {
   position: fixed;
   bottom: 20px;
   right: 20px;
   }
   This element will always be visible in the bottom-right corner of the screen, even while scrolling.

5. position: sticky
   Combines relative and fixed behavior. Element behaves like relative until you scroll past it. Then it sticks to a position in the viewport (like top: 0) until its container is scrolled past.
   Example:
   .sticky-header {
   position: sticky;
   top: 0;
   background: white;
   }
   This will stay at the top of the page while scrolling, but only within its container. Sticky only works when the parent container has enough height to scroll.
   What Do top, right, bottom, left Do?
   These properties are used with relative, absolute, fixed, and sticky positions.
   Property Moves Element...
   top Down from the top
   left Right from the left
   right Left from the right side
   bottom Up from the bottom
   They define offsets from the reference edge — based on the positioning context.

Common Mistakes:
Absolute element isn’t appearing in expected place No ancestor has position: relative Add position: relative to parent
Sticky not working Not enough content to scroll or overflow hidden Ensure parent has height and allows overflow
top, left have no effect position: static Must use relative, absolute, fixed, or sticky
Fixed element blocks content No spacing reserved Add padding/margin to layout to adjust

Advanced Tip: z-index Works With Positioned Elements
z-index controls stacking order (which element appears on top). Only applies to non-static elements (relative, absolute, fixed, sticky).
css:
.box {
position: absolute;
z-index: 10;
}

Recap:
position controls layout mode Defines how and where an element is rendered
relative is a reference parent for absolute Keeps it in the document but lets you shift
absolute floats away from flow Useful for exact placement
fixed sticks to the screen Doesn’t move on scroll
sticky scrolls until fixed Great for modern UI/UX patterns
