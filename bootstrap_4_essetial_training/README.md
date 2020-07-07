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

