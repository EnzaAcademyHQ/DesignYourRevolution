---
title: Lab 1: STEM with Enza Academy
---
## Lab 1

**Introduction:
Today we will be reviewing basic concepts in HTML. We will dissect the components of an HTML page, discussing different elements & tags.**

Office hours for 7/17:
6:30p-7:30p, Room 328

HTML pages are documents comprised of components called "elements". Every HTML page has elements. 

Think of it this way: in chemistry, matter is composed of core elements. Every piece of matter contains elements from the same base elements found in the periodic table. You can view web page elements as exhibiting the same functionality.

Just as every element on the periodic table has properties that make them unique, the same can be said about HTML elements. 

Every HTML page has encapsulating tags; meaning that the tag begins, content is added within the tag, and the tag is closed off with a matching tag. For example, every HTML page has "master" HTML tags, with an opening `<html>` tag, and ending with a closing `</html>` tag. The tags are simply composed of: a less-than sign, the name of the tag, and a greater-than sign. The HTML tag simply has 'html' between the less-than & greater-than signs as its tag. This is how the interpreter knows the document is HTML.

```html
<html>
</html>
```

Notice the similarities and differences between the opening and closing tags? They are exactly the same with the exception of an extra "/" after the closing tag's less-than(<) sign.

Before we continue to the next step, it is a good idea for you, the developer, to know exactly what is happening in the code. Developers do this by adding comments to their code. Comments are pieces of code that are there for reference purposes, and are not seen on the user side or executed. These are usually used for informing other developers looking at the code of something the original developer thought was important to indicate. They can also be helpful for you to use if you step away from your code for a good length of time and return to it.

In HTML, we define a comment with: less-than sign(<), an exclamation mark(!), 2 hyphens(--), and is closed off with 2 hyphens(--) and a greater-than sign(>):
```html
<!-- This is a comment. -->
```
Let's practice creating comments in our editor:
```html
<!-- This is a comment. -->
<!-- I will add code here. -->
<!-- This page will soon have a quizzer tool on it. -->
```

From here on, we will be adding comments before each new line we create. Our HTML comments will be in the formats of "I will be adding a __[tag name]__ tag here." and "I will be adding a __[tag name]__ tag for __[tag's purpose]__.", whichever makes more sense for the line being commented about. This is to know exactly what we are doing every step of the way.

Go back and add a comment to your HTML page:
```html
<html>
<!-- I will be adding HTML elements here. -->
</html>
```

Every part of the HTML page's content is enclosed within some nested tag of the HTML document. Because of this, when we add more content to the page, we must use the proper tags for the content we're adding. 

The next section of the HTML document is the `<head></head>` tags. Content within these tags contain identifying information about the document, such as titles, descriptions, and other types of data. This information is NOT seen on the user's end, but tools such as search engines and web crawlers use it to properly understand the document. For example, when you see a page in Google results, there is usually a title and description. This is simply the information that was defined in the document's title and description tags.

We will now add `<head>` tags(with comments!) to our working document. Ensure your comments match indentation of the line in which you are commenting about. Remember that this will be nested between our `<html>` tags. Every time we nest an element, we should make our code easier to read and see the nested effects. This is done by indenting 4 spaces for each nested level. However, most code editors use the "Tab" key as a shortcut to do this. Our document should now look like:
```html
<html>
<!-- I will be adding HTML elements here. -->

  <!-- I will be adding a head tag. -->
  <head></head>
</html>
```

Let's add our first piece of data to this page, which is the title. As you may have guessed, we need `<title></title>` tags to do this. Add your title within the `<head>` tags of the page.

This gives us:
```html
<html>
<!-- I will be adding HTML elements here. -->

  <!-- I will be adding a head tag. -->
  <head>
  
    <!-- I will be adding a title tag. -->
    <title>Mikos's Awesome Quizzer Tool</title>
  </head>
</html>
```

This gives us something to display to browser tabs and search engine results. Remember, we have not yet added anything we can see on the user side, so this title will not be displayed on the screen.
  
The next tags we will add for the tool we are building are `<body>` tags. The body tags simply tell the HTML interpreter that everything between the `<body></body>` tags is the body(better described as the content) of the page. Everything that we see displayed on an HTML page, such as images, paragraphs, and tables, is placed within the `<body>` tags.
  
