# CSM Web Tutorials: 2. Interactive CSS
This tutorial will show you how to use Javascript to change the styling of a webpage. We'll then implement this learning to create a chrome pluging that makes all websites you go on glow

### Prerequisites
* understanding of the role of HTML as the structure of your website, CSS as the styling and positioning of elements on your website and Javascript as handling anything is dynamic (as in, changes)
* understanding of how we connect our CSS and JS files to our main HTML file through links in our HTML
* know how to use some CSS methods to modify the styling of HTML objects
Both of these are explained in the previous tutorial

### Structure
    1. create a blank HTML file and fill it with boilerplate code
    2. Attach a CSS file and a JS file to the HTML
    3. write some HTML and label it with classes so we can style it
    4. Style the HTML with our CSS
    5. create a javascript function that changes the stylings every 10 seconds
    6. Potential applications of this technique

### 1. create a blank HTML file and fill it with boilerplate code
a. This step is different depending on if you're using VSCode or Glitch.com. If using VSCode:

i. then open a new VSCode window and then `click open folder` 

ii. click new folder and make a name for your website

iii. come up to your file browser in VSCode and make a new file called `index.html`

iiii. open the file and type `!` then hit the `enter` key. This should give you some boilerplate HTML

b. If you're using Glitch.com then:

i. create a new blank project 

ii. create an index.html file and paste in
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

### 2. Attach a CSS file and a JS file to the HTML
a. Now in the file browser of your IDE (glitch/VSCode) find the `new file` button at the top and create a `style.css` and a `script.js` file

b. go back into your `index.html` file and add this code to the <b>header</b>:
```
    <link rel="stylesheet" href="/style.css" />

    <script src="/script.js" defer></script>
```
### 3. write some HTML and label it with classes so we can style it

Add this text in between the `<body></body>` tags in your HTML page


    <div class="content" role="main">
        <h1 class="title">Hello World!</h1>
        <img
            src="https://cdn.glitch.com/a9975ea6-8949-4bab-addb-8a95021dc2da%2Fillustration.svg?v=1618177344016"
            class="illustration"
            alt="Editor illustration"
            title="Sample Image"
        />
        <div class="instructions">
            <h2>This is a smaller header</h2>
            <p>
            This is some body text
            </p>
        </div>
        <p >this is some<span id="specialText">special</span>text</p>
    </div>
* the first div is labelled with a `class` tag called `content`. Classes are <b>resuable tags</b>. We'll use to keep our content flowing downwards with a specific width.
* The header is labelled with a `class` tag called `title` which we'll use to set the font, size, and colour of the title
* the other type of label is an `id` which we use to tag unique parts of the page. 

### 4. Style Our HTML with CSS
Add this css to your `style.css` fille:
```
    .content {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    .title{
        font-size: 2rem;
        color: rgb(150, 200, 100);
    }
    p{
        color: red;
        transition: 5s;
    }
    #specialText{
        colour: blue;
    }
```
Note that:
* with `class`s we use a `.` to refer to the `class`
* with `id`s we use a `#` to refer to the id tag
* with `tag`s we just use write the `tag` name like `h1` to refer to the tag

### 5. create a javascript function that changes the stylings every 10 seconds
We'll be using a Javascript `setTimeout()` function to create a loop that makes a style change every 10 seconds
Some more information about the `setTimeout()` function can be found here:
https://developer.mozilla.org/en-US/docs/Web/API/setTimeout

Go into your `script.js` file and add this:
function changeText() {

    vaz textElements = document.getElementByTagName("p");
    for(let i =0; i< textElements.length-1; i++){
        textElements.style.
    }
    setTimeout(changeText, 5000);
}

changeText();
