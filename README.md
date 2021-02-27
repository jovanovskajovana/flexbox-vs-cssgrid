# CSS Grid vs Flexbox

This repository includes two examples of the same website template. One is built entirely with [Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) and the other with [CSS Grid](https://css-tricks.com/snippets/css/complete-guide-grid/).

<br/>

<img src="demo.gif" width="80%" height="auto" />

> [Demo](https://flexbox-vs-cssgrid.netlify.app/)

However, there is no strict guide to setting up the layout. You can choose based on the pattern you want to achieve, as well as what best suits your team and the site you build. You can create a Grid container and nest a Flexbox item in it, or make the Flexbox item a Grid container. Both can be as good or useful in a given situation and certainly they do not exclude each other.

## Pay attention to

#### CSS Grid's `gap` property

```
.posts {
  display: grid;
  gap: 2rem;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
}
```

> While in Flexbox you have to space each component out of its siblings with margins, CSS Grid provides the `gap` property to separate child components in a meaningful pattern.

#### The spacing in Flexbox container

```
.posts {
  display: flex;
  flex-wrap: wrap;
  margin-left: -1rem;
  margin-right: -1rem;
}

.post {
  width: calc(33.33% - 2rem);
  margin-left: 1rem;
  margin-right: 1rem;
  margin-bottom: 2rem;
}
```

> In order for the components to fill the entire space of the main container, Flexbox may require adding negative margins that will subtract the margin of the components.

#### Fractional units (fr) in CSS Grid

```
.posts {
  display: grid;
  gap: 2rem;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
}
```

> When working with percentages, you also have to calculate the gap (eg. a grid of 4 elements, each 25% wide, will go out of the viewport because it is 100% + 4 x 2rem gap). That is why we need fractional units. A `fr` takes up the amount of available space after all elements are placed.

#### Auto-Sizing Columns in CSS Grid

```
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(400px, 1fr));
  grid-auto-rows: 400px;
  grid-auto-flow: dense;
  gap: 2rem;
}
```

> Notice how the `repeat` notation, along with `minmax` and the auto-sizing properties `auto-fill` and `auto-fit`, make the grid responsive by nature, eliminating the need for media queries to some extent. Flexbox, however, requires some manually structured rows and columns for different screen sizes.

#### Page layout with grid-template-areas

```
.page-wrapper {
  display: grid;
  grid-template-areas:
    'header header'
    'sidebar container'
    'sidebar footer';
}
```

> Except of some global container sizes, in Flexbox there is no need to wrap the entire layout in a parent container. With CSS Grid, on the other hand, you can create an exact grid template referencing the names of the grid areas from which the page will be structured.

#### Overlaying without an absolute positioning

```
.sidebar {
  grid-area: sidebar;
  padding: 10vw 2vw;
  z-index: 1;
}

.container {
  grid-area: container;
  grid-column: 1 / -1;
  display: grid;
  row-gap: 10vw;
  padding: var(--page-padding);
}

.footer {
  grid-area: footer;
  grid-column: 1 / -1;
  padding: var(--page-padding);
}
```

> You can use `grid-column` and `grid-row` to specify the start and end line for a layout item. This allows the footer and main container to start from the `1` column line and extend to the last, marked `-1`. The sidebar will then hover over them without the need for absolute positioning.
