# Learning SCSS

- [Learning SCSS](#learning-scss)
  - [Fonts include](#fonts-include)
  - [Partials](#partials)

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
