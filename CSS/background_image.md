Background Images in CSS

1. What is a Background Image in CSS?
   A background image is a decorative image applied to the background of an element (like a <div>, <section>, or <body>) using CSS — not inserted inside the HTML like <img>.
   This image does not appear in the document content flow, but rather behind the content, inside the element’s background layer.

2. How to Add a Background Image
   You use the background-image property:
   css:
   element {
   background-image: url("image-path.jpg");
   }
   Example:css:
   body {
   background-image: url("background.jpg");
   }
   Explanation:
   url("...") is used to provide the path to the image.
   You can use relative paths, absolute paths, or even external URLs.

3. File Path Clarification
   Path Type Example Notes
   Relative Path url("images/bg.jpg") Looks for image relative to your CSS file or HTML
   Absolute Path url("/assets/bg.jpg") Starts from root of your domain or project
   External URL url("https://example.com/bg.jpg") Loads from another website

If your image is not loading, double-check your file path and ensure the image exists.

4. By Default, What Does a Background Image Do?
   If you only set background-image, it will:
   Tile (repeat) both horizontally and vertically
   Stick to the top-left corner of the element
   Size according to the image’s natural size, not the element’s size
   Not scale, not stretch, and not move on scroll by default
   That’s why additional background properties are important for full control.

5. Supplementary Background Properties

   1. background-repeat
      Controls tiling behavior.

   Value What It Does
   repeat Repeats both x and y (default)
   no-repeat Shows the image once, no tiling
   repeat-x Repeats horizontally only
   repeat-y Repeats vertically only
   space Repeats image with spacing (no clipping)
   round Scales image so it fits exactly

   css:
   div {
   background-repeat: no-repeat;
   } 2. background-position
   Controls where the image is placed within the element.

   Value Type Example Meaning
   Keywords top left, center Places image at keyword position
   Lengths 50px 100px Offsets image from top-left
   Percentages 50% 50% Centers image in both directions

   css:
   div {
   background-position: center center;
   } 3. background-size
   Controls how large or small the background image should appear.

   Value Meaning
   auto Default — keeps natural image size
   cover Stretches image to cover the entire element, cropping if needed
   contain Stretches image to fully fit inside element, no cropping
   100% 100% Force image to match element width and height exactly
   px, % Custom scaling (width first, then height)

   css:
   div {
   background-size: cover;
   } 4. background-attachment
   Controls scrolling behavior — does the image scroll with the page or stay fixed?

   Value Meaning
   scroll Moves when page scrolls (default)
   fixed Stays in place as content scrolls
   local Scrolls with the element (if scrollable)

   css:
   div {
   background-attachment: fixed;
   }
   Use with background-size: cover to create a parallax effect.

   5. background-color (optional)
      You can also layer a background color behind the image, or use it as a fallback.

   css:
   div {
   background-color: #000;
   }
   🎨 6. Shorthand Property: background
   You can combine all background properties into one line using background shorthand:
   css:
   div {
   background: url("bg.jpg") no-repeat center center / cover fixed;
   }
   The shorthand includes:
   background: [image] [repeat] [position] / [size] [attachment] [color];
   This is powerful but tricky — always double-check value order!

   7. Layering Multiple Background Images
      You can apply more than one background image, layered from top to bottom:
      CSS:
      div {
      background-image: url("pattern.png"), url("main-bg.jpg");
      background-repeat: repeat, no-repeat;
      background-position: top left, center;
      background-size: auto, cover;
      }
      First image is on top, second is below it

   8. Use Cases
      Hero image that covers full screen background-image, cover, center, no-repeat
      Pattern behind content repeat with small seamless image
      Sticky parallax background background-attachment: fixed; background-size: cover;
      Button with background icon background-image, no-repeat, left center

   9. Common Mistakes
      Image not showing Wrong file path Double-check file location and URL
      Image repeating unexpectedly Default behavior Set background-repeat: no-repeat;
      Image looks cut or stretched Image not scaled or sized properly Use background-size: cover or contain
      Image scrolls away You expected a fixed background Use background-attachment: fixed;

Summary
background-image Sets the image
background-repeat Repetition behavior
background-position Where image is placed in the element
background-size Scaling or fitting of the image
background-attachment Scroll or fixed behavior
background All-in-one shorthand
