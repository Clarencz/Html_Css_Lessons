HTML <button> Element
Buttons are interactive elements used to trigger actions, submit forms, or execute scripts. The <button> tag is versatile, semantic, and preferred over clickable <div> or <a> elements for interaction.

1. Basic Syntax
   <button>Click Me</button>
   Text between the tags is what users see and click.
   Browsers render this as a native clickable button with default styling.
   Supports text, images, icons, or even nested HTML (like <strong>).

2. Types of Buttons (type Attribute)
   <button type="submit">Submit</button>
   <button type="reset">Reset</button>
   <button type="button">Do Something</button>
   Type Description
   submit Default type inside a <form>. Submits the form.
   reset Resets form fields to their default values.
   button Does nothing by default — use it with JavaScript for custom actions.

Always specify the type explicitly to avoid unexpected form submission.

3. Attributes of <button>
   Attribute Purpose Example
   type Defines the button's behavior type="button"
   disabled Disables the button (non-clickable) disabled
   name Used in forms; assigns a name to the button name="sendButton"
   value Value submitted with a form value="send"
   autofocus Auto-focuses this button when page loads autofocus
   form Links the button to a specific form by ID form="contactForm"
   formaction Overrides form’s action URL for this button formaction="/submit-alt.php"
   formenctype Encoding type when submitting files multipart/form-data, etc.
   formmethod HTTP method (get, post) formmethod="get"
   formnovalidate Skips validation when form is submitted formnovalidate
   formtarget Target window (\_self, \_blank, etc.) formtarget="\_blank"

4. Button Content – Text, HTML, Icons
   <button><strong>Save</strong></button>
   <button><img src="icon.png" alt=""> Save</button>
   You can include text, HTML formatting, or even images inside the button.
   Avoid using too many nested elements — keep buttons simple and accessible.

5. Button Styling (Preview)
   While styling is covered deeply in CSS, here's a quick contrast:

Raw HTML:
<button>Click</button>
With basic CSS:
<button class="primary-btn">Click</button>
css

.primary-btn {
background-color: #007BFF;
color: white;
padding: 10px 20px;
border: none;
border-radius: 5px;
}
Styling makes the button match your site's theme, but remember: structure first, style second.

6. JavaScript Interaction
   <button onclick="alert('Button clicked!')">Click Me</button>
   onclick is the most common event used with buttons.

You can also use:
onmouseover
onfocus
onkeydown, etc. Or use JavaScript externally:

<button id="greet">Greet</button>

<script>
  document.getElementById("greet").onclick = function () {
    alert("Hello!");
  };
</script>

7. Accessibility Best Practices
   Use <button>, not clickable <div>s Buttons are keyboard focusable by default
   Add clear text (no icon-only buttons without aria-label) AS Screen reader users rely on it
   Don't remove focus outlines unless you replace them Visual cues for keyboard users
   Avoid overloading <button> with multiple roles Keep it simple, single purpose

8. Button vs Input Type="button"
   <button> <input type="button">
   Can contain HTML inside Cannot contain anything inside
   More flexible and stylable More limited, but simpler

<button><img src="save-icon.png"> Save</button> <!-- valid -->
<input type="button" value="Save"> <!-- plain only -->

9. Common Mistakes
   Omitting type Defaults to submit in a form Always specify type="button" if not submitting
   Using <div> or <span> as buttons Not keyboard accessible Use <button> or <a>
   Using only images with no alt or aria-label Not screen-reader friendly Add alt or aria-\*
   Nesting block-level elements (e.g., <div>) inside buttons Invalid HTML Only use inline content inside <button>

Summary Table
Tag Behavior Use For
<button> Flexible, supports HTML inside UI buttons, triggers
type="submit" Submits form Forms
type="reset" Resets form fields Forms
type="button" General actions JavaScript triggers
disabled Makes the button unclickable Validation, UX control

Real-World Use Cases

1.Login Button

<form action="/login" method="post">
  <button type="submit">Login</button>
</form>
2.JS-Controlled Confirmation
<button type="button" onclick="confirm('Are you sure?')">Delete</button>
3.Linked to a Form Outside
<form id="newsletter-form" action="/subscribe">
  <input type="email" name="email">
</form>
<button type="submit" form="newsletter-form">Subscribe</button>
