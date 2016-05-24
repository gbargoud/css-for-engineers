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
This is the default state for links. It is the pseudo-class that's applied to links before you ever interact with them.

### `:hover`
This one is fairly self-explanatory, but this pseudo-class is applied when the mouse is hovering over the element. It is used to indicate that the element is interactive, and that the user can expect something to happen when they click on it.

### `:active`
This pseudo-class is applied to an element while the element is being clicked on. Its only applied when the mouse is over the element and it is being pressed. Usually button clicks are pretty fast, so this class isn't applied for very long.

### `:visited`
Once an element has been clicked, this will become the new default state for that link. It is useful in blogs and similar sites, where you don't want your users to waste time visiting content that they have already seen.

Putting it all together:

![Demo](../images/stateful_pseudo_classes.gif)

Here is a codepen [demo](http://codepen.io/raemadeline/pen/MyNXqx) to illustrate the gif above.

### `:focus`

Focus is a special stateful pseudo-class because it can be applied to `<a>`s, `<buttons>`s, `<input>`s and `<textarea>`s. It refers to an element that is targeted by the keyboard or activated by the mouse. Its also used when "tabbing" through elements in a page to highlight which element is in focus at a given time. The default styling for `:focus` varies by browser, but it is usally an outline around the element. If you use chrome, you are probably familiar with this blue glow:

![Default Styling for `:focus`](../images/focus_default.png)

While you might think that this blue outline clashes with your style, and you might want to remove the default styling, it is important to have _some_ styling on `:focus`-able elements. This is because it is very beneficial for usability.

### `:disabled`

## Position and Index-Based Classes

### `:root`

### `:nth-child(N)`
also applies to `:first-child` and `:last-child`

### `:nth-of-type(N)`
also has `first-of-type`, `:last-of-type`, `:only-of-type`.

## Relational Pseudo-classes

### `:not(S)`

### `:empty`

## Text-related Pseudo-Elements

### `::first-letter`

### `::first-line`

## Content-related Pseudo-"Elements"

### `::before`
also applies to `::after`

## Pseudo-Classes on Inputs

Inputs have pseudo-classes applied to them based on the values inside them.

### `:checked`

### `:in-range`, `:out-of-range`

## Fun Combinations

These pseudo-classes can be used with combinators (check out [Part 1](1_selectors.md) if you forget what that means), and I thought I'd show a few fun examples to demonstrate.

* `a:not(:visited)`: All links that haven't been seen yet
* `input:out-of-range:focus`: You might put an error state on an input with invalid text, but you want it to go away when a user is typing.
* `p:first-child:first-letter`: Adding a drop cap to the first letter of the first paragraph of an essay.
* `:root::before`: Adding content before the start of the DOM

**Keep an eye out for Part 3 of this blog post where I will discuss more advanced selectors that can be used with SASS (a beautiful CSS preprocessor).**
