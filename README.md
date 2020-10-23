# Website template built with CSS Grid vs Flexbox

There is no strict guide for setting up a website layout. [Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) seems to have gained popularity among developers faster, but the [CSS Grid](https://css-tricks.com/snippets/css/complete-guide-grid/) stays very close behind. Part of the reason for that popularity is that frameworks like Bootstrap or React Native have adopted Flexbox as the foundation of their layout. Another may be the learning curve that initially complicates CSS Grid with so many different ways of creating a layout. Both, however, can be equally good or useful in a given situation. They also don't exclude each other, you can bild Grid container and nest a Flexbox item in it, or make the Flexbox item a Grid container.

### Positioning elements

That being said, the main importance of CSS Grid and Flexbox is that components are completely decoupled from the container, which means you can remove or reuse any component elsewhere without having to change the CSS, and everything will still look perfect.

Components should also not worry about their positioning. The parent container should place the component as it is, wrap it in a row or a column, at the beginning or the end of the container, and without the need for the component to change its spacing. The last thing may be the main difference between CSS Grid and Flexbox. In Flexbox you need to space each component out of its siblings with margins. CSS Grid provides the `gap` property to separate child components in a meaningful pattern.

```
.container {
  display: grid;
  gap: 2rem;
}
```

But, in order for the components to fill the entire space of the main container, Flexbox requires an additional inner container with negative margins that will subtract the margin of the components.

```
.container {
  primer so flexbox
}
```
