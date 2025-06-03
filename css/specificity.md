# CSS Specificity
- If there are two or more CSS rules that point to the same element, the selector with the highest specificity will "win", and its style declaration will be applied to that HTML element.
- If two or more CSS rules have equal specificity then the last selector will win.

## Specificity hierarchy
1. !important
2. Inline
3. Id
4. Classes and Pseudo Classes
5. Attributes
6. Elements and Pseudo Elements
7. Universal Selector

> **Note:**
> - ✔ Inheritance does **not** contribute to specificity.
> - ✔ `:not()` pseudo-class does not increase specificity.
> - ✔ `!important` can be overridden by another `!important` with higher specificity.

