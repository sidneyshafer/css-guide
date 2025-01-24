# CSS Sandbox Part 1

>CSS snippets, examples, and code breakdown for learning the basics of CSS.

## Table of Contents

* [CSS Basics](#css-basics)
    * [External CSS](#external-css)
    * [Internal CSS](#internal-css)
    * [Inline CSS](#inline-css---not-recommend-as-best-practice)
    * [CSS Rules and Specificity](#css-rules-and-specificity)
    * [Best Practices](#best-practices)
* Selectors
* Fonts

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