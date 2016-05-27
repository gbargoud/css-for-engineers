# A Crash Course in Selectors: Part 2

## What are Pseduo-Classes?

Pseudo-classes are specific attributes or properties of an element that can be used to make styling more robust, streamlined, and responsive to user interaction. All of this can be done without the added bloat of javascript, and provides a lot of value with minimal overhead.

## States

This section specifically refers to pseudo-classes that can be added to links. They can be styled like this:

```
a:hover {
  text-decoration: underline;
}
```

Any CSS declarations that can be made on the element itself can also be made on the pseudo-class. These are used to indicate to the user what state they are in in their interaction with the link. This also works with buttons.

### `:link`
This is the default state for links. It is the pseudo-class that's applied to links before you ever interact with them.

### `:hover`
This one is fairly self-explanatory, but this pseudo-class is applied when the mouse is hovering over the element. It is used to indicate that the element is interactive, and that the user can expect something to happen when they click on it. Hover is a special state because it can work on nearly any element in the DOM.

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

HTML inputs and buttons can be disabled by adding the word `disabled` to their tag, like this `<button disabled>Don't Click Me!</button>`. This attribute prevents the user from interacting with that element. By default, the pointer (which is usually an arrow, but becomes a pointing finger on clickable elements), will stay an arrow, and default (provided by the browser) hover and other interaction styling will be removed. This pseudo-class should be styled in a way that conveys to the user that this element cannot be interacted with.

## Position and Index-Based Classes

### `:root`

This pseudo-class applies to the element at root level in the page. In most cases, this refers to the `<html>` tag at the start of every file, but it can also refer to something else when using other markup languages like SVG and XML. This pseudo-class can be used to set base styling for the entire document.

Why would you want to use this instead of directly targeting the root element itself? The pseudo-class is less specific than directly targeting the element (stay tuned for Part 4 where I explain specificity).

### `:nth-child(N)`

Let's assume we have an HTML page that looks like this

```
<ul class="vegetables">
  <li>Avocado</li>
  <li>Beets</li>
  <li>Carrots</li>
  <li>Dill</li>
  <li>Eggplant</li>
  <li>Fennel</li>
  <li>Grapefruit</li>
  <li>Honeydew</li>
</ul>
```

Say we wanted to specifically target the carrots, we could use this as our CSS:

```
.vegetables :nth-child(2) {
  color: orange;
}
```

`:nth-child(N)` is zero-indexed, and can target any child element with that index, assuming there are that many children of the parent. You can also target `:nth-child(even)` and `:nth-child(odd)`.

If you wanted to get even more customized, you can do anything in the format of `:nth-child(an+b)`, where `a` is the multiplier and `b` is the offset. For instance, if you want to target `Dill`, `Fennel`, and `Honeydew`, you can do `:nth-child(2n + 3)`.

In a similar vein, you can also do the same thing but counting backwards from the end of the list using `:nth-last-child(N)`, using it the exact same way as you would `:nth-child(N)`.

For simplicity for commonly used selectors, you can substitute `:first-child` for `:nth-child(0)`, and `:last-child` for `:nth-last-child(0)`.

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
* `li:nth-child(N):before`: Adding custom bullet points to lists

**Keep an eye out for Parts 3 and 4 of this blog post where I will discuss more advanced selectors that can be used with SASS (a beautiful CSS preprocessor)n and specificity in CSS selectors.**
