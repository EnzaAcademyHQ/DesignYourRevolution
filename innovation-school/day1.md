---
title: Day 1: Innovation School with Enza Academy
---
## Day 1

**Introduction:
Today we will learn basic concepts of HTML. We will dissect the components of an HTML page, discussing different elements & tags.**

HTML pages are documents comprised of components called "elements". Every HTML page has elements. 
  
Think of it this way: in chemistry, matter is composed of core elements. Every piece of matter contains elements from the same base elements found in the periodic table. You can view web page elements as exhibiting the same functionality.

Just as every element on the periodic table has properties that make them unique, the same can be said about HTML elements. 

Every HTML page has encapsulating tags; meaning that the tag begins, content is added within the tag, and the tag is closed off with a matching tag. For example, every HTML page has "master" HTML tags, with an opening `<html>` tag, and ending with a closing `</html>` tag. The tags are simply composed of: a less-than sign, the name of the tag, and a greater-than sign. The HTML tag simply has 'html' between the less-than & greater-than signs as its tag. This is how the interpreter knows the document is HTML.

```html
<html>
</html>
```

Notice the similarities and differences between the opening and closing tags? They are exactly the same except for an extra "/" after the closing tag's less-than(<) sign.


Every part of the HTML page's content is enclosed within some nested tag of the HTML document. Because of this, when we add more content to the page, we must use the proper tags for the content we're adding. 

The next section of the HTML document is the `<head></head>` tags. Content within these tags contain identifying information about the document, such as titles, descriptions, and other types of data. This information is NOT seen on the user's end, but tools such as search engines and web crawlers use it to properly understand the document. For example, when you see a page in Google results, there is usually a title and description. This is simply the information that was defined in the document's title and description tags.

We will now add `<head>` tags(with comments!) to our working document. Ensure your comments match indentation of the line in which you are commenting about. Remember that this will be nested between our `<html>` tags. Every time we nest an element, we should make our code easier to read and see the nested effects. This is done by indenting 4 spaces for each nested level. However, most code editors use the "Tab" key as a shortcut to do this. Our document should now look like:
```html
<html>
  <head></head>
</html>
```

Let's add our first piece of data to this page, which is the title. As you may have guessed, we need `<title></title>` tags to do this. Add the title of your project within the `<head>` tags of the page.

This gives us:
```html
<html>
  <head>
    <title>My Awesome App Idea</title>
  </head>
</html>
```

This gives us something to display to browser tabs and search engine results. Remember, we have not yet added anything we can see on the user side, so this title will not be displayed on the screen.
  
The next tags we will add for the tool we are building are `<body>` tags. The body tags simply tell the HTML interpreter that everything between the `<body></body>` tags is the body(better described as the content) of the page. Everything that we see displayed on an HTML page, such as images, paragraphs, and tables, is placed within the `<body>` tags.
  
If you haven't yet noticed, HTML tags are composed hierarchically. With our current code, we see that we have master `<html>` tags, a child `<head>` tag, which has a child `<title>` tag of its own. That being said, <head> and <body> are siblings -- where do you think this means the `<body>` tags are placed? Because they are siblings, `<head>` and `<body>` tags are hierarchically on the same level. However, the `<head>` tags are always defined before the `<body>` tags. Let's add our `<body>` tags to our code:

```html
<html>
  <head>
    <title>My Awesome App Idea</title>
  </head>
  <body>
  </body>
</html>
```

Now that we have a section to hold the code we can actually see, we can now start adding visual elements to the page. Let's start by adding our navigation menu.

Our menu will be a list of our pages we will have on our site. For starters, let's just create a simple site with 3 pages: home, about us, and team. To put our list into HTML code, HTML has a tag for 2 types of lists: ordered(numbered, `<ol></ol>`) and unordered(not numbered, `<ul></ul>`). Because we will not be numbering our links, we will use unordered lists. Create a list of menu links directly under the body tag:
```html
<ul>
<li>Home</li>
<li>About Us</li>
<li>Team</li>
</ul>
```

Our code should now look like:
```html
<html>
  <head>
    <title>My Awesome App Idea</title>
  </head>
  <body>
    <ul>
      <li>Home</li>
      <li>About Us</li>
      <li>Team</li>
    </ul>
  </body>
</html>
```

Don't worry about formatting your menu at this moment, we will get to that soon enough. But let's divide our main webpage into 3 sections: one for each of our links.

How should we create these divisions in HTML? If you haven't guessed it yet, we have division tags for that:
`<div></div>`

We established earlier that we need 3 divisions for the page, meaning we will be creating 3 sets of div tags. Create these tags AFTER the `<ul>` tags, but before the closing `</body>` tag:
```html
<html>
  <head>
    <title>My Awesome App Idea</title>
  </head>
  <body>
    <ul>
      <li>Home</li>
      <li>About Us</li>
      <li>Team</li>
    </ul>
    <div></div>
    <div></div>
    <div></div>
  </body>
</html>
```
Now the only problem is <b>identifying</b> which div is for what. Because we are using multiple pages, we need to identify each page.

