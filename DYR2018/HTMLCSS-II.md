---
title: BLITZ CODING IN HTML & CSS II
---

**Introduction:
We will learn use what we know about HTML and CSS to add the framework bootstrap**

Use the Bootstrap reference throughout this lab as a guide:
https://getbootstrap.com/

Start by using the code from the previous lab(scroll down to the end of the list and paste into your pens).
Include bootstrap within your head tags:

```html
<head>
  <title>TutorFinder</title>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">
  <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js" integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q" crossorigin="anonymous"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js" integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl" crossorigin="anonymous"></script>
</head>
```

We will make a change to the team member photo: giving it a 'img-thumbnail' class to add the border as in bootstrap.
```html
      <!-- creating a div for each team member -->
      <div class="team-member">
        <img class="img-thumbnail team-member-photo" src="[Member photo link]" />
        <br><span class="team-member-title">[Member title]</span>
        <br><span class="team-member-name">[Member name]</span>
      </div>
      <!--...repeated for every team member-->
```

We will change our menu's background color. Since Bootstrap has default colors, we need to override it. We use the '!important' keyword to do this in CSS. We also need to add a z-index to make the menu appear in front of the rest of our page. Simply set this to a high value, and you should be safe. The value '9999' works:
```css
nav{
  background-color: navy !important;
  z-index: 9999;
}

```

We will be adding another advanced item to our page: a modal popup in the contact section. First we will start by adding the button:
```html
<!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#contactModal">
  Give us a shout!
</button>
```
The attributes aren't too important, as to how they work, just know they work. The important thing is to remember the 'data-target' attribute, because this is what makes the modal appear. We haven't created the modal yet, but we will do so now:

```html
<!-- Modal -->
<div class="modal fade" id="contactModal" tabindex="-1" role="dialog" aria-labelledby="contactModalLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Contact</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <form>
          <div class="form-group">
            <label>Name</label>
            <input type="text" class="form-control" placeholder="Enter name">
          </div>
          <div class="form-group">
            <label>Email address</label>
            <input type="email" class="form-control" placeholder="Enter email">
            <small class="form-text text-muted">We'll never share your email with anyone else.</small>
          </div>
          <div class="form-group">
            <label>Comment</label>
            <textarea class="form-control" placeholder="Enter comment"></textarea>
          </div>
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Send</button>
      </div>
    </div>
  </div>
</div>
```

Notice we added a contact form inside the modal. You can add whatever you'd like, but the form is a good start.

Now that you are familiar with adding components with bootstrap, take this time to scroll through the bootstrap documentation and try adding at least 2 more components to your pages for practice. We recommend adding a dropdown menu, and an image carousel.



Your HTML page should now look like this:

```html
<html>
  <head>
    <title>TutorFinder</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">
    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js" integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q" crossorigin="anonymous"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js" integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl" crossorigin="anonymous"></script>
  </head>
  <body>
    <nav class="nav justify-content-center">
      <a class="nav-link active" href="#home">Home</a>
      <a class="nav-link" href="#about">About</a>
      <a class="nav-link" href="#team">Team</a>
      <a class="nav-link" href="#contact">Contact</a>
    </nav>
    
    <div id="page-wrapper">
    <div id="home" class="page-section">
      <h1>TutorFinder</h1>
      <p>We see a need to build a platform to unite classrooms by connecting the strongest students in class with the students that need extra help.</p>
      <br>
      <p>Stay tuned for our web & mobile app launch!</p>
      <br>
      <p>Coming soon to iOS and Android!</p>
    </div>
    <div id="about" class="page-section">
      <h1>About</h1>
      <p>We are building a platform to connect the brightest in class to those who need help.</p>
      <br>
      <p>Our idea was conceived as a result of our founder needing help in class; but he was too shy to ask questions in front of the class, and too proud to utilize the university tutoring resources.</p>
    </div>
    <div id="team" class="page-section">
      <h1>Team</h1>
      <h2>Say hello to our awesome team!</h2>
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
      <!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#contactModal">
  Give us a shout!
</button>

<!-- Modal -->
<div class="modal fade" id="contactModal" tabindex="-1" role="dialog" aria-labelledby="contactModalLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Contact</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <form>
          <div class="form-group">
            <label>Name</label>
            <input type="text" class="form-control" placeholder="Enter name">
          </div>
          <div class="form-group">
            <label>Email address</label>
            <input type="email" class="form-control" placeholder="Enter email">
            <small class="form-text text-muted">We'll never share your email with anyone else.</small>
          </div>
          <div class="form-group">
            <label>Comment</label>
            <textarea class="form-control" placeholder="Enter comment"></textarea>
          </div>
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Send</button>
      </div>
    </div>
  </div>
</div>
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
  text-align: center;
}
nav{
  background-color: navy !important;
  z-index: 9999;
}
#page-wrapper{
  margin-left: auto;
  margin-right: auto;
  width: 960px;
}
h1{
  color:white;
  margin-bottom: 50px;
}
nav{
  position: fixed;
  top: 0;
  width: 100%;
  background-color: black;
  height: 40px;
}
nav a{
  color: white;
}
.page-section{
  padding-top:50px;
  min-height:500px;
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

Feel free to Google concepts that you either you are having trouble with, or desire to learn more information about. A great website to use to learn more about the topics discussed in class:<br>
**https://www.w3schools.com/**
<br>
Simply go here, search a specific topic, and you'll find detailed explanations and examples of all the topics that were discussed today.
