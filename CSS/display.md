The display Property in CSS
What is display? The display property in CSS determines how an element is displayed in the document layout.
It controls:
Whether the element starts on a new line
How it takes up space (width/height)
Whether it behaves like a box, container, or a flowing piece of text
If and how it participates in flex, grid, table, or other layout contexts

Where Does display Fit in CSS?
Most layout and visual behaviors in CSS are dictated by display
It comes before padding, margin, positioning, sizing, etc. — because those features behave differently based on the display type

Core Categories of display Values:
Normal Flow block, inline, inline-block Base structure and text flow
Layout Modules flex, inline-flex, grid, inline-grid Modern layout systems
Table-Based table, table-row, table-cell, etc. Replicating table behavior
None none Hides the element entirely

1. display: block
Description: Starts on a new line and takes up the full width of its parent by default. Accepts width, height, margin, and padding
Examples of block elements:
<div>, <p>, <h1>, <section>, <article>, <form>, <ul>, <ol>
Example:
div {
  display: block;
}

2. display: inline
   Description: Does not start on a new line and only takes up as much width as needed.It ignores width and height properties. Margins and paddings work horizontally, not vertically
   Examples of inline elements:
   <span>, <a>, <strong>, <em>, <label>
   Example:
   span {
   display: inline;
   }

3. display: inline-block
   Description: Flows like inline, behaves like block
   -Allows width/height control
   -Stays inline with text, but accepts full box model
   Use case:
   Buttons, badges, inputs with controlled size that sit inline
   Example:
   button {
   display: inline-block;
   }
4. display: none
   Description:
   Completely removes the element from the DOM visually
   -The element takes up no space at all
   -Not selectable, not tabbable, not visible to screen readers unless handled with ARIA
   Example:
   .nav-menu {
   display: none;
   }
   use cases:
   -Toggling menus or tabs
   -Responsive design for hiding/showing content

5. display: flex
   Description:
   -Enables flexbox layout model
   -The element becomes a flex container
   -Children (flex items) are laid out in row or column

Key features:
-Direction control (flex-direction)
-Alignment (justify-content, align-items)
-Dynamic sizing (flex-grow, flex-shrink)
Example:
.container {
display: flex;
}
Excellent for aligning items horizontally or vertically

6. display: grid
   Description:
   -Enables 2D grid layout
   -Element becomes a grid container
   -Children (grid items) are placed in rows and columns
   Key features:
   -Custom grid tracks (grid-template-rows, grid-template-columns)
   -Explicit and implicit placement- Grid lines, areas, and gaps

Example:
.wrapper {
display: grid;
grid-template-columns: 1fr 2fr;
}
Excellent for full page or section layouts

7. Table-Like Displays
   When you want to mimic HTML table behavior without using <table>:
   Value Acts Like
   table <table>
   table-row <tr>
   table-cell <td>

Example:
div.table {
display: table;
}
div.row {
display: table-row;
}
div.cell {
display: table-cell;
}

8. Inline Versions of Layouts
   These values allow layout systems inside inline content, useful for badges, buttons in text, etc.
   Value Description
   -inline-block Inline placement, block behavior
   -inline-flex Like flex, but flows inline
   -inline-grid Like grid, but flows inline

9. Changing Default Display
   Some elements change behavior based on their default:
   Element Default display

<div>	block
<span>	inline
<img>	inline-block
<li>	list-item
<a>	inline
<table>	table

You can override any of these using CSS:
a {
display: block;
}

10. Common mistakes:
    Using width on inline elements It won’t apply — inline elements ignore box sizing
    Mixing float with flex/grid Can lead to unpredictable layout issues
    Hiding with visibility: hidden only The element still takes space — use display: none
    Using display: inline for block content Can break wrapping or layout structure

Summary
Display Value Behavior Best For
block Full width, new line Sections, divs, layouts
inline Flows in text, no width/height Text elements (span, a)
inline-block Flows in text, respects box model Buttons, icons, nav items
none Hides element completely Menus, tabs, conditional views
flex Flexbox layout container Aligning boxes in a row/column
grid Grid layout container Full layout, rows and columns
table-\* Emulates table behavior Structured content without <table>
inline-flex/grid Layouts inside inline content Mixed-flow layouts