We can do this by adding a property to the div elements themselves. This is done by defining the identifier(id) on the opening div tag itself:
```html
<div id="your_unique_identifier">

</div>
```

Now that we know how to add identifiers, let's add them to our ambiguous `<div>` tags to get:
```html
<html>
  <head>
    <title>My Awesome App Idea</title>
  </head>
  <body>
    <ul>
      <li>Home</li>
      <li>About Us</li>
      <li>Team</li>
    </ul>
    <div id="home"></div>
    <div id="about-us"></div>
    <div id="team"></div>
  </body>
</html>
```

We now have our pages in their own sections, so let's inform the user of each section they are looking at. We can accomplish this by using elements called headings. This is not to be confused with the head elements. One is for the anatomy of the HTML document itself, and the other is for a visual component within the body of the document.

We will add headings to our page sections, telling the user which page is which. Heading tags are defined as `<h1>`. Did you notice the number after the letter? HTML has headings numbered up to 6 to indicate priority; the lower the number, the higher it is on the priority list. Try to experiment with headings in your editor space to see what each does:

```html
<h1>This is a heading 1</h1>
<h2>This is a heading 2</h2>
<h3>This is a heading 3</h3>
<h4>This is a heading 4</h4>
<h5>This is a heading 5</h5>
<h6>This is a heading 6</h6>
```

You do not need to keep the experimental code -- the purpose was to demonstrate the differences in the headings. We will keep our level 1 heading, and give each page its own title. Add a set of `<h1></h1>` tags directly after each page `<div>`:
```html
<html>
  <head>
    <title>My Awesome App Idea</title>
  </head>
  <body>
    <ul>
      <li>Home</li>
      <li>About Us</li>
      <li>Team</li>
    </ul>
    <div id="home">
      <h1>Home</h1>
    </div>
    <div id="about-us">
      <h1>About Us</h1>
    </div>
    <div id="team">
      <h1>Team</h1>
    </div>
  </body>
</html>
```

Let's now add a paragraph to each page for more content. Paragraphs use `<p>` tags, so simply add the paragraph content within embedded `<p>` tags within the page section div:
```html
<html>
  <head>
    <title>My Awesome App Idea</title>
  </head>
  <body>
    <ul>
      <li>Home</li>
      <li>About Us</li>
      <li>Team</li>
    </ul>
    <div id="home">
      <h1>Home</h1>
      <p>Welcome to My Awesome App Idea!</p>
    </div>
    <div id="about-us">
      <h1>About Us</h1>
      <p>We need some really nice things!</p>
    </div>
    <div id="team">
      <h1>Team</h1>
      <p>We have a really big team!</p>
    </div>
  </body>
</html>
```
We will now go on to the aesthetics of the page, CSS(Cascading Style Sheets). CSS is used to make your page unique by altering the appearance: adding colors, changing font sizes, paragraph spacing, etc. It is the primary language for styling in web development.

We have our HTML, so let's start adding our CSS code. First, give your a minimum height of 500px:
```css
#home{
  min-height: 500px;
}
#about-us{
  min-height: 500px;
}
#team{
  min-height: 500px;
}
```

