Combinators
What are CSS Combinators?
CSS combinators are special symbols or patterns used between selectors to define the relationship between two or more HTML elements. You use combinators when you want to target elements based on how they are positioned or nested in your HTML structure.

They combine selectors — hence the name "combinators".

There are 4 Main Types of CSS Combinators
Combinator Symbol Relationship Type
Descendant (space) Any level inside (nested)
Child > Direct child only
Adjacent sibling + Immediately next sibling
General sibling ~ Any following sibling

We'll now break each one down, clearly, deeply, and with examples.

1. Descendant Combinator ( space)
   Targets any element that is nested inside another, at any depth.
   Syntax:css:
   parent child {
   /_ styles here _/
   }
   Explanation:
   The "child" can be directly inside or deeply nested. It matches all descendants, not just direct children.

Example HTML:

<div class="card">
  <p>This is a paragraph inside card.</p>
  <div>
    <p>This is a nested paragraph.</p>
  </div>
</div>
CSS:
.card p {
  color: blue;
}
Result:
All <p> tags inside .card, no matter how deeply nested, turn blue.

2. Child Combinator (>)
Targets only the elements that are direct children of the specified parent — not deeper descendants.
Syntax:css:
parent > child {
/_ styles here _/
}
Explanation:
Think of a parent-child relationship. The child must be one level deep, not grandchild or deeper.
Example HTML:
<div class="wrapper">
  <p>This is a direct child.</p>
  <div>
    <p>This is nested deeper.</p>
  </div>
</div>
CSS:
.wrapper > p {
  color: green;
}
Result:
Only the first <p> becomes green. The second one (inside the nested <div>) is ignored.

3. Adjacent Sibling Combinator (+)
Targets an element that is the immediate next sibling of another.
Syntax:css:
element1 + element2 {
/_ styles here _/
}
Explanation:
element2 must be right after element1 in the HTML (same parent). No elements must be in between.
Example HTML:
<h2>Main Title</h2>
<p>This paragraph is right after h2.</p>
<p>This paragraph is not adjacent to h2.</p>
CSS:
h2 + p {
  font-weight: bold;
}
Result:
Only the first <p> after <h2> becomes bold. The second <p> is not directly adjacent to the <h2>, so it is not selected.

4. General Sibling Combinator (~)
   Targets all siblings that come after a specific element — not just the first.
   Syntax:css:
   element1 ~ element2 {
   /_ styles here _/
   }
   Explanation:
   Both elements must have the same parent element2 must appear after element1, but does not need to be adjacent

Example HTML:

<h2>Section Heading</h2>
<p>Paragraph 1</p>
<p>Paragraph 2</p>
CSS:
h2 ~ p {
  font-style: italic;
}
Result:
Both <p> tags after <h2> will be italicized, because they are siblings that come after the <h2>.

Visual Summary of Combinators
A B B is a descendant of A Any level nested inside A
A > B B is a direct child of A Only 1 level deep
A + B B is the next sibling after A Only the immediate following sibling
A ~ B B is a following sibling of A All siblings that come after A

Use Cases:
Style all links inside nav nav a Any depth inside nav
Style only direct list items ul > li Prevent styling nested submenus
Style a tooltip after icon .icon + .tooltip Tooltip appears right after icon
Style all following messages .alert ~ .message Apply style to all messages after alert

Common Mistakes:
Confusing + with ~ + is only first sibling, ~ is all siblings Use the correct one
Using > expecting all nested items Only selects direct children Use space (descendant) instead
Expecting unrelated elements to match Combinators only apply when structure matches exactly Ensure HTML structure supports it
