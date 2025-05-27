Fonts in CSS

1. What Is a Font?
   A font is a specific style, weight, and design of a typeface.
   Typeface = a font family (e.g., "Poppins", "Arial")
   Font = one variation, like "Poppins-Light" or "Arial Bold Italic"
   In CSS, fonts are not just visual — they affect legibility, tone, performance, and accessibility.

2. CSS Font Properties (Conceptual Breakdown)
   font-family The typeface used "Arial", sans-serif
   font-size The size of the text 16px, 1em, clamp()
   font-weight How bold or light the text is 400, bold, 100
   font-style Whether it’s italic or normal italic, normal
   font-variant Enables small-caps or stylistic sets small-caps
   font Shorthand to set multiple font properties font: italic 16px Arial

3. font-family — The Heart of Font Styling
   Syntax:css:
   font-family: 'Poppins', 'Segoe UI', sans-serif;
   How Browsers Use Font-Family:
   Tries to load 'Poppins',If not available, tries 'Segoe UI',If still not available, falls back to system generic font (sans-serif)

Always end with a generic family:
serif
sans-serif
monospace
cursive
fantasy
system-ui
Helps maintain readability if custom fonts fail to load.

4. Font Sources — Where Fonts Come From
   A. System Fonts
   Pre-installed on the user's device,Fastest and safest
   Examples: Arial, Verdana, Georgia, Courier New

B. Web Fonts
Loaded from external files or services
Examples: Google Fonts, custom .ttf or .woff files
Must be declared with @font-face

C. Variable Fonts
A newer format (.woff2) that allows multiple weights/styles in one file
Reduces load time and allows smoother transitions

5. @font-face — Using Custom Fonts
   Purpose:
   Allows you to load fonts from your project or a URL and give them a name for CSS use.
   Example:css:
   @font-face {
   font-family: 'MyFont';
   src: url('fonts/MyFont.woff2') format('woff2');
   }
   font-family: The name you assign to the font
   src: The location of the font file (relative or absolute)
   format: (Optional) tells the browser what type of file it is
   You can now use 'MyFont' in your font-family declarations.

6. Font File Formats — Why They Matter
   Format Use Case Notes
   .ttf TrueType Font Larger file, good compatibility
   .otf OpenType Font Supports advanced features
   .woff Web Open Font Format Optimized for web
   .woff2 Compressed WOFF (modern) Smallest size, fastest loading
   .eot Embedded OpenType (IE only) Obsolete
   .svg Used in older iOS Obsolete

Use .woff2 if performance matters
Always provide fallbacks (.woff, .ttf) if you support old browsers

7. Font Units — How Size is Measured
   Unit Based On Example Notes
   px Absolute pixels font-size: 16px Fixed size, consistent but rigid
   em Relative to parent 1em = parent size Responsive, good for scaling
   rem Relative to root (html) 1rem = root font-size More predictable scaling
   % Relative to parent 150% Less common for fonts

8. Fallback Strategies
   Why:
   Not all fonts are available everywhere, Users may block web fonts
   Good Practice:css:
   font-family: 'Open Sans', 'Segoe UI', sans-serif;
   First: try web font
   Second: try common system font
   Last: fallback to system's default sans-serif

9. Font Performance and Accessibility
   Concern Explanation
   Font loading delay Prevents page from rendering text if font hasn't loaded
   font-display Controls how fonts behave during load (swap, fallback, etc.)
   Readability Font size, weight, and spacing impact UX
   Accessibility Use high-contrast, readable fonts, avoid light gray text on white
   font-display Example:css:
   @font-face {
   font-family: 'Roboto';
   src: url('roboto.woff2') format('woff2');
   font-display: swap;
   }

10. CSS Shorthand for Font
    font: italic bold 1.2em/1.5 'Open Sans', sans-serif;
    Breakdown:
    italic → font-style
    bold → font-weight
    1.2em/1.5 → font-size and line-height
    'Open Sans', sans-serif → font-family