Notice how much more space we have between our pages now? In CSS, we give an element we want to style, and place the style inside curly braces `{}`. We use a hashtag(#) to indicate we want to style an element with a specific id. Because our pages have unique ids, we simply use a hashtag before the exact id name we gave the element.

We have our pages, but our top navigation bar doesn't work to click to the page sections. First we need to make our navigation links clickable, and we do this by adding `<a></a>` tags to them. When we create `<a>` tags, we usually give it a link as well to go to. Since we have a single page, we will navigate to sections instead of other pages. To add a link, we need to add an `href` property to our `<a>` tags. Add the `href` property the same way you added the id, and give it the id's name you desire the link navigates to. For example, to have the "Home" link navigate to the "home" section, add the "#home" id to the `href` value:
```html
<li><a href="#home">Home</a></li>
```
See how we kept the hashtag the same way we did in CSS? HTML also recognizes ids with the hashtag symbol. Continue adding `<a>` tags for your other links:


Go back and add `<a>` tags to all menu links so they look like this:
```html
<html>
  <head>
    <title>My Awesome App Idea</title>
  </head>
  <body>
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#about-us">About Us</a></li>
      <li><a href="#team">Team</a></li>
    </ul>
    <div id="home">
      <h1>Home</h1>
      <p>Welcome to My Awesome App Idea!</p>
    </div>
    <div id="about-us">
      <h1>About Us</h1>
      <p>We need some really nice things!</p>
    </div>
    <div id="team">
      <h1>Team</h1>
      <p>We have a really big team!</p>
    </div>
  </body>
</html>
```

Our links are now clickable, but our menu doesn't hang around after we click a link. We need to find a way to make our navigation menu stay in place. We need to add CSS rules for this. Distinguish your menu by giving it an id with a name of "top-menu":
```html
<ul id="top-menu">
  <li><a href="#home">Home</a></li>
  <li><a href="#about-us">About Us</a></li>
  <li><a href="#team">Team</a></li>
</ul>
```

Now that we have an id for our menu, add a CSS rule to it:
```css
#top-menu{
  position: fixed;
}
```
You should keep your CSS rules in the order of which they appear on your page, so this rule goes to the top. Your CSS file should now look like:
```css
#top-menu{
  position: fixed;
}
#home{
  min-height: 500px;
}
#about-us{
  min-height: 500px;
}
#team{
  min-height: 500px;
}
```

Our menu sticks, but it is not attractive at all. Format your menu links by first making the list elements appear in one line. Do this by adding a `display: inline;` rule to them. Add this after the main `#top-menu` rule:
```css
#top-menu li{
  display: inline;
}
```

See how we named 2 elements before the curly braces this time? We can do this in CSS when you have nested elements. The `<li>` elements are nested within the `#top-menu` id, so we simply place the elements in its nested order to be specific in CSS. We only want the `<li>` elements in the #top-menu id to have this rule, so we must indicate it.

We want to remove the ugly underlined property of the menu links, so we need to add another rule for the nested `<a>` tags. Because this is nested both #top-menu and li elements, we will name 3 elements in our CSS rule. Add a `text-decoration:none;` rule after the last li rule:
```css
#top-menu li a{
  text-decoration: none;
}
```
Your CSS should now look like:
```css
#top-menu{
  position: fixed;
}
#top-menu li{
  display: inline;
}
#top-menu li a{
  text-decoration: none;
}
#home{
  min-height: 500px;
}
#about-us{
  min-height: 500px;
}
#team{
  min-height: 500px;
}
```
Add a background color, a height of 30px, and width of 100% to the `#top-menu` rule to stretch it across the entire page:
```css
#top-menu{
  position: fixed;
  background-color: black;
  height: 30px;
  width: 100%;
}
```

We have extra space from margins and padding that shouldn't be there, so remove it with an all(*) rule at the top of the CSS file:
```css
* {
  padding: 0px;
  margin: 0px;
}
```

Your CSS should now be:
```css
*{
  padding: 0px;
  margin: 0px;
}
#top-menu{
  position: fixed;
  background-color: black;
  height: 30px;
  width: 100%;
}
#top-menu li{
  display: inline;
}
#top-menu li a{
  text-decoration: none;
}

#home{
  min-height: 500px;
}
#about-us{
  min-height: 500px;
}
#team{
  min-height: 500px;
}
```

Our pages are, for the most part, set up; it's just a matter of adding padding to the top of the pages so we can see the titles. Add a `padding-top: 50px;` rule to each of your pages:
```css
#home{
  min-height: 500px;
  padding-top: 50px;
}
#about-us{
  min-height: 500px;
  padding-top: 50px;
}
#team{
  min-height: 500px;
  padding-top: 50px;
}
```

Clean up your menu's appearance by changing the font color of the links:
```css
#top-menu li a{
  color: white;
  text-decoration: none;
}
```

And then adding padding of 10px along the top & 20px along the left sides:
```css
#top-menu{
  position: fixed;
  background-color: black;
  height: 30px;
  width: 100%;
  padding-top: 10px;
  padding-left: 20px;
}
```

Space your links out a bit more by adding a `margin-right` rule to the `#top-menu li` ruleset:
```css
#top-menu li{
  display: inline;
  margin-right: 20px;
}
```
Your CSS is now:
```css
*{
  padding: 0px;
  margin: 0px;
}

#top-menu{
  position: fixed;
  background-color: black;
  height: 30px;
  width: 100%;
  padding-top: 10px;
  padding-left: 20px;
}
#top-menu li{
  display: inline;
  margin-right: 20px;
}
#top-menu li a{
  color: white;
  text-decoration: none;
}

#home{
  min-height: 500px;
  padding-top: 50px;
}
#about-us{
  min-height: 500px;
  padding-top: 50px;
}
#team{
  min-height: 500px;
  padding-top: 50px;
}
```

Play with the spacing until it meets your team's visual tastes.

You now have a basic first page for your project's landing page. You can now focus on adding content to each of the sections, along with thinking of more elements to add to it. We will show you how to implement adding images to your sites in the future, in case you want to add things such as team photos.

Feel free to Google concepts that you either you are having trouble with, or desire to learn more information about. A great website to use to learn more about the topics discussed in class:<br>
**https://www.w3schools.com/**
<br>
Simply go here, search a specific topic, and you'll find detailed explanations and examples of all the topics that were discussed today.

Instructor contact information can be found at the bottom of the lab for one-on-one questions.

Team Enza:
<ul>
<li>Mr. Jenkins: mjenkins@enzaacademy.org</li>
<li>Mr. Kyei: kkyei@enzaacademy.org</li>
<li>Mr. Kibret: nkibret@enzaacademy.org</li>
<li>Mr. Cudjoe: rcudjoe@enzaacademy.org</li>
</ul>
