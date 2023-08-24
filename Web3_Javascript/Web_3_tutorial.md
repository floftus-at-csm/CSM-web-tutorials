# Changing HTML with JavaScript: A Beginner's Tutorial

### Introduction:
In this tutorial, you'll learn how to dynamically modify HTML content using JavaScript. This is a core Javascript technique that can be used to make interactive and dynamic websites and web applications. In Javascript we can do a whole host of things. These are some examples of Javascript (JS) libraries:
* P5.js
    a creative toolkit designed for users to learn how to program and for making interactive apps - https://p5js.org/
* Three.js
    a javascript library for incorporating 3D graphics into a website - most 3D web experiences use this library at some point - https://threejs.org/
* Tensorflow.js
    For using machine learning models with javascript
* Aframe
    For creating VR experiences on websites
* Firebase
    an application for building web applications with databases. Create a database with firebase and access it with javascript
* Web Serial API
    an API for connecting your web applications with serial devices - can be used to connect any physical computing/Arduino projects with websites
One core output of these libraries is to change a website's content based on something dynamic thats happening in the javascript.
So, to get the most out of most Javascript libraries we want to be able to modify HTML via JS

This begs the question:
can you remind me of the difference between HTML and JS?
* HTML
    the structure and content of a page. The HTML is static. The HTML says things like: put a title first with this content, then a paragraph of text with that content, then this image etc.
* Javascript (JS)
    Javascript allows us to do dynamic programming which involves things like: doing calculations, responding to events, connecting to other devices, animation. When we change the appearance of a webpage with Javascript we are modifying the HTML in real time, while the user is on the page


### Prerequisites:

* Basic knowledge of HTML
    to do this tutorial you should know some HTML tags, like `<a></a>`, `<h1></h1>`, `<img src="<your source>"/>` etc
    Know how to layout an HTML document, as in what the `<head></head>` and `<body></body>` section are doing
* some knowledge of grouping HTML with classes and id's you do this in CSS to target specific bits of your HTML (this isn't essential as I'll explain it here but it's useful for this tutorial)
### Steps

#### 1. How does Javscript connect to and modify HTML?
Intuitive Answer: The browser has a series of prewritten functions (which for now you can think of as buttons) to find different things in your HTML and to then modify them. As in, javascript has methods for doing this built into the language. BUT to do this, your javascript needs to be attached to your HTML. This is done by linking to a Javascript script (a text document with your Javascript code in it)  

Technical Answer: The browser reads your HTML (the Document) and creates a series of Objects following the Document Objects Model (DOM) which represents your webpage in javascript. Your javascript code then uses these objects from the Document by using commands like `document.getElementById()`

Lets now go through how to ensure your Javascript can access the HTML
The quickest way of getting a simple HTML page up in VSCode is to:
1. create a new html file. For example `index.html`
2. then type in `!` then the `enter key`
    * this will give you this code:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```
 * If you're using the Glitch IDE then copy and paste this code into an index.html file
 3. There are two ways main ways to use JS with HTML*:
    a. writing JS inline - ie. writing JS within your HTML document
    this is what the script tags do 
    ```
    <script>
    </script>
    ```
    https://www.w3schools.com/tags/tag_script.asp
    https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script

    b. writing your JS in a separate document and then linking to your JS script in your HTML
    We'll do this by:
        i. creating a new file in your file browser and naming it `script.js`
        ii. going into our HTML and then within the header typing
        ```
        <head>
            ...
            <script src="/script.js" defer></script>
        </head>
        ```
 *  you can also create websites using Web Frameworks like React, Vue and Svelte 

 4. lets now add some content to our HTML so it looks like this
    ```
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <h1>
            The Title
        </h1>
        <p> Paragraph </p>
        <p id="pick_me"> Pick this one to change! </p>
        <button id="button1">Click for change 1</button>
        <button onclick="change2">Click for change 2 </button>
    </body>
    </html>
    ```
5. now we're set up to start modifying our HTML with Javascript

#### 2. Accessing HTML Elements from JS
The core methods to access HTML elements are `document.getElementById(<your_element>)` or `document.getElementsByClassName(<your_class_name>)` or `document.getElementsByTagName(<your_tag_name>)`
Lets break this phrase in two:
`document` - in HTML the document phrase gets you your entire HTML (or, it gets you all of your document objects)
`.getElementById(<your_element_id>)` or `.getElementsByClassName(<your_class_name>)` or `.getElementsByTagName(<your_tag_name>)` - to find specific content within all the HTML content we need a search method. These are three options: `ids` `classes` and `tags`
* `ids` are unique tags we can add to HTML content
* `classes` are non-unique tags we can add to HTML content - they are re-usable
* `tags` are the types of HTML elements themselves. For example `<img />` is a tag and `<p></p>` is a tag 

Our process of accessing HTML elements from JS goes like this:
1. Decide what HTML elements we want to access. Decide if we just want to access one element or multiple. If we want to access `tags` then skip the next step
2. label our HTML elements with `id="<your_id>"` or `class="<your_class>"` if you do
3. Write javascript to target these HTML elements


Lets go through these now one by one

1. Deciding on HTML Elements
Lets say we want to:
a. change a specific bit of text
b. change an image