# 🎯 CSS Transitions

**CSS transitions** allow us to smoothly animate from one style to another when their CSS properties change.

---

## ✅ **1. Basic Syntax**

```css
transition: property duration timing-function delay;
```

* `property`: The CSS property to animate (e.g. `width`, `color`)
* `duration`: Time the animation takes (`s` or `ms`)
* `timing-function`: Controls the speed of the transition (e.g. `ease`, `linear`)
* `delay`: Specifies a delay before the transition starts. 

---

## ✅ **2. Example: Hover to Change Width**

```css
.box {
  width: 100px;
  transition: width 0.5s ease-in-out;
}

.box:hover {
  width: 200px;
}
```

✅ On hover, the box **smoothly resizes** from 100px to 200px.

---

## ✅ **3. `transition-timing-function`**

Controls **animation speed curve**:

| Value                       | Behavior                       |
| --------------------------- | ------------------------------ |
| `ease`                      | Slow start, fast mid, slow end |
| `linear`                    | Same speed throughout          |
| `ease-in`                   | Starts slow                    |
| `ease-out`                  | Ends slow                      |
| `ease-in-out`               | Starts & ends slow             |
| `cubic-bezier(x1,y1,x2,y2)` | Custom easing                  |

---


## ✅ **4. Multiple Transitions**

```css
.box {
  transition: width 0.5s, height 0.3s ease-in 0.2s;
}
```

✅ Animate both `width` and `height` with different durations/delays.