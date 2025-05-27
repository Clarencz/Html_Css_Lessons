CSS Flexbox:
📖 1. What Is Flexbox?
Flexbox, or Flexible Box Layout, is a CSS layout system that allows you to arrange elements in one direction (row or column), and easily control:

Spacing between items
Alignment (horizontal and vertical)
Item sizing, wrapping, and ordering
Responsiveness without media queries
It solves many problems that traditional layouts using float, inline-block, or position couldn’t handle elegantly.

2. Core Structure
🔹 Flex Container
The parent element that holds the flex items.
css:
.container {
display: flex;
}
🔹 Flex Items
The direct children of the flex container.
html:
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>

3. Axes: The Foundation of Flexbox
   Flexbox works along two invisible lines:
   Axis Controlled By Affects
   Main Axis flex-direction Primary direction of items
   Cross Axis Perpendicular to main Used for vertical/horizontal alignment

4. flex-direction: Main Axis Direction
   Sets the direction of the main axis, changing how items are laid out.
   Values:
   Value Layout Direction
   row (default) Left to right (horizontal)
   row-reverse Right to left
   column Top to bottom (vertical)
   column-reverse Bottom to top

Example:css:
.container {
display: flex;
flex-direction: row;
}

5. justify-content: Main Axis Alignment
   Controls how flex items are distributed along the main axis.
   Values:
   Value Meaning
   flex-start Items packed to the start of main axis
   flex-end Packed to the end
   center Centered in the container
   space-between Equal space between items only
   space-around Equal space around items
   space-evenly Equal space between and around items

Example:css:
.container {
display: flex;
justify-content: space-between;
}

6. align-items: Cross Axis Alignment
   Controls how items are aligned along the cross axis.
   Values:
   Value Meaning
   stretch Items stretch to fill cross axis (default)
   flex-start Aligns items to top (row) or left (column)
   flex-end Aligns to bottom or right
   center Aligns items in the middle
   baseline Aligns by the text baseline

Example:css:
.container {
display: flex;
align-items: center;
}

7. align-self: Individual Item Alignment
   Overrides align-items for one specific flex item.
   css:
   .item-special {
   align-self: flex-end;
   }

8. flex-wrap: Controlling Item Wrapping
   By default, Flexbox keeps all items on one line, even if they overflow. Use flex-wrap to wrap them onto multiple lines.
   Values:
   Value Behavior
   nowrap (default) No wrapping
   wrap Items wrap onto next line
   wrap-reverse Items wrap in reverse order

Example:css:
.container {
flex-wrap: wrap;
}

9. flex-flow: Shorthand
   This combines flex-direction and flex-wrap.
   css:
   .container {
   flex-flow: row wrap;
   }

10. gap: Space Between Items
    Introduced in Flexbox as a native way to space items.
    css:
    .container {
    display: flex;
    gap: 20px;
    }
    Replaces old margin hacks between items. Works in modern browsers.

11. flex: Sizing Items Automatically
    A shorthand for:
    flex-grow flex-shrink flex-basis
    Basic Usage:
    css:
    .item {
    flex: 1;
    }
    Each item takes up equal share of available space.

12. Understanding the Full flex Shorthand
    Format:
    flex: [grow] [shrink] [basis];
    Example:css:
    .item {
    flex: 2 1 100px;
    }
    2 → Grow twice as much as others
    1 → Shrink if needed
    100px → Start at 100px width

13. flex-grow, flex-shrink, flex-basis
    Property What It Does
    flex-grow Ratio of how item grows
    flex-shrink Ratio of how item shrinks
    flex-basis Starting size before growing/shrinking

14. order: Visual Reordering
    Changes the visual order of items (without changing HTML order).
    css:
    .item:nth-child(2) {
    order: 1;
    }
    Items with lower order values come first.

15. Practical Layout Examples
    Horizontal Centering,css:
    .container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    }
    Sidebar Layout,css:
    .container {
    display: flex;
    }
    .sidebar {
    width: 200px;
    }
    .content {
    flex: 1;
    }

16. Common Mistakes & Fixes:
    Not using display: flex None of the properties work Always start with display: flex
    Forgetting flex-wrap Items overflow the container Add flex-wrap: wrap;
    Misusing align-items Doesn’t center as expected Combine with justify-content
    Applying flex to non-direct children Only direct children are flex items Structure your HTML accordingly

Summary:
1D Layouts - Arrange items in row or column
Centering - Easily center items in both directions
Responsiveness - Adjust items without media queries
Equal spacing - Use gap or justify-content
Item growth/shrink - Use flex, flex-grow, flex-basis
Reordering - Use order without HTML change
