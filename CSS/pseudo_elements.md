Pseudo-Elements
What Is a Pseudo-Element?
A pseudo-element is a special CSS keyword used to style specific parts of an element's content, or to insert content that doesn’t exist in the HTML.

Think of it like adding fake parts to an element using CSS — such as before it begins, after it ends, or targeting the first line or letter of the text.

✅ Syntax
selector::pseudo-element {
property: value;
}
Two colons :: are used for pseudo-elements to distinguish them from pseudo-classes (:), but browsers also accept a single colon : for older ones (like :before).

Main Pseudo-Elements
Pseudo-Element What It Does
::before Inserts content before an element’s real content
::after Inserts content after an element’s real content
::first-line Targets the first line of text inside an element
::first-letter Targets the first letter of the text
::selection Styles the text the user highlights/ selects
(others) ::marker, ::placeholder, etc. (covered later)

::before
🔎 What it does:
Inserts generated content before the actual content of the element.

Requirements:
The element must be able to contain content (like a <div>, <p>, <span>)
Must use the content property in CSS — otherwise nothing shows.

📄 Example HTML:

<p class="quote">Do or do not. There is no try.</p>

CSS:
.quote::before {
content: "❝ ";
color: gray;
font-size: 1.5em;
}
Result:
The output will appear like:

❝ Do or do not. There is no try.
This is useful for icons, quotes, labels, or tags inserted before content.

::after
What it does:
Inserts generated content after the real content of the element.

📄 Example:HTML:

<p class="quote">Do or do not. There is no try.</p>

CSS:
.quote::after {
content: " ❞";
color: gray;
}
RESULT:

Do or do not. There is no try. ❞
Common uses include decorations, indicators, clearing floats, icons, or adding auto-labels after items.

Clearfix Trick Using ::after

.clearfix::after {
content: "";
display: table;
clear: both;
}
This is a real-world use of ::after to make sure parent containers expand around floated children.

::first-line
What it does:
Targets and styles only the first visible line of text inside an element.

📄 Example:html

<p class="highlight">This is a long paragraph that spans multiple lines on the screen when wrapped.</p>

css
.highlight::first-line {
font-weight: bold;
color: green;
}
Result:
Only the first visible line (as rendered by the browser) becomes bold and green. You cannot control where the line breaks — it's based on screen size and layout.

::first-letter
What it does:
Targets the first letter of the first word of a block of text.

📄 Example:html

<p class="lead">Once upon a time...</p>

css
.lead::first-letter {
font-size: 2em;
color: red;
float: left;
}
Result:
This creates a "drop cap" effect — the first letter is larger and colored.
Commonly used in magazine or newspaper-style layouts.

::selection
What it does:
Styles text only when the user highlights/selects it (click + drag or Ctrl+A).

📄 Example:css:
p::selection {
background: yellow;
color: black;
}
This only works on a few properties: color, background, text-shadow, etc.

-Other Notable Pseudo-Elements
Pseudo-Element Purpose
::placeholder Styles the placeholder text in input or textarea fields
::marker Styles bullet or number in lists (<ul>, <ol>)
::cue (media) Styles WebVTT subtitles and captions in <video>
::file-selector-button Styles the file input button in file inputs

Example:css:
input::placeholder {
color: gray;
font-style: italic;
}

When to Use Pseudo-Elements
Add icons or symbols before/after ::before, ::after
Drop caps or stylized headings ::first-letter, ::first-line
Input placeholders ::placeholder
Custom list bullets ::marker
Interactive selections ::selection
Add styling without HTML change All of the above

🚩Important Notes
::before and ::after require content: ""; to show anything.
These elements do not exist in the HTML, only visually in the CSS layer.
They can be styled like normal elements (colors, fonts, spacing, positioning).
They cannot receive input or interaction like real HTML elements.
