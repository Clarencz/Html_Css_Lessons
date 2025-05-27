CSS Pseudo-Classes
What is a Pseudo-Class?
A pseudo-class in CSS is a special keyword added to a selector that lets you style elements based on a specific state or behavior, without adding a class or ID in the HTML.

The word "pseudo" means fake or implied — the class doesn't exist in your HTML, but CSS behaves as if it does, based on how the user interacts or how the element behaves.

📘 General Syntax
selector:pseudo-class {
/_ style rules here _/
}
Note: There’s no space between the selector and the colon (:).

Example:
a:hover {
color: red;
}
This will change the link's color to red when the mouse hovers over it.

Types of Pseudo-Classes (Grouped for Understanding)
Let’s break them into 5 main categories, and we’ll explain each with detailed examples:

Category Examples
🔹 User Interaction :hover, :active, :focus
🔸 Position & Order :first-child, :last-child, :nth-child()
🔹 Form & Input States :checked, :disabled, :required
🔸 Structural & Logic :not(), :empty, :root
🔹 Links :link, :visited

1. User Interaction Pseudo-Classes
   These depend on how the user interacts with the element.

:hover
Applies when a user points the mouse over the element.

button:hover {
background-color: blue;
}
:active
Applies while the user is clicking the element (i.e., between mousedown and mouseup).

a:active {
color: green;
}
:focus
Applies when an element (like a form input) is selected/ready for input (like when clicked or tabbed into).

input:focus {
border: 2px solid orange;
}
Used heavily in form accessibility and keyboard navigation.

2. Positional Pseudo-Classes
   These target elements based on their position inside a parent.

:first-child
Selects the first element inside its parent.

ul li:first-child {
color: red;
}
:last-child
Selects the last element inside its parent.

ul li:last-child {
font-weight: bold;
}
:nth-child(n)
Selects the n-th element (1-based) inside its parent.

li:nth-child(3) {
color: blue;
}
You can use patterns:
:nth-child(even) → every 2nd
:nth-child(odd) → every 1st, 3rd, 5th...
:nth-child(3n) → every 3rd element

:nth-of-type(n)
Same as :nth-child, but matches only if the element is of a certain tag.

p:nth-of-type(2) {
font-style: italic;
}
Useful when you have mixed elements like <p>, <h2>, <div> under one parent.

3. Form & Input State Pseudo-Classes
   These respond to form element status or user input.

:checked
Targets checked checkboxes or radio buttons.

input[type="checkbox"]:checked {
outline: 2px solid green;
}
:disabled
Targets inputs or buttons that are disabled and not interactable.

input:disabled {
background-color: #ccc;
}
:required and :optional
:required → applies to inputs with the required attribute
:optional → inputs without the required attribute

input:required {
border-left: 5px solid red;
}
These are helpful in styling form validation states visually.

4. Structural / Logical Pseudo-Classes
   These work on page logic and HTML structure, not user interaction.

:not(selector)
Selects everything except the given selector.

div:not(.important) {
opacity: 0.5;
}
Useful to avoid applying styles to certain elements without creating new classes.

:empty
Selects elements that have no children and no text — completely empty.

p:empty {
display: none;
}
:root
Targets the root element of the page — typically the <html> element.

:root {
--main-color: #333;
}
Used in CSS Variables to define global values.

5. Link Pseudo-Classes
   These apply only to <a> tags with or without links.

:link
Applies to links that have not yet been visited.

a:link {
color: blue;
}
:visited
Applies to links that have already been visited (i.e., clicked before).

a:visited {
color: purple;
}
Browsers limit how much styling is allowed on :visited for security/privacy reasons.

Summary:
:hover When mouse is over the element
:focus When element is focused (input, textarea)
:active When being clicked
:first-child First child of parent
:nth-child(n) Nth child of parent
:checked Checked inputs like checkboxes/radios
:disabled Disabled form fields
:not(selector) Everything except the selector
:empty Element with no content
:link, :visited Anchor link states
