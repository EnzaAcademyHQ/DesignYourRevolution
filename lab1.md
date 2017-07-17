---
title: Lab 1: STEM with Enza Academy
---
## Lab 1

Introduction:
Today we will be reviewing basic concepts in HTML. We will dissect the components of an HTML page, discussing different elements & tags.

HTML pages are complete documents comprised of components called "elements". Every HTML page has elements. Think of it this way: in chemistry, matter is composed of core elements. Every piece of matter contain elements from the same base elements found in the periodic table. You can view web page elements as exhibiting the same functionality.

Just as every element on the periodic table has properties that make them unique, the same can be said about HTML elements. 

Every HTML page has encapsulating tags; meaning that the tag begins, content is added within the tag, and the tag is closed off with a matching tag. For example, every HTML page has "master" HTML tags, with an opening `<html>` tag, and ending with a closing `</html>` tag. The tags are simply composed of: a less-than sign, the name of the tag, and a greater-than sign. The HTML tag simply has 'html' between the less-than & greater-than signs as its tag. This is how the interpreter knows the document is HTML.

```html
<html>
</html>
```

Notice the similarities and differences between the opening and closing tags? They are exactly the same with the exception of an extra "/" after the closing tag's less-than(<) sign.

Every part of the HTML page's content is enclosed within some nested tag of the HTML document. Because of this, when we add more content to the page, we must use the proper tags for the content we're adding. 

The next section of the HTML document is the `<head></head>` tags. Content within these tags contain identifying information about the document, such as titles, descriptions, and other types of data. This information is NOT seen on the user's end, but tools such as search engines and web crawlers use it to properly understand the document. For example, when you see a page in Google results, there is usually a title and description. This is simply the information that was defined in the document's title and description tags.

We will now add `<head>` tags to our working document. Our document should now look like:
```html
<html>
  <head></head>
</html>
```

Let's add our first piece of data to this page, which is the title. As you may have guessed, we need `<title></title>` tags to do this. Add your title within the `<head>` tags of the page.

This gives us:
```html
<html>
  <head>
    <title>Mikos's Awesome Quizzer Tool</title>
  </head>
</html>
```

This gives us something to display to browser tabs and search engine results. Remember, we have not yet added anything we can see on the user side, so this title will not be displayed on the screen.
  
The next tags we will add for the tool we are building are `<body>` tags. The body tags simply tell the HTML interpreter that everything between the `<body></body>` tags is the body(better described as the content) of the page. Everything that we see displayed on an HTML page, such as images, paragraphs, and tables, is placed within the `<body>` tags.
  
If you haven't yet noticed, HTML tags are composed hierarchically. With our current code, we see that we have master `<html>` tags, a child `<head>` tag, which has a child `<title>` tag of its own. That being said, <head> and <body> are siblings -- where do you think this means the `<body>` tags are placed? Because they are siblings, `<head>` and `<body>` tags are hierchically on the same level. However, the `<head>` tags are always defined before the `<body>` tags. Let's add our `<body>` tags to our code:

```html
<html>
  <head>
    <title>Mikos's Awesome Quizzer Tool</title>
  </head>
  <body>
  </body>
</html>
```

Now that we have a section to hold the code we can actually see, we can now start adding visual elements to the page. The first thing we should do is tell the user what they are looking at. We can accomplish this by using elements called headings. This is not to be confused with the head elements. One is for the anatomy of the HTML document itself, and the other is for a visual component within the body of the document.

We will add a heading to our page telling the user the page will contain our quizzer tool. Heading tags are defined as `<h1>`. Did you notice the number after the letter? HTML has headings numbered up to 6 to indicate priority; the lower the number, the higher it is on the priority list. Try to experiment with headings in your editor space to see what each does:

```html
<h1>This is a heading 1</h1>
<h2>This is a heading 2</h2>
<h3>This is a heading 3</h3>
<h4>This is a heading 4</h4>
<h5>This is a heading 5</h5>
<h6>This is a heading 6</h6>
```
You do not need to keep the experimental code -- the purpose was to demonstrate the differences in the headings. We will keep our level 1 heading, and give our quizzer tool a title the user can see. Add the following heading line within your `<body>` tags:

```html
<h1>Mikos's Awesome Quizzer Tool</h1>
```
We have added our first piece of data the user can see. We are now at:
```html
<html>
  <head>
    <title>Mikos's Awesome Quizzer Tool</title>
  </head>
  <body>
    <h1>Mikos's Awesome Quizzer Tool</h1>
  </body>
</html>
```
The next thing we want to do is divide our HTML document into sections. First let's think about the sections we will need for our page:
<ul>
<li>A section for our quiz</li>
<li>A section for quiz feedback to display to the test-taker</li>
</ul>

How should we create these divisions in HTML? If you haven't guessed it yet, we have division tags for that:
`<div></div>`

Comments:
A quick note -- did you notice the line of text inside the `<html>` tags? This is called a "comment". Comments are pieces of code that is there for reference purposes, and is not seen on the user side or deciphered by the interpreter. These are usually used for informing other people looking at the code something the programmer thought was important or worth noting. In HTML, we define a comment with: less-than sign, an exclamation mark, 2 hyphens, and is closed off with 2 hyphens and a greater-than sign. Like HTML tags, these are how comment tags are defined.

