---
title: HTML & CSS I
---

**Introduction:
We will learn basic HTML & CSS to create a basic landing page for your project. We will dissect the components of an HTML page, discussing different elements & tags.**

HTML pages are documents comprised of components called "elements". Every HTML page has elements. 

Think of this: in chemistry, matter is composed of elements. Every piece of matter contains elements from the periodic table. You can view web page elements as exhibiting the same functionality.

Just as every element on the periodic table has properties that make them unique, the same can be said about HTML elements. 

Every HTML page has encapsulating tags; meaning that the tag begins, content is added within the tag, and the tag is closed off with a matching tag. For example, every HTML page has "master" HTML tags, with an opening `<html>` tag, and ending with a closing `</html>` tag. The tags are simply composed of: a less-than sign, the name of the tag, and a greater-than sign. The HTML tag simply has 'html' between the less-than & greater-than signs as its tag. This is how the interpreter knows the document is HTML.

```html
<html>
</html>
```

Notice the similarities and differences between the opening and closing tags? They are exactly the same except for an extra "/" after the closing tag's less-than(<) sign.

Before we continue to the next step, it is a good idea for you, the developer, to know exactly what is happening in the code. Developers do this by adding comments to their code. Comments are pieces of code that are there for reference purposes, and are not seen on the user side or executed. These are usually used for informing other developers looking at the code of something the original developer thought was important to indicate. They can also be helpful for you to use if you step away from your code for a good length of time and return to it.

In HTML, we define a comment with: less-than sign(<), an exclamation mark(!), 2 hyphens(--), and is closed off with 2 hyphens(--) and a greater-than sign(>):
```html
<!-- This is a comment. -->
```
Let's practice creating comments in our editor:
```html
<!-- This is a comment. -->
<!-- I will add code here. -->
<!-- This will be a landing page. -->
```

We will be adding comments before each important section we create. This will help us know exactly what we are doing every step of the way.

Every part of the HTML page's content is enclosed within some nested tag of the HTML document. Because of this, when we add more content to the page, we must use the proper tags for the content we're adding. 

The next section of the HTML document is the `<head></head>` tags. Content within these tags contain identifying information about the document, such as titles, descriptions, and other types of data. This information is NOT seen on the user's end, but tools such as search engines and web crawlers use it to properly understand the document. For example, when you see a page in Google results, there is usually a title and description. This is the information defined in the code's title and description tags.

We will add `<head>` tags to our document. Ensure your comments match indentation of the line in which you are commenting about. Remember that this will be nested between our `<html>` tags. Every time we nest an element, we should make our code easier to read and see the nested effects. This is done by indenting 4 spaces for each nested level. However, most code editors use the "Tab" key as a shortcut to do this. Our document should now look like:
```html
<html>
  <!-- creating head tag-->
  <head></head>
</html>
```

Let's add our first piece of data to this page, which is the title. As you may have guessed, we need `<title></title>` tags to do this. Add your title within the `<head>` tags of the page.

This gives us:
```html
<html>
  <!-- creating head tag-->
  <head>
    <title>[Project name]</title>
  </head>
</html>
```

This gives us something to display to browser tabs and search engine results. Remember, we have not yet added anything we can see on the user side, so this title will not be displayed on the screen.
  
The next tags we will add for the tool we are building are `<body>` tags. The body tags simply tell the HTML interpreter that everything between the `<body></body>` tags is the content of the page. Everything we see displayed on an HTML page, such as images, paragraphs, and tables, is placed within the `<body>` tags.
  
HTML tags are composed hierarchically. With our current code, we see that we have master `<html>` tags, a child `<head>` tag, which has a child `<title>` tag of its own. That being said, <head> and <body> are siblings -- where do you think this means the `<body>` tags are placed? Because they are siblings, `<head>` and `<body>` tags are hierarchically on the same level. However, the `<head>` tags are always defined before the `<body>` tags. Let's add our `<body>` tags to our code:

```html
<html>
  <!-- creating head tag-->
  <head>
    <title>[Project name]</title>
  </head>
  
  <!-- creating body tag -->
  <body>
  </body>
</html>
```

Now that we have a section to hold the code we can actually see, we can now start adding visual elements to the page. The first thing we should do is add our menu. A menu is simply a list of links, so we need to add list tags. Page menus aren't numbered, so we will use unordered list tags(<ul>). If we want numbered lists, we use ordered list(<ol>) tags. Our menu will have 4 links to start, so let's create it after the body tag, with each element enclosed within a list(<li>) tag. :

```html
<html>
  <!-- creating head tag-->
  <head>
    <title>[Project name]</title>
  </head>
  
  <!-- creating body tag -->
  <body>
    <!-- creating a menu list -->
    <ul>
      <li>Home</li>
      <li>About</li>
      <li>Team</li>
      <li>Contact</li>
    </ul>
  </body>
</html>
```

In the end, you may want to add more pages, but this is the bare minimum required for your projects.

Our links need to be clickable, so we need to surround them with 'a' tags. You'll see how this works later. Surround each link with an 'a' tag:
```html
<ul>
  <li><a>Home</a></li>
  <li><a>About</a></li>
  <li><a>Team</a></li>
  <li><a>Contact</a></li>
</ul>
```
Our menu still does nothing we can see yet, but we will come back to this after we create our page sections. 


Creating Page Wrapper
======

