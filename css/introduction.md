# CSS

CSS (Cascading Style Sheets) is a stylesheet language used to style web pages.

## 1️⃣Types of CSS

- **Inline CSS** (inside HTML elements)
- **Internal CSS** (inside `<style>` in `<head>`)
- **External CSS** (separate .css file)

## 2️⃣ Inheritance

Inheritance controls what happens when no value is specified for a property on an element.

CSS properties can be categorized in two types:

- **inherited properties:** When no value for an inherited property has been specified on an element, the element gets the computed value of that property on its parent element. Only the root element of the document gets the initial value of that property.
- **non-inherited properties:** When no value for a non-inherited property has been specified on an element, the element gets the initial value of that property.

## 3️⃣ Cascading

Cascading refers to the process by which the browser decides which rule wins when multiple rules apply to the same element.
The cascade follows a specific order of importance:

1. **Importance** (`!important` wins over everything)

1. **Specificity** (how specific the selector is)

1. **Source order** (last rule wins if specificity is equal)

## 4️⃣ CSS Specificity

Specificity is an algorithm that assigns a weight to each CSS selector, determining which rule is more "specific" and thus takes precedence over less specific rules.

### Specificity hierarchy

1. Inline
1. Id
1. Classes and Pseudo Classes
1. Attributes
1. Elements and Pseudo Elements
1. Universal Selector

> **Note:**
>
> - ✔ Inheritance does **not** contribute to specificity.
> - ✔ `:not()` pseudo-class does not increase specificity.
> - ✔ `!important` can be overridden by another `!important` with higher specificity.
