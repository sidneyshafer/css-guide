# CSS Sandbox Part 1

>CSS snippets, examples, and code breakdown for learning the basics of CSS.

## Table of Contents

* **[CSS Basics](#css-basics)**
    * [External CSS](#external-css)
    * [Internal CSS](#internal-css)
    * [Inline CSS](#inline-css---not-recommend-as-best-practice)
    * [CSS Rules and Specificity](#css-rules-and-specificity)
    * [Best Practices](#best-practices)
* **[Selectors](#selectors)**
    * [Element Selector](#element-selector)
    * [Class Selector](#class-selector)
    * [ID Selector](#id-selector)
    * [Multiple Selectors](#multiple-selectors)
    * [Nested Selector](#nested-selector)
    * [Selector Best Practices](#selector-best-practices)
* **[Fonts](#fonts)**
    * [Font Family](#font-family)
    * [Google Fonts](#google-fonts)
    * [Font Size](#font-size)
    * [Line Height](#line-height)
    * [Font Weight](#font-weight)
    * [Font Style](#font-style)
* **[Colors](#colors)**
    * [The Color Property](#the-color-property)
    * [Color Definitions in the CSS](#color-definitions-in-the-css)
    * [Colors Best Practices](#color-best-practices)

## CSS Basics

>CSS stands for **Cascading Style Sheets**

### External CSS
```
<link rel="stylesheet" href="css/style.css">
```
* Links to an external CSS file. In this case, it is located at `css/style.css` (in a folder named `css`).
* External CSS keeps styles separate from HTML, improving maintainability and reusability across multiple webpages.
* Any CSS rules in `css/style.css` are applied to this document.

### Internal CSS
```
<style>
    h2 {
        color: green;
    }
</style>
```
* Internal CSS requires the `<style></style>` element within the `<head>` tag.
* Internal CSS applies styles to this specific HTML document without requiring an external file.
* Internal styles are only applied to the document in which it is defined in.
* This is useful for quick styles or when external styles may not be practical.
* In this example, the `<h2>` elements in the document will have green text (`color: green`).

### Inline CSS - Not Recommend as Best Practice
```
<h1 style="color: red;">Heading One</h1>
```
* Adds CSS directly to the `style` attribute of an HTML element.
* Inline CSS is used for quick, specific styling for individual elements.
* **Generally not recommended because it mixes style with structure, making it harder to maintain.**

### CSS Rules and Specificity
Document styles follow a **CSS specificity hierarchy**:
1. **Inline CSS** has the highest specificity and overrides both internal and external CSS.
2. **Internal CSS** takes precedence over external CSS but can be overridden by inline styles.
3. **External CSS** has the lowest specificity but provides a global, maintainable styling approach.

### Best Practices
1. **Use External CSS**: Keep styling separate from HTML, making the code cleaner and easier to maintain.
2. **Limit Internal CSS**: Useful for specific pages or testing, but not ideal for large projects.
3. **Avoid Inline CSS**: Difficult to maintain and does not support reusability.

>See full source code for this section [01-basic.html](https://github.com/sidneyshafer/css-sandbox/blob/master/01-basic.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Selectors

>CSS selectors are used to apply styles to specific elements based on their type, class, ID, or hierarchy.

### Element Selector
```
body {
    background-color: #333;
}
```
* Targets all `<body>` elements.
* Element selectors apply styles to all elements of a specific type.
* In this example, sets the `background-color` property to a dark gray (`#333`).


### Class Selector
```
.primary-heading {
    color: green;
}
...

<h2 class="primary-heading">Welcome</h2>
```
* Targets all elements with the class `primary-heading`.
* Class names start with a period (`.`).
* Classes are reusable and can be applied to multiple elements.

### ID Selector
```
#welcome {
   background-color: #f4f4f4;
}
...

<div id="welcome">
```
* Targets the element with the ID `welcome`.
* An ID starts with a hash symbol (`#`).
* IDs are unique and are used to style a single element. They should not be used on multiple elements in a document.

### Multiple Selectors
```
#welcome, #about {
    border: 1px solid #ccc;
    padding: 10px;
    margin-bottom: 5px;
}
```
* Targets the elements with the IDs `welcome` and `about`.
* Multiple selectors allow applying the same styles to several elements, separated by commas.

### Nested Selector
```
#welcome p {
    font-size: 20px;
}
...

<div id="welcome">
      <h2 class="primary-heading">Welcome</h2>
      <p>...</p>  <!-- Targets this element -->
</div>
```
* In this case, targets `<p>` elements that are children of the element with the ID `welcome`.
* Nested (or descendant) selectors target elements based on their parent-child relationship.
* These styles will set the font size of the paragraph inside `#welcome` to `20px`.

### Selector Best Practices
* **Use Classes (`.classname`) for Reusability**: Prefer classes for styles that might apply to multiple elements.
* **Use IDs (`#id`) Sparingly**: IDs should be unique to each element within each document and used only when necessary.
* **Leverage Specificity**: Combine selectors (e.g., `#welcome p`) for precise targeting without overusing inline styles.
* **Keep Styles Organized**: Group related styles together (e.g., `#welcome` and `#about`).

>See full source code for this section [02-selectors.html](https://github.com/sidneyshafer/css-sandbox/blob/master/02-selectors.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Fonts

### `font-family`
```
body {
    font-family: 'Roboto', sans-serif;
}
```
* The `font-family` property defines the typeface for text. 
* In this example, `'Roboto'` is the **primary font** used for the document (Roboto is a **[Google Font](#google-fonts)**).
* `sans-serif` is the generic **fallback font**. If the browser cannot load Roboto, it will use any available sans-serif font.

### Google Fonts

```
<link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
```
* Statement importing a font from the Google Fonts library using the `<link>` tag in the HTML document.
* This fetches the `'Roboto'` font from Google Fonts and makes it available for use in the stylesheet.

>See more about using **[Google Fonts](https://fonts.google.com/)**

### `font-size`
```
body {
   font-size: 18px;
}
```
* The `font-size` property controls the size of the text.
* In this example, font size is set to `18px` for the entire document, meaning all text inherits this size unless overridden by more specific rules.

### `line-height`
```
body {
   line-height: 1.6em;
}
```
* The `line-height` property controls the vertical spacing between lines of text.
* Line height improves readability by adding spacing between lines of text.
* In this example, the value `1.6em` means the line height is 1.6 times the font size (`18px × 1.6 = 28.8px`).

### `font-weight`
```
#welcome p span {
   font-weight: bold;
}
```
* The `font-weight` property controls the thickness of the font.
* The `bold` value increases the font's weight, making the text appear thicker.
* Font weight values are specified by keyword or numeric values.

**Keyword Font Weight Values**
| Keyword   | Description |
| --------- | ----------- |
| `normal`  | The default font weight, which is equal to **400** |
| `bold`    | The bold font weight, which is equal to **700** |
| `lighter` | Makes the font weight one level lighter than the parent element |
| `bolder`  | Makes the font weight one level heavier than the parent element |

**Numeric Font Weight Values**
| Keyword   | Description |
| --------- | ----------- |
| `100`     | Thin |
| `200`     | Extra light |
| `300`     | Light |
| `400`     | Normal |
| `500`     | Medium |
| `600`     | Semi bold |
| `700`     | Bold |
| `800`     | Extra bold |
| `900`     | Black |

### `font-style`
```
#about p span {
   font-style: italic;
}
```
* The `font-style` property defines whether text is normal, italicized, or oblique.
* The `italic` value applies an italic style to the font, slanting it to the right.

>See full source code for this section [03-fonts.html](https://github.com/sidneyshafer/css-sandbox/blob/master/03-fonts.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Colors

### The `color` Property
* The `color` property is used to set the text color of an element.
* The value of the `color` property can be specified using:
    * Named colors
    * RGB values
    * Hexadecimal values

### Color Definitions in the CSS

**Color Name**
```
h1 {
   color: red;
}
```
* The text color is set to `red`, a predefined color name.
* CSS supports a set of standard color names (e.g., red, blue, green, etc.). 
* While convenient, they are limited in number and often not specific enough for detailed designs.

**RGB Color**
```
h2 {
   color: rgb(255, 255, 120);
}
```
* The `rgb()` function allows specifying colors using the Red, Green, and Blue values (in that specific order).
* Each color value (Red, Green, and Blue) can range from 0 (none of that color) to 255 (full intensity of that color).
* RGB provides precise control over the color, and allows for blending and transparency when combined with `rgba()`.
* In the example above:
    * Red: Full intensity (255).
    * Green: Full intensity (255).
    * Blue: Medium intensity (120).

**Hexadecimal Color**
```
h3 {
   color: #088faf;
}
```
* Hexadecimal colors are defined using a `#` followed by six hexadecimal digits (base 16).
* The format is `#RRGGBB`, where:
    * `RR` represents the red component.
    * `GG` represents the green component.
    * `BB` represents the blue component.
* The values range from 00 to FF, which is the same as 0 to 255 in RGB. 
* Setting all three values to 00 results in black, and setting all three values to FF results in white.
* Some common hexadecimal colors include: `#333` (dark gray), `#ccc` (medium-light gray), `#ddd` (lighter gray), `#f4f4f4` (very light gray)

### Color Best Practices
* Use a consistent color format throughout a project for maintainability.
* Consider accessibility, such as sufficient contrast for readability.

>See full source code for this section [04-colors.html](https://github.com/sidneyshafer/css-sandbox/blob/master/04-colors.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>