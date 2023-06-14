# HTML Lists

Let's dive into HTML lists. This is important because a lot of the data we display in web apps are lists. 

Even things that you wouldn't normally consider to be lists actually are. Consider a typical navigation header on a website. It's a 'list' of navigation items (e.g. Home, About, Contact).

Have a look at the [Gov.uk website](https://www.gov.uk/). How many lists can we see here? Most of the homepage is made up of lists! There's the 'Popular on GOV.UK' list of links, the navigation menu, the 'Topics', the 'Government activity', the 'Featured' etc. 

HTML provides three types of lists: unordered lists (`<ul>`), ordered lists (`<ol>`), and description lists (`<dl>` commonly used for glossaries or definitions.). We will mainly be focusing on `ul`. 

## Unordered Lists (`<ul>`):

Unordered lists are used to present items in a bulleted format. Each item is wrapped in a list item tag (`<li>`). 

Here's an example:

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

This will render as:

- Item 1
- Item 2
- Item 3

Often our `li` contains more than just text and we can use CSS (we'll get to that later) to remove the bullet points. Very useful!

Consider the following:

```html
<ul>
    <li>
        <div>
            <h3>Driving and Transport</h3>
            <p>Includes vehicle tax, MOT and driving licences</p>
        </div>
    </li>
    <li>
        <div>
            <h3>Driving and Transport</h3>
            <p>Includes vehicle tax, MOT and driving licences</p>
        </div>
    </li>
    <li>
        <div>
            <h3>Driving and Transport</h3>
            <p>Includes vehicle tax, MOT and driving licences</p>
        </div>
    </li>
</ul>

```

Here, the `li` tags contain `div` tags which in turn contain an `h3` and a `p`


