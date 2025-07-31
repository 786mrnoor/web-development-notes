# CSS Specificity

Specificity is an algorithm that assigns a weight to each CSS selector, determining which rule is more "specific" and thus takes precedence over less specific rules.

## Specificity hierarchy

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
