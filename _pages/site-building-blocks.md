---
layout: page
title: Website Building Blocks
nav-order: 2
---

# HTML, CSS, and JavaScript

## HTML 

#### Reference: [https://www.w3schools.com/html/](https://www.w3schools.com/html/)

Every webpage on the internet is built using Hypertext Markup Language (HTML). Every webpage is built up from **elements**, or single semantic componenets, which are represented in code as `<element>`, which is called an element tag. For example, a blog you'd read online is built from a few paragraphs (`<p>`), a few images (`<img src="URL">`), and links (`<a href="URL">`) to other sites. Some elements, like images and links, exist as a discrete unit; however, other elements, like paragraphs, **wrap** other content. These elements that wrap content are represented in code as `<element> Content </element>` where that second element tag closes (represented with the `</`) the first element tag. Because HTML is so dynamic, most of the elements encountered in HTML have wrapping capabilities and will require a closing tag. Comments in HTML are indicated with the opening and closing tags `<!--- Content --->`.

For example, if you had a paragraph it would look like this:

```html
<p>
    This is a paragraph.
</p>
```

The basic structure of any webpage looks like this:

```html
<html>
    <head>
        Metadata about the website goes here.
    </head>
    
    <body>
        Our actual site content goes here.
        <!-- This is a comment about the site content. -->
    </body>
</html>
```
We can build an example page that has the following HTML:
```html
<html>
    <head>
        <title> HTML Example </title>
    </head>
    
    <body>
        <p>
            This is paragraph one.
        </p>

        <p>
            This is paragraph two.
        </p> 

        <h1>
            This is a Heading
        </h1> 
    </body>
</html>
```

When editing a template that you've downloaded, you'll want to look in the `<body>` portion of the page. An example of a simple web page built using just HTML can be found [here](/tutorial/html-demo.html). This looks pretty simplistic! And that's because it's built from just barebones HTML. Cascading Style Sheets (CSS) is another language that adds on to HTML to style each individual element.

## CSS

#### Reference: [https://www.w3schools.com/css/](https://www.w3schools.com/css/)

Cascading Style Sheets (CSS) is what makes websites pretty. CSS describes the presentation of web pages written in a markup langauge - such as HTML - including layout, colors, fonts, etc. In CSS, selectors declare which part of the markup a particular style applies to by matching HTML tags to style attributes. For example, you may encounter the following:

```css
h1 {
    font-size: 20px;
    letter-spacing: 3px;
}
```
which changes how large Heading 1 elements look like on your web browser. Specifically, all content between Heading 1 tags (i.e. looks like `<h1> Content </h1>`) will have a font size of 20 pixels and a letter spacing of 3 pixels. You may also see sizes specified in terms relative to other elements:
```css
h1 {
    font-size: 2.25rem;
    letter-spacing: 0.5rem;
}
```
says that all content between `<h1>` tags should have a font size 2.25 times that of the root element (rem) and a letter spacing of 0.5 times that of the parent element of the heading (em). (See [here](https://medium.com/code-better/css-units-for-font-size-px-em-rem-79f7e592bb97) for more.)

CSS also adds two more concepts to HTML: classes and ids. An HTML element can have both a class and an id `<p class="my-class" id="my-id">`, and the relevant CSS selectors for this element would be:

```css
/* This applies to all <p> elements */
p {
    font-size: 2.25rem;
}

/* This applies to all classes with class="my-class" */
.my-class {
    color: red
}

/* This applies to all elements (should just be one) with id="my-id" */
#my-id {
    letter-spacing: 0.5rem;
}
```

IDs are unique, and should not be used for different elements in a page. Classes are not unique and can be used for different instances of a single element and different element types all together. Continuing our example from the HTML section, the following would be valid:
```html
<html>
    <head>
        <title> HTML + CSS Example </title>
        <!-- This line points to where the CSS lives -->
        <link rel="stylesheet" href="assets/main.css">
    </head>
    <body>
        <p class="my-class" id="paragraph-one">
            This is paragraph one.
        </p>
        <p class="my-class" id="paragraph-two">
            This is paragraph two.
        </p> 
        <h1 class="my-class" id="heading-one">
            This is a Heading
        </h1> 
    </body>
</html>
```
and with the following CSS, all would be colored red, but each would have a different font size:
```css
.my-class {
    color: red
}

#paragraph-one {
    font-size: 1em;
}

#paragraph-two {
    font-size: 2em;
}

#heading-one {
    font-size: 3em;
}
```
This is shown in another example webpage [here](/tutorial/html-css-demo.html) with the CSS found [here](/tutorial/assets/main.css). Finally, it is important to note that you can hard code CSS styling into your HTML without referencing an external file or using CSS selectors by using the `style` attribute of an HTML element. For example, we can replicate the above example without separating the HTML and CSS with the following:

```html
<p style="font-size: 1em; color:red;">
    This is paragraph one.
</p>

<p style="font-size: 2em; color:red;">
    This is paragraph two.
</p> 

<h1 style="font-size: 3em; color:red;">
    This is a Heading
</h1>
```
However, do note that this is bad practice, as it's wasted effort to make all of the above elements individually red, instead of giving them all a class which makes them red. If all elements look the same in some way (e.g. the same color), then they should all be the same class. If one particular element looks different, you should give it an ID and use the CSS ID selector to change its styling.

When you are editing a template site, and you are interested in changing how an element looks, first identify what element it is (`<p>`, `<h1>`, `<img>`), what class it is (look for `<element class="class-name">`), and what ID it has (look for `<element id="id-name">`). Next, you want to find that element, class, and id in the page's CSS file and make your changes there.

## JavaScript

#### Reference: [https://www.w3schools.com/js/](https://www.w3schools.com/js/)

Finally, whereas HTML provides the structure of a web page and CSS provides the styling, JavaScript makes webpages **dynamic**, meaning their content and styling changes as users interact with them. When you are editing a templated webpage, you shouldn't have to worry too much about writing your own JavaScript. However, it is useful to know that it is there. 

JavaScript enables interactive web pages, supporting dynamic behavior, information storage, and requests + responses. When JavaScript is used in conjunction with HTML, JavaScript code can react to HTML events, such as when a page is loaded, an input field is changed, or a button is clicked. The following example closes an article after the user presses ESC:
```js
// Event: Hide on ESC       
if (config.hideOnEscape)
    //  If a user presses down on a key
    $window.on('keydown', function(event) {
        // If the key pressed is the escape (ESC) key
        if (event.keyCode == 27)
            // Hide the objects
            $this._hide(event);
    });

return $this;
```
