# CSS Flexbox

**Flexbox** is used to create **one-dimensional** layout with **rows** OR **columns**.

**A flexbox consists of:**
- **Flex Container** → The parent element on which we applied `display: flex`
- **Flex Items** → The child elements inside the container
- **Main Axis** → The primary direction (**row** or **column**)
- **Cross Axis** → **Perpendicular** to the **main axis**

## Properties for Flex Container

- `flex-direction` - Specifies the direction of the flex items inside a flex container

  - `row` - default
  - `column`
  - `row-reverse`
  - `column-reverse`

- `flex-wrap` - Specifies whether the flex items should wrap or not, if there is not enough room for them on one flex line
  - `no-wrap` - default
  - `wrap`
  
- `justify-content` - Aligns the flex items on the main-axis when the items do not use all available space
  - `normal` - default
  - `flex-start`
  - `space-around`
  - `space-between`
  - `space-evenly`
  - `center`
  - `flex-end`

- `align-items` - Aligns the flex items on the cross-axis when the items do not use all available space
  - `normal` - default
  - `flex-start`
  - `stretch`
  - `flex-end`
  - `baseline`

- `align-content` : It aligns the **flex lines**.
  - `normal` - default
  - `flex-start`
  - `space-around`
  - `space-between`
  - `center`
  - `flex-end`
  - `stretch`

- `gap: row-gap column-gap;`
- `flex-flow: flex-direction flex-wrap;`

## Properties for Flex Items

- `order: <number>;`- 
  - Specifies the order of the flex items inside the container 
  - default value is: 0

- `flex-grow: <number>;`: 
  -  specifies how much a flex item will grow relative to the rest of the flex items.
  - default value is: `0` 

- `flex-shrink: <number>;`
  - specifies how much a flex item will shrink relative to the rest of the flex items.
  - default value is: `0` 

- `flex-basis: <length>;`: specifies the initial length of a flex item.

- `flex: flex-grow flex-shrink flex-basis;`

- `align-self` - Specifies the alignment for a flex item (overrides the flex container's align-items property)
  -  `flex-start`
  -  `center`
  -  `flex-end`