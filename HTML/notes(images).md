HTML Images (<img>)

1. Basic Syntax

<img src="image.jpg" alt="Description of the image">
Explanation:
<img> is a void (self-closing) tag — it does not wrap around content.

It embeds an image into a web page.
Requires at least two attributes:
src: the source URL of the image.
alt: the alternative text for screen readers and broken image fallback.

2. src Attribute – Source of the Image
   Syntax:

<img src="https://example.com/photo.jpg" alt="A scenic photo">
Explanation:
Stands for source.
Specifies the path to the image file.
Can be:
Absolute URL: Full internet path.
Relative URL: Path relative to current document.
Data URI: Base64-encoded inline image (data:image/png;base64,...).

3. alt Attribute – Alternative Text
   Syntax:

<img src="dog.jpg" alt="A brown dog running through a field">
Explanation:
Essential for accessibility.
Used by screen readers for visually impaired users.
Also displays if the image fails to load.
Should be meaningful — describe what the image shows in context.
If the image is purely decorative, use alt="".

4. width and height Attributes
   Syntax:

<img src="logo.png" alt="Company Logo" width="200" height="100">
Explanation:
Specifies the display dimensions of the image in pixels.
Helps browsers reserve space before the image loads (avoids layout shifts).
You can also style dimensions using CSS:

img {
width: 50%;
height: auto;
}
Always maintain aspect ratio — avoid setting both width and height unless the image is exactly those dimensions.

5. loading Attribute – Lazy Loading
   Syntax:

<img src="photo.jpg" alt="Landscape" loading="lazy">
Explanation:
lazy: Defers loading the image until it's about to enter the viewport.
Improves page performance and reduces initial load time.
eager: Default behavior (loads immediately).
Supported natively by modern browsers.

6. title Attribute – Tooltip on Hover
   Syntax:

<img src="icon.png" alt="Settings Icon" title="Click to open settings">
Explanation:
Displays a tooltip when the user hovers over the image.
Optional.
Not accessible for screen readers — use alt for accessibility.

7. usemap and <map> – Clickable Image Areas (Image Maps)
   Syntax:

<img src="world-map.jpg" usemap="#worldmap" alt="Clickable world map">
<map name="worldmap">
  <area shape="rect" coords="34,44,270,350" href="america.html" alt="America">
  <area shape="circle" coords="400,200,60" href="europe.html" alt="Europe">
</map>
Explanation:
Creates interactive regions inside an image.
usemap references a <map> element by name.

<area> defines a clickable region:

shape: rect, circle, or poly
coords: coordinates for the clickable area
href: where to link
alt: description for accessibility

8. Responsive Images – srcset and sizes
   Syntax:

<img
  src="image-800.jpg"
  srcset="image-400.jpg 400w, image-800.jpg 800w, image-1200.jpg 1200w"
  sizes="(max-width: 600px) 100vw, 800px"
  alt="A person riding a bike">
Explanation:
Helps browsers choose the best image size based on the screen or resolution.
srcset: List of images with widths or pixel densities.
sizes: Hints to the browser about how much screen space the image will occupy.
Great for performance on mobile devices and retina screens.

9. CSS Styling Images (instead of attributes)
   Example:

<img src="avatar.jpg" alt="User Avatar" class="rounded">

img.rounded {
border-radius: 50%;
border: 2px solid #333;
max-width: 100%;
height: auto;
}
Explanation:
Use CSS for better control and responsiveness.
Common styles:
max-width: 100% – scales the image to fit its container.
border-radius – makes circular or rounded images.
box-shadow, filter, object-fit, etc.

10. Common Mistakes
    Missing alt- Always provide meaningful alt text or alt="" for decorative images
    Using stretched dimensions-Use only width or height, or maintain aspect ratio
    Using huge images-Use optimized images or responsive srcset
    Using title instead of alt-title is optional, not for accessibility

Best Practices
-Always use alt for accessibility and SEO.
-Use loading="lazy" to improve performance.
-Serve responsive images with srcset for different screen sizes.
-Use CSS for layout and styling, not width/height attributes unless necessary.
-Compress and optimize images before uploading.

Other Use Cases
SVG Images:
<img src="logo.svg" alt="Scalable logo">
Vector graphics — scale without loss of quality.

Great for icons and logos.
Decorative Background Images:
css
.hero {
background-image: url('hero.jpg');
}
Use CSS background images for purely visual content.
