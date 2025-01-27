# Learning SCSS

- [Learning SCSS](#learning-scss)
  - [Fonts include](#fonts-include)
  - [Partials](#partials)
  - [Variables](#variables)
    - [SCSS Variables vs. CSS Custom Properties (CSS Variables)](#scss-variables-vs-css-custom-properties-css-variables)
  - [Mixins](#mixins)

## Fonts include

```scss
@include font-face("ValueSansPro", "ValueSansPro-Italic", 300, "italic");
@include font-face("ValueSansPro", "ValueSansPro-MediumItalic", 400, "italic");
@include font-face("ValueSansPro", "ValueSansPro-Regular", 400, "normal");

@mixin font-face($font-family, $font-file, $weight, $style) {
  @font-face {
    font-family: $font-family;
    src: url($font-file + ".woff") format("woff"),
    url($font-file + ".ttf") format("truetype"),
    url($font-file + ".woff2") format("woff");
    font-weight: $weight;
    font-style: $style;
  }
}

```

## Partials

In scss/sass elements named with underscore `_card.scss` can be imported as partials

```scss
@import "./card.scss"
```

## Variables

SCSS variables are a powerful feature for managing and organizing your styles. They allow you to store values that can be reused throughout your stylesheet, making it easier to maintain and update your styles. They're especially useful for consistent design systems, responsive layouts, and themes.

**Setup SCSS variables:**

Create separate partial like `_variables.scss` for managing your variables within the stylesheets folder or as you see fit.

```scss
// app/assets/stylesheets/base/_variables.scss

$primary-color: #3498db;
$secondary-color: #2ecc71;
$font-size-base: 16px;
$font-family-base: 'Arial', sans-serif;
$padding-base: 20px;
$breakpoints: (
  sm: 576px,
  md: 768px,
  lg: 992px
);

```

**Usage:**

```scss
// _styles.scss

@import 'variables';

body {
  font-family: $font-family-base;
  font-size: $font-size-base;
  color: $primary-color;
}

```

### SCSS Variables vs. CSS Custom Properties (CSS Variables)

- **SCSS variables** are preprocessed and can be used only in SCSS files. They are replaced by their values when SCSS is compiled to CSS.

- **CSS Custom Properties (CSS Variables)** are runtime variables in the browser, which can be accessed and modified directly in CSS and JavaScript.

```scss
/* SCSS Variable */
$primary-color: #3498db;

/* CSS Custom Property (Runtime) */
:root {
  --primary-color: #3498db;
}
```

## Mixins

In simpler terms, mixins act like functions that you can call in your stylesheets to generate a block of CSS. This allows you to apply complex styles to different parts of your website without repeating the code each time.

**Example:**

```scss
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
  -moz-border-radius: $radius;
  border-radius: $radius;
}
```

**Usage:**

```scss
.box {
  @include border-radius(10px);
}
```