The next step is to create a page wrapper, which "wraps" the content within its own section, aside from the menu and rest of the page. This is done by using division, or div, tags. Div tags need differentiation, so usually a class or id is attached to it to do this. They are functionally the same, but are used differently. IDs are only used once, while classes can be used more than once. Since we will ony have one page wrapper, an id is appropriate here. You will see the difference when you use classes later. To attach an id or class to a tag, simply type the type and value within the opening tag. You can name your ids and classes as you like, they just need to be consistent in CSS. Create a page wrapper div after the menu list with an id of "page-wrapper":

```html
<html>
  <!-- creating head tag-->
  <head>
    <title>[Project name]</title>
  </head>
  <!-- creating body tag -->
  <body>
    <!-- creating a menu list -->
    <ul>
      <li><a>Home</a></li>
      <li><a>About</a></li>
      <li><a>Team</a></li>
      <li><a>Contact</a></li>
    </ul>
    <!-- creating wrapper for entire page -->
    <div id="page-wrapper">
    </div>
  </body>
</html>
```

Creating Page Sections
======
We are ready to create our page sections now. Our first section is the home section, so create a div with an id of "home" within the page wrapper div. Don't forget to properly indent and close your tags:
```html
<div id="page-wrapper">
  <div id="home"></div>
</div>
```

Let's finish creating our other sections while we're at it. Put space between each section so it is less confusing when building pages:
```html
<div id="page-wrapper">
  <div id="home"></div>
  
  
  <div id="about"></div>
  
  
  <div id="team"></div>
  
  
  <div id="contact"></div>
</div>
```

Adding Page Section Content
======
Let's start adding to our section. Add headings using the h1 tag for each respective section. Your home section heading will simply be the name of your project:
```html
  <div id="home">
    <h1>[Project Name]</h1>
  </div>
  
  
  <div id="about">
    <h1>About</h1>
  </div>
  
  
  <div id="team">
    <h1>Team</h1>
  </div>
  
  
  <div id="contact">
    <h1>Contact</h1>
  </div>
```


We need our list to stand out as a menu instead of a plain list, so we give it an "id" to do so. Simply type the word "id" within the opening ul tag and name it "top-menu". You can name it whatever you'd like, as long as it is consistent on th CSS side. We will use "top-menu" as the name here.
```html
    <!-- creating a menu list -->
    <ul <mark>id="top-menu"</mark>>
      <li>Home</a>
      <li>About</a>
      <li>Team</a>
      <li>Contact</a>
      </li>
    </ul>
```


We need to create individual sections within our wrapper for each page section, and we do this in a similar fashion. Because we have 4 page sections, we will be using a class for them instead of ids:


tell the user what they are looking at. We can accomplish this by using elements called headings. This is not to be confused with the head elements. One is for the anatomy of the HTML document itself, and the other is for a visual component within the body of the document.

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

Your HTML page should now look like this:

```html
<html>
  <!-- creating head tag-->
  <head>
    <title>[Project name]</title>
  </head>
  <!-- creating body tag -->
  <body>
    <!-- creating a menu list -->
    <ul id="top-menu">
      <li><a href="#home">Home</a>
      <li><a href="#about">About</a>
      <li><a href="#team">Team</a>
      <li><a href="#contact">Contact</a>
      </li>
    </ul>
    <!-- creating wrapper for entire page -->
    <div id="page-wrapper">
      <!-- creating divs for each page section -->
      <div id="home" class="page-section">
        <h1>[Project name]</h1>
        <p>[Project information & where app will be located]</p>
      </div>
      <div id="about" class="page-section">
        <h1>About</h1>
        <p>[Project's mission]</p>
      </div>
      <div id="team" class="page-section">
        <h1>Team</h1>
        <p>Here is our wonderful team!</p>
        <!-- creating a div for team members row -->
        <div id="team-members">
          <!-- creating a div for each team member -->
          <div class="team-member">
            <img class="team-member-photo" src="[Member photo link]" />
            <br><span class="team-member-title">[Member title]</span>
            <br><span class="team-member-name">[Member name]</span>
          </div>
          <!--...repeated for every team member-->
        </div>
      </div>
      <div id="contact" class="page-section">
        <h1>Contact</h1>
        <p>For additional information, contact us at [Team email address]</p>
      </div>
    </div>
  </body>
</html>
```

Your CSS side should now look like:
```css
*{
  padding:0;
  margin: 0;
}
body{
  background: teal;
  color: white;
  font-size: 20px;
}
#page-wrapper{
  margin-left: auto;
  margin-right: auto;
  width: 960px;
}
h1{
  color:white;
}
#top-menu{
  position: fixed;
  top: 0;
  width: 100%;
  background-color: black;
  height: 25px;
}
#top-menu li{
  margin-left: 50px;
  display: inline;
}
#top-menu li a{
  text-decoration: none;
  color: white;
}
.page-section{
  padding-top:50px;
  min-height:500px;
}
.app-store-icons{
  width: 200px;
}
.team-member{
  display: inline-block;
  margin-left: 50px;
}
.team-member-photo{
  height: 100px;
  width: 100px;
}
```

Voila! You have a basic skeleton of an HTML & CSS page with a menu, headings, images, links, and styles. This is all you need to house your landing page. If you feel you want a more challenging task, proceed to check out the HTML & CSS II lab.

Feel free to Google concepts that you either you are having trouble with, or desire to learn more information about. A great website to use to learn more about the topics discussed in class:<br>
**https://www.w3schools.com/**
<br>
Simply go here, search a specific topic, and you'll find detailed explanations and examples of all the topics that were discussed today.
