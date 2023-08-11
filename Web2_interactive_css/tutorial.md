# CSM Web Tutorials: 2. Interactive CSS
This tutorial will show you how to use css to make some simple interactions around hovering and clicking.
We'll do this by building a version of Mendi Lewis Obakie's net-art piece "keeping up appearances"
So, to start, have a look at the piece:
https://webenact.rhizome.org/keeping-up-appearances/20151029152713/http://blacknetart.com/keepingupappearances.html
As you move your mouse around the page, text appears that was previously hidden, revealing the writer's inner monologue.  
The core functionality here is a hover effect which utilises the css
`:hover` class
https://developer.mozilla.org/en-US/docs/Web/CSS/:hover

## Step 1: HTML
to be able to achieve this effect we'll first need some HTML
I'll be working in VSCode but you could easily be using the Glitch IDE. The quickest way of getting a simple HTML page up in VSCode is to:
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

3. Now lets add some text:
    * inside the body tags add some paragraph text using the `<p></p>` tags:
    ```
    <body>
        <p>this is the text I want to show this is the text I want to hide</p>
    </body>
    ```
    * we could have used any other HTML text tags likee `h1` or `h2` - https://www.w3schools.com/html/html_headings.asp -  https://www.w3schools.com/html/html_paragraphs.asp - https://www.w3schools.com/html/html_formatting.asp 
    * Now lets move onto the CSS

## Step 2: CSS
CSS is used to style our HTML content. It adds the colours, fonts, sizings and some of the simple interactive elements. We can write CSS `inline` which means creating a html tag called a style tag. e.g. `<style>your CSS </style>`. However, generally we'll keep our CSS separate to our HTML to keep things neater. If you're
1. The first thing we need to do is create a css file to store our stylings 
