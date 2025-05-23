Semantic HTML
What is Semantic HTML?
Semantic HTML uses HTML elements that convey meaning about the structure and purpose of the content to browsers, developers, and assistive technologies.

"Semantic" means:
The tag describes the content it holds. It’s not just how it looks — it's what it is.
Compare:
Semantic Non-Semantic

<header>	   <div id="header">
<nav>	       <div class="nav">
<article>	   <div>

Semantic HTML helps:
Screen readers and assistive tools
Search engines understand your content (SEO)
Developers understand your code more easily

1. Semantic Page Structure Elements
   These elements define the layout and role of different sections in a web page.

<header>
Purpose:
Represents the introductory content or branding of a page or section.
Common Usage:
Logo
Site title
Navigation links
Taglines

<header>
  <h1>My Blog</h1>
  <nav> ... </nav>
</header>
You can have multiple <header> tags (e.g., one for the page, one inside an <article>).

<nav>
Purpose: Contains navigation links to other parts of the site or page.
<nav>
  <ul>
    <li><a href="/about">About</a></li>
    <li><a href="/blog">Blog</a></li>
  </ul>
</nav>
Should only wrap actual navigational links, not every list or menu.

<main>
Purpose:Represents the main content of the page — the content unique to this page.
<main>
  <h2>Welcome to My Website</h2>
  <p>This site covers web development tutorials.</p>
</main>
There should be only one <main> per page.

<article>
Purpose: A self-contained block of content that could be independently reused or syndicated.
Examples:
Blog post
News story
Forum post
Product card

<article>
  <h2>10 Tips for Learning HTML</h2>
  <p>HTML is the foundation of web development...</p>
</article>
Can contain its own <header>, <footer>, <section>, etc.

<section>
Purpose: Defines a thematic grouping of related content.
Examples:
A chapter in an article
A step in a tutorial
A team section on a homepage

<section>
  <h3>Our Services</h3>
  <ul>
    <li>Web Design</li>
    <li>Consulting</li>
  </ul>
</section>
Use when the group of content has a heading and can be given a label.

<aside>
Purpose: Content that is indirectly related to the main content.
Examples:
Ads
Sidebars
Related links
Pull quotes

<aside>
  <h4>Related Posts</h4>
  <ul>
    <li><a href="#">HTML Tables</a></li>
    <li><a href="#">CSS Basics</a></li>
  </ul>
</aside>
Typically placed beside or below the main content, but still semantically tied.

<footer>
Purpose: Contains footer information for the page or a section.
Common Content:
Copyright
Contact info
Social links
Site map

<footer>
  <p>&copy; 2025 My Website</p>
</footer>
Like <header>, multiple <footer>s are allowed (e.g., for articles).

2. Text-Level Semantic Elements
   These elements describe the meaning of the text itself — not layout, but what the content means.

<strong> and <em>

<p>This is <strong>very important</strong> for your safety.</p>
<p>Please <em>read carefully</em> before proceeding.</p>

<strong>: Indicates strong importance, not just bold style.
<em>: Indicates emphasis, not just italic style.

Both are recognized by screen readers, unlike <b> and <i> (which are purely visual).

Other inline semantic elements:
Tag
<abbr> Abbreviations with tooltip (title) <abbr title="World Health Organization">WHO</abbr>
<cite> Title of a work (book, movie, etc.) <cite>The Great Gatsby</cite>
<code> Inline code snippet <code>document.querySelector()</code>
<kbd> Keyboard input <kbd>Ctrl</kbd> + <kbd>S</kbd>
<mark> Highlighted or marked text <mark>urgent</mark>
<s> Struck-through text (e.g., outdated) <s>$99</s> now $49
<time> Date or time (can be machine-readable) <time datetime="2025-05-22">May 22, 2025</time>
<var> A variable in a math or programming expression <var>x</var> + <var>y</var>
<dfn> First use of a defined term <dfn>HTML</dfn> is a markup language.

3. Why Use Semantic HTML?
   Accessibility
   Screen readers can understand structure <nav>, <header>, etc. help users navigate faster

SEO
Search engines understand what’s content vs. structure <article> content is treated more seriously than generic <div>s

Maintainability
Clear code = easier to read, style, and modify Teams can understand each other's work quickly

Best Practices
Use <main> only once - Helps screen readers know where to focus
Don’t misuse <section> - Only use when the content has a heading
Avoid using only <div> - They carry no meaning — use semantically
Use <h1>–<h6> correctly - For a logical, outline-based document flow
Group content with headings - Headings give context to sections and articles
