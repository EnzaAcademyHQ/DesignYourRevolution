---
title: Lab 2: STEM with Enza Academy
---
## Lab 2

**Introduction:
Today we will introduce the JavaScript programming language, along with clarifying its relationship with HTML in how it adds functionality to it.**

Office hours for 7/18:
9:35p-10:35a, Room 328

JavaScript is a primarily front-end programming language that shares similarities with other high level languages. This is a great language to learn because it shares concepts such as if-else conditionals and for loops, but can be practiced at a lower level.

Much of the things you learn can be immediately practiced for understanding, and we will get into how to do so.

Building upon things from the last lab, we will learn how to manipulate and target the HTML elements on the page we previously created and identified with the 'id' property.

First, we will discuss variables in JavaScript. Variables are simply entities used to store values. In math, you are usually trying to solve for a variable's value. In programming, we already know what the values are because we are defining them. We define vaiables using the `var` keyword:
```javascript
var me = "Mikos";
```

In that example, we created a variable called "me", with a value of "Mikos". Notice the semicolon at the end? All JavaScript statements must end with a semicolon. Unlike HTML, if JavaScript statements aren't closed off, it will return an error and break the program. A broken program cannot run.

The standard practice to test variables is using the JavaScript console. The console is simply a window that usually displays errors, but can also be used to code JavaScript.

To test code, we simply type: 
```javascript
console.log([test code]);
```

So if we want to test the value of our variable, we would simply type:
```javascript
console.log(me);
```

Try to experiment with setting variables and printing them in the console:
```javascript
var first_name = "[your name]";
var last_name = "[your name]";
var home_state = "[your home state]";
var school_name = "[your school name]";

console.log(first_name);
console.log(last_name);
console.log(home_state);
console.log(school_name);
```

Now that you know how to set variables, we can proceed to test manipulation of data on the page. Remember the id properties we set on the `<div>` elements yesterday? We will now learn how they play with JavaScript.

You should recall the fact that the HTML page is a document, and this is how you call and manipulate the page in JavaScript: declaring the div itself as a variable. Let's make our main_quiz_area div a variable:

```javascript
var main_quiz_area = document.getElementById("main_quiz_area");
```

We now have a reference in JavaScript that we can call on to manipulate the data related to the div. 

Voila! You now know JavaScript basics, including variables, getting/referencing HTML elements, and adding HTML to it. This is all you need to house the quizzer on the HTML side. We will learn more about adding functionality to the button and introducing another language, JavaScript, to you in the next lab.

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