If you haven't yet noticed, HTML tags are composed hierarchically. With our current code, we see that we have master `<html>` tags, a child `<head>` tag, which has a child `<title>` tag of its own. That being said, <head> and <body> are siblings -- where do you think this means the `<body>` tags are placed? Because they are siblings, `<head>` and `<body>` tags are hierchically on the same level. However, the `<head>` tags are always defined before the `<body>` tags. Let's add our `<body>` tags to our code:

```html
<html>
<!-- I will be adding HTML elements here. -->

  <!-- I will be adding a head tag. -->
  <head>
  
    <!-- I will be adding a title tag. -->
    <title>Mikos's Awesome Quizzer Tool</title>
  </head>
  
  <!-- I will be adding a body tag. -->
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
<!-- I will be adding HTML elements here. -->

  <!-- I will be adding a head tag. -->
  <head>
  
    <!-- I will be adding a title tag. -->
    <title>Mikos's Awesome Quizzer Tool</title>
  </head>
  
  <!-- I will be adding a body tag. -->
  <body>
  
    <!-- I will be adding an h1 tag for my quizzer's heading. -->
    <h1>Mikos's Awesome Quizzer Tool</h1>
  </body>
</html>
```
The next thing we want to do is divide our HTML document into sections. First let's think about the sections we will need for our page:
<ul>
<li>A main section for our quiz</li>
<li>A section for quiz feedback to display to the test-taker</li>
</ul>

How should we create these divisions in HTML? If you haven't guessed it yet, we have division tags for that:
`<div></div>`

We established earlier that we need 2 divisions for the page, meaning we will be creating 2 sets of div tags. Before we create the tags, let's make sense of where they should go. 

If there is a main section in which the quiz-related content goes, and because the feedback is quiz-related, feedback should be within the main section. One set of div tags should be nested within the other:

```html
<div>
  <div></div>
</div>
```

Add this nested div section to your working code and it should appear as:
```html
<html>
<!-- I will be adding HTML elements here. -->

  <!-- I will be adding a head tag. -->
  <head>
  
    <!-- I will be adding a title tag. -->
    <title>Mikos's Awesome Quizzer Tool</title>
  </head>
  
  <!-- I will be adding a body tag. -->
  <body>
  
    <!-- I will be adding an h1 tag for my quizzer's heading. -->
    <h1>Mikos's Awesome Quizzer Tool</h1>
    
    <!-- I will be adding a div tag for the main quiz section. -->
    <div>
    
      <!-- I will be adding a div tag for quiz result feedback. -->
      <div></div>
    </div>
  </body>
</html>
```

That makes sense, right? Sure, but the only problem is identifying which div is for what. This might not be a problem to leave it as is initially, but what if we want to specifically manipulate the feedback division without manipulating the main quiz division? We need a way to identify these divisions.

We can do this by adding a property to the div elements themselves. This is done by defining the identifier(id) on the opening div tag itself:
```html
<div id="our_unique_identifier">

</div>
```

Now that we know how to add identifiers, let's add them to our ambiguous `<div>` tags to get:
```html
<html>
<!-- I will be adding HTML elements here. -->

  <!-- I will be adding a head tag. -->
  <head>
  
    <!-- I will be adding a title tag. -->
    <title>Mikos's Awesome Quizzer Tool</title>
  </head>
  
  <!-- I will be adding a body tag. -->
  <body>
  
    <!-- I will be adding an h1 tag for my quizzer's heading. -->
    <h1>Mikos's Awesome Quizzer Tool</h1>
    
    <!-- I will be adding a div tag for the main quiz section. -->
    <div id="main_quiz_section">
    
      <!-- I will be adding a div tag for quiz result feedback. -->
      <div id="quiz_result_feedback_section"></div>
    </div>
  </body>
</html>
```

We are almost done with our core HTML page, with only 2 items missing from our initial quizzer tool: a form for our questions, and a button to start the quizzer. 

Yes, HTML has elements for forms and buttons! They follow the same convention as the other tags we've learned:
`<form>` and `<button>` respectively. 

We are using a form because the quiz is simply a form full of questions to be submitted. Where should the <form> go might you ask? We know it goes somewhere within the main quiz section, but should it go before or after the feedback?

