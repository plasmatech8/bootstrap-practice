# Bootstrap 4 Essential Training

See https://www.linkedin.com/learning/bootstrap-4-essential-training

- [Bootstrap 4 Essential Training](#bootstrap-4-essential-training)
  - [01. Getting Started](#01-getting-started)
  - [02. Using Basic Styles](#02-using-basic-styles)

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