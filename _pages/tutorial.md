---
layout: page
title: Website Tutorial
nav-order: 1
---

This page contains a tutorial to get you set up with a personal website using our [AstroSites template page](/template/). At the end of this tutorial you will:

1. Know the basics of HTML, CSS, and JavaScript.
2. Know how to edit an [HTML5 template](https://html5up.net/) site to make it your own.
3. Have a personal website published using GitHub Pages.

# HTML, CSS, and JavaScript

## HTML 

#### Reference: [https://www.w3schools.com/html/](https://www.w3schools.com/html/)

Every webpage on the internet is built using Hypertext Markup Language (HTML). Every webpage is built up from **elements**, or single semantic componenets, which are represented in code as `<element>`, which is called an element tag. For example, a blog you'd read online is built from a few paragraphs (`<p>`), a few images (`<img src="URL">`), and links (`<a href="URL">`) to other sites. Some elements, like images and links, exist as a discrete unit; however, other elements, like paragraphs, **wrap** other content. These elements that wrap content are represented in code as `<element> Content </element>` where that second element tag closes (represented with the `</`) the first element tag. For example, if you had a paragraph it would look like this:

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

and when you are looking to edit a template that you've downloaded, you'll want to look in the `<body>` portion of the page. An example of a simple web page built using just HTML can be found [here](/tutorial/html-demo.html). This looks pretty boring! And that's because it's built from just barebones HTML. Cascading Style Sheets (CSS) is another language that adds on to HTML to style each individual element.

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

# Add information about where to get template and why we used this one!

# Grabbing the Template

Before we start making our personal website, we first need to grab the template from the AstroSites public repository on GitHub. 
1. Navigate to [https://github.com/astrosites/template](https://github.com/astrosites/template). 
2. **fork** the repository, following the image below.
    ![](/tutorial/images/repository.png)
3. Rename the repository. Click "Settings", replace "template" with "your-github-name.github.io" in the "Repository name" form, and click "Rename":
    ![](/tutorial/images/settings.png)
        
    ![](/tutorial/images/rename.png)    
    
    ![](/tutorial/images/renamed.png)
4. Once renamed, navigate back to "Setting" and scroll down in the settings to the "GitHub Pages" section. Ensure that Ensure that your repository has GitHub Pages enabled and that the master branch is chosen under “Source”.
    ![](/tutorial/images/gh-pages.png)
    
    If it says "Your site is *ready* to be published...", wait a minute or two and then refresh the page. It should publish automatically. If it's still not ready, you can move on with the tutorial and wait for the publishing to happen in the background.
5. You are done! Your new site is now published at [https://your-github-name.github.io](#)!

Now we can start editing the template to personalize it!

# Repository Structure

When people access the URL [https://your-github-name.github.io](#), they will be served up the file `index.html` which is in the root folder of your repository. The CSS and JavaScript that the page uses is stored in the `assets` folder, and images the site uses are stored in the `images` folder:

![](/tutorial/images/repo-summary.png)

# Editing the Template

Most of the edits we will perform will be on `index.html`. Click on that file in your repository to open it up. Once the file is loaded, click on the **pencil** icon to start making edits.

![](/tutorial/images/first-edit.png)

In a second tab or window, pull up your site by navigating to [https://your-github-name.github.io](#). This will allow you to see your edits happen as you make them in the HTML file.

![](/tutorial/images/initial-site.png)

## Template Site Structure

This template consists of two main portions. First, the home page, which is what you see in the previous image. The home page consists of a heading that displays your name, an image where you can put a headshot of yourself, space for you to put your position and institution or a short blurb about yourself, along with a navigation bar filled with buttons that navigate the user to different sections of the site.

![](/tutorial/images/site-structure.png)

Each of the navigation buttons opens up a "card" within the window which provides the user with more information about you, your research, or anything else. Seen below is the website after clicking the "About Me" button:

![](/tutorial/images/about-me.png)

## Changing Names

The first thing we want to do is add our name to the site. To do this, we will use the Inspector tool in our web browser to identify which elements in the HTML control what we see displayed as "First Last". Hover your mouse cursor over "First Last", right-click, and select "Inspect". Note that your inspection panel will look different depending on which browser you are using. However, all browsers should have this same functionality available.

![](/tutorial/images/inspect.png)

By observing what we see in the inspector, we can find the information in `index.html` that we should change to make our desired edits. We see that the "First Last" text is contained in `<h1>` tags which are children elements of `<div class="inner">` and is followed by an `<img>` tag which contains the image we see displayed on the front page.

![](/tutorial/images/inspect-first-last.png)

Use your mouse cursor (or arrow keys) to click on the different elements inside the inspector (for example the parent `<div class="inner">` element and the `<img>` following it>) surrounding the "First Last" heading to see how selecting elements in the inspector on the right will show you visually where those elements appear on the page on the left.

![](/tutorial/images/inspect-div-inner.png)

Going back to GitHub, we can now find and edit the "First Last" text. Use Ctrl-F or Command-F to perform a descriptive search of the element we are looking for. For example, you can search for "First Last", or "<div class="inner">" to find what you are looking for in the page. Once you find the text, change it to your name. When you are done making your edits, scroll to the bottom of the page and "commit" your changes. In the first text box, put a descriptive summary of the changes you've made and click "Commit changes".

![](/tutorial/images/commit-changes.png)

If you refresh your website at [https://your-github-name.github.io](#), you should see your site with the updates you've made.

![](/tutorial/images/site-with-name.png)

## Changing Images

Next, we will add a photo of ourselves to our page. Again, to find where to edit the `index.html` file, we'll right click on the image on the front page and use the Inspector to examine the image.

![](/tutorial/images/inspect-img.png)

We can see the image is created with the element `<img src="images/Astronomy.jpg" style="width:280px; height:280px; object-fit: cover;">`. The `src="images/Astronomy.jpg"` tells the browser to grab the image called `Astronomy.jpg` located in the `images` directory of your repository. Note that you can also use **any** URL here. For example, we can grab [this nice photo from Wikipedia](https://upload.wikimedia.org/wikipedia/commons/6/62/Starsinthesky.jpg) and use it instead: `<img src="https://upload.wikimedia.org/wikipedia/commons/6/62/Starsinthesky.jpg">`. The `style="width:280px; height:280px; object-fit: cover;"` is some CSS that tells the browser to make the image 280 pixels wide, 280 pixels high, and to crop the image (`object-fit: cover`) instead of stretching it when resizing. Next, we will upload our own image to use to the `images` directory of our repository and change the HTML to point to that image instead of the one provided.

First, gather an image that you want to use as your headshot (or replacement photo) and take note of its filename. Our photo will be called `Headshot.jpg`, and you should replace instances of that name below with the name of your file. Next, on the main page of your site repository, click on the `images` folder:

![](/tutorial/images/images.png)

Next, click on the "Upload files" button.

![](/tutorial/images/upload.png)

Either drag your photo into the area specified or click the upload area and use the window that pops up to navigate to and upload your photo. Provide a descriptive summary of your change in the "Commit changes" section. Click the "Commit changes" button to finish uploading your file.

![](/tutorial/images/upload-image-commit.png)

Navigate back to the `images` folder in your repository and notice that your file has been uploaded.

![](/tutorial/images/uploaded-image.png)

On your website, this file can be accessed by loading the URL [https://your-github-name.github.io/images/Headshot.jpg](#), and inside the `index.html` file, we can reference this image using the URL `images/Headshot.jpg`. Next, open the `index.html` file and click the pencil icon to edit it. Perform a descriptive search to find the image element that we inspected before. For example you can search for "img src="images/Astronomy.jpg""

![](/tutorial/images/img-search.png)

Change `src="images/Astronomy.jpg"` to `src="images/Headshot.jpg"` and then commit your changes.

![](/tutorial/images/img-change.png)

![](/tutorial/images/img-change-commit.png)

Now if you reload your site, you'll find your image has changed!

![](/tutorial/images/img-changed.png)

## Changing "About Me" Information

Next, we'll change the information that exists in one of the pop-up cards, specifically the "About Me" card. First, on our site we'll click on the "About Me" button to open the card.

![](/tutorial/images/about-me-click.png)

On the "About Me" card, we see that there appears to be a heading, a space for an image, and space for information about us.

![](/tutorial/images/about-me-summary.png)

Next, we'll inspect this card to learn more about how the HTML in `index.html` is structured to form this card. Right click on the dark square that wraps around the "About Me" card and click inpsect. 

![](/tutorial/images/about-me-inspect.png)

We can see that the card is created using the following HTML:
```html
<article id="about" style="" class="active">
    Content inside here
</article>
```
which is an `<article>` element with the ID `about` and the class `active`. Notice also that there are other `<article>` elements below this one with IDs `research`, `community`, and `contact`, which are the names of the other buttons, and which do not have the `class="active"` attribute but do have a `style="display: none;"` attribute. Finally, notice that upon clicking the "About Me" button on the home page, we were redirected to [https://your-github-name.github.io/#about](#). When a URL is followed by `#something`, your browser moves the page to display the element with `id=something`. This indicates that the template has some JavaScript built into it that hides all of the cards when you initially load the page, but shows them by changing the `<article>` elements' `class` and `style` attributes when you click on one of the navigation buttons on the front page. (Finally, notice what happens to the URL and `<article>` elements when you click the "X" icon in the top-right of the card.)

Next, in the GitHub interface, navigate to `index.html` and click the pencil icon so we can make some changes. Perform a descriptive search to find the HTML we are interested in. Note that since the HTML we are interested in is so far down in the `index.html` file, you may need to use the built in file search function to perform a search. To do so, click on the inner box in the webpage that contains the text of `index.html` and hit Ctrl-F or Command-F again to do your search.

![](/tutorial/images/about-me-search.png)

Here we find the HTML used to make the "About Me" card:

![](/tutorial/images/about-me-search-result.png)

Edit the information here to describe yourself. Note that if you don't want an image on the card, you can comment out the `<span> ... </span>` element (by wrapping the element in comment tags: `<!-- <span> ... </span> -->`) or deleting the element altogether. Once you've finished your edits, commit your changes and reload your page to see the edits on your site.

![](/tutorial/images/about-me-edits.png)

## Changing the Site Title

You may have noticed in your web browser that the tab that has your site open has the text "AstroSites" in it.

![](/tutorial/images/site-title.png)

This part of the website is controlled in the `<head>` of the `index.html` page, which we haven't looked at yet. Open the `index.html` file in your browser and perform a search for "<head>".

![](/tutorial/images/head.png)

There are two important things to notice. First, the `<title>` element, which controls the title of the site, and thus what appears in the tab of your web browser. Second, the `<link>` element which points your web browser to the CSS that styles the template site which is located in `assets/css/main.css`. Go ahead and change what is contained in the `<title>` element from "AstroSites" to your name and commit your changes. Reload your site and see the results!

![](/tutorial/images/site-title-changed.png)

## Continuing Edits

We've shown you how to edit the basic components of this template. You should now be able to edit this template to your heart's content! You can also find another template that better suits your tastes and needs and start editing it in a similar way.

What follows are optional changes that you might want to make

### Changing the Background Image

On this template it's a bit hard to find the HTML and CSS that controls the background image. However, if right click on the main page of the site and click inspect, you will find that there are two children elements of the `<body>` tag: the `<div id="wrapper">` (which wraps the main content of the site) and the `<div id="bg">` element, which appears to take up the whole page. The conspicious name and the element's rendered size indicate to us that this element controls the background image. 

![](/tutorial/images/bg-inspect.png)

![](/tutorial/images/bg-inspect-element.png)

If you look inside the `<div id="bg>` element, you will see that it does not contain much inside of it other than a `::before` and `::after` element. This indicates that the background is entirely controlled through the site's CSS. To edit the image, we will need to edit the CSS file. Using the GitHub browser, from the root folder navigate to the `assets` then to the `css` folder. Open the file `main.css` and click the pencil icon to make edits. Perform a search for the **ID** of the div element: "#bg" (since the element was `<div id="bg">` then the CSS selector will be `#bg`). Next we will scroll down and visually inspect the CSS for where the `background-image` attribute is in use. (Note that we could have just opened the CSS file and searched for "background-image" to see where the background was being manipulated. However, since there are other ways in HTML and CSS to set a background image, this method is not always reliable.)

![](/tutorial/images/background-image.png)

Note that there are two locations where `background-image` is set, however they are set with two different values of `z-index`. The `z-index` attribute sets the order that elements are rendered in. Elements that have a larger value of `z-index` set are rendered on top of elements with a smaller value of `z-index`. This indicates that the real background image is the one with `z-index: 1` under the `#bg:after` selector. (The other background image is a speckled gray overlay that makes text stand out on the real background. Check out `images/overlay.png` to see it.) The background image is set to `url("../../images/bg.jpg");` which loads an image from the URL `../../images/bg.jpg`. Here the `../` tells the browser to go up a level in the website's file structure. This is necessary since our CSS file exists at the location `assets/css/`. Thus inside the CSS file a URL of `../` would really point to `assets/` and `../../` would really point to the root folder of our site, allowing us to access the `images/` folder. Change the url from `url("../../images/bg.jpg");` to `url("../../images/Astronomy.jpg");` to change the background image and then commit your changes. You can also use any other URL you want to point elsewhere on the web, or you can upload another image to use instead. Reload your site to see your changes!

![](/tutorial/images/background-changed.png)
