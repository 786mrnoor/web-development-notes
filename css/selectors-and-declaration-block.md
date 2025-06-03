# CSS Syntax (Selectors & Declaration Block)
A CSS rule consists of a **selector** and a **declaration block**.

## 1️⃣CSS Selectors

CSS selectors are used to target or select the **HTML elements**  to style them. They can be categorized into several types:

### 👉**Simple Selectors**
select elements based on **name**, **id**, **class**, **universal** and **group selector**.

### 👉**Attribute selectors**
select elements based on **attributes** and **their values**:

- `a[attribute]`
- `a[attribute="value"]`
- `[attribute~="value"]` - value can be exactly the specified word, or the specified value followed by a space.
- `[class|="top"]` - value can be exactly the specified value, or the specified value followed by a hyphen (-).
- `[attribute^="value"]` - value starts with the specified value.
- `[attribute$="value"]` - value ends with a specified value.
- `[attribute*="value"]` - value contains a specified value.

### 👉**Combinator selectors**
select elements based on their relationship with other elements:
- **Descendant combinator (space)**
- **Child combinator (`>`)**
- **Next(Adjacent) sibling combinator (`+`)**
- **Subsequent-sibling(General) combinator (`~`)**

### 👉**Pseudo-class selectors** 
select elements based on their state or position:

- `:link` - unvisited link
- `:visited` 
- `:hover`
- `:active`
- `:first-child` - Selects the element that is the first child of its parent (among a group of sibling elements)
- `:last-child`
- `:first-of-type` - Selects the first element of its type among a group of sibling elements
- `:nth-child(index | odd | even | an+b)`
- `:nth-of-type(n)`
- `:nth-last-child()` - matches elements based on their position among a group of siblings, counting from the end.
- `:not(selector)`
- `:has(selector)`
- `:only-child` - Selects any element that is the only child of its parent
- `:placeholder-shown`
- `:user-invalid` - 	Selects any form element with an invalid value (after the user have interacted with it)
- `:user-valid` - 	Selects any form element with a valid value (after the user have interacted with it)
- `:valid` - Selects all input elements with a valid value
- `:where(selector-list)`
- `:is(selector-list)`

### 👉**Pseudo-elements selectors** 
select and style parts of an element

- `::before`
- `::after`
- `::first-line`
- `::first-letter`
- `::marker`
- `::selection`

> **Note:** The `:where()` pseudo-class is equal to the `:is()` pseudo-class, except in specificity: 
> - `:where()` always has 0 specificity
> - `:is()` takes on the specificity of the most specific selector in its argument.

## 2️⃣Declaration Block (properties & values)

- The declaration blocks are surrounded by curly braces.
- It contains one or more declarations separated by semicolons.
- Each declaration includes a CSS property name and a value.
