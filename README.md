# Learning CSS

- [Learning CSS](#learning-css)
  - [Units](#units)
    - [EM](#em)
    - [REM](#rem)
  - [Pseudo-Classes](#pseudo-classes)
    - [:focus-within](#focus-within)
    - [:root](#root)
  - [Snippets](#snippets)
    - [SVG Dropdown shadow](#svg-dropdown-shadow)
    - [Hiding scroll](#hiding-scroll)
    - [Hiding input spinner](#hiding-input-spinner)
    - [Highlight every element from view](#highlight-every-element-from-view)

## Units

### EM

Is a unite based on it's parent's font-size, which means it carries on this size, by consequence that makes easy to gets confused.
Every time you see EM unity in one element it's same like says that it uses the current parent font-size and increase it relatively, as default 1em = 16px about, however if parent element has it's font-size changed to font-size: 32px, it's first level children will will have 1em = 32px.

### REM

Simple doesn't inherit the font-size from it's parent, it only inherit from root html.

## Pseudo-Classes

### :focus-within  

Allow you to attack the parent from the element in focus

### :root  

Allow  various default configurations, but mostly css variables creation
to create a variable, you set a '--variable-name: value;'

```css
:root {
  --hero-gradient: linear-gradient(-45deg, #9F02CC, #5484f4);
}
```

## Snippets

### SVG Dropdown shadow

```css
svg {
  filter: drop-shadow(0 0 4px #ff0090);
}

```

### Hiding scroll

```css
.scroll { /* Edge */
    -ms-overflow-style: none;
}
    
.scroll::-webkit-scrollbar { /* Chrome, Safari, Opera, Firefox */
    display: none; 
}
```

### Hiding input spinner

```css
.spinner { /* Firefox */
    
    -moz-appearance:textfield;
 }
    
.spinner::-webkit-outer-spin-button,
.spinner::-webkit-inner-spin-button { /* Chrome, Safari, Edge, Opera */
    -webkit-appearance: none;
    margin: 0;
}
```

### Highlight every element from view

```css
* { background-color: rgba(255,0,0,.2); }
* * { background-color: rgba(0,255,0,.2); }
* * * { background-color: rgba(0,0,255,.2); }
* * * * { background-color: rgba(255,0,255,.2); }
* * * * * { background-color: rgba(0,255,255,.2); }
* * * * * * { background-color: rgba(255,255,0,.2); }
* * * * * * * { background-color: rgba(255,0,0,.2); }
* * * * * * * * { background-color: rgba(0,255,0,.2); }
* * * * * * * * * { background-color: rgba(0,0,255,.2); }
```
