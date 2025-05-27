What is a Border in CSS?
A border is a line drawn around the edge of an HTML element’s box. It sits between the element’s content (and padding) and its margin. Used for visual separation, emphasis, decorative boxes, and interactive cues. Think of it like a picture frame around a content box.

1. The Box Model: Where Borders Live
   Borders are part of the CSS box model:
   Margin
   Border
   Padding
   Content
   So, when you apply a border: It affects the size of the element unless using box-sizing: border-box. It visually wraps around the padding and content.

2. Border Properties
   CSS allows you to define borders in parts or all at once.
   The 3 Core Border Properties:
   border-width
   border-style
   border-color
   Example:
   div {
   border-width: 2px;
   border-style: solid;
   border-color: blue;
   }
   Shorthand:
   div {
   border: 2px solid blue;
   }
   Order: border: [width] [style] [color];
   All 3 values are required when using shorthand, or the border may not render.

3. Border Styles — The Visual Types
   none - No border (default)
   solid - A single solid line
   dashed - A series of short dashes
   dotted - A series of small dots
   double - Two parallel lines
   groove - Carved/3D effect (depends on color)
   ridge - Raised 3D effect (inverse of groove)
   inset - Sunken box effect (looks pressed in)
   outset Raised box effect (looks popped out)
   hidden - Like none, but used in table border conflict resolution
   These are visual styles — use them to create effects, emphasis, or UI states (e.g. focus, hover, selection).

4. Border Sides
   You can style each side of an element separately.
   border-top = Top side border-top: 2px solid red;
   border-right = Right side
   border-bottom = Bottom side
   border-left = Left side

You can also control width, color, and style independently for each side:
div {
border-top-style: dashed;
border-bottom-width: 5px;
border-left-color: green;
} 5. Border Width
px - Fixed pixel width
em, rem - Relative to font-size
thin, medium, thick - Predefined keywords

Example:
border-width: 1px 2px 3px 4px; /_ top right bottom left _/ 6. Border Color
Can be any valid CSS color (named, hex, rgb, etc.) Default color is the text color (currentColor)
Examples:
border-color: red;
border-color: red green blue yellow; /_ top right bottom left _/ 7. Border Shorthand
One-line definition:
border: 2px dotted teal;
Per-side:
border-left: 5px solid purple;
border-top: 3px dashed gray; 8. Rounded Corners- (border-radius)
Rounded borders are done using border-radius.
Example:
div {
border: 2px solid black;
border-radius: 10px;
}
Works on all 4 corners. Accepts single or multiple values

border-radius: 10px 20px 30px 40px; /_ TL, TR, BR, BL _/
You can create circles using:
border-radius: 50%; 9. Advanced Border Tricks
A. Colored Borders with Transparent Background:
div {
border: 4px solid tomato;
background-color: transparent;
}
B. Apply Borders Only on Hover:
button:hover {
border: 2px solid lime;
}
C. Gradient Border (with workaround using background-clip):
div {
border: 5px solid transparent;
background: linear-gradient(white, white), linear-gradient(to right, red, blue);
background-clip: padding-box, border-box;
background-origin: border-box;
} 10. Use Cases of Borders
Emphasis Highlight a section or button
Separation Border between card elements
Decoration Dashed lines, double frames
Interaction feedback Input focus states (:focus)
Layout guides Developer debugging visual boxes

Recap Table
border Full border shorthand
border-style Controls the visual line style
border-width Sets thickness of the line
border-color Defines border color
border-radius Adds curvature to corners
border-[side] Applies to top, right, bottom, or left
