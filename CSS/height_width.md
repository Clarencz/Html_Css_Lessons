Understanding height and width in CSS

1. What Are height and width in CSS?
   In CSS, the height and width properties are used to control how tall and how wide an element should appear in the browser window.
   width sets the horizontal size of an element.
   height sets the vertical size of an element.
   These dimensions apply to the content area of the element, unless otherwise specified.

2. What Do We Mean by “Content Area”?
   Every HTML element is represented in CSS as a box. This box is made up of four parts:
   Margin (outside)
   Border
   Padding
   Content (core area)
   By default, height and width only apply to the content area of the box — they do not include the padding or border. That means:
   div {
   width: 200px;
   padding: 20px;
   border: 5px solid;
   }
   The total visible width = 200px (content) + 20px (left padding) + 20px (right padding) + 5px (left border) + 5px (right border) = 250px
   This is called the content-box model, and it is the default in CSS.

3. How to Include Padding and Border Inside the Width?
   To make the width/height include padding and border (so the box doesn't grow), use:
   {
   box-sizing: border-box;
   }
   Now, if you set width: 200px, then:
   The content will shrink to accommodate padding and border the total size remains 200px. This is called the border-box model, and is widely preferred today for layout consistency.

4. Default Behavior of HTML Elements (Before Setting Width or Height)
   A. Block-Level Elements (like <div>, <p>, <section>)
   Default width = 100% of the parent container
   Default height = auto (height grows as needed based on content)

B. Inline Elements (like <span>, <a>, <strong>)
Do not respond to width or height Size is controlled by the length of the content. Must be converted to display: inline-block or display: block to apply dimensions

5. Value Types You Can Use with width and height
   Pixels (px) width: 300px; Fixed size — will not adjust automatically
   Percent (%) width: 50%; Relative to the size of the parent container
   Viewport Units (vh, vw) height: 100vh; Based on browser screen size. 1vh = 1% of viewport height
   Em/Rem width: 20em; Relative to font size (em = parent, rem = root)
   auto height: auto; Let the browser automatically size based on content
   min- / max- max-width: 600px; Define limits for resizing behavior

6. Examples of Each in Practice
   A. Fixed Width and Height Using Pixels
   .box {
   width: 300px;
   height: 150px;
   }
   Always 300px wide and 150px tall, regardless of screen size.

B. Percentage-Based Width
.container {
width: 80%;
}
Width is 80% of its parent element. Automatically adjusts based on the screen or parent’s size.
Using % for height requires that the parent element must also have a defined height. Otherwise, the browser has no reference point and won’t know how tall to make the element.

C. Using Viewport Units
.hero {
width: 100vw; /_ 100% of viewport width _/
height: 100vh; /_ 100% of viewport height _/
}
Commonly used to create full-screen landing sections or splash areas.

D. Using auto
img {
width: auto;
height: auto;
}
The browser will automatically determine the size based on content or intrinsic size (like an image’s native resolution).

E. Using min-width and max-width
.card {
width: 100%;
max-width: 500px;
}
The card can stretch up to 100% of its parent, but never wider than 500px.
This makes layouts responsive while preventing content from becoming too wide on large screens.

7. What Happens When Content Overflows a Set Height or Width?
   If content inside an element is larger than the width or height you've set, then one of the following will happen:
   It overflows visually (not clipped)
   It gets cut off if you use overflow: hidden
   A scroll bar appears if you use overflow: auto or overflow: scroll
   Example:
   .box {
   width: 200px;
   height: 100px;
   overflow: auto;
   }

8. Common Mistakes and Misconceptions
   Setting height in % without parent having height Browser can't calculate height Always set height on parent too
   Applying width to inline element (like <span>) Doesn’t work Change to display: inline-block
   Expecting padding to stay inside width Not true in default box model Use box-sizing: border-box
   Using height: auto on fixed-height containers Might not resize properly Use min-height or remove height constraint

Use Cases:
Full-screen section height: 100vh; width: 100vw;
Responsive card width: 90%; max-width: 600px;
Square thumbnail width: 200px; height: 200px;
Fluid image max-width: 100%; height: auto;
Vertical scrollable box height: 300px; overflow-y: auto;

Summary:
Width & height control box size But only content box by default
Use box-sizing: border-box To make dimensions include padding/border
Percentages depend on parent Especially height: % without parent height = broken
Use viewport units for full screen 100vh, 100vw work great for splash areas
Don’t forget scroll or clipping Overflow settings control how extra content behaves
