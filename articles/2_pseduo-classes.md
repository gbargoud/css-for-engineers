# A Crash Course in Selectors: Part 2

## What are Pseduo-Classes?

Pseudo-classes are specific attributes or properties of an element that can be used to make styling more robust, streamlined, and responsive to user interaction.

## States

This section specifically refers to pseudo-classes that can be added to links. They can be styled like this:

```
a:hover {
  text-decoration: underline;
}
```

Any CSS declarations that can be made on the element itself can also be made on the pseudo-class. These are used to indicate to the user what state they are in in their interaction with the link.

### `:link`
<!-- TODO(maddie): explain -->

### `:hover`
<!-- TODO(maddie): explain -->

### `:active`
<!-- TODO(maddie): explain -->

### `:visited`
<!-- TODO(maddie): explain -->

Putting it all together:

![Demo](../images/stateful_pseudo_classes.gif)

Here is a codepen [demo](http://codepen.io/raemadeline/pen/MyNXqx) to illustrate the gif above.

### `:focus`
