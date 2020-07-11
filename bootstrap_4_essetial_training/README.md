# Bootstrap 4 Essential Training

See https://www.linkedin.com/learning/bootstrap-4-essential-training

- [Bootstrap 4 Essential Training](#bootstrap-4-essential-training)
  - [01. Getting Started](#01-getting-started)
  - [02. Using Basic Styles](#02-using-basic-styles)
    - [Basic Typography](#basic-typography)
    - [Typographic Utilities](#typographic-utilities)
    - [Blockquotes and lists](#blockquotes-and-lists)
    - [Using Colors with bootstrap](#using-colors-with-bootstrap)
    - [Work with images](#work-with-images)
    - [CSS variables](#css-variables)
  - [03. Mastering Layout with Bootstrap](#03-mastering-layout-with-bootstrap)
    - [Containers](#containers)
    - [Rows and Columns](#rows-and-columns)
    - [Usage Notes](#usage-notes)
    - [Offset columns](#offset-columns)
    - [Nested columns, Custom order](#nested-columns-custom-order)
    - [Grid alignment options](#grid-alignment-options)

## 01. Getting Started

Install options:
* Download the precompiled CSS and JS
* Use bootstrap CDN link (browser grabs from CDN and stores in browser)
* Download source files (original source files, SASS, JS, etc)

CDN is good for production. precompiled CSS/JS is good for development.

The `css` and `js` folder contains:
* Normal versions
* Minified versions
* Grid only versions
* Maps for link to the original SASS
* Bundle version (also includes popper.js library)

We will likely only need **bootstrap.min.css** and **bootstrap.min.js**.

We will need:
* jQuery (`npm install jquery` see [here](https://jquery.com/))
* PopperJS (`npm i @popperjs/core` see [here](https://popper.js.org/))

In `index.html`, the `.container` class is a bootstrap class that allows
everything to fit to the default grid.

## 02. Using Basic Styles

Browser styles are default styles stored by the browser. Custom CSS is usually
added to style your website.

Browser Styles -> Bootstrap CSS -> Custom CSS

**Reboot** makes styles consistent across different browsers and platforms.
(uses 1rem instead of 16px)

### Basic Typography

How bootstrap handles typography:
* **`Reboot.css` styles**
  * At start of bootstrap code, there are `Reboot.css` styles to normalise.
* **Use `Rems`**
* **Avoid `margin-top`**
  * Use only margin-bottom to space elements
* **Use `inherit` when possible**
* **Use `border-box`**
  * box-sizing is element only, border-box is box + padding
* **Use `native font stacks`**
  * Good for native devices
* **Special styles**
  * There are bootstrap classes for styling such as: `h1`, `h2`, `p`, etc.
*** Display styles**
  * Other bootstrap classes: `display-1`, `display-2`, `lead` (bigger paragraph), etc

### Typographic Utilities

Horizontal Alignment:
* `text-justify`
  * On a big paragraph, aligned both sides to sides.
* `text-XX-POS`
  * Use to do something at different viewport sizes
  * XX: sm (> 576px), mx (> 768px), lg (> 992px), xl (> 1200px)
  * POS: left, center, right

Line Height Alignment
* `aligh-SID`
  * For inline, inline block, inline table, table cell elements
  * SID: baseline, top, middle, bottom, text-bottom, text-top, right


Capitalisation:
* `text-TYP`
  * TYP: lowercase, uppercase, capitalize, monospace

Text Styles:
* `font-STYL`
  * STYL: italic, weight-normal, weight-light, weight-ligher, weight-bold, weight-bolder

Text modifiers:
* `text-decoration-none`
  * Removes hyperlink underline
* `text-reset`
  * Removes hyperlink color

Flow:
* `text-FLOW`
  * FLOW: wrap, nowrap, break, truncate (elipses)
  * How words off the page are handled.

### Blockquotes and lists

Lists:
* `list-unstyled` no bullets
* `list-inline` & `list-inline-item` inline lists

Blockquotes:
* `blockquote` & `blockquote-footer` for blockquotes
* `blockquote-reverse` for right-aligned

### Using Colors with bootstrap

* `text-COLOR`
  * COLOR: primary, secondary, successs, danger, warming, info, light, dark, white, **transparent**, etc

### Work with images

Formatting images:
* `img-fluid` responsive + automatically adjust to width of container
* `img-thumbnail` rounded 1px border
* `ROUNDED-SID-SHA-SIZ`
  * (optional) SID: top, right, bottom, left
  * (optional) SHA: circle, pill
  * (optional) SIZ: 0, sm, lg

Aligning images:
* `float-left` or `float-right`
* `text-center` center inlign element
* `mx-auto` center block element

Figures:
* `<figure class="figure">` Figure
* `<img class="figure-img">` Image
* `<figure class="figure-caption">` Text

### CSS variables

You can use CSS variables with bootstrap.

This version of bootstrap provides pre-written CSS variables.

Variables:
* New feature in CSS
* Browser support is very low.
* Use `var()` and `:root`

Color/Contextual variables:
* `--blue`, `--indigo`, `--primary`, `--secondary`, `--info` `--danger`, etc

Media queries:
* `--breakpoint-sm`, `--breakpoint-md`, `--breakpoint-lg`, etc

Fonts:
* `--font-family-sans-serif`, `--font-family-monospace`, etc

e.g.
```html
<style>
    :root {
    --pink: #C4226F
    }
</style>

<h2 style="color: var(--pink);">Testimonials</h2>
```
Note that if we try to override `--danger`, it will not work because it is hard
coded into the bootstrap CSS and has the `!important` keyword (overrides all).

Think of CSS variables just as shortcuts.

## 03. Mastering Layout with Bootstrap

### Containers

The grid is a responsive 12-column system.

Uses Flexbox.

Need to know classes: `container`, `row`, `column`

Grid Containers:
* `container(-SIZ)`
  * SIZ: sm, md, lg, xl, fluid
  * Each size will cause the conainer to snap to a maximium size, or 100% page width
  * Containers include 15px padding (30px gutter between contrainers)

### Rows and Columns

Rows:
* `row`
* `row-cols(-BP)(-COL)`
  * BP: sm, md, lg, xl
  * COL: 1-6
* `no-gutters`
  * Removes grid spacing

Columns:
* `col(-BP)(-COL)`
  * BP: sm, md, lg, xl
  * COL: 1-12
  * `column`s must be inside of a `row`
  * Columns will attempt to wrap to the next line when there is not enough space

Aligning columns:
* Vertical: `align-TYP-DIR`
  * TYP: items, self
  * DIR: start, center, end
* Horizontal: `justify-content-DIR`
  * DIR: start, center, end, around, between

### Usage Notes

We can make a grid that starts with 4 columns, and snaps to 2 columns when
there is not enough space: `class="row row-cols-2 row-cols-lg-4"` (at the large
break-point, take up a 4 break-points of width). This is better than having the
second row items being stretched.

You can make some cells take more space by setting `class="column-6"` (6/12 of
the available vertical grid spaces).

If we set three columns to a width of BP=3 (totalling 9 BP), we will have 3
BP of empty space to the right. We can centre the grid using
`class="row justify-content-center"`

`vh-100`: set vertical height to 100%

`bg-secondary`: set colour to secondary **can help to see cells**

`img-thumbnail`: create frame around image **can help to see img**

We can either use `class="row row-cols-2"` to create equal columns of 2, or we
can set all columns to use `class="col-6"` to give custom spacing. We can also
specify the BPs for each col so that the sizing is only applied at certain
container widths.

### Offset columns

Just shifts a column over. Can be used to add empty space on either side of the
cells. For alignment, it is better to use alignment/flexbox utilities.

`offset-BP-COL`
* BP: sm, md, lg, xl
* COL: 1-11

### Nested columns, Custom order

We can put grids inside of grids by putting another set of row/col tags inside
of a grid tag.

We can customize order using class: `order(-BP)-ORD`. We can also use flexbox
classes: `d-flex` and `flex-column`.

### Grid alignment options

Vertical:
* `align-items-ALN`
  * ALN: start, center, end

Individual/horizontal alignment:
* `align-self-ALN`
  * ALN: start, center, end (top, center, bottom)
  * **Use to add vertical positioning of cells in a row**

Horizontal alignment:
* `justify-content-ALN`
  * ALN: start, center, end, around, between
  * Column width needs to be specified
  * **Use to add horizontal spacing between cells in a row**

We can use these to ensure that taller cells are aligned with each other.

