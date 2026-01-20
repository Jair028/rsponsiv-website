Project Setup:
Global Styles (Foundation Layer)

every element _{}
pseudo elements _::before, \*::after

-->Boilerplate
Purpose:
Reset browser quirks
Establish defaults
Remove body margin
Set base font family
-Fonts
-Font Size
This file exists in every project.

    --fs-14: calc(14 / 16 * 1rem);
    --fs-16: calc(16 / 16 * 1rem);
    --fs-24: calc(24 / 16 * 1rem);
    --fs-36: calc(36 / 16 * 1rem);
    --fs-42: calc(42 / 16 * 1rem);
    --fs-48: calc(48 / 16 * 1rem);
    --fs-72: calc(72 / 16 * 1rem);

    --font-size-topnav: var(--fs-14);
    --font-size-h1: var(--fs-42);
    --font-size-h2: var(--fs-36);
    --font-size-h3: var(--fs-24);

    @media (width >= calc(600 / 16 * 1rem))
      --font-size-topnav: var(--fs-16);
      --font-size-h1: var(--fs-72);
      --font-size-h2: var(--fs-48);

-->Colors
Use CSS custom properties, not Sass variables.
Rules
Prefix variables by purpose (--color-\*)
Use HSL for easy light/dark variations
Root variables = global
Local variables allowed inside components

    --c-white: hsl(0, 0%, 100%);
    --c-gray-dark: hsl(233, 14%, 25%);
    --c-purple: hsl(232, 58%, 55%);
    --c-teal: hsl(180, 100%, 42%);
    --c-transparent: transparent;
    --c-magenta: hsl(320, 85%, 41%);

    --color-main-bg: var(--c-white);
    --color-text-dark: var(--c-gray-dark);
    --color-text-light: var(--c-white);
    --color-header-bg: var(--c-purple);
    --color-hero-bg: var(--c-purple);
    --color-button-primary-bg: var(--c-teal);
    --color-button-primary-text: var(--c-gray-dark);
    --color-button-secondary-bg: var(--c-transparent);
    --color-button-secondary-border: var(--c-white);
    --color-button-secondary-text: var(--c-white);
    --color-fullwidth-bg: var(--c-magenta);

-->Layout
This file controls spacing and structure, not appearance.
Wrapper classes
Max-width logic
Padding helpers
Padding Rule
Always prefer padding over margins for section spacing.
This prevents margin collapse bugs.

-->Decoration
Reusable stylistic helpers:
Rounded corners
Highlights
Emphasis styles
These styles should:
Be optional
Work anywhere

Utility Layer (Logic, Not Styles)

-->Functions
Rules
Use pixels only as inputs
Output must be relative units

-->Mixins
Breakpoints with Maps
Rules
Breakpoints use em, never px
Maps prevent magic numbers
Media queries scale with font size

<!-- ----------------------------------------------------- -->

+++++ HTML Rules
Semantic First
Use the correct element before adding classes:
header, nav, main, section, footer
Lists for navigation
HTML describes content meaning, not appearance.

++++++ BEM Naming System (Primary Styling Method)
Format
.block
.block**element
.block**element--modifier
Rules
Block = component
Element = child
Modifier = variation

+++++++ Accessibility Rules (Non Optional)
Font sizes use rem
Spacing uses rem
Media queries use em
Layout must survive increased font size
Test by doubling browser font size.
If layout breaks → fix it.

+++++++ Default Browser Styles Awareness
Know that these have default margins:
p
h1–h6
Vertical margins collapse.
Fix with:
Padding
Border
Block formatting context
Never fight margin collapse blindly — understand it.

+++++++ JavaScript Philosophy
JavaScript is for:
Toggling classes
Enhancing UX
JavaScript is not for layout.

+++++++ Final Rule
If you can’t explain why a style exists, delete it.
This system is meant to be boring, predictable, and powerful.
That’s how professional front end websites are built.
