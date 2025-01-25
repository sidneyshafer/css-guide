# CSS Sandbox Part 1

>Snippets, examples, and code breakdowns for learning the basics of CSS..

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
* **[Backgrounds and Borders](#backgrounds-and-borders)**
    * [Background Properties](#background-properties)
    * [Using Background Shorthand Property](#using-background-shorthand-property)
    * [Border Properties](#border-properties)
    * [Individual Border Sides](#individual-border-sides)
    * [Common Border Styles](#common-border-styles)
    * [Using Border Shorthand Property](#using-border-shorthand-property)
* **[CSS Box Model](#css-box-model)**
    * [Box Model Overview](#box-model-overview)
    * [CSS Reset](#css-reset)
    * [Padding](#padding)
    * [Margin](#margin)
* **[Float and Align Properties](#float-and-align-properties)**
    * [Text Alignment](#text-alignment)
    * [Clearfix](#clearfix)
    * [Float Layout](#float-layout)
* **[Styling Links and Buttons](#styling-links-and-buttons)**
    * [Styling Links](#styling-links-a)
    * [Styling Buttons](#styling-buttons)
* **[CSS Menus](#css-menus)**
    * [Styling a Simple Navbar](#styling-a-simple-navbar)
    * [Styling a Simple Side Menu](#styling-a-simple-side-menu)
* **[Inline and Block Styling](#inline-and-block-styling)**
    * [CSS for Inline Elements](#css-for-inline-elements)
    * [CSS for Block Elements](#css-for-block-elements)
    * [CSS for Inline-Block Elements](#css-for-inline-block-elements)
* **[CSS Position Properties](#css-position-properties)**
    * [Static](#static-default)
    * [Relative](#relative)
    * [Absolute](#absolute)
    * [Fixed](#fixed)
    * [Sticky](#sticky)
    * [Positioning Properties](#positioning-properties)
    * [Summary of CSS Positioning](#summary-of-css-positioning)
* **[Styling a Form](#styling-a-form)**
* **[Aside - Other CSS Rules & Properties](#aside---other-css-rules--properties)**
    * [Display None](#display-none)
    * [Hidden Visibility](#hidden-visibility)
    * [!important Rule](#important-rule)
    * [Negative Values](#negative-values)
* **[Media Queries](#media-queries)**
    * [Smartphones](#smartphones-max-width-500px)
    * [Tablets](#tablets-501px-to-768px)
    * [Laptops and Desktops](#laptops-and-desktops---normal-screen-size-769px-to-1200px)
    * [Widescreen](#widescreen-min-width-1201px)
    * [Landscape](#landscape-max-height-500px)
    * [Using an External Stylesheet](#external-stylesheet-for-conditional-styling)
* **[Em and Rem Units](#em-and-rem-units)**
    * [Overview](#overview-of-em-and-rem)
    * [Code Breakdown](#em-and-rem-code-breakdown)
* **[Viewport Height and Viewport Width Units](#viewport-height-vh-and-viewport-width-vw)**
    * [Overview](#overview-of-vh-and-vw-units)
    * [Example](#example-using-vh-and-vw)
    * [Best Practices](#best-practices-using-vh-and-vw)
* **[CSS Flexbox Basics](#css-flexbox-basics)**
    * [The Flex Container](#display-flex---the-flex-container)
        * [flex-direction](#flex-direction)
        * [flex-wrap](#flex-wrap)
    * [The Flex Items](#flex---the-flex-items)
        * [flex-grow](#flex-grow)
        * [flex-shrink](#flex-shrink)
        * [flex-basis](#flex-basis)
* **[Flexbox Alignment](#flexbox-alignment)**
    * [Flexbox Alignment Overview](#flexbox-alignment-overview)
    * [Flexbox Alignment Properties](#flexbox-alignment-properties)
        * [Aligning Along the Cross Axis](#aligning-along-the-cross-axis)
        * [Aligning Along the Main Axis](#aligning-along-the-main-axis)
        * [Per-Item Cross-Axis Alignment](#per-item-cross-axis-alignment)

## CSS Basics

>CSS stands for **Cascading Style Sheets**

### External CSS
```html
<link rel="stylesheet" href="css/style.css">
```
* Links to an external CSS file. In this case, it is located at `css/style.css` (in a folder named `css`).
* External CSS keeps styles separate from HTML, improving maintainability and reusability across multiple webpages.
* Any CSS rules in `css/style.css` are applied to this document.

### Internal CSS
```html
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

>See full source code for this section [01-basic.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/01-basic.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Selectors

>CSS selectors are used to apply styles to specific elements based on their type, class, ID, or hierarchy.

### Element Selector
```css
body {
    background-color: #333;
}
```
* Targets all `<body>` elements.
* Element selectors apply styles to all elements of a specific type.
* In this example, sets the `background-color` property to a dark gray (`#333`).


### Class Selector
```css
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
```css
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
```css
#welcome, #about {
    border: 1px solid #ccc;
    padding: 10px;
    margin-bottom: 5px;
}
```
* Targets the elements with the IDs `welcome` and `about`.
* Multiple selectors allow applying the same styles to several elements, separated by commas.

### Nested Selector
```html
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

>See full source code for this section [02-selectors.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/02-selectors.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Fonts

### `font-family`
```css
body {
    font-family: 'Roboto', sans-serif;
}
```
* The `font-family` property defines the typeface for text. 
* In this example, `'Roboto'` is the **primary font** used for the document (Roboto is a **[Google Font](#google-fonts)**).
* `sans-serif` is the generic **fallback font**. If the browser cannot load Roboto, it will use any available sans-serif font.

### Google Fonts

```html
<link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
```
* Statement importing a font from the Google Fonts library using the `<link>` tag in the HTML document.
* This fetches the `'Roboto'` font from Google Fonts and makes it available for use in the stylesheet.

>See more about using **[Google Fonts](https://fonts.google.com/)**

### `font-size`
```css
body {
   font-size: 18px;
}
```
* The `font-size` property controls the size of the text.
* In this example, font size is set to `18px` for the entire document, meaning all text inherits this size unless overridden by more specific rules.

### `line-height`
```css
body {
   line-height: 1.6em;
}
```
* The `line-height` property controls the vertical spacing between lines of text.
* Line height improves readability by adding spacing between lines of text.
* In this example, the value `1.6em` means the line height is 1.6 times the font size (`18px × 1.6 = 28.8px`).

### `font-weight`
```css
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
```css
#about p span {
   font-style: italic;
}
```
* The `font-style` property defines whether text is normal, italicized, or oblique.
* The `italic` value applies an italic style to the font, slanting it to the right.

>See full source code for this section [03-fonts.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/03-fonts.html)

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
```css
h1 {
   color: red;
}
```
* The text color is set to `red`, a predefined color name.
* CSS supports a set of standard color names (e.g., red, blue, green, etc.). 
* While convenient, they are limited in number and often not specific enough for detailed designs.

**RGB Color**
```css
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
```css
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

>See full source code for this section [04-colors.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/04-colors.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Backgrounds and Borders

### Background Properties
| Property           | Description |
| ------------------ | ----------- |
| `background-color` | Specifies the background color to be used |
| `background-image` | Specifies one or more background images to be used |
| `background-position` | Specifies the position of the background images |
| `background-size` | Specifies the size of the background images |
| `background-repeat` | Specifies how to repeat the background images |
| `background-origin` | Specifies the positioning area of the background images |
| `background-clip` | Specifies the painting area of the background images |
| `background-attachment` | Specifies whether the background images are fixed or scrolls with the rest of the page |

```css
#box-1 {
   background-color: #ccc;
}
```
* Sets the background color to a light gray using the color code `#ccc`.

## Using Background Shorthand Property

**Example 1**
```css
#box-2 {
   background: #333;
}
```
* When using the shorthand property, the order of the property values are:
    1. `background-color`
    2. `background-image`
    3. `background-repeat`
    4. `background-attachment`
    5. `background-position`

* Does not matter if one of the property values is missing, as long as the other ones are in this order.

**Example 2**
```css
#box-3 {
   background: url('./img/stars.jpg') no-repeat center center/cover;
}
```
* Sets the background to an image located at `./img/stars.jpg`.
* `no-repeat`: prevents the image from repeating.
* `center center`: centers the image both horizontally and vertically.
* `cover`: ensures the image covers the entire area of the box while maintaining its aspect ratio.

**Example 3**
```css
#box-4 {
    background: url('./img/leaf.png') no-repeat center center;
    background-attachment: fixed;
}
```
* Sets the background to an image located at `./img/leaf.png`.
* `no-repeat`: prevents the image from repeating.
* `center center`: centers the image both horizontally and vertically.
* `background-attachment: fixed;`
    * Fixes the background image so that it does not scroll with the rest of the page. 
    * The image remains static while the content scrolls.

## Border Properties
| Property           | Description |
| ------------------ | ----------- |
| `border-style`     | Determines the type of border |
| `border-width`     | Sets the width of the border |
| `border-color`     | Specifies the border color |
| `border-radius`    | Creates rounded corners for elements |

## Individual Border Sides
* CSS allows you to style each side of a border individually, giving flexibility in design (top, right, bottom, and left):
    * `border-top-[type]`
    * `border-right-[type]`
    * `border-bottom-[type]`
    * `border-left-[type]`

* `[type]` is optional and can be any border property type, including: `style`, `width`, `color`, or `radius`.

**Example**
```css
#box-2 {
    border-top: blue solid 5px;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
}
```
* `border-top: blue solid 5px;`
    * Sets the top border to a color of `blue`, a border style of `solid`, and a border width of `5px`.
* `border-top-left-radius: 10px;`
    * Defines a border radius of `10px` at the top left corner.
* `border-top-right-radius: 10px;`
    * Defines a border radius of `10px` at the top right corner.

## Common Border Styles
The `border-style` property specifies the type of border. Below is a list of common border style types.

| Border Style | Description |
| ------------ | ----------- |
| `dotted`     | Defines a dotted border |
| `dashed`     | Defines a dashed border |
| `solid`      | Defines a solid border  |
| `double`     | Defines a double border |
| `groove`     | Defines a 3D grooved border. The effect depends on the `border-color` value |
| `ridge`      | Defines a 3D ridged border. The effect depends on the `border-color` value |
| `inset`      | Defines a 3D inset border. The effect depends on the `border-color` value |
| `outset`     | Defines a 3D outset border. The effect depends on the `border-color` value |
| `none`       | Defines no border |
| `hidden`     | Defines a hidden border |

>Read more about border styles and code examples [CSS Border Style](https://www.w3schools.com/css/css_border.asp)

## Using Border Shorthand Property
```css
#box-1 {
    border: 3px solid red;
}
```
* The `border` property is a shorthand property for the following individual border properties:
    * `border-width`
    * `border-style`
    * `border-color`
* In this example, border width is set to `3px`, border style is set to `solid`, and border color is set to `red`.
* Border shorthand can also be used in conjunction with more precise border sides:
    * `border-top`
    * `border-right`
    * `border-bottom`
    * `border-left`

    * Example: `border-top: blue solid 5px;`

>Read more about borders and border properties [CSS Borders](https://www.geeksforgeeks.org/css-borders/)

>See full source code for this section [05-backgrounds-borders.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/05-backgrounds-borders.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## CSS Box Model

## Box Model Overview
![CSS Box Model Image](/src/img/box-model.png)

The box model consists of four layers:
* **Content**: The actual text or element inside the box.
* **Padding**: Space between the content and the border.
* **Border**: Surrounds the padding; it adds a defined boundary to the element.
* **Margin**: Space outside the border to separate the element from others.

### CSS Reset
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```
* **Universal Selector (`*`)**: Applies style rules to all elements in a document.
* `margin: 0;` and `padding: 0;`: Removes default browser margins and padding.
* `box-sizing: border-box;`: Ensures the width and height of elements include the padding and border but exclude the margin.

### Padding
```css
.box {
    /* Padding on all sides */
    padding: 20px;

    /* Padding per side */
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 10px;
    padding-left: 20px;

    /* Padding shorthand = top, right, bottom, left */
    padding: 10px 20px 10px 20px;

    /* Padding shorthand = top/bottom left/right */
    padding: 10px 20px;
}
```
* **Padding is the space between the content and the element's border.**
* Specifying the padding for each side of an element:
    * `padding-top`
    * `padding-right`
    * `padding-bottom`
    * `padding-left`

**Padding Shorthand Property**
* The `padding` property is a shorthand property for the following patterns:
    * `padding-top`
    * `padding-right`
    * `padding-bottom`
    * `padding-left`

**Padding Property Values**
* `length` - specifies a padding in `px`, `pt`, `cm`, `em`, `rem`, etc.
* `%` - specifies a padding in % of the width of the containing element
* `inherit` - specifies that the padding should be inherited from the parent element

* Example with **four** values:
    * `padding: 10px 20px 10px 20px;`
    * Top padding are 10px
    * Right padding are 20px
    * Bottom padding are 10px
    * Left padding are 20px

* Example with **three** values:
    * `padding: 10px 20px 30px;`
    * Top padding are 10px
    * Right **and** left paddings are 20px
    * Bottom padding are 30px

* Example with **two** values:
    * `padding: 10px 20px;`
    * Top **and** bottom paddings are 10px
    * Right **and** left paddings are 20px

* Example with **one** value:
    * `padding: 20px;`
    * Top, bottom, right, and left paddings are all 20px

### Margin
```css
.box {
    /* Margin on all sides */
    margin: 20px;
    
    /* Margin per side */
    margin-top: 10px;
    margin-right: 20px;
    margin-bottom: 10px;
    margin-left: 20px;

    /* Margin shorthand = top, right, bottom, left */
    margin: 10px 20px 10px 20px;

    /* Margin shorthand = top/bottom left/right */
    margin: 10px 20px;
}
```
* **Margin is the space outside the border, separating the element from adjacent elements.**
* Margin properties function similar to padding.
* Specifying the margin for each side of an element:
    * `margin-top`
    * `margin-right`
    * `margin-bottom`
    * `margin-left`

**Margin Property Values**
* `auto` - the browser calculates the margin
* `length` - specifies a margin in `px`, `pt`, `cm`, `em`, `rem`, etc.
* `%` - specifies a margin in % of the width of the containing element
* `inherit` - specifies that the margin should be inherited from the parent element

**Margin Shorthand Property**
* The `margin` property is a shorthand property for the following patterns:
    * `margin-top`
    * `margin-right`
    * `margin-bottom`
    * `margin-left`

* Example with **four** values:
    * `margin: 10px 20px 10px 20px;`
    * Top margin are 10px
    * Right margin are 20px
    * Bottom margin are 10px
    * Left margin are 20px

* Example with **three** values:
    * `margin: 10px 20px 30px;`
    * Top margin are 10px
    * Right **and** left margins are 20px
    * Bottom margin are 30px

* Example with **two** values:
    * `margin: 10px 20px;`
    * Top **and** bottom margins are 10px
    * Right **and** left margins are 20px

* Example with **one** value:
    * `margin: 20px;`
    * Top, bottom, right, and left margins are all 20px

>See full source code for this section [06-box-model.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/06-box-model.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Float and Align Properties

### Text Alignment
```css
.box p {
    text-align: left;
    text-align: center;
    text-align: right;
    text-align: justify;
}
```
The `text-align` property aligns text within an element.

**Text Align Values**
| Value    | Description |
| -------- | ----------- |
| `left`   | Aligns text to the left (**default**) |
| `center` | Centers text horizontally |
| `right`  | Aligns text to the right |
| `justify`| Distributes text evenly across the width of the element, making the lines appear neat and straight |

### Clearfix
```html
.clr {
   clear: both;
}

...

<div class="container">
      <div id="box-1" class="box">
         ...
      </div>
      <div id="box-2" class="box">
        ...
      </div>
      <div id="box-3" class="box">
        ...
      </div>
      <div class="clr"></div>
      <div id="box-4" class="box">
        ...
      </div>
</div>
```
* Ensures that elements following floated elements start below them, not next to them.
* In this example, it is used to clear the float after `#box-2` and `#box-3`, allowing `#box-4` to appear on a new line.

### Float Layout
```css
#box-2 {
   float: left;
   width: 68%;
}
```
* `float: left;`: Positions the `#box-2` element to the left within the parent element (which in this case is `.container`).
* `width: 68%;`: Specifies a width for `#box-2` to occupy 68% of the container's width.

```css
#box-3 {
   float: right;
   width: 30%;
}
```
* `float: right;`: Positions the `#box-3` element to the right within the parent element (which in this case is `.container`).
* `width: 30%;`: Specifies a width for `#box-3` to occupy 30% of the container's width.

>See full source code for this section [07-float-align.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/07-float-align.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Styling Links and Buttons

### Styling Links (`<a>`)
```css
a {
    color: #333;
    text-decoration: none;
}
```
* `color: #333;`: Sets the text color of links to dark gray.
* `text-decoration: none;`: Removes the default underline styling of links.

**Hover Effect**
```css
a:hover {
   color: coral;
   text-decoration: underline;
}
```
* `a:hover`: Selector that targets the link when a user hovers over it.
* `color: coral;`: Changes the link color to a coral shade on hover.
* `text-decoration: underline;`: Changes the underline style to 'underline' on hover.

**Active State**
```css
a:active {
   color: red;
}
```
* `a:active`: Selector that targets the link when it is actively being clicked.
* `color: red;`: Changes the link color to red during the click action.

**Visited State**
```css
a:visited {
    color: red;
}
```
* `a:visited`: Selector that targets links a user has previously visited.
* `color: red;`: Changes the link color to red once a user has visited the link.

### Styling Buttons

**Example - Using CSS Classes**
```html
<button class="btn">My Button</button>
```
```css
.btn {
    background: #4c6ca0;
    color: #fff;
    border: none;
    font-size: 16px;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
}
```
* `background: #4c6ca0;`: Sets a dark blue background for the button.
* `color: #fff;`: Sets the text color to white.
* `border: none;`: Removes any default borders.
* `font-size: 16px;`: Sets the font size to 16 pixels.
* `padding: 10px 20px;`: Adds internal spacing around the text.
* `border-radius: 5px;`: Rounds the button corners for a softer appearance.
* `cursor: pointer;`: Changes the cursor to a pointer when hovering over the button

**Hover Effect for Buttons**
```css
.btn:hover {
   color: #f4f4f4;
   background: #446190;
}
```
* `btn:hover`: Targets buttons when the user hovers over them.
* `color: #f4f4f4;`: Changes the text color to a lighter gray.
* `background: #446190;`: Darkens the background slightly for a hover effect.

>See full source code for this section [08-links-buttons.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/08-links-buttons.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## CSS Menus

### Styling a Simple Navbar

**HTML Code**
```html
<ul class="navbar">
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
</ul>
```

**CSS Styles**

>**NavBar Structure**
```css
.navbar {
    list-style: none;
    margin: 0;
    padding: 0;
    background: #4c6ca0;
    border-radius: 5px;
    overflow: auto;
}
```
* `list-style: none;`: Removes default list markers (bullets).
* `margin: 0;` and `padding: 0;`: Removes default spacing around the `<ul>` element.
* `background: #4c6ca0;`: Sets a dark blue background.
* `border-radius: 5px;`: Rounds the corners of the navbar.
* `overflow: auto;`: Ensures the navbar clears its floated child elements.

>**Navbar List Items**
```css
.navbar li {
   float: left;
}
```
* `float: left;`: Aligns each list item (`<li>`) horizontally.

>**Navbar Links**
```css
.navbar li a {
   display: block;
   color: #fff;
   text-decoration: none;
   padding: 15px 20px;
}
```
* `display: block;`: Links will fill the entire area of the list item.
* `color: #fff;`: Sets the text color to white.
* `text-decoration: none;`: Removes the default underline from links.
* `padding: 15px 20px;`: Adds spacing around the text content.

>**Hover Effect**
```css
.navbar li a:hover {
   background-color: #446190;
   color: #f4f4f4;
}
```
* `.navbar li a:hover`: Targets navbar links when a user hovers over them.
* `background-color: #446190;`: Changes the background color of the link on hover.
* `color: #f4f4f4;`: Changes the text color on hover.

### Styling a Simple Side Menu

**HTML Code**
```html
<ul class="side-menu">
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
</ul>
```

**CSS Styles**

>**Side Menu Structure**
```css
.side-menu {
    list-style: none;
    border: 1px #ddd solid;
    border-radius: 10px;
    width: 300px;
    padding: 20px;
}
```
* `list-style: none;`: Removes default list markers (bullets).
* `border: 1px #ddd solid;`: Adds a light gray solid border around the side menu.
* `border-radius: 10px;`: Rounds the corners of the side menu.
* `width: 300px;`: Sets the fixed width of the menu to 300 pixels.
* `padding: 20px;`: Adds internal spacing around the content of the side menu.

>**Side Menu List Items**
```css
.side-menu li {
    font-size: 18px;
    line-height: 2.4em;
    border-bottom: dotted 1px #ddd;
}
```
* `font-size: 18px;`: Sets the font size to `18px` for all `<li>` elements within the `.side-menu`.
* `line-height: 2.4em;`: Adds vertical spacing between the list items.
* `border-bottom: dotted 1px #ddd`;: Adds a dotted gray line below each list item.

>**Last List Item**
```css
.side-menu li:last-child {
   border: none;
}
```
* `:last-child`: Targets the last item in a list.
* `border: none;`: Removes the bottom border for the last list item.

>**Side Menu Links**
```css
.side-menu li a {
    color: #333;
    text-decoration: none;
}
```
* `color: #333;`: Sets the text color.
* `text-decoration: none;`: Removes the default underline from links.

>**Hover Effect**
```css
.side-menu li a:hover {
   color: coral;
}
```
* `color: coral;`: Changes the text color to coral on hover.

>See full source code for this section [09-menus.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/09-menus.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Inline and Block Styling

### CSS for Inline Elements

```css
li {
    display: inline;  
}
```
* The `<li>` elements (list items) are styled to have a `display: inline;`.
* **Behavior of Inline Elements**:
    * Inline elements flow with the surrounding text and do not start on a new line.
    * Only the element content is affected by their dimensions. 
    * Width and height cannot be set directly.
* In this case, the `<li>` elements will appear next to each other horizontally within the `<ul>` container.

### CSS for Block Elements
```css
img {
    display: block;
    margin: auto;
}
```
* The `<img>` element is styled as a block-level element.
* `display: block;`: Forces the image to act as a block element.
* `margin: auto;`: Centers the image horizontally within its container.
* **Behavior of Block Elements**:
    * Block elements start on a new line and stretch to occupy the full width of their container.
    * You can control their width, height, margins, and padding.

### CSS for Inline-Block Elements
```css
.box {
    display: inline-block;
}
```
* `display: inline-block;`: Makes the boxes align horizontally (like inline elements) but still allows block-level box styling.
* **Behavior of Inline-Block Elements**:
    * Inline-block elements behave like inline elements (they appear next to each other without starting on a new line).
    * Unlike true inline elements, they allow for setting dimensions like width, height, padding, and margins.

**Differences**
| Property         | Inline                | Block                | Inline-Block          |
| ---------------- | --------------------- | -------------------- | --------------------- |
| Default Behavior | Aligns with text flow | Starts on a new line | Aligns with text flow |
| Width/Height     | Cannot be set directly| Can be set           | Can be set            |   

>See full source code for this section [10-inline-block.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/10-inline-block.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## CSS Position Properties

* The `position` CSS property sets how an element is positioned in a document. The `top`, `right`, `bottom`, and `left` properties determine the final location of positioned elements.

### Static (Default)
* All elements are positioned statically by default unless another `position` value is explicitly set.
* Elements with `position: static;` follow the normal document flow and are not affected by positioning properties like `top`, `left`, `right`, or `bottom`.

### Relative
```css
#box-1 {
    position: relative;
    top: 50px;
    left: 50px;
    z-index: 1;
    background: red;
}
```
* `position: relative;`: Positions the element relative to its normal (static) position in the document flow.
* `top: 50px;`: Moves the element down 50 pixels from the top of the document.
* `left: 50px;`: Moves the element right 50 pixels from the left side of the document.
* The space the element originally occupied in the flow remains intact.
* `z-index: 1;`: Ensures the element appears above elements with a lower or default `z-index`.

### Absolute
```css
#box-2 {
    position: absolute;
    top: 100px;
    left: 100px;
    background: yellow;
}

#box-3 {
    position: absolute;
    bottom: 100px;
    right: 100px;
    background: green;
}
```
* `position: absolute;`: Positions an element relative to the nearest positioned ancestor (an ancestor with position `relative`, `absolute`, or `fixed`). If no such ancestor exists, it positions relative to the `<html>` element.
* In this example, `#box-2` and `#box-3` exist within a parent element (`.container`) which is positioned `relative` on the page, so their placement is calculated based on the container.

### Fixed
```css
#box-4 {
    position: fixed;
    background: blue;
}
```
* `position: fixed;`: Removes the element from the document flow and positions it relative to the viewport.
* The element remains fixed in place even when scrolling.
* In this example, since no `top`, `left`, `right`, or `bottom` values are provided, the box stays at the top-left corner of the viewport.

### Sticky
```css
#box-5 {
    position: sticky;
    top: 0;
    background: orange;
    z-index: -1;
}
```
* `position: sticky;`: Toggles between `relative` and `fixed` based on the scroll position.
* Initially, it behaves as `relative`. As the user scrolls, it "sticks" to the specified top value (0px in this case) when it reaches that point in the viewport.
* **The sticky element requires a scrollable container to function.**
* `z-index: -1;`: Places it behind other elements.

### Positioning Properties
**`top`**
* Specifies the distance between the top edge of the element and the top edge of its containing block.
* Positive values push the element down, and negative values pull it up.

**`left`**
* Specifies the distance between the left edge of the element and the left edge of its containing block.
* Positive values push the element right, and negative values pull it left.

**`right`**
* Specifies the distance between the right edge of the element and the right edge of its containing block.
* Positive values pull the element left, and negative values push it right.

**`bottom`**
* Specifies the distance between the bottom edge of the element and the bottom edge of its containing block.
* Positive values pull the element up, and negative values push it down.

### Summary of CSS Positioning
| Property   | Relative To                 | Remains in Document Flow? | Scroll Behavior      |
| ---------- | --------------------------- | ------------------------- | -------------------- |
| Static     | Default positioning         | Yes                       | Moves with scrolling |
| Relative   | Itself                      | Yes                       | Moves with scrolling |
| Absolute   | Nearest positioned ancestor | No                        | Moves with scrolling |
| Fixed      | Viewport                    | No                        | Stays fixed in viewport |
| Sticky     | Nearest scrollable ancestor | Partially                 | Sticks at defined position |

>**See more examples of CSS positioning in [20-position-ex.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/20-position-ex.html)**

>See full source code for this section [11-position.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/11-position.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Styling a Form
>**Full Code example in [12-form-styling.html](https://github.com/sidneyshafer/css-sandbox/blob/master/source-code/12-form-styling.html)**

**Code Breakdown**
>**Outer Container (`#container`)**
```css
#container {
   max-width: 400px;
   margin: 30px auto;
   padding: 20px;
}
```
* Restricts the form's width to a maximum of 400px.
* Centers the form using `margin: 30px auto;` (horizontal centering via auto and `30px` top margin).
* Adds padding around the content for spacing.

>**Form Wrapper (`.form-wrap`)**
```css
.form-wrap {
   background: #fff;
   padding: 15px 25px;
}
```
* Adds a white background and provides inner spacing with padding.

>**Headings and Paragraphs**
```css
.form-wrap h1, .form-wrap p {
    text-align: center;
}

.form-wrap h1 {
    margin-top: 15px;
    margin-bottom: 10px;
}
```
* Aligns the headings and description text in the center.
* Adds vertical space (margin) to `<h1>` elements for better spacing.

>**Form Groups**
```css
.form-wrap .form-group {
    margin-top: 15px;
    color: #333;
}

.form-wrap .form-group label {
    display: block;
    color: #666;
}
```
* Each input group is separated with `margin-top: 15px`.
* Labels are displayed as block-level elements, ensuring they appear above the input fields.

>**Input Fields**
```css
.form-wrap .form-group input {
    width: 100%;
    padding: 10px;
    border: #ddd 1px solid;
    border-radius: 5px;
}
```
* Input fields span the full width of their container (`width: 100%`).

>**Submit Button**
```css
.form-wrap button {
    display: block;
    color: #fff;
    font-size: 16px;
    width: 100%;
    background: #49c1a2;
    border: none;
    border-radius: 5px;
    padding: 10px;
    margin-top: 20px;
    cursor: pointer;
}

.form-wrap button:hover {
    background: #37a08e;
}
```
* The button is styled as a block-level element to occupy the full width of the form.
* Background color is a vibrant teal (`#49c1a2`), changing to a darker shade on `hover` (`#37a08e`).

>**Bottom Text**
```css
.form-wrap .bottom-text {
   font-size: 13px;
   margin-top: 20px;
}
```
* Defines font size and margin top styles to a text below the form.

>**Footer**
```css
footer {
   color: #fff;
   text-align: center;
   margin-top: 10px;
}
footer a {
   color: #49c1a2;
}
```
* Centers the footer text and uses white as the main color.
* Links in the footer are styled with the same teal color as the button.

>See full source code for this section [12-form-styling.html](https://github.com/sidneyshafer/css-sandbox/blob/master/source-code/12-form-styling.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Aside - Other CSS Rules & Properties

### Display None
```css
h1 {
   display: none; 
}
```
* `display: none;`: Completely removes the element from the document flow. The element won't be visible or occupy any space on the page.

### Hidden Visibility
```css
h1 {
    visibility: hidden;
}
```
* `visibility: hidden;`: Hides the content but preserves the space it occupies. This is useful for creating placeholders or temporarily hiding content without affecting the layout.

### `!important` Rule
```css
h1 {
   color: blue !important;
}
```
* The `!important` rule overrides any other conflicting styles, ensuring this rule always takes precedence.

### Negative Values
```css
.hello {
    /* Cannot have negative numbers with padding */
    margin-top: -30px;
    margin-left: -30px;
}
```
* Applies negative margins to the top and left of the element.
* Negative margins pull the element closer to neighboring elements or move it outside its container.
* **Padding cannot take negative values**, unlike margins. Padding is the space between the content and the element's border, and it always grows outward.

>See full source code for this section [13-aside.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/13-aside.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Media Queries

Media queries allow conditional application of CSS rules based on device properties, such as screen width, height, and orientation.

### Smartphones (max-width: 500px)
```css
 @media only screen and (max-width: 500px) {
    body {
        background: red;
    }

    #smartphone h1 {
        display: block;
    }
}
```
* For screens **500px wide or smaller**, typically smartphones:
    * The body background changes to red.
    * The `<h1> `inside the `#smartphone` div becomes visible (`display: block;`).

### Tablets (501px to 768px)
```css
@media(min-width: 501px) and (max-width: 768px) {
    body {
        background: blue;
    } 

    #tablet h1 {
        display: block;
    }
}
```
* For screens between **501px and 768px**, typically tablets:
    * The `body` background changes to blue.
    * The `<h1>` inside the `#tablet` div becomes visible.

### Laptops and Desktops - "Normal" Screen Size (769px to 1200px)
```css
@media(min-width: 769px) and (max-width: 1200px) {
   body {
      background: green;
   }

   #normal h1 {
      display: block;
   }
}
```
* For screens between **769px and 1200px**, such as laptops or desktops:
    * The `body` background changes to green.
    * The `<h1>` inside the `#normal` div becomes visible.

###  Widescreen (min-width: 1201px)
```css
@media(min-width: 1201px) {
   body {
      background: black;
   }

   #widescreen h1 {
      display: block;
   }
}
```
* For screens **wider than 1200px**, typically widescreen monitors:
    * The `body` background changes to black.
    * The `<h1>` inside the `#widescreen` div becomes visible.

### Landscape (max-height: 500px)
```css
@media(max-height: 500px) {
   body {
      background: orange;
   }

   #landscape h1 {
      display: block;
   }
}
```
* For screens with a **maximum height of 500px**, typically landscape orientations on small devices:
    * The `body` background changes to orange.
    * The `<h1>` inside the `#landscape` div becomes visible.

### External Stylesheet for Conditional Styling
```html
<link rel="stylesheet" media="screen and (min-width: 501px) and (max-width: 768px)" href="css/mobile.css">
```
* An external stylesheet (`mobile.css`) is conditionally applied for screens **between 501px and 768px** (Tablet Screens). 
* This can be useful for separating specific styles into a different file.

>See full source code for this section [14-media-queries.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/14-media-queries.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Em and Rem Units

### Overview of `em` and `rem`

**`em`**:
* Relative to the font size of the parent element.
* If an element’s parent has a font size of `16px`, `1em` equals `16px`. If the parent changes, em adjusts accordingly.
* Commonly used for padding, margin, and font sizes.

**`rem`**:
* Relative to the font size of the root element (`html` element).
* `rem` values remain consistent regardless of the nesting structure.
* Easier to maintain and provides more predictable behavior.

### `em` and `rem` Code Breakdown

**Setting a Root Font Size**
```css
html {
   font-size: 10px;
}
```
* Sets the base font size of the entire document to `10px`. This means:
    * `1rem = 10px`

**Box 1**
```css
html {
   font-size: 10px;
}
```
* Sets the font size for `#box-1` to `20px`. This affects all child elements unless they override it.

```css
#box-1 p {
   font-size: 1.5em;
   padding: 1em;
}
```
* `font-size: 1.5em`: 1.5 times the parent font size (i.e., `20px × 1.5 = 30px`). 30px is set as the font size value for all paragraph child elements of `#box-1`.
* `padding: 1em`: Padding is equal to the computed font size of the `<p>` element, which is 30px.

```css
#box-1 ul {
   font-size: 1.2em;
}
```
* `font-size`: 1.2em: 1.2 times the parent font size (i.e., `20px × 1.2 = 24px`).

**Box 2**
```css
#box-2 h3 {
   font-size: 2.3rem;
}
```
* `font-size: 2.3rem`: 2.3 times the root font size (which was set to `10px`).
* `10px × 2.3 = 23px`.

```css
#box-2 p {
   font-size: 1.6rem;
   line-height: 1.7rem;
}
```
* `font-size: 1.6rem`: 1.6 times the root font size (i.e., `10px × 1.6 = 16px`).
* `line-height: 1.7rem`: Line height is `10px × 1.7 = 17px`.

>See full source code for this section [15-em-rem.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/15-em-rem.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Viewport Height (`vh`) and Viewport Width (`vw`)

### Overview of `vh` and `vw` Units

* Viewport height (`vh`) and viewport width (`vw`) are **relative length units** in CSS that are based on the **size of the viewport**. 
* Viewport is the visible area of a web page in the browser window. 
* These units are responsive, making them ideal for dynamic layouts and modern web design.

**Definition:**
* `1vh`: Equals 1% of the viewport's height.
* `1vw`: Equals 1% of the viewport's width.

**Full-Page Dimensions:**
* `100vh`: The height of the viewport.
* `100vw`: The width of the viewport.

### Example using `vh` and `vw`
```css
header {
    height: 100vh;
    width: 100vw;
    background: #333 url('https://source.unsplash.com/daily') no-repeat center center/cover;
}
```
* Ensures the header fills the entire viewport, regardless of screen size.

## Best Practices Using `vh` and `vw`
* Use `vh` and `vw` sparingly in combination with other units like `em`, `rem`, or percentages for better control.
* Test across devices to ensure compatibility, especially on mobile browsers.
* Combine media queries with `vh` and `vw` for fully responsive designs.

>See full source code for this section [16-vh-vw.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/16-vh-vw.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## CSS Flexbox Basics

### `display: flex;` - The Flex Container
```css
.flex-container {
    display: flex;
    /* flex-direction: row; */
    /* flex-direction: row-reverse; */
    /* flex-direction: column; */
    /* flex-direction: column-reverse; */
    /* flex-wrap: wrap; */
}
```
* Turns the container into a flex container.
* All child elements become flex items, which can be laid out along the main axis or the cross axis.

#### `flex-direction`
* Specifies the direction of the main axis (how items are arranged).
* **Possible values include**:
    * `row` (default): Items are placed in a row (horizontally).
    * `row-reverse`: Items are placed in a row but in reverse order.
    * `column`: Items are stacked vertically.
    * `column-reverse`: Items are stacked vertically in reverse order.

#### `flex-wrap`
* Controls whether items wrap to the next line if they overflow the container.
* **Possible values include**:
    * `nowrap` (default): Items stay on a single line.
    * `wrap`: Items wrap onto new lines if needed.
    * `wrap-reverse`: Items wrap onto new lines in reverse order.

### `flex` - The Flex Items
```css
.item {
   flex: 1 0 200px;
}
```
* The `flex` property is shorthand for: `flex-grow flex-shrink flex-basis;`.

#### `flex-grow`
* Determines how much a flex item can grow relative to the others when there is extra space in the container.
* In this example, all items can grow equally because they have the same `flex-grow` value.

#### `flex-shrink`
* Determines how much a flex item can shrink relative to the others when there is not enough space.
* Here, `0` means the item will not shrink below its `flex-basis`.

#### `flex-basis`
* Specifies the initial size of the item before growing or shrinking.
* Here, each item starts with a base width of `200px`.

>See full source code for this section [17-flex-basics.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/17-flex-basics.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

## Flexbox Alignment

### Flexbox Alignment Overview

![Diagram of CSS Flexbox Alignment](/src/img/flex-alignment.png)

In CSS Flexbox, alignment is controlled along two axes:
* **Main Axis**: The direction in which items are placed (defined by `flex-direction`).
* **Cross Axis**: Perpendicular to the main axis.

>**Full Code example in [18-flex-align.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/18-flex-align.html).**

**In this example, the `.flex-container` is a flex container, and the `.item` elements inside it are flex items.**

### Flexbox Alignment Properties

#### Aligning Along the Cross Axis
```css
.flex-container {
    display: flex;
    flex-direction: row;
    align-items: center;
    height: 50vh;
}
```
* `align-items`: Aligns all flex items along the **cross axis**.
* **Possible values include:**
    * `flex-start`: Items align at the start of the cross axis.
    * `flex-end`: Items align at the end of the cross axis.
    * `center`: Items are centered along the cross axis.
    * `stretch` (default): Items stretch to fill the cross axis if they lack a height.
    * `baseline`: Items align based on their text's baseline.
* `align-items: center;` centers all items vertically within the container's height (`50vh`).

#### Aligning Along the Main Axis
```css
justify-content: center;
```
* `justify-content`: Aligns all flex items along the **main axis**.
* **Possible values include:**
    * `flex-start` (default): Items align at the start of the main axis.
    * `flex-end`: Items align at the end of the main axis.
    * `center`: Items are centered along the main axis.
    * `space-around`: Items are spaced evenly with gaps between items and edges.
    * `space-between`: Items are spaced evenly, with no space at the edges.
    * `space-evenly`: Items are evenly distributed with equal space between and around them.
* `justify-content: center;` centers all items horizontally.

#### Per-Item Cross-Axis Alignment
```css
.item-1 {
    align-self: flex-start;
}
.item-3 {
    align-self: flex-end;
}
```
* `align-self`:  Overrides `align-items` for a specific flex item, aligning it differently along the **cross axis**.
* **Possible values include: (sames as `align-items`)**
    * `flex-start`: Items align at the start of the cross axis.
    * `flex-end`: Items align at the end of the cross axis.
    * `center`: Items are centered along the cross axis.
    * `stretch` (default): Items stretch to fill the cross axis if they lack a height.
    * `baseline`: Items align based on their text's baseline.
* `.item-1` has `align-self: flex-start;`, so it aligns at the top of the container, ignoring `align-items: center`.
* `.item-3` has `align-self: flex-end;`, so it aligns at the bottom of the container.

>**See another example for implementing CSS Flexbox in [19-flexbox-example.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/19-flexbox-example.html)**

>See full source code for this section [18-flex-align.html](https://github.com/sidneyshafer/css-sandbox/blob/master/src/18-flex-align.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>