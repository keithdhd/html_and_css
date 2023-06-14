# Rendering Logic

## Inheritance

Certain CSS properties inherit. When we apply a color to an element, that value gets passed down to all children and grand children. It's a little like inheritance in programming. CSS will look up the tree to find an appropriate selector!

Most of the properties that inherit are typography related. Like color, font-size, text-shadow, etc.

It's common for anchor tags to inherit the color of their parent.

```css
a {
  color: inherit;
}
```
```html
<p style="color: purple;">
  <a>This link will be purple</a>
</p>
```

## The Cascade Algorithm

If there are competing rules to apply to an element, there will be a battle! Who wins?

In order of importance:

- inherited styles (not very important)
- tag styles
- classes
- ids
- inline styles
- Marked as important! (the most important. Always wins.)

If we're using styled components, for example in React, we should never have to worry about the cascade because our CSS will be black-boxed.

## Block and Inline

CSS has two axes. A block axis (vertical) and an inline axis (horizontal)

Block direction is like lego blocks: they stack together one on top of the other.

Inline direction is like people standing in-line; they stand side by side, not one on top of the other.

HTML elements have a default direction - either block or inline, that the browser built-in styles apply. For example, <p> elements are block by default and so stack on top of each other.

## The Box Model

A critical part of the CSS rendering model. There are four elements to the box model.

1. Content
2. Padding
3. Border
4. Margin

What does it mean when we say an element has a width of 100%? Consider the following:

```css
section{
  width: 200px;
}

.card{
  width: 100%;
  padding: 10px;
  border: 5px solid;
  /* box-sizing: border-box; We'll use this in a minute! */
}
```
```html
<section>
  <div class="card">
  </div>
</section>
```

The card will have dimensions of 230px x 30px.

The default sizing for a box is content-box. Padding and border are added to 'both' sides of the width.

- Width: 200 (that's the 100% bit) + 10 (left-padding) + 10 (right-padding) + 5 (left-border) + 5 (right-border)
- Height: 10 (top-padding) + 10 (bottom-padding) + 5 (top-border) + 5 (bottom-border)

So the browser ADDS the padding, and border values to the 200px original size. This is not really what we want. We can get around this by setting the box-sizing property of our card to be `box-sizing: border-box;`

Now, the total width of the card will be 200px. This is much easier to reason about.

Since we always want to use border-box throughout, we can set it as a global style and apply it to all elements:

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}
```

## Padding

For padding and margin, values are entered in a clockwise way from north.

```css
.card{
  padding: 10px 20px 5px 3px;
}
```

The top will have padding 10, the right will be 20, the bottom 5 and the left 3.

In the next example, all sides will have padding 20px;

```css
.card{
  padding: 20px;
}
```

You can over-write a side with a more specific property.

```css
.card{
  padding: 20px;
  padding-left: 10px;
}
```
The left side will have padding 10 while all others will be 20. Note: The more specific
padding-left hast to come AFTER the padding.

## Border

There are three styles specific to border:

- Border width (eg. 3px, 1em)
- Border style (eg. solid, dotted)
- Border color (eg. dodgerblue, black)

Usually, they are used in the shorthand style:

```css
.card{
  border: 1px solid black;
}
```

For a rounded corners:

```css
.card{
  border: 1px solid black;
  border-radius: 5px;
}
```

## Margin

For padding and margin, values are entered in a clockwise way from north.

One quick and easy way to center an element is to use margin:auto. Note, the element must have a width. In this case, 50%. Note, this only works with width.  

```css
.content {
  width: 50%;
  margin-left: auto;
  margin-right: auto;
}

```

### Negative Margin

... can be really useful. Margin is not exclusively about changing the selected element's position. It's about changing the gap between elements.

Negative margin can affect the position of all siblings.

An example would be having a heading 'pop up' a little bit from it's article. A full width image in a paragraph of text can also be achieved with negative margin. (images are like foreign objects being imported into the DOM so we have to wrap them in a div usually to make applying margin negative more useful)

## Flow Layout

CSS has 7 distinct layout algorithms. You will already have heard of some of them. Like Flexbox ( technically flexible box layout) and Grid?

https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_mode

The default is "Normal Flow" aka Flow Layout. Flow layout is based on `inline` elements and `block` elements. Inline elements display one after the other, starting on the left, and block elements start at the top and move down the page. If you think about a newspaper this makes sense. Block elements are like paragraphs that are stacked on top of each other. Inline elements like `<strong>` do not stack. They just sit in the flow of the text from left to right. By default, most elements are `block`.

Exceptions to this rule are `replaced elements`. A replaced element is one that embeds a "foreign" object. This includes:

```
<img />
<video />
<canvas />
```

The other exception is `<button>`. Buttons are inline elements but if you were to give it a margin-top, it would take effect, unlike a `span`. Weird!

Block elements like `h1` and `p` and `div` will expand to fill the available space.


### Width Algorithms

`max-content` is useful to set the width to fit the width of it's content.

```css
div {
  width: max-content;
  background-color: dodgerblue;
}
```

`auto` will fill the available space of the parent.

`fit-content` means the element will use the available space, but never more than max-content.

A max-width wrapper is really useful to have and drop-in when needed. It keeps the card in the centre whilst allowing for mobile viewports to display it properly too.


```html
<!--
Create a “max-width-wrapper” utility.

• Should have a max-width of 350px
• Should have 16px of “breathing room” on
  smaller screens.
• HINT: Some HTML changes might be necessary.
  Feel free to tweak the markup.
-->

<style>
  /* TODO */
  .max-width-wrapper {
    max-width: 350px;
    margin-left: auto;
    margin-right: auto;
    padding-left: 16px;
    padding-right: 16px;
  }

  /* Cosmetic styles */
  body {
    background: #222;
    padding: 0px;
    padding-top: 32px;
  }

  .card {
    background-color: white;
    padding: 32px;
    border-radius: 8px;
  }

  p {
    margin-bottom: 16px;
  }
</style>

<div class="max-width-wrapper">
<div class="card">
  <p>
    Otters have long, slim bodies and relatively short limbs. Their most striking anatomical features are the powerful webbed feet used to swim, and their seal-like abilities holding breath underwater.
  </p>
</div>
</div>

```


### Height Algorithms

<!-- TODO -->
