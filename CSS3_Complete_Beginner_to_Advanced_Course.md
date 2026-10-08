# CSS3 — Complete Beginner to Advanced Course

> A structured CSS3 course for full-stack development, from fundamentals to professional architecture and real-world projects.

---

# Table of Contents

1. [Lesson 1 — CSS Fundamentals](#lesson-1--css-fundamentals)
2. [Lesson 2 — Selectors & Specificity](#lesson-2--selectors--specificity)
3. [Lesson 3 — Colors, Units & Typography](#lesson-3--colors-units--typography)
4. [Lesson 4 — Box Model](#lesson-4--box-model)
5. [Lesson 5 — Display & Positioning](#lesson-5--display--positioning)
6. [Lesson 6 — Flexbox](#lesson-6--flexbox)
7. [Lesson 7 — CSS Grid](#lesson-7--css-grid)
8. [Lesson 8 — Responsive CSS](#lesson-8--responsive-css)
9. [Lesson 9 — Backgrounds & Images](#lesson-9--backgrounds--images)
10. [Lesson 10 — Forms & UI](#lesson-10--forms--ui)
11. [Lesson 11 — Transitions, Transforms & Animations](#lesson-11--transitions-transforms--animations)
12. [Lesson 12 — Modern CSS](#lesson-12--modern-css)
13. [Lesson 13 — Advanced CSS](#lesson-13--advanced-css)
14. [Lesson 14 — Real-World CSS Projects](#lesson-14--real-world-css-projects)
15. [Final CSS Cheat Sheet](#final-css-cheat-sheet)
16. [Professional CSS Checklist](#professional-css-checklist)
17. [Final Learning Roadmap](#final-learning-roadmap)

---

# Lesson 1 — CSS Fundamentals

## 1.1 What is CSS?

CSS means **Cascading Style Sheets**.

HTML provides structure:

```html
<h1>Hello</h1>
<p>Welcome to my website.</p>
```

CSS controls presentation:

```css
h1 {
    color: blue;
    font-size: 40px;
}
```

JavaScript controls behavior:

```text
HTML → Structure
CSS  → Presentation
JS   → Behavior
```

---

## 1.2 CSS Syntax

Basic syntax:

```css
selector {
    property: value;
}
```

Example:

```css
p {
    color: blue;
    font-size: 18px;
}
```

Parts:

```text
p
↓
selector

color
↓
property

blue
↓
value
```

A complete declaration is:

```css
color: blue;
```

---

## 1.3 Three Ways to Add CSS

### Inline CSS

```html
<p style="color: red;">Hello</p>
```

Good for quick tests, but avoid it for large applications.

### Internal CSS

```html
<head>
    <style>
        p {
            color: red;
        }
    </style>
</head>
```

### External CSS

HTML:

```html
<link rel="stylesheet" href="style.css">
```

CSS:

```css
p {
    color: red;
}
```

For real projects, external CSS is usually the preferred approach.

---

## 1.4 CSS Comments

```css
/* This is a CSS comment */

.card {
    padding: 20px;
}
```

---

## 1.5 Basic Selectors

### Element selector

```css
p {
    color: blue;
}
```

### Class selector

```css
.card {
    padding: 20px;
}
```

HTML:

```html
<div class="card"></div>
```

### ID selector

```css
#main-title {
    color: red;
}
```

### Universal selector

```css
* {
    box-sizing: border-box;
}
```

### Grouping selector

```css
h1,
h2,
h3 {
    color: navy;
}
```

---

## 1.6 Basic Colors

```css
color: red;
color: #ff0000;
color: rgb(255 0 0);
color: hsl(0 100% 50%);
```

---

## 1.7 Common CSS Properties

```css
color
background
font-size
font-family
font-weight
width
height
margin
padding
border
border-radius
display
position
top
right
bottom
left
z-index
```

---

## 1.8 CSS Units

Common units:

```text
px
%
rem
em
vw
vh
dvh
svh
lvh
ch
```

Example:

```css
.container {
    width: 80%;
    max-width: 1200px;
    padding: 2rem;
}
```

---

## 1.9 Basic Box Model

Every element can be understood as:

```text
┌──────────────────────────────┐
│            Margin            │
│   ┌──────────────────────┐   │
│   │       Border         │   │
│   │  ┌────────────────┐  │   │
│   │  │    Padding     │  │   │
│   │  │  ┌──────────┐  │  │   │
│   │  │  │ Content  │  │  │   │
│   │  │  └──────────┘  │  │   │
│   │  └────────────────┘  │   │
│   └──────────────────────┘   │
└──────────────────────────────┘
```

---

## 1.10 First Professional Reset

```css
*,
*::before,
*::after {
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    margin: 0;
}
```

---

## Practice

Create:

- A heading
- A paragraph
- A button
- A card
- A colored background
- Padding
- Margin
- Border
- Border radius

---

# Lesson 2 — Selectors & Specificity

## 2.1 Element Selector

```css
p {
    color: blue;
}
```

---

## 2.2 Class Selector

```css
.text {
    color: green;
}
```

```html
<p class="text">Hello</p>
```

---

## 2.3 ID Selector

```css
#title {
    color: red;
}
```

---

## 2.4 Multiple Classes

```html
<button class="btn primary">Buy</button>
```

```css
.btn {
    padding: 10px 20px;
}

.btn.primary {
    background: blue;
}
```

Notice:

```css
.btn.primary
```

means an element having both classes.

---

## 2.5 Descendant Selector

```css
.card p {
    color: gray;
}
```

Means any `p` inside `.card`.

---

## 2.6 Child Selector

```css
.card > p {
    color: red;
}
```

Only direct children.

---

## 2.7 Adjacent Sibling

```css
h2 + p {
    margin-top: 0;
}
```

Selects the immediately following `p`.

---

## 2.8 General Sibling

```css
h2 ~ p {
    color: gray;
}
```

Selects following sibling paragraphs.

---

## 2.9 Attribute Selectors

```css
input[type="text"] {
    border: 1px solid gray;
}
```

```css
input[required] {
    border-color: red;
}
```

Starts with:

```css
[href^="https"]
```

Ends with:

```css
[href$=".pdf"]
```

Contains:

```css
[href*="github"]
```

---

## 2.10 Pseudo-Classes

Pseudo-classes represent states or conditions.

```css
button:hover {
    background: black;
}
```

Common pseudo-classes:

```text
:hover
:active
:focus
:focus-visible
:disabled
:checked
:first-child
:last-child
:nth-child()
:not()
:is()
:where()
:has()
```

Example:

```css
button:focus-visible {
    outline: 3px solid blue;
    outline-offset: 3px;
}
```

---

## 2.11 Pseudo-Elements

Pseudo-elements style a part of an element.

```css
p::first-letter {
    font-size: 2rem;
}
```

Common examples:

```text
::before
::after
::first-letter
::first-line
::selection
```

Example:

```css
.link::after {
    content: "";
    display: block;
    width: 0;
    height: 2px;
    background: currentColor;
    transition: width 200ms;
}

.link:hover::after {
    width: 100%;
}
```

---

## 2.12 Specificity

Mental hierarchy:

```text
Inline style
    ↓
ID
    ↓
Class / Attribute / Pseudo-class
    ↓
Element / Pseudo-element
    ↓
Universal
```

Example:

```css
p {
    color: blue;
}

.text {
    color: green;
}

#title {
    color: red;
}
```

An element with all three receives:

```text
red
```

because the ID selector is more specific.

---

## 2.13 Specificity Examples

```css
#header .nav a
```

Specificity:

```text
IDs:      1
Classes:  1
Elements: 1

= 1-1-1
```

```css
.container .card button:hover
```

Specificity:

```text
IDs:      0
Classes:  3
Elements: 1

= 0-3-1
```

---

## 2.14 `!important`

```css
.title {
    color: red !important;
}
```

Use this sparingly.

Overusing `!important` usually indicates a specificity or architecture problem.

---

## Practice

Build a selector playground demonstrating:

- element selector
- class selector
- ID selector
- child selector
- descendant selector
- attribute selector
- hover
- focus
- nth-child
- before/after

---

# Lesson 3 — Colors, Units & Typography

## 3.1 HEX

```css
color: #2563eb;
```

Short form:

```css
color: #fff;
```

---

## 3.2 RGB

```css
color: rgb(37 99 235);
```

Transparency can be represented with:

```css
color: rgb(37 99 235 / 50%);
```

---

## 3.3 HSL

```css
color: hsl(221 83% 53%);
```

---

## 3.4 CSS Variables

```css
:root {
    --primary: #2563eb;
    --text: #111827;
    --muted: #6b7280;
}
```

Use:

```css
button {
    background: var(--primary);
}
```

Fallback:

```css
color: var(--unknown, blue);
```

---

## 3.5 Units

### px

Fixed CSS pixel unit.

```css
font-size: 16px;
```

### %

Relative to a relevant parent/container dimension.

```css
width: 50%;
```

### rem

Relative to the root element's font size.

```css
font-size: 1.5rem;
```

### em

Relative to the relevant element's font size.

```css
padding: 1em;
```

### vw

Viewport width.

```css
width: 50vw;
```

### vh

Viewport height.

```css
height: 100vh;
```

Modern viewport units:

```css
100svh
100lvh
100dvh
```

`dvh` is useful for dynamic mobile viewport sizing.

---

## 3.6 Typography

### Font family

```css
body {
    font-family:
        system-ui,
        -apple-system,
        "Segoe UI",
        sans-serif;
}
```

### Font size

```css
h1 {
    font-size: 3rem;
}
```

### Font weight

```css
font-weight: 700;
```

Common values:

```text
100
200
300
400
500
600
700
800
900
```

### Font style

```css
font-style: italic;
```

### Line height

```css
p {
    line-height: 1.7;
}
```

### Letter spacing

```css
h1 {
    letter-spacing: -0.02em;
}
```

### Text alignment

```css
text-align: center;
```

### Text transform

```css
text-transform: uppercase;
```

### Text decoration

```css
text-decoration: underline;
```

---

## 3.7 Text Overflow

```css
.title {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

For readable paragraphs:

```css
p {
    max-width: 65ch;
}
```

---

## 3.8 Responsive Typography

```css
h1 {
    font-size: clamp(2rem, 5vw, 5rem);
}
```

Structure:

```text
clamp(minimum, preferred, maximum)
```

---

## Professional Typography

```css
:root {
    --text-primary: #111827;
    --text-secondary: #4b5563;
}

body {
    margin: 0;
    font-family: system-ui, sans-serif;
    color: var(--text-primary);
    line-height: 1.5;
}

h1 {
    margin: 0;
    font-size: clamp(2.25rem, 5vw, 4rem);
    line-height: 1.1;
    letter-spacing: -0.02em;
}

p {
    max-width: 65ch;
    color: var(--text-secondary);
    font-size: 1.125rem;
    line-height: 1.7;
}
```

---

# Lesson 4 — Box Model

## 4.1 The Four Parts

```text
Content
  ↓
Padding
  ↓
Border
  ↓
Margin
```

Visual:

```text
┌──────────────────────────────┐
│            Margin            │
│   ┌──────────────────────┐   │
│   │       Border         │   │
│   │  ┌────────────────┐  │   │
│   │  │    Padding     │  │   │
│   │  │  ┌──────────┐  │  │   │
│   │  │  │ Content  │  │  │   │
│   │  │  └──────────┘  │  │   │
│   │  └────────────────┘  │   │
│   └──────────────────────┘   │
└──────────────────────────────┘
```

---

## 4.2 Padding

```css
.card {
    padding: 20px;
}
```

Directional:

```css
padding-top: 10px;
padding-right: 20px;
padding-bottom: 10px;
padding-left: 20px;
```

Shorthand:

```css
padding: 10px 20px;
```

Means:

```text
top/bottom = 10px
left/right = 20px
```

Four values:

```css
padding: 10px 20px 30px 40px;
```

Order:

```text
top right bottom left
```

---

## 4.3 Margin

```css
.card {
    margin: 20px;
}
```

Center a fixed/constrained block:

```css
.container {
    width: min(100% - 2rem, 1200px);
    margin-inline: auto;
}
```

---

## 4.4 Border

```css
.card {
    border: 1px solid #ddd;
}
```

Directional:

```css
border-top: 2px solid black;
```

---

## 4.5 Border Radius

```css
.card {
    border-radius: 12px;
}
```

Circle:

```css
.avatar {
    width: 100px;
    aspect-ratio: 1;
    border-radius: 50%;
}
```

---

## 4.6 Box Sizing

Default:

```css
box-sizing: content-box;
```

Professional reset:

```css
*,
*::before,
*::after {
    box-sizing: border-box;
}
```

With `border-box`, declared width includes content + padding + border.

---

## 4.7 Width Calculation

With `content-box`:

```css
.box {
    width: 300px;
    padding: 20px;
    border: 5px solid;
}
```

Actual outer width:

```text
300 + 20 + 20 + 5 + 5
= 350px
```

With `border-box`:

```text
outer width = 300px
```

---

## 4.8 Min and Max Sizes

```css
.container {
    min-width: 300px;
    max-width: 1200px;
}
```

Also:

```css
min-height
max-height
```

---

## 4.9 Box Shadow

```css
.card {
    box-shadow:
        0 10px 30px rgb(0 0 0 / 10%);
}
```

---

## 4.10 Outline

```css
button:focus-visible {
    outline: 3px solid blue;
    outline-offset: 3px;
}
```

Unlike borders, outlines generally don't participate in layout.

---

## 4.11 Margin Collapse

Vertical margins of normal block elements can sometimes collapse.

For example:

```css
h1 {
    margin-bottom: 20px;
}

p {
    margin-top: 30px;
}
```

The resulting gap isn't necessarily 50px.

Flexbox and Grid provide different layout behavior and avoid traditional margin collapse between their children.

Prefer:

```css
.container {
    display: flex;
    flex-direction: column;
    gap: 20px;
}
```

for predictable component spacing.

---

## Practice

Build a profile card containing:

- image
- name
- role
- description
- button
- padding
- border
- border-radius
- shadow
- focus state

---

# Lesson 5 — Display & Positioning

## 5.1 `display: block`

```css
div {
    display: block;
}
```

A block element generally starts on a new line and can occupy available inline space.

Examples:

```text
div
section
article
p
h1
```

---

## 5.2 `display: inline`

```css
span {
    display: inline;
}
```

Inline elements participate in text flow.

Examples:

```text
span
a
strong
em
```

---

## 5.3 `inline-block`

```css
.badge {
    display: inline-block;
}
```

Combines inline flow with the ability to control width/height more like a block.

---

## 5.4 `display: none`

```css
.hidden {
    display: none;
}
```

Element is removed from layout.

---

## 5.5 `visibility: hidden`

```css
.hidden {
    visibility: hidden;
}
```

Element is invisible but its layout space remains.

---

# Positioning

## 5.6 Static

Default:

```css
position: static;
```

Normal document flow.

---

## 5.7 Relative

```css
.card {
    position: relative;
}
```

The element remains in normal flow and becomes an important positioning reference for absolutely positioned descendants.

---

## 5.8 Absolute

```css
.badge {
    position: absolute;
    top: 10px;
    right: 10px;
}
```

Usually positioned relative to the nearest appropriate positioned ancestor.

Common pattern:

```css
.card {
    position: relative;
}

.badge {
    position: absolute;
    top: 10px;
    right: 10px;
}
```

---

## 5.9 Absolute Centering

```css
.child {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
```

---

## 5.10 Fixed

```css
.button {
    position: fixed;
    right: 20px;
    bottom: 20px;
}
```

The element is positioned relative to the viewport in the usual case and does not occupy normal flow space.

---

## 5.11 Sticky

```css
header {
    position: sticky;
    top: 0;
    z-index: 100;
}
```

Useful for:

- sticky headers
- sidebar navigation
- section headings

---

## 5.12 `inset`

Instead of:

```css
top: 0;
right: 0;
bottom: 0;
left: 0;
```

Use:

```css
inset: 0;
```

---

## 5.13 Z-Index

```css
.modal {
    position: fixed;
    z-index: 1000;
}
```

A larger z-index doesn't automatically beat every other element because stacking contexts matter.

---

## 5.14 Overflow

```css
.box {
    overflow: hidden;
}
```

Other values:

```text
visible
hidden
auto
scroll
clip
```

Examples:

```css
.card {
    overflow: hidden;
    border-radius: 16px;
}
```

---

## Practice

Create:

- sticky header
- card with absolute badge
- fixed help button
- modal overlay
- z-index layering
- image clipped inside rounded card

---

# Lesson 6 — Flexbox

## 6.1 What is Flexbox?

Flexbox is primarily a **one-dimensional layout system**.

```css
.container {
    display: flex;
}
```

Visual:

```text
┌──────────────────────────────┐
│ [A] [B] [C] [D]             │
└──────────────────────────────┘
```

---

## 6.2 Main Axis and Cross Axis

For:

```css
flex-direction: row;
```

```text
Main axis →
┌─────────────────────────┐
│ A    B    C    D        │
└─────────────────────────┘
```

Cross axis is vertical.

For:

```css
flex-direction: column;
```

Main axis becomes vertical.

---

## 6.3 `justify-content`

Controls distribution along the main axis.

```css
justify-content: flex-start;
justify-content: flex-end;
justify-content: center;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;
```

---

## 6.4 `align-items`

Controls alignment across the cross axis.

```css
align-items: stretch;
align-items: flex-start;
align-items: center;
align-items: flex-end;
align-items: baseline;
```

---

## 6.5 Perfect Centering

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

---

## 6.6 Direction

```css
flex-direction: row;
flex-direction: row-reverse;
flex-direction: column;
flex-direction: column-reverse;
```

---

## 6.7 Gap

```css
.container {
    display: flex;
    gap: 20px;
}
```

Directional:

```css
row-gap: 10px;
column-gap: 20px;
```

---

## 6.8 Wrapping

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

This allows items to move to new lines.

---

## 6.9 `align-content`

Controls distribution of multiple flex lines.

```css
.container {
    align-content: center;
}
```

It matters when there is extra cross-axis space and multiple lines.

---

## 6.10 Flex Item Properties

### Grow

```css
.item {
    flex-grow: 1;
}
```

### Shrink

```css
.item {
    flex-shrink: 1;
}
```

### Basis

```css
.item {
    flex-basis: 250px;
}
```

### Shorthand

```css
.item {
    flex: 1 1 250px;
}
```

---

## 6.11 `flex: 1`

```css
.card {
    flex: 1;
}
```

Commonly makes siblings share available space.

---

## 6.12 Order

```css
.item {
    order: 2;
}
```

Be careful: visual reordering can differ from source/reading order and affect accessibility.

---

## 6.13 `align-self`

```css
.item {
    align-self: flex-end;
}
```

Overrides the parent's `align-items` for that item.

---

## 6.14 Auto Margin

```css
.nav {
    display: flex;
}

.login {
    margin-left: auto;
}
```

This pushes `.login` toward the opposite side.

---

## 6.15 Responsive Cards

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 24px;
}

.card {
    flex: 1 1 250px;
}
```

---

## 6.16 `min-width: 0`

Flex items may have a content-based minimum size.

When content refuses to shrink:

```css
.content {
    min-width: 0;
}
```

This is especially useful in:

- dashboards
- chat interfaces
- sidebars
- long URLs
- cards

---

## Practice

Build:

- responsive navbar
- centered login page
- responsive card row
- sidebar + content
- footer with left and right sections

---

# Lesson 7 — CSS Grid

## 7.1 What is Grid?

Grid is a **two-dimensional layout system**.

```css
.container {
    display: grid;
}
```

Visual:

```text
┌────────┬────────┬────────┐
│   A    │   B    │   C    │
├────────┼────────┼────────┤
│   D    │   E    │   F    │
└────────┴────────┴────────┘
```

---

## 7.2 Columns

```css
.grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

---

## 7.3 `fr`

`fr` represents a fraction of available grid space.

```css
grid-template-columns: 1fr 2fr;
```

Approximately:

```text
1 part | 2 parts
```

---

## 7.4 `repeat()`

```css
grid-template-columns:
    repeat(3, 1fr);
```

---

## 7.5 Mixed Columns

```css
grid-template-columns:
    250px 1fr 250px;
```

---

## 7.6 Gap

```css
grid {
    gap: 24px;
}
```

Correct syntax:

```css
.container {
    display: grid;
    gap: 24px;
}
```

---

## 7.7 Responsive Cards

One of the most useful patterns:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(250px, 1fr));
    gap: 24px;
}
```

This can adapt automatically without many media queries.

---

## 7.8 `minmax()`

```css
grid-template-columns:
    repeat(3, minmax(200px, 1fr));
```

Means each track can range from 200px to 1fr.

---

## 7.9 Grid Placement

```css
.item {
    grid-column: 1 / 3;
}
```

Or:

```css
.item {
    grid-column: span 2;
}
```

Rows:

```css
grid-row: 1 / 3;
```

---

## 7.10 Grid Areas

```css
.layout {
    display: grid;

    grid-template-columns: 250px 1fr;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";
}
```

Children:

```css
.header {
    grid-area: header;
}

.sidebar {
    grid-area: sidebar;
}

.main {
    grid-area: main;
}

.footer {
    grid-area: footer;
}
```

---

## 7.11 Alignment

```css
justify-items: center;
align-items: center;
place-items: center;
```

These align grid items within their grid areas.

For the entire grid:

```css
justify-content: center;
align-content: center;
place-content: center;
```

---

## 7.12 Implicit Grid

If more items exist than explicitly defined tracks, Grid creates implicit tracks.

Control them:

```css
grid-auto-rows: 200px;
```

---

## 7.13 `grid-auto-flow`

```css
grid-auto-flow: row;
grid-auto-flow: column;
grid-auto-flow: dense;
```

Use `dense` carefully because visual packing can affect expected visual order.

---

## 7.14 `subgrid`

```css
.card {
    display: grid;
    grid-template-rows: subgrid;
}
```

This allows nested grid content to align with parent grid tracks.

---

## Practice

Build a responsive portfolio:

```text
Header
Hero
Projects
Skills
About
Contact
Footer
```

Use Grid for the major page structure and Flexbox for component internals.

---

# Lesson 8 — Responsive CSS

## 8.1 What is Responsive Design?

A responsive website adapts to:

```text
Mobile
Tablet
Laptop
Desktop
Large screens
```

Avoid designing separate websites for every device.

---

## 8.2 Viewport

Responsive behavior depends heavily on the viewport.

For modern web pages, include:

```html
<meta
    name="viewport"
    content="width=device-width, initial-scale=1"
>
```

---

## 8.3 Media Queries

```css
@media (max-width: 768px) {
    .nav {
        flex-direction: column;
    }
}
```

Or mobile-first:

```css
@media (min-width: 768px) {
    .nav {
        flex-direction: row;
    }
}
```

---

## 8.4 Mobile-First CSS

Start with mobile:

```css
.nav {
    flex-direction: column;
}
```

Then enhance:

```css
@media (min-width: 768px) {
    .nav {
        flex-direction: row;
    }
}
```

This is often easier to maintain.

---

## 8.5 Don't Blindly Memorize Breakpoints

Common values may be useful:

```text
480px
768px
1024px
1280px
```

But professional CSS should use breakpoints based on when the layout actually needs to change.

---

## 8.6 Responsive Container

```css
.container {
    width: min(100% - 2rem, 1200px);
    margin-inline: auto;
}
```

This means:

- keep horizontal breathing room
- never exceed 1200px
- center the content

---

## 8.7 Responsive Images

```css
img {
    max-width: 100%;
    height: auto;
}
```

For fixed aspect-ratio containers:

```css
.image {
    width: 100%;
    aspect-ratio: 16 / 9;
    object-fit: cover;
}
```

---

## 8.8 Responsive Typography

```css
h1 {
    font-size: clamp(2rem, 5vw, 5rem);
}
```

---

## 8.9 `min()`

```css
.container {
    width: min(90%, 1200px);
}
```

---

## 8.10 `max()`

```css
.section {
    padding: max(2rem, 5vw);
}
```

---

## 8.11 `calc()`

```css
.box {
    width: calc(100% - 40px);
}
```

---

## 8.12 Responsive Grid

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(250px, 1fr));
    gap: 1.5rem;
}
```

---

## 8.13 Responsive Sidebar

```css
.layout {
    display: grid;
    grid-template-columns: 1fr;
}

@media (min-width: 900px) {
    .layout {
        grid-template-columns: 250px 1fr;
    }
}
```

---

## 8.14 Avoid Forced Overflow Fixes

Don't automatically write:

```css
body {
    overflow-x: hidden;
}
```

First find the actual overflowing element.

Common causes:

- fixed widths
- oversized images
- long text
- large transforms
- grid minimum sizes
- absolute positioning

---

## 8.15 Responsive Debugging

Use browser DevTools:

```text
Inspect
→ Toggle device toolbar
→ Test widths
→ Inspect layout
→ Find overflow
```

---

## Practice

Build a complete responsive portfolio with:

- mobile-first CSS
- responsive navbar
- responsive hero
- responsive project grid
- responsive typography
- responsive images
- media queries
- `clamp()`
- `min()`
- `max()`

---

# Lesson 9 — Backgrounds & Images

## 9.1 Background Color

```css
.hero {
    background-color: #111827;
}
```

---

## 9.2 Background Image

```css
.hero {
    background-image: url("hero.jpg");
}
```

---

## 9.3 Background Size

```css
background-size: cover;
```

`cover` makes the background cover the entire box, potentially cropping it.

```css
background-size: contain;
```

Attempts to show the entire image within the box.

---

## 9.4 Background Position

```css
background-position: center;
```

Other examples:

```css
background-position: top;
background-position: center right;
background-position: 50% 30%;
```

---

## 9.5 Background Repeat

```css
background-repeat: no-repeat;
```

---

## 9.6 Background Attachment

```css
background-attachment: fixed;
```

Use carefully, especially on mobile devices.

---

## 9.7 Background Shorthand

```css
.hero {
    background:
        url("hero.jpg")
        center / cover
        no-repeat;
}
```

---

## 9.8 Multiple Backgrounds

```css
.hero {
    background:
        linear-gradient(rgb(0 0 0 / 50%), rgb(0 0 0 / 50%)),
        url("hero.jpg")
        center / cover
        no-repeat;
}
```

This creates an overlay.

---

# Gradients

## 9.9 Linear Gradient

```css
background:
    linear-gradient(135deg, #2563eb, #7c3aed);
```

---

## 9.10 Radial Gradient

```css
background:
    radial-gradient(circle, white, #dbeafe);
```

---

## 9.11 Conic Gradient

```css
background:
    conic-gradient(
        from 0deg,
        red,
        yellow,
        green,
        blue,
        red
    );
```

Useful for decorative effects and charts.

---

# Images

## 9.12 `object-fit`

```css
img {
    width: 100%;
    height: 300px;
    object-fit: cover;
}
```

Values:

```text
fill
contain
cover
none
scale-down
```

---

## 9.13 `object-position`

```css
img {
    object-position: center top;
}
```

---

## 9.14 `aspect-ratio`

```css
.thumbnail {
    aspect-ratio: 16 / 9;
}
```

Useful for:

- videos
- cards
- product images
- avatars
- thumbnails

---

## 9.15 Image Card

```css
.card {
    overflow: hidden;
    border-radius: 1rem;
}

.card img {
    display: block;
    width: 100%;
    aspect-ratio: 16 / 10;
    object-fit: cover;
}
```

---

## Practice

Create a landing-page hero with:

- background image
- gradient overlay
- heading
- description
- CTA
- responsive height
- responsive typography

---

# Lesson 10 — Forms & UI

## 10.1 Basic Form

```html
<form>
    <label for="email">Email</label>
    <input
        id="email"
        type="email"
        placeholder="you@example.com"
    >

    <button type="submit">
        Submit
    </button>
</form>
```

---

## 10.2 Label

Always associate labels with controls:

```html
<label for="name">Name</label>
<input id="name" type="text">
```

This improves usability and accessibility.

---

## 10.3 Input Styling

```css
input,
textarea,
select {
    width: 100%;
    padding: 0.75rem 1rem;

    border: 1px solid #d1d5db;
    border-radius: 0.5rem;

    font: inherit;
}
```

---

## 10.4 Focus

```css
input:focus {
    border-color: #2563eb;
}
```

Prefer:

```css
input:focus-visible {
    outline: 3px solid rgb(37 99 235 / 25%);
    outline-offset: 2px;
}
```

Don't remove focus indicators without replacing them with an accessible alternative.

---

## 10.5 Placeholder

```css
input::placeholder {
    color: #9ca3af;
}
```

Placeholder text should not replace a proper label.

---

## 10.6 Disabled

```css
button:disabled {
    opacity: 0.5;
    cursor: not-allowed;
}
```

---

## 10.7 Checked

```css
input[type="checkbox"]:checked {
    accent-color: #2563eb;
}
```

---

## 10.8 Validation

HTML:

```html
<input
    type="email"
    required
>
```

CSS:

```css
input:invalid {
    border-color: #dc2626;
}

input:valid {
    border-color: #16a34a;
}
```

Don't rely only on color to communicate errors.

---

## 10.9 `accent-color`

```css
input[type="checkbox"],
input[type="radio"] {
    accent-color: #2563eb;
}
```

---

## 10.10 Buttons

```css
.button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;

    min-height: 44px;
    padding: 0.7rem 1rem;

    border: 0;
    border-radius: 0.6rem;

    background: #2563eb;
    color: white;

    font: inherit;
    cursor: pointer;
}
```

---

## 10.11 Responsive Form

```css
.form {
    display: grid;
    gap: 1rem;
}

.form-row {
    display: grid;
    gap: 1rem;
}

@media (min-width: 700px) {
    .form-row {
        grid-template-columns: 1fr 1fr;
    }
}
```

---

## 10.12 Fieldset and Legend

```html
<fieldset>
    <legend>Personal Information</legend>

    ...
</fieldset>
```

Useful for grouping related controls.

---

## Practice

Build a professional signup form:

- name
- email
- password
- confirm password
- gender/radio options
- terms checkbox
- submit button
- focus states
- validation states
- responsive layout

---

# Lesson 11 — Transitions, Transforms & Animations

## 11.1 Transition

Basic:

```css
.button {
    transition: background 200ms ease;
}
```

Full syntax:

```css
transition:
    property
    duration
    timing-function
    delay;
```

Example:

```css
transition:
    transform 200ms ease,
    opacity 200ms ease;
```

---

## 11.2 Timing Functions

Common:

```text
linear
ease
ease-in
ease-out
ease-in-out
```

Custom:

```css
transition-timing-function:
    cubic-bezier(0.2, 0.8, 0.2, 1);
```

---

# Transform

## 11.3 Translate

```css
transform: translateX(20px);
```

```css
transform: translateY(-5px);
```

```css
transform: translate(20px, -5px);
```

---

## 11.4 Scale

```css
transform: scale(1.05);
```

---

## 11.5 Rotate

```css
transform: rotate(10deg);
```

---

## 11.6 Skew

```css
transform: skewX(10deg);
```

---

## 11.7 Transform Origin

```css
transform-origin: center;
```

Other values:

```css
transform-origin: top left;
```

---

## 11.8 Hover Card

```css
.card {
    transition:
        transform 200ms ease,
        box-shadow 200ms ease;
}

.card:hover {
    transform: translateY(-5px);
}
```

---

# Animations

## 11.9 Keyframes

```css
@keyframes fadeIn {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
```

Apply:

```css
.element {
    animation: fadeIn 500ms ease;
}
```

---

## 11.10 Animation Properties

```css
animation-name
animation-duration
animation-timing-function
animation-delay
animation-iteration-count
animation-direction
animation-fill-mode
animation-play-state
```

---

## 11.11 Infinite Animation

```css
.spinner {
    animation:
        spin 1s linear infinite;
}

@keyframes spin {
    to {
        transform: rotate(360deg);
    }
}
```

---

## 11.12 Pulse

```css
@keyframes pulse {
    0%,
    100% {
        transform: scale(1);
    }

    50% {
        transform: scale(1.05);
    }
}
```

---

## 11.13 Staggered Animation

```css
.item:nth-child(1) {
    animation-delay: 100ms;
}

.item:nth-child(2) {
    animation-delay: 200ms;
}

.item:nth-child(3) {
    animation-delay: 300ms;
}
```

---

## 11.14 Prefer Transform and Opacity

Prefer:

```css
transform
opacity
```

for many UI animations because they can often be handled more efficiently by browsers.

Avoid unnecessarily animating layout-heavy properties such as:

```text
width
height
top
left
```

when transform can achieve the same visual result.

---

## 11.15 Reduced Motion

Respect users who prefer reduced motion:

```css
@media (prefers-reduced-motion: reduce) {
    *,
    *::before,
    *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
        scroll-behavior: auto !important;
    }
}
```

---

## Practice

Create an animated developer portfolio:

- animated hero
- card hover
- button hover
- loading spinner
- fade-up sections
- animated underline
- reduced-motion support

---

# Lesson 12 — Modern CSS

## 12.1 CSS Custom Properties

```css
:root {
    --primary: #2563eb;
    --surface: #ffffff;
    --text: #111827;
}
```

Use:

```css
.button {
    background: var(--primary);
}
```

---

## 12.2 Local Variables

```css
.card {
    --card-padding: 1.5rem;

    padding: var(--card-padding);
}
```

Variables can be scoped.

---

## 12.3 `calc()`

```css
.box {
    width: calc(100% - 40px);
}
```

---

## 12.4 `min()`

```css
.container {
    width: min(100% - 2rem, 1200px);
}
```

---

## 12.5 `max()`

```css
.section {
    padding: max(2rem, 5vw);
}
```

---

## 12.6 `clamp()`

```css
h1 {
    font-size: clamp(2rem, 5vw, 5rem);
}
```

Structure:

```text
clamp(minimum, preferred, maximum)
```

---

## 12.7 `:is()`

```css
.card :is(h1, h2, h3) {
    margin: 0;
}
```

Useful for grouping selectors.

---

## 12.8 `:where()`

```css
.card :where(h1, h2, h3) {
    margin: 0;
}
```

`:where()` always has zero specificity.

Useful for low-specificity base styles.

---

## 12.9 `:not()`

```css
button:not(.primary) {
    background: gray;
}
```

---

## 12.10 `:has()`

`:has()` enables parent/relational selection.

```css
.card:has(img) {
    border: 2px solid blue;
}
```

Form example:

```css
.form-group:has(input:invalid) {
    color: #dc2626;
}
```

---

## 12.11 CSS Nesting

Modern CSS supports nesting:

```css
.card {
    padding: 1rem;

    h2 {
        margin: 0;
    }

    &:hover {
        transform: translateY(-4px);
    }
}
```

Avoid excessive nesting because it can make selectors difficult to understand.

---

## 12.12 Logical Properties

Instead of:

```css
margin-left: auto;
```

you can often use:

```css
margin-inline-start: auto;
```

Common logical properties:

```text
margin-inline
margin-block
padding-inline
padding-block
border-inline
border-block
inset-inline
inset-block
```

Centering:

```css
margin-inline: auto;
```

---

## 12.13 Modern Colors

```css
color: oklch(60% 0.2 250);
```

Other modern functions:

```text
oklab()
oklch()
color-mix()
```

Example:

```css
background:
    color-mix(
        in srgb,
        blue 70%,
        white
    );
```

---

## 12.14 `@supports`

```css
@supports (display: grid) {
    .layout {
        display: grid;
    }
}
```

Selector support:

```css
@supports selector(:has(*)) {
    .card:has(img) {
        ...
    }
}
```

---

## 12.15 Cascade Layers

```css
@layer reset, base, components, utilities;
```

Example:

```css
@layer reset {
    *,
    *::before,
    *::after {
        box-sizing: border-box;
    }
}

@layer base {
    body {
        margin: 0;
    }
}

@layer components {
    .button {
        padding: 0.75rem 1rem;
    }
}

@layer utilities {
    .hidden {
        display: none;
    }
}
```

---

## 12.16 Container Queries

Media queries respond to the viewport.

Container queries respond to the component's container.

```css
.card-wrapper {
    container-type: inline-size;
}
```

Then:

```css
@container (min-width: 500px) {
    .card {
        display: grid;
        grid-template-columns: 200px 1fr;
    }
}
```

This is excellent for reusable components.

---

## 12.17 Modern Card

```css
.card {
    container-type: inline-size;

    padding: clamp(1rem, 3vw, 2rem);

    border-radius: 1rem;

    transition:
        transform 200ms ease;
}

.card:hover {
    transform: translateY(-4px);
}

@container (min-width: 500px) {
    .card {
        display: grid;
        grid-template-columns: 200px 1fr;
    }
}
```

---

## Practice

Build a responsive product card using:

- CSS variables
- `clamp()`
- Grid
- nesting
- container queries
- `aspect-ratio`
- `object-fit`
- hover
- focus-visible
- logical properties

---

# Lesson 13 — Advanced CSS

## 13.1 Advanced Specificity

A useful mental model:

```text
Inline
  ↓
ID
  ↓
Class / Attribute / Pseudo-class
  ↓
Element / Pseudo-element
```

Example:

```css
#header .nav a {
    color: red;
}
```

Specificity:

```text
1 ID
1 class
1 element
```

---

## 13.2 `:is()`, `:not()`, `:has()`

These functions take the specificity of the most specific selector in their argument list.

Example:

```css
:is(#main, .card) {
    color: red;
}
```

The `#main` argument gives ID-level specificity.

By contrast:

```css
:where(#main, .card) {
    color: red;
}
```

has zero specificity.

---

## 13.3 Cascade Order

A simplified model:

```text
Origin + importance
        ↓
Cascade layer
        ↓
Specificity
        ↓
Source order
```

Don't think of specificity as the only part of the cascade.

---

## 13.4 Inheritance Keywords

```css
color: inherit;
```

Explicitly inherits.

```css
color: initial;
```

Uses the property's initial value.

```css
color: unset;
```

Acts as inherit for inherited properties and initial for non-inherited properties.

```css
all: revert;
```

Can return control toward earlier cascade origins.

```css
color: revert-layer;
```

Reverts toward the value from an earlier cascade layer.

---

# Stacking Contexts

## 13.5 Why Huge `z-index` Can Fail

Suppose:

```css
.parent {
    position: relative;
    z-index: 1;
}

.child {
    position: absolute;
    z-index: 999999;
}

.other {
    position: relative;
    z-index: 2;
}
```

The child is still constrained by its parent's stacking context.

Think:

```text
Parent context = 1
    └── Child = 999999

Other context = 2
```

The entire parent context can remain below the other context.

---

## 13.6 Common Stacking Context Triggers

Common examples include:

```text
position + relevant z-index
opacity < 1
transform
filter
isolation: isolate
```

There are additional cases defined by the CSS specifications.

---

## 13.7 Professional Z-Index Scale

```css
:root {
    --z-base: 0;
    --z-dropdown: 100;
    --z-sticky: 200;
    --z-modal: 300;
    --z-toast: 400;
}
```

Use:

```css
.modal {
    z-index: var(--z-modal);
}
```

Avoid random huge values.

---

# Containing Blocks

## 13.8 Absolute Positioning

Common pattern:

```css
.card {
    position: relative;
}

.badge {
    position: absolute;
    inset-block-start: 10px;
    inset-inline-end: 10px;
}
```

The card establishes the relevant positioning context.

---

# Advanced Flexbox

## 13.9 Flex Shorthand

```css
.item {
    flex: 1 1 300px;
}
```

Conceptually:

```text
grow   = 1
shrink = 1
basis  = 300px
```

---

## 13.10 `min-width: 0`

Important:

```css
.item {
    min-width: 0;
}
```

This can solve unexpected overflow in flex layouts.

---

## 13.11 Auto Margin

```css
.nav {
    display: flex;
}

.actions {
    margin-inline-start: auto;
}
```

---

# Advanced Grid

## 13.12 `minmax()`

```css
grid-template-columns:
    repeat(3, minmax(200px, 1fr));
```

---

## 13.13 `auto-fit`

```css
grid-template-columns:
    repeat(auto-fit, minmax(250px, 1fr));
```

Excellent for responsive card layouts.

---

## 13.14 `auto-fill`

```css
grid-template-columns:
    repeat(auto-fill, minmax(250px, 1fr));
```

Can maintain empty tracks when space is available.

---

## 13.15 Implicit Tracks

```css
grid-auto-rows: 200px;
```

Controls automatically generated rows.

---

## 13.16 Dense Placement

```css
grid-auto-flow: dense;
```

Can fill gaps but should be used carefully when visual order matters.

---

## 13.17 Named Grid Lines

```css
.layout {
    display: grid;

    grid-template-columns:
        [sidebar-start] 250px
        [sidebar-end content-start] 1fr
        [content-end];
}
```

---

## 13.18 Subgrid

```css
.card {
    display: grid;
    grid-template-rows: subgrid;
}
```

Useful for consistent alignment between nested components.

---

# Intrinsic Sizing

## 13.19 `min-content`

```css
.item {
    width: min-content;
}
```

The content is allowed to become as small as its content constraints permit.

---

## 13.20 `max-content`

```css
.item {
    width: max-content;
}
```

Allows content to take the space needed without normal wrapping where possible.

Use carefully because it can cause overflow.

---

## 13.21 `fit-content()`

```css
.item {
    width: fit-content(300px);
}
```

Useful when you want content-driven sizing with a limit.

---

# CSS Architecture

## 13.22 Suggested Project Structure

```text
styles/
│
├── reset.css
├── tokens.css
├── base.css
│
├── components/
│   ├── button.css
│   ├── card.css
│   ├── navbar.css
│   └── modal.css
│
├── layouts/
│   ├── header.css
│   ├── dashboard.css
│   └── grid.css
│
└── utilities/
    ├── spacing.css
    └── typography.css
```

---

# BEM

## 13.23 Block

```html
<article class="card"></article>
```

## 13.24 Element

```html
<h2 class="card__title"></h2>
```

## 13.25 Modifier

```html
<button class="card__button card__button--primary">
```

Structure:

```text
card
 ├── card__title
 ├── card__description
 └── card__button
          └── card__button--primary
```

---

# Design Tokens

## 13.26 Tokens

```css
:root {
    --color-primary: #2563eb;
    --color-danger: #dc2626;

    --space-xs: 0.25rem;
    --space-sm: 0.5rem;
    --space-md: 1rem;
    --space-lg: 2rem;

    --radius-sm: 0.375rem;
    --radius-md: 0.75rem;

    --shadow-sm:
        0 2px 8px rgb(0 0 0 / 8%);
}
```

Use:

```css
.card {
    padding: var(--space-lg);
    border-radius: var(--radius-md);
    box-shadow: var(--shadow-sm);
}
```

---

# CSS Performance

## 13.27 Prefer Efficient Animations

Prefer:

```text
transform
opacity
```

when appropriate.

Avoid unnecessary animations of:

```text
width
height
top
left
```

when transform can accomplish the same visual effect.

---

## 13.28 Avoid Unnecessary `will-change`

Don't do:

```css
* {
    will-change: transform;
}
```

Use only when there is a measured or well-understood reason.

---

## 13.29 Expensive Effects

Use heavy effects carefully:

```text
filter
backdrop-filter
large shadows
complex animations
```

Performance depends on the browser, device, page structure, and effect.

---

# CSS Debugging

## 13.30 Professional Workflow

When CSS doesn't work:

```text
1. Inspect element
        ↓
2. Check matched selectors
        ↓
3. Check computed styles
        ↓
4. Check specificity
        ↓
5. Check box model
        ↓
6. Check display
        ↓
7. Check flex/grid
        ↓
8. Check overflow
        ↓
9. Check positioning
        ↓
10. Check stacking context
```

---

## Practice

Build a professional dashboard containing:

```text
┌──────────────────────────────────────────────┐
│                  NAVBAR                      │
├─────────────┬────────────────────────────────┤
│             │                                │
│  SIDEBAR    │             MAIN               │
│             │                                │
│ Dashboard   │   ┌─────┐ ┌─────┐ ┌─────┐   │
│ Users       │   │Card │ │Card │ │Card │   │
│ Projects    │   └─────┘ └─────┘ └─────┘   │
│ Settings    │                                │
│             │       Activity                 │
└─────────────┴────────────────────────────────┘
```

Requirements:

- CSS Grid
- Flexbox
- `minmax()`
- `auto-fit`
- variables
- `clamp()`
- BEM
- responsive design
- `min-width: 0`
- z-index
- sticky sidebar/header
- focus-visible
- cascade layers

---

# Lesson 14 — Real-World CSS Projects

This is where you combine everything.

---

# Project 1 — Profile Card

## Requirements

```text
Image
Name
Role
Description
Social links
Button
```

Use:

- box model
- typography
- colors
- border radius
- shadow
- Flexbox

---

# Project 2 — Login / Signup UI

Build:

```text
Logo
Heading
Email
Password
Remember me
Forgot password
Login
Social login
Signup link
```

Use:

- forms
- Grid/Flexbox
- focus-visible
- validation
- responsive layout

---

# Project 3 — Responsive Navbar

Desktop:

```text
Logo      Home About Projects Contact      Login
```

Mobile:

```text
Logo                              ☰
```

Use:

- Flexbox
- media queries
- transitions
- pseudo-classes
- accessible focus states

JavaScript can later control the mobile menu state.

---

# Project 4 — Landing Page

Sections:

```text
Navbar
Hero
Features
Statistics
Testimonials
Pricing
CTA
Footer
```

Use:

- Grid
- Flexbox
- gradients
- responsive typography
- animations
- variables
- container widths

---

# Project 5 — Developer Portfolio

Structure:

```text
Navbar
Hero
About
Skills
Projects
Experience
Education
Contact
Footer
```

Recommended CSS:

```text
CSS variables
Flexbox
Grid
clamp()
min()
max()
media queries
container queries
animations
focus-visible
BEM
```

---

# Project 6 — Dashboard

Structure:

```text
Sidebar
Header
Stats
Charts
Recent Activity
Users
Notifications
Footer
```

Use:

```text
Grid
Flexbox
sticky
overflow
z-index
responsive design
subgrid where useful
```

---

# Project 7 — E-Commerce UI

Build:

```text
Navbar
Search
Categories
Product Grid
Product Card
Filters
Product Details
Cart
Checkout
Footer
```

Product card:

```text
Image
Badge
Title
Rating
Price
Old price
Discount
Add to Cart
Wishlist
```

---

# Project 8 — SaaS Website

Structure:

```text
Navbar
Hero
Logo cloud
Features
How it works
Pricing
Testimonials
FAQ
CTA
Footer
```

Use:

- design tokens
- CSS Grid
- Flexbox
- responsive typography
- animations
- container queries
- BEM/components

---

# Project 9 — Full Responsive Portfolio

Final portfolio should contain:

```text
Home
About
Skills
Projects
Services
Experience
Education
Contact
```

Requirements:

```text
Mobile-first
Responsive navigation
Responsive images
CSS Grid
Flexbox
Animations
Reduced motion
Accessible forms
CSS variables
Modern CSS
Component architecture
BEM
Design tokens
```

---

# Final CSS Cheat Sheet

## Selectors

```css
p {}
.class {}
#id {}
* {}
a[href] {}
.card p {}
.card > p {}
h2 + p {}
h2 ~ p {}
button:hover {}
input:focus-visible {}
.card::before {}
```

---

## Box Model

```css
width
height
min-width
max-width
padding
margin
border
border-radius
box-sizing
box-shadow
outline
```

---

## Display

```css
display: block;
display: inline;
display: inline-block;
display: flex;
display: grid;
display: none;
```

---

## Position

```css
position: static;
position: relative;
position: absolute;
position: fixed;
position: sticky;

top
right
bottom
left
inset
z-index
```

---

## Flexbox

```css
display: flex;
flex-direction
justify-content
align-items
align-content
flex-wrap
gap
flex-grow
flex-shrink
flex-basis
flex
order
align-self
```

---

## Grid

```css
display: grid;
grid-template-columns
grid-template-rows
grid-template-areas
grid-column
grid-row
grid-area
grid-auto-flow
grid-auto-rows
gap
minmax()
repeat()
subgrid
```

---

## Responsive

```css
@media
clamp()
min()
max()
calc()
%
rem
em
vw
vh
svh
lvh
dvh
```

---

## Images

```css
object-fit
object-position
aspect-ratio
background-image
background-size
background-position
background-repeat
```

---

## Animation

```css
transition
transform
animation
@keyframes
opacity
cubic-bezier()
will-change
prefers-reduced-motion
```

---

## Modern CSS

```css
var()
calc()
min()
max()
clamp()

:is()
:where()
:not()
:has()

@supports
@layer
@container

margin-inline
padding-inline
inset-inline

oklch()
oklab()
color-mix()
```

---

# Professional CSS Checklist

Before considering a CSS project finished, check:

## Structure

- [ ] CSS is organized
- [ ] Components have clear names
- [ ] Repeated values use variables/tokens
- [ ] No unnecessary specificity
- [ ] No excessive `!important`

## Responsive

- [ ] Mobile works
- [ ] Tablet works
- [ ] Desktop works
- [ ] No horizontal overflow
- [ ] Images resize correctly
- [ ] Typography scales

## Accessibility

- [ ] Keyboard navigation works
- [ ] Focus indicators exist
- [ ] Form controls have labels
- [ ] Color isn't the only error indicator
- [ ] Reduced motion is respected
- [ ] Source order makes sense

## Performance

- [ ] Animations prefer transform/opacity
- [ ] Heavy effects are used intentionally
- [ ] `will-change` isn't everywhere
- [ ] CSS isn't unnecessarily duplicated

## Maintainability

- [ ] Variables/tokens are used
- [ ] Naming is consistent
- [ ] Components are reusable
- [ ] Breakpoints are based on layout needs
- [ ] Selectors aren't unnecessarily deep

---

# Final Learning Roadmap

```text
BEGINNER
│
├── CSS Syntax
├── Selectors
├── Colors
├── Units
├── Typography
├── Box Model
│
↓
INTERMEDIATE
│
├── Display
├── Position
├── Flexbox
├── Grid
├── Images
├── Forms
├── Pseudo-classes
├── Transitions
│
↓
RESPONSIVE
│
├── Media Queries
├── Mobile First
├── Responsive Grid
├── Responsive Flexbox
├── clamp()
├── min()
├── max()
├── calc()
├── Responsive Images
│
↓
ADVANCED
│
├── CSS Variables
├── Nesting
├── :is()
├── :where()
├── :not()
├── :has()
├── Logical Properties
├── Cascade Layers
├── Container Queries
├── Stacking Contexts
├── Intrinsic Sizing
├── Subgrid
│
↓
PROFESSIONAL
│
├── CSS Architecture
├── BEM
├── Design Tokens
├── Component Systems
├── Accessibility
├── Performance
├── DevTools
├── Design Systems
│
↓
REAL PROJECTS
│
├── Profile Card
├── Login UI
├── Responsive Navbar
├── Landing Page
├── Portfolio
├── Dashboard
├── E-Commerce UI
├── SaaS Website
└── Full Responsive Portfolio
```

---

# Final Goal

After completing this course, you should be able to take a design or screenshot and translate it into a responsive interface using:

```text
HTML
+
CSS
+
Flexbox
+
Grid
+
Responsive Design
+
Modern CSS
+
Accessibility
+
CSS Architecture
```

The most important skill is not memorizing hundreds of CSS properties.

The real skill is understanding:

```text
LAYOUT
+
SIZING
+
CASCADE
+
RESPONSIVENESS
+
COMPONENT DESIGN
+
ACCESSIBILITY
+
MAINTAINABILITY
```

Once these concepts are strong, you can build professional frontends for full-stack applications.
