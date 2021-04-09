## Grid

### Resources

[Awesome free video course on grid by Wes Bos](https://cssgrid.io/)

[THE grid reference](https://css-tricks.com/snippets/css/complete-guide-grid/)

### Challenges

- [Play around with grid](https://cssgridgarden.com/)
- [Grid Exercises 1](https://coursework.vschool.io/css-grid-practice/)
- [Grid Exercises 2](https://github.com/danmcatee/ccl-grid-exercises)

### Why learn grid?

- Easier to create two dimensional layouts
- Simpler markup
- Flexible
- Skip frameworks
- Browser Support

![Grid Example](../ressources/grid.png)

```html
<!-- GRID -->

<div class="container">
  <div class="header">HEADER</div>
  <div class="menu">MENU</div>
  <div class="content">CONTENT</div>
  <div class="footer">FOOTER</div>
</div>
```

```html
<!-- BOOTSTRAP -->

<div class="row">
  <div class="col-12 header">HEADER</div>
</div>
<div class="row">
  <div class="col-4 menu">MENU</div>
  <div class="col-8 content">CONTENT</div>
</div>
<div class="row">
  <div class="col-12 footer">FOOTER</div>
</div>
```

### Your first grid

```html
<div class="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

![Without CSS](../ressources/without-css.png)

```css
.container {
  display: grid;
  grid-template-columns: 100px auto 100px;
  grid-template-rows: 100px 100px;
}
```

![With CSS](../ressources/with-css.png)

### Defining a grid

- `display: grid;`
  - With a grid defined on the parent element, all direct children become "grid items"
- `grid-template-columns`
- `grid-template-rows`
  - With these properties we define an explicit grid.
- `grid-column-gap`
- `grid-row-gap`
- `grid-gap`
  - We can create a gap between rows and columns.
- `grid-template-columns: 1fr 1fr 1fr;`
  - The fr unit is a fraction unit, representing a fraction of the available space in the container
- `grid-template-columns: 1fr 2fr 1fr;`
  - We have created 3 columns the units add up to 4. The space is split into 4 equal parts, the first track is given 1 part, the second is given 2 parts and the third is given 1 part again.
- `grid-template-columns: repeat(3, 1fr);`
  - The repeat syntax lets us define a repeating pattern of tracks
- The explicit grid is defined with rows and columns, If we didn't define rows however, grid would create implicit row tracks for us. These will be auto sized by default.
- `grid-auto-rows: 200px;`
  - We can define the size of implicit rows and columns with the properties `grid-auto-rows` and `grid-auto-columns`
- `grid-template-columns: repeat(auto-fill, 200px);`
  - Use the `auto-fill` keyword and grid will create as many tracks as will fit in the container
- `grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));`
  - The `minmax()` function enables the creation of flexible grids. The first value is the minimum size of the grid track, the second the max size. Set that to 1fr to allow the track to take up remaining space.

### Placing items on the grid

![Grid diagram](https://webkit.org/wp-content/uploads/grid-concepts.svg)

#### Grid track

A grid track is the space between two grid lines. Tracks can be horizontal or vertical (rows or columns)

#### Grid Lines

Lines can be horizontal or vertical. They are referred to by number and can be named

#### Grid Cell

The smallest unit on our grid, a grid cell is the space between 4 grid lines. It's just like a table cell.

#### Grid Area

Any area of the grid bound by 4 grid lines. It can contain multiple grid cells.

#### Using line numbers

- [Line based placement](https://codepen.io/rachelandrew/pen/RPXNod)
- [Line based placement spanning tracks](https://codepen.io/rachelandrew/pen/XbvJMz)
- [Line based placement spanning tracks with the span keyword](https://codepen.io/rachelandrew/pen/oXKgwa)

#### Defining Grid Areas

- [Example](https://codepen.io/rachelandrew/pen/oXKgoQ)

### Box alignment

- [Box alignment align-items](https://codepen.io/rachelandrew/pen/WQNqKy)
  - Aligns grid items along the block (column) axis
- [Box alignment justify-items](https://codepen.io/rachelandrew/pen/NGWZLM)
  - Aligns grid items along the inline (row) axis
- [Box alignment align-self](https://codepen.io/rachelandrew/pen/KdKLLX)
  - Aligns grid item inside a cell along the block (column) axis
- [Box alignment justify-self](https://codepen.io/rachelandrew/pen/dYyBeM)
  - Aligns grid item inside a cell along the inline (row) axis

### Nested Grid

- [Example](https://codepen.io/rachelandrew/pen/NqQPBR)

[Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
