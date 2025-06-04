# CSS Grid

CSS Grid is used to create 2D layouts with rows and columns.

**A grid consists of:**

- **Grid Container** - The parent element on which we applied the `display: grid;`
- **Grid Items** - The child elements inside the **grid container**
- **Grid Columns** - The vertical lines of grid items are called columns.
- **Grid Rows** - The horizontal lines of grid items are called rows.
- **Grid Gaps** - The spaces between each column/row are called gaps.
- **Grid Lines** - The lines between columns are called column lines. The lines between rows are called row lines.

## CSS Grid Container Properties

- `grid-template-columns` - Specifies the size of the columns, and how many columns in a grid layout
- `grid-template-rows` - Specifies the size of the rows in a grid layout
- `grid-template-areas` - Specifies how to display columns and rows, using named grid items
- `row-gap` - Specifies the gap between the grid rows
- `column-gap` - Specifies the gap between the columns
- `gap` - A shorthand property for the `row-gap` and the `column-gap` properties
- `justify-content` - Horizontally align the grid items when they do not use all available space.
- `align-content` - Vertically align the grid items when they do not use all available space.
- `place-content` - A shorthand property for the `align-content` and the `justify-content` properties.
- `align-items` - Aligns content in a grid item along the column axis

## CSS Grid Items Properties

- `grid-column` - A shorthand property for the `grid-column-start` and the `grid-column-end` properties 
  - `grid-column: 1 / 3;`
  - `grid-column: 1 / span 2;`
- `grid-row` - A shorthand property for the grid-row-start and the grid-row-end properties
  - `grid-row: 1 / 3;`
  - `grid-row: 1 / span 2;`
- `grid-area`
  - A shorthand property for the `grid-row-start`, `grid-column-start`, `grid-row-end` and the `grid-column-end` properties  
  `grid-area: 2 / 1 / span 2 / span 3;`

  - The grid-area property can also be used to assign a name to a grid item. Named grid items can then be referenced to by the `grid-template-areas` property of the grid container.  
  `grid-area: myArea;`
- `align-self` - Aligns the grid item along the column axis
- `justify-self` - Aligns the grid item along the row axis
- `place-self` - A shorthand property for the` align-self` and the `justify-self` properties