# CSS

CSS (Cascading Style Sheets) is a stylesheet language used to style web pages.

## 1️⃣Types of CSS

- **Inline CSS** (inside HTML elements)
- **Internal CSS** (inside `<style>` in `<head>`)
- **External CSS** (separate .css file)

## 2️⃣ Inheritance

Inheritance controls what happens when no value is specified for a property on an element.

CSS properties can be categorized in two types:

- **inherited properties:** When no value for an inherited property has been specified on an element, the element gets the computed value of that property on its parent element. Only the root element of the document gets the initial value given in the property's summary.
- **non-inherited properties:** When no value for a non-inherited property has been specified on an element, the element gets the initial value of that property (as specified in the property's summary).

## 3️⃣ Cascading

Cascading refers to the process by which the browser decides which rule wins when multiple rules apply to the same element.
The cascade follows a specific order of importance:

1. **Importance** (`!important` wins over everything)

1. **Specificity** (how specific the selector is)

1. **Source order** (last rule wins if specificity is equal)
