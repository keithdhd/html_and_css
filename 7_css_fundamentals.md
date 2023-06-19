CSS (Cascading Style Sheets) is a language that is used in combination with HTML to customise how HTML elements will appear. CSS can define styles and change the layout and design of a document.

## Linking CSS to HTML

```html
<head>
  <link rel="stylesheet" href="style.css">
</head>
```

In the example above, the `<link>` element is placed within the `<head>` section. The rel attribute specifies the relationship between the HTML document and the linked file, and the href attribute specifies the path or URL to the stylesheet file. In this case, the stylesheet file is named `style.css` and is located in the same directory as the HTML file.

## Some Terminology

```css
.welcome-text {
  color: green;
  margin-top: 24px;
}
```

This whole things is called a `rule`

`.welcome-text` is called the `selector`

`color` is called a `property`

`color: green;` is called a `declaration`

`24px` is called a `unit`
