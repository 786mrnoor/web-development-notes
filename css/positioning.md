# CSS position Property
It is used to place elements in the document. It has five main values:

- `static` (default)
- `relative`
- `absolute`
- `fixed`
- `sticky`

## 1️⃣ `static` (Default)
- The element follows the normal document flow.
- Can not use `top`, `left`, `right`, or `bottom`.

## 2️⃣ `relative`
- The element stays in the **normal document flow** and **moves relative to itself without affecting surrounding elements**.
- Can use `top`, `left`, `right`, or `bottom`.
- Space remains reserved for the element.
```css
.box {
  position: relative;
  top: 20px; /* Moves 20px down */
  left: 30px; /* Moves 30px right */
}
```

## 3️⃣ `absolute`
- **Removed from normal document flow** (other elements ignore it).
- **Moves relative to the nearest `relative`, `absolute`, `fixed`, or `sticky` parent.**
- If no such parent exists, it moves relative to `<html>` (the whole page).

```css
.container {
  position: relative; /* Important for absolute positioning */
}
.box {
  position: absolute;
  top: 50px; /* Moves 50px down from .container */
  left: 100px; /* Moves 100px right from .container */
}
```

## 4️⃣ `fixed`

- The element **stays fixed** on the screen, even when scrolling.
- Moves relative to the **viewport (browser window)**.

```css
.fixed-box {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: black;
  color: white;
}
```

## 5️⃣ `sticky`
- Acts `static` until scrolled, then behaves like `fixed`.
- Needs `top`, `left`, `right`, or `bottom` to work.
```css
.sticky-box {
  position: sticky;
  top: 10px; /* Sticks after scrolling 10px */
  background: yellow;
}
```