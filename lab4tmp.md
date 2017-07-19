---
title: Lab 4: STEM with Enza Academy
---
## Lab 4

**Introduction:
Today we will learn about functions, adding events to HTML, and CSS.

Office hours for 7/20:
6:30p-7:30p, Room 328

We will discuss objects first. Look around -- objects are all around you. These objects all have properties. For example, if you were to think about a car as being an object, think about what makes a car a car: make, model, year, and type are some quick properties. All cars have a make, model, year, and a type. 

In JavaScript, to create an object, we start with curly braces `{}`, then add properties & values within those curly braces. The format is: `{property: value}`. 

If we were to create a car object in JavaScript, it would look like:
```javascript
var car = {make:'BMW', model:'328i', year: "2017", type: 'sedan'};
```
The above code created a car object that has a "BMW" make, "328i" model, "2017" year, and "sedan" type.

We can then use dot-notation to get the properties of those objects: `car.make` or `car.year`.

Think about what we want to create when it comes to a question. What components do all questions have? A question and an answer. So a question object would look something like:
```javascript
var car = {question:'What is the capital of Italy?', answer:'Rome'};
```

Practice creating a few objects & testing properties of some in a blank codepen pad:
```javascript
var person = {name:'John', age:'26', hometown: "Los Angeles"};
var phone = {name:'iPhone', manufacturer:'Apple', model: "7s Plus"};
var computer = {name:'Macbook', manufacturer:'Apple', model: "Macbook Air"};

console.log(person.age);
console.log(phone.model);
console.log(computer.manufacturer);

```

Now that we know how to create question objects, we just need to learn how create a list to hold them.
Lists in JavaScript are called "arrays". To declare an array, we use brackets `[]`. An array of numbers looks like:
```javascript
var number_list = [1, 2, 3, 4, 5];
```
This simply creates an array with 5 values: 1, 2, 3, 4 and 5. 

You can select a specified item in the list, based on their position in the list. Counting array positions in programming starts at 0. For example, if we have:

```javascript
var name_list = ["Jack", "Joe", "Mark", "James"];
```
The position of "Joe" in 'name_list' is position 1, instead of 2, like you may think. We don't start counting 1, 2, 3, 4... -- but instead 0, 1, 2, 3...

If we wanted to get "Joe" from the list, we use brackets on the array withthe position to do so. Since "Joe" is at the 1 position, we get "Joe" from the list with:

```javascript
name_list[1];
```

And "James":
```javascript
name_list[3];
```

Try verifying these in the console:
```javascript
console.log(name_list[1]);
console.log(name_list[3]);
```
 Now that you know how to count indexes in the array, we can go back to creating our question list. Create an array of at least 10 questions you will use for your app:
```javascript
var question_list = [
    {question:'What is the capital of Italy?', answer:'Rome'},
    {question:'What is the capital of the United States?', answer:'Washington D.C.'},
    {question:'What is the capital of Alabama?', answer:'Montgomery'},
    {question:'What is the capital of Arkansas?', answer:'Little Rock'},
    {question:'What is the capital of Arizona?', answer:'Phoenix'},
    {question:'What is the capital of Alaska?', answer:'Juneau'},
    {question:'What is the capital of California?', answer:'Sacramento'},
    {question:'What is the capital of Colorado?', answer:'Denver'},
    {question:'What is the capital of Connecticut?', answer:'Hartford'},
    {question:'What is the capital of Delaware?', answer:'Dover'}
];
```

Your javascript file should now look like this:
```javascript
var main_quiz_area_div = document.getElementById("main_quiz_area");

var question_list = [
    {question:'What is the capital of Italy?', answer:'Rome'},
    {question:'What is the capital of the United States?', answer:'Washington D.C.'},
    {question:'What is the capital of Alabama?', answer:'Montgomery'},
    {question:'What is the capital of Arkansas?', answer:'Little Rock'},
    {question:'What is the capital of Arizona?', answer:'Phoenix'},
    {question:'What is the capital of Alaska?', answer:'Juneau'},
    {question:'What is the capital of California?', answer:'Sacramento'},
    {question:'What is the capital of Colorado?', answer:'Denver'},
    {question:'What is the capital of Connecticut?', answer:'Hartford'},
    {question:'What is the capital of Delaware?', answer:'Dover'}
];
```

You now have your list of questions but no way to loop through the list. We can manually select individual questions from the list with indexing, but that is not efficient. What if there were 150 questions? We would need to write 150 lines of code to do the exact same thing. What if there was a way to execute one line of code for all 150 items? Looping through the array will allow you to do so.

To loop through an array, we use something called a "for" loop. We set up for loops like this:
```javascript
var names = ["Jack", "Joe", "Mark", "James"];
for(i=0;i<names.length;i++){
  console.log(names[i]);
}
```
Try that code above in your scrap editor.

There are 4 parts to the for loop -- set the index, give our index a max, increment our index until we meet that max, and tell the program to do something each time. So for our example, we set the index to 0, gave it a max of 1 less than the length of the names array(which is 4), incremented the index from 0 until we reached the max, and told the console to print the result of the item at the current index.

As you can guess, to loop through our questions array we would need to loop through the array in a similar fashion:
```javascript
for(i=0;i<questions.length;i++){
  console.log(questions[i]);
}
```


Voila! You now know JavaScript basics, including variables, getting/referencing HTML elements, and adding code to HTML. If you were able to complete the extras, you also know how to create objects, access properties, and create arrays. You are well on your way to creating an awesome quizzer tool.

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
