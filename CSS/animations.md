CSS Animations
What Is a CSS Animation?
A CSS animation lets you animate the transition between different CSS styles over time — like fading, moving, scaling, or rotating an element.

It works entirely in CSS, without needing JavaScript for basic effects.

Structure of CSS Animation
There are two key parts:
@keyframes — Defines the stages of the animation
animation properties — Controls how the animation runs (duration, delay, iteration, etc.)

1. @keyframes — Define the Animation
   This is where you write how your element changes over time.
   Syntax:CSS:
   @keyframes animation-name {
   0% { /_ starting styles _/ }
   50% { /_ middle styles _/ }
   100% { /_ ending styles _/ }
   }
   Example:CSS:
   @keyframes slide-in {
   0% { transform: translateX(-100%); opacity: 0; }
   100% { transform: translateX(0); opacity: 1; }
   }

2. Animation Properties
   These go in the CSS selector to control timing, behavior, repetition, and direction.

Property What It Does
animation-name Which keyframes to use
animation-duration How long it lasts
animation-timing-function Speed curve (ease, linear, etc.)
animation-delay When it starts
animation-iteration-count How many times it runs
animation-direction Forward, backward, alternate
animation-fill-mode What styles stay before/after animation
animation-play-state Play or pause animation

Common Example:CSS:
.box {
animation-name: slide-in;
animation-duration: 1s;
animation-timing-function: ease;
animation-delay: 0s;
animation-iteration-count: 1;
animation-fill-mode: forwards;
}
This means: Animate using slide-in over 1 second, ease-in curve, no delay, play once, and keep the end state (forwards).

Breakdown of Each Animation Property

animation-name
Connects your element to the @keyframes.
css:
animation-name: bounce;

animation-duration
Time (in s or ms) the animation takes to complete.
css:
animation-duration: 2s;
Required! If you forget it, nothing will animate.

animation-timing-function
Controls the speed curve (easing) of the animation.
Value Description
linear - Same speed from start to end
ease - Starts slow, speeds up, then slows
ease-in Starts slow, then speeds up
ease-out Starts fast, then slows down
ease-in-out Starts slow, speeds up, slows down
cubic-bezier(...) Custom speed curve
css:
animation-timing-function: ease-in-out;

animation-delay
Wait before animation starts.
css:
animation-delay: 0.5s;

animation-iteration-count
Number of times animation repeats.
Value Meaning
1 Run once
infinite Loop forever
n Run n times
css:
animation-iteration-count: infinite;

animation-direction
Control direction of the animation.
Value Meaning
normal Forward (0% → 100%)
reverse Backward (100% → 0%)
alternate Forward, then reverse
alternate-reverse Reverse, then forward

animation-fill-mode
Defines what styles persist before or after the animation.
Value Description
none Reverts to original styles (default)
forwards Keeps the styles at 100% keyframe
backwards Applies styles at 0% keyframe before delay ends
both Combines forwards and backwards
css:
animation-fill-mode: forwards;

animation-play-state
Lets you pause/resume the animation.
css:
animation-play-state: paused;
Can be toggled dynamically using JavaScript or hover.

Animation Shorthand
You can combine all animation properties in one line:
css:
animation: slide-in 1s ease 0.5s 1 forwards;
This is equivalent to setting:
animation-name: slide-in;
animation-duration: 1s;
animation-timing-function: ease;
animation-delay: 0.5s;
animation-iteration-count: 1;
animation-fill-mode: forwards;

Use Cases:
Goal Animation Strategy
Slide in a modal translateX/translateY
Fade in an image opacity
Make a spinner rotate() with infinite loop
Hover zoom effect scale() on :hover
Notification popup translate + opacity + delay
Button wave animation Use keyframes with scale

Example: Fade-In and Slide-In
HTML:

<div class="box">Hello</div>

CSS:
@keyframes fade-slide {
0% {
opacity: 0;
transform: translateY(50px);
}
100% {
opacity: 1;
transform: translateY(0);
}
}

.box {
animation: fade-slide 0.8s ease-out forwards;
}

Common Pitfalls:
Animation not playing Missing animation-duration or name Always set both name + duration
Wrong delay or order Forgetting delay, or keyframe % too spaced Check timing and keyframe steps
Animation jumps back to start No animation-fill-mode: forwards; Add it to keep final state
Unexpected easing Default is ease Try linear or ease-in-out

Concept Summary:
@keyframes Defines animation steps
animation-name Links keyframes to an element
animation-duration Required for it to work
animation-timing-function Controls speed curve
animation-delay When animation starts
animation-iteration-count Loops or not
animation-direction Forward, reverse, or both
animation-fill-mode Keeps styles after animation ends
