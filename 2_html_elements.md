# HTML Elements 

HTML tags (formally known as HTML elements) are usually nested inside each other to create the desired structure.

## Nesting tags

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My HTML document</title>
  </head>
  <body>
    <h1>Welcome to my HTML document</h1>
  </body>
</html>
```

In the above example the `h1` tag is nested inside the `body` tag. 

## Top 10 Commonly used HTML elements 

- `<h1>` to `<h6>` Heading tags used to define different levels of headings, with `<h1>` being the highest level and `<h6>` the lowest. (Your document should have only one `h1` tag) 
- `<p>` Represents a paragraph of text.
- `<a>` Creates a hyperlink, allowing you to link to other web pages or resources.
- `<img>` Inserts an image into the webpage, with attributes like src (source) and alt (alternative text).
- `<ul>` and `<li>` Used together to create an unordered (bulleted) list, with `<ul>` as the container and `<li>` for each list item.
- `<div>` A generic container that helps group and style other elements together. It's commonly used for layout purposes.
- `<span>` Inline container for styling specific portions of text.
- `<input>` Creates form input fields for user input.
- `<button>` Represents a clickable button.
- `<table>`, `<tr>`, `<td>` Used together to create tables with rows and cells.


Add the following code to your `index.html` between the opening and closing `body` tags so that it looks like this:

```html
  <div>
    <h1>Heading 1</h1>
    <h2>Heading 2</h2>
    
    <p>This is a paragraph of text.</p>
    
    <a href="https://www.example.com">Visit Example.com</a>
    
    <img src="image.jpg" alt="My Image">
    
    <ul>
      <li>List item 1</li>
      <li>List item 2</li>
      <li>List item 3</li>
    </ul>
    
    <p>This is a <span>span element</span> within a paragraph.</p>
    
    <input type="text" placeholder="Enter your name">
    
    <button>Click me</button>
    
    <table>
      <tr>
        <td>Table cell 1</td>
        <td>Table cell 2</td>
      </tr>
      <tr>
        <td>Table cell 3</td>
        <td>Table cell 4</td>
      </tr>
    </table>
  </div>
```


2. Tag attributes
3. classes & ids
Identify ordered, unordered and definition lists
Identify images
Identify links
Identify HTML validation tools
Tables

https://validator.w3.org/




[Next lesson >>](./3_html_lists.md)