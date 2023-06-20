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








## Debugging with Chrome devtools

Right click on the browser and select "Inspect". Open the "Elements" tab and the "Styles" tab.

Here you can see the CSS that is applied to the HTML elements. You can edit your CSS here and see it change in the browser.

Remember though that any changes you make in the Devtools will need to be copied into your actual CSS file otherwise they won't be saved.