When you take a quiz, you will likely scroll to the bottom of the question list to submit your answers -- therefore it makes sense to place the form before the feedback section. This way, you will see the results feedback at the end of the quiz after it is submitted.

Let's insert our `<form>` element before our feedback section:
```html
<html>
<!-- I will be adding HTML elements here. -->

  <!-- I will be adding a head tag. -->
  <head>
  
    <!-- I will be adding a title tag. -->
    <title>Mikos's Awesome Quizzer Tool</title>
  </head>
  
  <!-- I will be adding a body tag. -->
  <body>
  
    <!-- I will be adding an h1 tag for my quizzer's heading. -->
    <h1>Mikos's Awesome Quizzer Tool</h1>
    
    <!-- I will be adding a div tag for the main quiz section. -->
    <div id="main_quiz_section">
    
      <!-- I will be adding a form tag for quiz questions. -->
      <form></form>
      
      <!-- I will be adding a div tag for quiz result feedback. -->
      <div id="quiz_result_feedback_section"></div>
    </div>
  </body>
</html>
```

We will add an id property to our form so that we can identify its purpose:
```html
<html>
<!-- I will be adding HTML elements here. -->

  <!-- I will be adding a head tag. -->
  <head>
  
    <!-- I will be adding a title tag. -->
    <title>Mikos's Awesome Quizzer Tool</title>
  </head>
  
  <!-- I will be adding a body tag. -->
  <body>
  
    <!-- I will be adding an h1 tag for my quizzer's heading. -->
    <h1>Mikos's Awesome Quizzer Tool</h1>
    
    <!-- I will be adding a div tag for the main quiz section. -->
    <div id="main_quiz_section">
    
      <!-- I will be adding a form tag for quiz questions. -->
      <form id="questions_form"></form>
      
      <!-- I will be adding a div tag for quiz result feedback. -->
      <div id="quiz_result_feedback_section"></div>
    </div>
  </body>
</html>
```

Our last step for today will be adding the button to start the quiz. First, let's experiment with the way a button works by creating a couple of buttons:

```html
<button>Test Button 1</button>
<button>Test Button 2</button>
<button>Test Button 3</button>
<button>Test Button 4</button>
```

Now that we see how simple it is to create buttons, we are ready to add one to our code. Where should this button go? Because the button to start the quiz cannot be a part of the quiz itself, we will place it outside of the main quiz section:

```html
<html>
<!-- I will be adding HTML elements here. -->

  <!-- I will be adding a head tag. -->
  <head>
  
    <!-- I will be adding a title tag. -->
    <title>Mikos's Awesome Quizzer Tool</title>
  </head>
  
  <!-- I will be adding a body tag. -->
  <body>
  
    <!-- I will be adding an h1 tag for my quizzer's heading. -->
    <h1>Mikos's Awesome Quizzer Tool</h1>
    
    <!-- I will be adding a div tag for the main quiz section. -->
    <div id="main_quiz_section">
    
      <!-- I will be adding a form tag for quiz questions. -->
      <form id="questions_form"></form>
      
      <!-- I will be adding a div tag for quiz result feedback. -->
      <div id="quiz_result_feedback_section"></div>
    </div>
    
    <!-- I will be adding a button to start the quiz. -->
    <button>Start Quiz</button>
  </body>
</html>
```

Voila! You have a basic skeleton of an HTML page with a heading, div sections, a form, and a button. This is all you need to house the quizzer on the HTML side. We will learn more about adding functionality to the button and introducing another language, JavaScript, to you in the next lab.

Feel free to Google concepts that you either you are having trouble with, or desire to learn more information about. A great website to use to learn more about the topics discussed in class:<br>
**https://www.w3schools.com/**
Simply go here, search a specific topic, and you'll find detailed exmplanations and examples of all the topics that were discussed today.


Instructor contact information can be found at the bottom of the lab for one-on-one questions.

Enza Instructors:
<ul>
<li>Mr. Jenkins: mjenkins@enzaacademy.org</li>
<li>Mr. Kyei: kkyei@enzaacademy.org</li>
<li>Mr. Kibret: nkibret@enzaacademy.org</li>
<li>Mr. Cudjoe: rcudjoe@enzaacademy.org</li>
</ul>
