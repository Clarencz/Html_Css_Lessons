Understanding Inline, Internal, and External CSS in HTML
WHY WE NEED STYLING METHODS
HTML only provides the structure of a webpage — it doesn’t describe how it looks. CSS (Cascading Style Sheets) is used to describe the presentation, but there are multiple ways to connect CSS to HTML.

1. INLINE STYLES — (Per-element declarations)
   What is Inline CSS?
   Inline styles are CSS written directly on the HTML element using the style attribute.
   Key Concept:
   -The style is attached to a single tag.
   -It only affects that one element.
   -It's not reusable.

Structure:

<p style="color: red;">This is red text</p>
When do you use it?
-Temporary tweaks
-Overriding other styles in specific cases
-Quick demos
-Email templates (where external styles might not load)

Why it's limited:
-Hard to maintain in large files
-No separation of content and presentation
-Cannot apply across multiple elements

2. INTERNAL STYLES — (Page-specific block styles)
   What is Internal CSS? Internal CSS is written inside the <style> tag in the <head> section of an HTML document.
   Key Concept:
   -Styles apply to the entire document, but are stored within the HTML file.
   -Still allows you to apply classes and IDs.

**Only affects that page, not others.**

Structure:

<head>
  <style>
    p {
      color: blue;
    }
  </style>
</head>
When do you use it (conceptually)?
-Single-page projects
-When external files are not practical
-For embedded examples (like tutorials or demos)

Limitation:
-If you change your design across many pages, you’d need to repeat or duplicate your internal styles.

3. EXTERNAL STYLES — (Linked style sheets — most powerful & maintainable)
What is External CSS? External CSS involves writing CSS rules in a separate .css file, and linking it to your HTML using a <link> tag.
Structure:
<head>
  <link rel="stylesheet" href="styles.css">
</head>
The external file (e.g., styles.css) contains only CSS:
body {
  background-color: white;
}
Why External CSS is Essential
-Separation of concerns: content (HTML) and design (CSS) are kept separate
-Reusability: same CSS can be linked to many HTML pages
-Maintainability: change one CSS file → all linked pages update
-Cleaner HTML: less cluttered, more readable
-Scalability: best for large websites and collaborative work

Specificity in External CSS — How browsers decide which rule wins
External CSS often competes with internal and inline styles. To win, it depends on specificity.

What Is Specificity? Specificity is a ranking system browsers use to decide which CSS rule to apply when there’s a conflict. Think of it as a weighting system:
Selector Type Specificity Value
Element (e.g., p) 0,0,0,1
Class (.btn) 0,0,1,0
ID (#header) 0,1,0,0
Inline style (style="") 1,0,0,0
!important (override flag) Overrides all, but should be avoided

**So, inline styles > IDs > classes > elements**

Why Is This Important in External CSS?
In large websites: Multiple stylesheets may be used and Styles might overlap or contradict each other You must write selectors that are specific enough to override others without depending on !important or inline fixes

Assume you have:

<link rel="stylesheet" href="global.css">
<link rel="stylesheet" href="page.css">
And in the CSS files:
/_ global.css _/
p {
color: black;
}

/_ page.css _/
#main-content p {
color: blue;
}
Even though both are external:
-The one with a more specific selector (#main-content p) will override the general one (p).
