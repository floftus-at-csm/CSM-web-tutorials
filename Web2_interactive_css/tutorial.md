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
1. The first thing we need to do is create a css file to store our stylings. Go to the file browser in your IDE and either `right click->add file` or find the file simple. Then type in `style.css` and hit enter. You can also do this on the command line if you'd prefer. The linux and mac command to add a file is `touch <your_file_name>` so `touch style.css`
2. now we need to link to our css file in our HTML. Our HTML file is our central file that the browser runs, so if we want another file to do something we need to make a link to it. We'll do this by going to the `<head></head>` tags and adding a new line: `<link rel="stylesheet" href="/style.css" />`
    If you had named the .css file anything different to `style.css` then we'd need to adjust this line of code to reflect that name 
    now the folder structure should look like this:
    ```
    project_folder
    │   index.html
    │   style.css
    ```
3. now our CSS file should be linked. Lets prove that. 
    a. Go to your index.html file and in between the `<body></body>` tags add some header tags and title text:
    ```
    <h1>
    Keeping Up Appearances
    </h1>
    ```
    b. then in your css write:
    ```
    h1{
        colour: red;
    }
    ```
    c.
    Now, if you're on VSCode right click the `index.html` file and click `open with Live Server`. If this option doesn't come up go to the extensions panel and type in `Live Server` and install it.
    If you're on glitch go to the panel at the bottom right of the page and click `preview in new window`
    d. 
    Hopefully you can now see a blank page with some red header text!
4. Now lets add the text from the poem with no formatting:
    ```
        <p>
        i used to work for this fellow.<span>under
        him. with him, you know.</span><br><br>
        he was a pretty nice guy.
    
        <span>
        he was white,
        but </font></span>i knew him from the church. <span>this
        won’t make sense if you're thinking of my church <i>home</i>. there were no white people where i worshipped. we worked together at the board of the worldwide church. (the only place where we integrate.)</span>
        <br><br>
        </span><p>he was from a powerful family. <span>he was also married to this sister. we were supposed to think he was therefore
        on our side or, you know, at least interesting.</span><br><br>
    
        <p>so anyway, <span>(it’s
        best not to dwell on white people’s miscalculations in public, even in
        invisible parentheticals) </span>he showed me the ropes at work. he was a
        mentor to me. <span>the
        only thing was, showing me the ropes often meant we had to be off somewhere
        alone together. the strangest things would happen in these moments, the
        first of which was when he reached inside my blouse to adjust my bra strap.
        he walked away, leaving me standing in the middle of the office floor,
        thinking about the two separate occasions in which a male had, without
        invitation, reached for my bra. the first time, the other kid and i were
        both around twelve years old. it was a little strange, but i was okay with
        it. he was a friend. this time, it felt creepy. on the one hand, there
        was the age difference. this guy was at least twenty years older than me.
        </span>on the other hand, he was a peer.
        <br><br>
        <span>i was, after all, eighteen. an adult now.</span> maybe it’s just like that when you’re
        an adult.
        <br><br>
        <span>but
        then he turned around and came towards me: “oh, don’t think anything of
        that,” he said. “i have a wife and kid, i would never . . .” i don’t remember
        whether he let it trail off like that or i just stopped listening.</span>
        <br><br>
        i never said anything to him about this. <span>but
        of course i thought something of it. standing there, head pounding. there
        was the attempt to pull my thoughts together. looking at the faces of people
        now walking by or moving around in nearby rooms. busy in their cubicles.
        busy in the copy room. there was the desire to keep this from happening
        again, but bigger than that was the desire for this to be nothing.</span>
        <br><br>
        this <span>
        is a series of things i told myself i had forgotten:
        there</span> was <span>
        the
        chance he really meant nothing by it, wasn’t there?
        and if i just made sure my bra strap didn’t show
        again, there would be
        nothing to question, right? i could tell him about my
        discomfort and he
        could get better (and keep explaining how he meant
        nothing by it) or get
        worse. or i could act like it was nothing and things
        could get better (because
        nothing had happened) or get worse. worst case
        scenario: i could say stop
        and he could show himself to be as evil as i feared
        him to be. best case
        scenario: i could say nothing and nothing (else) would
        happen. i was an
        optimist.</span>
        <br><br>
    </p>
    ```
5. Now lets make this page interactive! If you've done everything right so far you should see all of the text in your browser. This doesn't look like Mendi Obadike's piece. To create the same effect as the piece we'll use hover states: 
    https://www.w3schools.com/cssref/sel_hover.php 
    https://developer.mozilla.org/en-US/docs/Web/CSS/:hover

    Hover states attach to a CSS class to allow us to change styles when the user hovers over something. In the code above we have one `<p>...</p>` tag that wraps around all of the text. 
    This means that all the text is paragraph text. Then, some of the text is in `<span>...</span>` tags. Check out what `<span></span>` tags do here: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span
    In short, they allow us to group chunks of text so we can give them different stylings.
    To prove this, lets go to our `style.css` file and change the style of our tags:
    ```
    span{
        color: rgb(150, 255, 0);
    }    
    ```
    note that there isn't a `.` before span. This is because we're targetting all instances of an HTML tag
    This should have changed the appearance of some of your text. Time to make this interactive with the `:hover` tag
    on the line below what we just added to your css add:
    ```
    span:hover{
        color: rgb(255,150,0);
    }
    ```

    Hopefully some of your text now changes colour when you hover over it! The colours I've chosen aren't correct as they don't hide the text.

    Task
    1. can you now complete this sketch and replicate Mendi Obadike's piece?
    2. Can you add a fade so it takes a little time for the text to appear? https://www.w3schools.com/css/css3_transitions.asp
    <!-- 3. Can you make an image appear when you hover over the image? Here's some guidance
        a. first we need to find an image and make it accessible. There are a few ways to do this
            i. go to google, find an image and `copy image address` - this is a URL where the image is hosted
            ii. upload the image to a CDN (Content Delivery Network) and then `copy the image address` - an easy one to use (RECOMMENDED) is glitch's CDN. Go to a glitch project and then `assets`. You can then drag and drop images in.
            iii. if you're using VSCode and don't want to use glitch then make a folder in the folder/directory your code is in and drop your image into this folder. Then right click on the image and click `copy relative path`
            ***NOTE*** you want your images to be lightweight for the web, as in low file sizes! Anything close to 1mb is too big in most circumstances - If your image is too big then you should compress your images. A really good compression app is `Squoosh` https://squoosh.app/ which runs in your browser
        b. Now we need to add the image to our html. Add an image tag to our html and paste in the iamge address you copied from step 3a into the src parameter:
        ```
        <body>
        ...
        <img src="<the path you copied>">
        </body>
        ```
        c. now lets add -->
