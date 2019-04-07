# Flexbox

## Container properties

__display:__ This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.
```
.container {
  display: flex; /* or inline-flex */
}
```

__flex-direction:__ This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is (aside from optional wrapping) a single-direction layout concept. Think of flex items as primarily laying out either in horizontal rows or vertical columns.

```
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```
__flex-wrap:__ By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.

```
.container{
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

__flex-flow:__ This is a shorthand flex-direction and flex-wrap properties, which together define the flex container's main and cross axes. Default is row nowrap.

```
flex-flow: <‘flex-direction’> || <‘flex-wrap’>
```

__justify-content:__ This defines the alignment along the main axis. It helps distribute extra free space left over when either all the flex items on a line are inflexible, or are flexible but have reached their maximum size. It also exerts some control over the alignment of items when they overflow the line.

```
.container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
}
```

__align-items:__ This defines the default behavior for how flex items are laid out along the cross axis on the current line. Think of it as the justify-content version for the cross-axis (perpendicular to the main-axis).

```
.container {
  align-items: stretch | flex-start | flex-end | center | baseline;
}
```

__align-content:__ This aligns a flex container's lines within when there is extra space in the cross-axis, similar to how justify-content aligns individual items within the main-axis.

**Note**: this property has no effect when there is only one line of flex items.

```
.container {
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}
```


## Items properties

__order:__ By default, flex items are laid out in the source order. However, the order property controls the order in which they appear in the flex container.

```
.item {
  order: <integer>; /* default is 0 */
}
```

__flex-grow:__ This defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

If all items have flex-grow set to 1, the remaining space in the container will be distributed equally to all children. If one of the children has a value of 2, the remaining space would take up twice as much space as the others (or it will try to, at least).

**Note**: Negative numbers are invalid.

```
.item {
  flex-grow: <number>; /* default 0 */
}
```

__flex-shrink:__ This defines the ability for a flex item to shrink if necessary.

**Note**: Negative numbers are invalid.

```
.item {
  flex-shrink: <number>; /* default 1 */
}
```

__flex-basis:__ This defines the default size of an element before the remaining space is distributed. It can be a length (e.g. 20%, 5rem, etc.) or a keyword. The auto keyword means "look at my width or height property" (which was temporarily done by the main-size keyword until deprecated). The content keyword means "size it based on the item's content" - this keyword isn't well supported yet, so it's hard to test and harder to know what its brethren max-content, min-content, and fit-content do.

**Note**: Negative numbers are invalid.

```
.item {
  flex-basis: <length> | auto; /* default auto */
}
```

__flex:__ This is the shorthand for flex-grow, flex-shrink and flex-basis combined. The second and third parameters (flex-shrink and flex-basis) are optional. Default is 0 1 auto.

**It is recommended that you use this shorthand property** rather than set the individual properties. The short hand sets the other values intelligently.

```
.item {
  flex-basis: <length> | auto; /* default auto */
}
```

__align-self:__ This allows the default alignment (or the one specified by align-items) to be overridden for individual flex items.

Please see the align-items explanation to understand the available values.

**It is recommended that you use this shorthand property** rather than set the individual properties. The short hand sets the other values intelligently.

**Note**: that float, clear and vertical-align have no effect on a flex item.

```
.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```