Dropdown Menus

1. What is a Dropdown Menu?
   A dropdown menu is a type of menu that expands or drops down to reveal hidden options when triggered — usually by hovering or clicking.
   It is most often used in:
   -Navigation bars
   -Forms (like <select>)
   -Settings/profile menus
   -E-commerce category menus

2. What Do You Need to Build a Dropdown?
   To make a custom dropdown menu (not <select>), you need:
   HTML To create the structure (menu items)
   CSS To style the menu + control visibility
   JavaScript (Optional) To add interactivity (toggle on click, close on blur, etc.)
   Let’s first look at how to build one only with HTML + CSS, then explain how JavaScript enhances it.

3. Structure — HTML for a Basic Dropdown
<div class="dropdown">
  <button class="dropbtn">Menu</button>
  <div class="dropdown-content">
    <a href="#">Option 1</a>
    <a href="#">Option 2</a>
    <a href="#">Option 3</a>
  </div>
</div>
Explanation:
Tag/Class	Purpose
.dropdown	The wrapper (container)
.dropbtn	The button or link the user interacts with
.dropdown-content	The hidden menu items shown when dropdown opens

4. Styling — CSS to Make It Work
   Basic container
   .dropdown {
   position: relative;
   display: inline-block;
   }

The button
.dropbtn {
padding: 10px 20px;
background-color: #3498db;
color: white;
cursor: pointer;
border: none;
}

Dropdown content: hidden by default
.dropdown-content {
display: none;
position: absolute;
background-color: white;
min-width: 160px;
box-shadow: 0px 8px 16px rgba(0,0,0,0.2);
z-index: 1;
}

Show links vertically
.dropdown-content a {
padding: 10px;
display: block;
color: black;
text-decoration: none;
}

On hover, change link background
.dropdown-content a:hover {
background-color: #f1f1f1;
}

Show dropdown on hover (pure CSS)
.dropdown:hover .dropdown-content {
display: block;
}
What’s Happening:
position: relative on .dropdown creates a positioning context.
position: absolute on .dropdown-content makes it appear below the button.
display: none hides it until hover.
display: block shows it on .dropdown:hover.

5. Add JavaScript (for Click-to-Open Dropdown)
   CSS-only dropdowns often open on hover, but real apps usually use click.
   HTML stays mostly the same.
   Add JavaScript:
   document.querySelector('.dropbtn').addEventListener('click', function () {
   document.querySelector('.dropdown-content').classList.toggle('show');
   });
   Update CSS:
   .dropdown-content {
   display: none;
   }
   .dropdown-content.show {
   display: block;
   }
   This allows the dropdown to open/close on click, rather than hover — especially useful on mobile!

6. Accessibility Best Practices
   Use <button> not <div> for triggers Makes it keyboard-accessible
   Use aria-haspopup="true" Announces to screen readers
   Use aria-expanded="true/false" Reflects the state of the dropdown
   Use keyboard events (keydown) Allow navigation via arrow/tab keys
   Accessibility ensures dropdowns are usable for everyone, including keyboard users and screen readers.

7. Real-World Use Cases
   Use Case Behavior
   Navbar with dropdown Show submenu on hover or click
   Profile/settings menu Toggle open/close on click
   Category selector Show categories in stacked links
   Form language selector Acts like <select>

Recap:
Dropdowns hide/show content They reveal options when triggered
CSS display + position Control visibility and placement
Hover vs Click Hover is easier; click is more controlled
JavaScript Enhances UX Adds toggles, close-on-outside-click, animations
Mobile UX matters Click is better than hover for phones
Accessibility is vital Use semantic tags and ARIA roles
