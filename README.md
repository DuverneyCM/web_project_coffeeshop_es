# Triple Espresso

This project has the goal of appropiate knowledge and apply it in a real context, a Coffee Shop in this case. At the moment, we had learned techs like HTML, CSS, W3C Validators, style checkers like Prettier, Name conventions like BEM and Atomic, Web Browsers and Devtools, GitHub, MD documentation, Research aided by IA, among others.

## Optimizations and Future Works

- The main header image overlaps the text, so a transparency effect could be applied that adjusts as the screen size decreases, and the image also could be made slightly smaller.
- The form for reservations could be placed in a modal, though this would require the user to take extra steps to achieve their goal, and additional content would be needed to fill the page.
- The form for reservations should include a comments section, allowing users to share preferences or specify products they would like reserved or sourced.
- Create a "dark mode" version that loads automatically when the user's device or browser is set to dark mode.
- Section for product and service menus.
- Reviews section with a form for users to submit their own reviews.
- Login and logout options.
- Form for private comments/feedback (inquiries, complaints, claims, suggestions, and compliments).
- Direct contact information (mobile, WhatsApp, email) in addition to social media links.
- Responsive design to ensure the layout and sizing adapt to the device's screen.
- Backend integration for securely storing or retrieving data from databases, and dinamic content loaded from databases.

## Highlighting my learning

### HTML

- In header, the title, metadata and links to external sources (files or urls with icons, fonts, css, scripts, etc) that is loaded before the page.
- In body, one define the appareance of the webpage, that is, any element and is location in the DOM and their attibutes (classes, id, name, type, for, etc).
- \<div> is a generic tab to group content, but there are more specialized tags oriented to improve accesibility aspects, like: {header, footer, main, nav, section, fieldset, aside, among others}

### CSS

