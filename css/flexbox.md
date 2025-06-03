# CSS Flexbox

**Flexbox** is used to create **one-dimensional** layout with **rows** OR **columns**.

**Key Terms**
- **Flex Container** → The parent element (`display: flex`)
- **Flex Items** → The child elements inside the container
- **Main Axis** → The primary direction (**row** or **column**)
- **Cross Axis** → **Perpendicular** to the **main axis**

## Properties for Flex Container

> - `display: flex;`

> - `flex-direction`
>   - `row`
>   - `column`
>   - `row-reverse`
>   - `column-reverse`

> - `flex-wrap`
>   - `no-wrap`
>   - `wrap`
  
> - `justify-content`
>   - `normal`
>   - `flex-start`
>   - `space-around`
>   - `space-between`
>   - `space-evenly`
>   - `center`
>   - `flex-end`

> - `align-items`
>   - `normal`
>   - `flex-start`
>   - `stretch`
>   - `flex-end`
>   - `baseline`

> - `align-content` : It aligns the **flex lines**.
>   - `normal`
>   - `flex-start`
>   - `space-around`
>   - `space-between`
>   - `center`
>   - `flex-end`
>   - `stretch`

> - `gap: row-gap column-gap;`
> - `flex-flow: flex-direction flex-wrap`

## Properties for Flex Items

> - `order: <number>;`: default value is: 0

> - `flex-grow: <number>;`: 
>   - default value is: `0` 
>   -  specifies how much a flex item will grow relative to the rest of the flex items.

> - `flex-shrink: <number>;`
>   - default value is: `0` 
>   - specifies how much a flex item will shrink relative to the rest of the flex items.

> - `flex-basis: <length>;`: specifies the initial length of a flex item.

> - `flex: flex-grow flex-shrink flex-basis;`

> - `align-self`
>   -  `flex-start`
>   -  `center`
>   -  `flex-end`