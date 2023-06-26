# CSS Fundamentals

CSS (Cascading Style Sheets) is a language that is used in combination with HTML to customise how HTML elements will appear. CSS can define styles and change the layout and design of a document.

## Linking CSS to HTML

```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
```

In the example above, the `<link>` element is placed within the `<head>` section. The rel attribute specifies the relationship between the HTML document and the linked file, and the href attribute specifies the path or URL to the stylesheet file. In this case, the stylesheet file is named `style.css` and is located in the same directory as the HTML file.

## Some Terminology

In our stylesheet is where we declare our CSS "rules" that will affect the HTML it is linked to.

```css
.welcome-text {
    color: grey;
    font-size: 3rem;
}
```

It's important to be able to talk technically about our code, so let's look at some vocabulary to describe what is going on in this fragment.

This whole block of code is called a CSS `rule`

`.welcome-text` is the `selector`

`color` is a `property`

`color: grey;` is a `declaration`

`3rem` is a `unit`

Using the above rule, we can associate it with an HTML element in the index.html, in this case using the `class` attribute.

```html
 <h1 class="welcome-text">Welcome to CodeClan Services</h1>
```

The result would be:

![Welcome text example](../images/welcome_text_example.png)


## CSS Selectors

In the above example we targeted the HTML element using the `class` selector. However, there are many ways to target HTML elements. The most common are listed here: 

### Common Element Selectors

```css
/* Make all h2 elements black */
h2 {
    color: black;
}

/* Remove the underscore from all anchor tags */
a {
    text-decoration: none;
}
```

### Class Selectors

```css
/* Give all the elements with class 'card' a top margin */
.card {
    top-margin: 10px;
}
```

### ID Selectors

```css
/* Give the element with id 'main-section' a flex display */
#main-section {
    display: flex;
}
```

## Pseudo-classes

```css
/* :hover is one of the most common pseudo-classes */
/* Remove the underscore from all links on hover */
a:hover {
    text-decoration: none;
}
```

## Combinators

Combinators are characters between selectors that combine elements

### The space combinator (all descendants!)

Add a space between 'nav' and 'a'

```css
/* Make all links inside a nav blue and bold */
/* This applies to all links no matter how deeply nested they are within the nav */
nav a {
  color: blue;
  font-weight: bold;
}

/* Target ONLY the direct children */
nav > a {
  color: blue;
  font-weight: bold;
}
```


## Debugging with Chrome devtools

Chrome DevTools is a set of web developer tools built directly into the Google Chrome browser. This is **really** useful for development and debugging. It takes a bit of practice to use it effectively so it's good to start playing with it now.

Right click on the browser and select "Inspect". Open the "Elements" tab and the "Styles" tab.

Here you can see the CSS that is applied to the HTML elements. You can edit your CSS here and see it change in the browser.

Remember though that any changes you make in the DevTools will need to be copied into your actual CSS file otherwise they won't be saved.

# Next Lesson
[CSS Box Model >>](./8_css_box_model.md)