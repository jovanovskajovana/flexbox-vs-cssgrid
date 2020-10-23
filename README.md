# CSS Grid vs Flexbox

This repository includes two examples of a same website template. One is built entirely with [Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) and the other with [CSS Grid](https://css-tricks.com/snippets/css/complete-guide-grid/).

<img src="demo.gif" width="80%" height="auto" />

<br/>

However, there is no strict guide for setting up the layout. You can choose based on the pattern you want to achieve, as well as what works well for your team and the site you build. Both can be as good or useful in a given situation, nor do they exclude each other. You can bild a Grid container and nest a Flexbox item in it, or make the Flexbox item a Grid container.

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