- **games**: I really appropiate better the concepts by playing games like [Flexbox Froggy](https://flexboxfroggy.com/) and [CSS Diner](https://flukeout.github.io/), and enjoy it a lot.

- **Selectors:** CSS look up for all the elements that match with the selector pattern, similar to a select query in sql. Next, apply the properties definded in the bracket block. Selectors can be by tag { **div** }, class { **.header** }, id { **#cel1** }, attribute { **[type="email"]** }, pseudoclass{ **:hover** }, pseudoelement { **::after** } or universal { **\*** }. You can combine multiple selectors to define a new selector pattern. This combination can be:
  - **composed** (.p1.p2.p3): without spaces, is like an AND gate, applying the style to all the elements that have **all the selectors** of the list.
  - **grouped** (.p1, .p2, .p3): with spaces, is like an OR gate, applying the style to all the elements that have **at least one selector** of the list.
  - **descendant or child** (main .h2): all .h2 that decend (or are contained) from main
  - **direct child** (main > .h2): only direct descendants. That
  - **adyacents or siblings** (.p1 ~ .p2): all .p2 that are after and at the same level that .p1.
  - **direct sibling** (.p1 + .p2): only .p2 that are just after .p1
  - **nesting** (&h1, & h1, h1): Selectors inside the selector block are nested by starting with &. Nesting without space (&h1) is equivalent to composed. Nesting with space (or without &) is equivalent to descendant.
  - **attribute's match modifiers** (=, ^=, $=, \*=, ~=, |=): attribute selectors like [type="email"] can match patterns in many ways: Exact match, Start with, End with, contain inside, contain a word separated by spaces (similar to .word in class), contain a exact word that can end with a dash (like lang="en" for "en" and "en-us" ).
  - **pseudos as filters**: state (:checked), events (:hover), conditions (:last-child), filter functions ( :not(.h2) or :nth-of-type(3n + 2) )

- **at-rules:** They are special instructions that say to the browser additional behavior, instead of apply the styles in waterfall. Some are: @media, @keyframes, @support, @import, @font-face, @charset, @layer, @container and @property.

- **Style Specificity:** It is based on a 4-column priority vector [a,b,c,d], where priority decrease from left to right. Vector is calculated by counting the number of elements of each selector (or style attribute in html). Universal selector (\*), combinators (+, >, ~, ' ') and :where() don't modify the counting. In case of tie, the last declaration in css file is used. This order can be changes using !important modifier or @layer rule.
  - a = embedded html style e.g. style="color:blue"
  - b = id selectors e.g. #my-id
  - c = classes, pseudoclasses and attribute selectors, e.g .my-class :hover [type="text"]
  - d = elements and pseudo-elements e.g p ::after

- **Variables (--varname, var(--varname)):** In UI/UX, **assets** are associated to resource files (images, icons, fonts, videos, etc) that are external, but the project use it; and **design tokens** are centralized design values (brand colors, indentation, fonts, etc) used in the project UI. Both can be specified using variables in the :root (html tag) and using after with the function var(). Variables has scope, so you can define variables by section, taking effect only inside that section. You can assign other variable to a variable, which is useful to link different scopes declaration.

- **Built-in functions:** allow to perform dynamic operations without using JS. Some examples are:
  - var(): get a variable value
  - attr(): get an attribute value
  - calc(): perform basic math operations, combining different units
  - clam(min, ideal, max): set a range of values, indicating the prefered value.
  - min(), max(): return the min or maximum value.
  - rgb(), rgba(), hsl(), hsla(): to define colors in Red-Green-Blue or Hue-Saturation-Lightness, and opacity.
  - linear-gradient(), radial-gradient(): used inside the functions like background to generate gradients.
  - translate(), rotate(), scale(): used inside the **transform** property.

- **Position Property:** static by default, normal flow. Relative, absolute, and sticky are referenced to the near ancestor with the property position defined (body-tag layout if any ancestor is defined), whereas fixed is referenced to the viewport. All non-static values allow using coordinate ajustment by using top, right, bottom and left, and the property z-index.

- **Display Property** (none, block, inline, inline-block, flex, grid): Some properties only work depend of the display value in the parent.
  - **parent with flex:** in the parent (justify-content, align-items, align-content, flex-direction, flex-wrap, flex-flow, gap) and in the childs (flex-grow, flex-shrink, flex-basis, align-self, order).
    - justify-content: stretch, start, flex-start, end, flex-end, center, space-between, space-around, space-evenly.
    - align-items: stretch, start, flex-start, end, flex-end, center, baseline, self-start, self-end
    - align-content: stretch, start, flex-start, end, flex-end, center, space-between, space-around, space-evenly, normal
    - flex-direction: row, row-reverse, column, column-reverse
    - flex-wrap: no-wrap, wrap, wrap-reverse
    - flex-flow: \<flex-direction> \<flex-wrap>;
    - gap: spacing between items.
    - flex-grow: (float >= 0) 0 by default. Increase/distributed proportionally the size of children to fit the container size, based on this value, so value=0 don't increase his size.
    - flex-shrink: (float >= 0) 0 by default. Decrease/distributed proportionally the size of children to fit the container size, based on this value, so value=0 don't decrease his size. Excess space only make sense with nowrap.
    - align-self: overwrite in the child the align-items defined in the parent.
    - order: […, -2, -1, 0, 1, 2, …]

  - **parent with grid:** in the parent (grid-template-columns, grid-template-rows, grid-template-areas, gap) and in the child (grid-column, grid-row, grid-area)

- **Dimension properties:** width (min-width, max-width), height (min-height, max-height), padding, border, margin, box-sizing
- **Typing:** font (-family, -size, -weight, -style), line-height, color
- **Visuals:** background (-color, -image, -repeat, -position, -size), box-shadow, opacity, border-radius, overflow

### Web Browser Devtools

- Box view, so usefull to find issues in padding, border, margin and dimensions of an element.
- Add and edit code directly in DevTools.
- Easy selection or location of any component both from the code or the page itself.
- See the effects of z-index, in special negative values where the transparent body layer covers the other elements and avoid to select/locate them directly from the page.
- Locate elements by coding selectors or xpath.
