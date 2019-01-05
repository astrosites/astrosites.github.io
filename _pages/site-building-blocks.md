---
layout: page
title: Website Building Blocks
nav-order: 2
---

# HTML
Hyper Text Markup Language (HTML) is the standard markup language for creating web pages. HTML code is made up of *elements* which build a webpage piece-by-piece to include backgrounds, headings, paragraphs, images, tables, etc. HTML elements are represented by *tags*, or labels that are placed at the beginning and end of a particular element to communicate which type of element is being constructed. For example, to create a paragraph use the following tags: 

        <p>
		Here is a paragraph.
        </p>

HTML code controls the **content** of a web page. <a href="https://www.w3schools.com/html/">Learn more about HTML.</a>

# CSS
Cascading Style Sheets (CSS) is a style sheet language that describes the presentation of web pages written in a markup langauge - such as HTML - including layout, colors, fonts, etc. In CSS, *selectors* declare which part of the markup a particular style applies to by matching HTML tags to style attributes. For example, you may encounter the following:

        h1 {
                font-size: 2.25rem;
                letter-spacing: 0.5rem;
        }

This says that the Header 1 styling for a particular web page carries the tag "h1". All pieces of text within the HTML code that hold the tags <h1> ... </h1> will have a font size of 2.25 times that of the root element (defined elsewhere in the CSS file, default 16pt) and a letter spacing of 0.5 times that of the root element.

CSS code controls the **styling** of a web page. <a href="https://www.w3schools.com/css/">Learn more about CSS.</a>

# JavaScript

JavaScript enables interactive web pages, supporting dynamic behavior, information storage, and requests + responses. When JavaScript is used in conjunction with HTML, JavaScript code can react to HTML *events*, such as when a page is loaded, an input field is changed, or a button is clicked. The following example closes an article after the user presses ESC:

        // Window.                                                                                                                                      

                // Event: Hide on ESC.                                                                                                                  
                        if (config.hideOnEscape)
                                $window.on('keydown', function(event) {

                                        if (event.keyCode == 27)
                                                $this._hide(event);

                                });

        return $this;


JavaScript code controls user **interactions** with a web page. <a href="https://www.w3schools.com/js/">Learn more about JavaScript.</a>