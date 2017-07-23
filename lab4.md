---
title: Lab 4: STEM with Enza Academy
---
## Lab 4

**Introduction:
Today we will learn about loops, adding events to HTML, and CSS.**

Office hours for 7/20:
6:30p-7:30p, Room 328


You now have your list of questions but no way to loop through the list. We can manually select individual questions from the list with indexing, but that is not efficient. What if there were 150 questions? We would need to write 150 lines of code to do the exact same thing. What if there was a way to execute one line of code for all 150 items? Looping through the array will allow you to do so.

To loop through an array, we use something called a "for" loop. We set up for loops like this:
```javascript
var names = ["Jack", "Joe", "Mark", "James"];
for(counter=0; counter<names.length; counter++){
  console.log(names[counter]);
}
```
Try that code above in your scrap editor.

There are 4 parts to the for loop -- set the counter, give our counter a max, increment our counter until we meet that max, and tell the program to do something each time. So for our example, we set the counter to 0, gave it a max of 1 less than the length of the names array(which is 4), incremented the counter from 0 until we reached the max, and told the console to print the question it is currently on in the loop.

As you can guess, to loop through our questions array we would need to loop through the array in a similar fashion. Remember that clicking the "Start Quiz" button on our HTML side makes the questions appear, so let's place the following code inside our 'startQuiz()' function:
```javascript
function startQuiz(){
 for(counter=0; counter<questions.length; counter++){
   console.log(questions[counter]);
 }
}
```
Although we have code, the button still isn't doing anything when we click it. We must connect the 'Start Quiz' button to the 'startQuiz()' function. To do this, we add a property to the button called an 'onclick', and set it equal to the function we want to execute when it is clicked. In this case we want to set it to the 'startQuiz()' function. So our HTML button should look like:
```html
<button onclick="startQuiz()">Start Quiz</button>
```

Try clicking the 'Start Quiz' button. Our code is now being executed because the button is connected to the function.

Notice that this gives us the entire question object -- the console prints the object itself. However, we want the parts of the object. To get a specific property value of the object, we use bracket notation on the object. It is easiest to set another variable so that we don't confuse ourselves:
```javascript
function startQuiz(){
 for(counter=0; counter<questions.length; counter++){
   var current_question_in_loop = questions[counter];
   var question_text = current_question_in_loop['question'];
   
   console.log(question_text);
 }
}
```
Now you see the question text from all of the questions, but they are all printing back to back. There is no formatting. We want to display a number before the question, starting with 1, so let's just add the number 1 to our counter to get the number of the question in the list. For instance, we know our counter starts at 0, which is the number 1 question. This means when the counter is at 1, it is the number 2 question, and when the counter is 2, it is the number 3 question etc. Let's create a 'display_number' number so we know what's going on:
```javascript
function startQuiz(){
 for(counter=0; counter<questions.length; counter++){
   var current_question_in_loop = questions[i];
   var question_text = current_question_in_loop['question'];
   var question_number = counter+1;

   console.log(question_number);
 }
}
```
We now have a question and a display number to format the appearance of the questions. Remember we can simply concatenate(add) strings to each other to get a longer string. So let's add our numbers to the questions:
```javascript
function startQuiz(){
 for(counter=0; counter<questions.length; counter++){
   var current_question_in_loop = questions[i];
   var question_text = current_question_in_loop['question'];
   var question_number = counter+1;
   var displayed_question = question_number+". "+question_text;

   console.log(displayed_question);
 }
}
```
We now see the question number, a period, a space, and our question text correctly. Let's start adding this stuff to our HTML page. Recall that adding to HTML is simply calling the 'innerHTML' function on the div.

We want our questions to appear on our HTML form, so let's create a reference variable at the top of our JS file under the quiz feedback variable:
```javascript
var questions_form_div = document.getElementById("questions_form");
```

Our file should now look something like:
```javascript
var main_quiz_area_div = document.getElementById("main_quiz_area");
var questions_form_div = document.getElementById("questions_form");

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

function startQuiz(){
 for(counter=0; counter<questions.length; counter++){
   var current_question_in_loop = questions[i];
   var question_text = current_question_in_loop['question'];
   var question_number = counter+1;
   var displayed_question = question_number+". "+question_text;

   console.log(displayed_question);
 }
}

function submitAnswers(){
}

function displayQuizResults(questions_wrong_count){
}
```

We have a reference to our HTML form, so now we are ready to use the innerHTML function to add the questions to the page. SO in the 'startQuiz()' function, set the displayed question equal to the innerHTML:
```javascript
function startQuiz(){
 for(counter=0; counter<questions.length; counter++){
   var current_question_in_loop = questions[i];
   var question_text = current_question_in_loop['question'];
   var question_number = counter+1;
   var displayed_question = question_number+". "+question_text;

   questions_form_div.innerHTML = displayed_question;
 }
}
```

Whoops, what happened? We are only seeing our last question being added to the HTML and not the others. Why aren't our other questions being displayed? This is because we keep overwriting the previous question with the next one when set the innerHTML. If we use an equal sign, it simply replaces the value with what we tell it. We don't want to replace the value, but add to it instead. So instead of an equal sign, we use a plus-equal sign:`+=`. Change the `=` sign atfer innerHTML to `+=` and notice the difference:
```javascript
function startQuiz(){
 for(counter=0; counter<questions.length; counter++){
   var current_question_in_loop = questions[i];
   var question_text = current_question_in_loop['question'];
   var question_number = counter+1;
   var displayed_question = question_number+". "+question_text;

   questions_form_div.innerHTML += displayed_question;
 }
}
```
We see our questions being displayed, but they all run together. We want them to appear on a separate line each, so let's add HTML code that accomplishes this. HTML has break tags, `<br>`, to break the current line and go to the next. Ideally we want to add these to the end of our displayed question -- this will make every question start on its own line. Let's add break tags to our 'displayed_question' variable:
```javascript
function startQuiz(){
 for(counter=0; counter<questions.length; counter++){
   var current_question_in_loop = questions[i];
   var question_text = current_question_in_loop['question'];
   var question_number = counter+1;
   var displayed_question = question_number+". "+question_text+"<br>";

   questions_form_div.innerHTML += displayed_question;
 }
}
```

We should now see our questions being displayed on their own lines. Recall that we need to inform the user when a specific question is wrong. We currently have no way to identify each question. How can we do that? Give it an id! Let's make our questions labels using an HTML label tag, and give it an id:
```javascript
function startQuiz(){
 for(counter=0; counter<questions.length; counter++){
   var current_question_in_loop = questions[i];
   var question_text = current_question_in_loop['question'];
   var question_number = counter+1;
   var displayed_question = "<label id='question"+counter+"'>"+question_number+". "+question_text+"</label><br>";

   questions_form_div.innerHTML += displayed_question;
 }
}
```

See where we included the counter in the id? The reason we do this is to differentiate every question id from each other. Because we are inside a loop, if we used an id without using our counter, every question would be issued the same id, which will not work when we want to target a specific question. The counter changes for every question, so it makes sense to use that counter in our question id. 

Also, pay close attention to the quote usage. We started our line with double quotes, but also used single quotes. Whatever quote type we start with, the code will look for that same type to close the quote. For example, see where we close the double quote right before the `+` sign and the `counter` variable? This is to ensure we got the variable `counter` and not the word "counter". If we kept the word "counter" inside the double quotes, it would display the word "counter" instead of the number of the counter, which is what we want. When we started the double quotes again, noticed we added a single quote to finish closing off the id name of the label. Remember that our ids need to be inside quotes, but we needed to use 2 types of quotes to mix our variables with our HTML.

There are a couple of more things missing from our function: displaying text boxes for answers, and displaying a "Submit Answers" button.

For displaying text boxes, we simply add a line for that after we display our question. Create a variable for this line and it at the end of the loop:
```javascript
var displayed_answer_input = "<input /><br>";
questions_form_div.innerHTML += displayed_answer_input;
```

Our function should now look like this:
```javascript
function startQuiz(){
 for(counter=0; counter<questions.length; counter++){
   var current_question_in_loop = questions[i];
   var question_text = current_question_in_loop['question'];
   var question_number = counter+1;
   var displayed_question = "<label id='question"+counter+"'>"+question_number+". "+question_text+"</label><br>";

   questions_form_div.innerHTML += displayed_question;
   
   var displayed_answer_input = "<input /><br>";
   questions_form_div.innerHTML += displayed_answer_input;
 }
}
```
Notice we created a new 'input' tag, but this tag doesn't have a closing `</input>` tag. You will learn that some HTML tags are exceptions and do not need full closing `</tag>` type of tags, and simply adding a forward slash can close it. The `<input>` tag is one of those tags.

Our last step is to show a button to submit answers. We will add this inside the function but outside of the loop. Because we don't want this button to display for every question, only once. Let's add this at the bottom of our function outside of the loop:
```javascript
function startQuiz(){
 for(counter=0; counter<questions.length; counter++){
   var current_question_in_loop = questions[i];
   var question_text = current_question_in_loop['question'];
   var question_number = counter+1;
   var displayed_question = "<label id='question"+counter+"'>"+question_number+". "+question_text+"</label><br>";

   questions_form_div.innerHTML += displayed_question;
   
   var displayed_answer_input = "<input /><br>";
   questions_form_div.innerHTML += displayed_answer_input;
 }
 questions_form_div.innerHTML += "<input type='button' onclick='submitAnswers()' value='Submit Answers' /><br>";
}
```

Notice that we added a "type" and "onclick" properties to the input tags. We do not want to add a button tag because in our case it won't behave correctly, so we add an input tag and give it a button type. If we added a regular button, it would submit the entire form, which would refresh the page. We don't want this behavior, so making it an input and linking it to our 'submitAnswers()' function is what we want.

But notice we need to clear our HTML before we re-add questions because the questions are adding on to each other instead of clearing out first. Let's add one line to clear our html before the loop:
```javascript
questions_form_div.innerHTML = '';
 ```

```javascript
function startQuiz(){
  questions_form_div.innerHTML = '';
 for(counter=0; counter<questions.length; counter++){
   var current_question_in_loop = questions[i];
   var question_text = current_question_in_loop['question'];
   var question_number = counter+1;
   var displayed_question = "<label id='question"+counter+"'>"+question_number+". "+question_text+"</label><br>";

   questions_form_div.innerHTML += displayed_question;
   
   var displayed_answer_input = "<input /><br>";
   questions_form_div.innerHTML += displayed_answer_input;
 }
 questions_form_div.innerHTML += "<input type='button' onclick='submitAnswers()' value='Submit Answers' /><br>";
}
```


We will now learn how to check our answers. Loop through your answers, and compare the answers submitted to the answers defined:
```javascript
function checkAnswers(){
  var number_incorrect = 0;
  var submittedAnswers = document.getElementsByTagName("input");

  for(i=0;i<submittedAnswers.length;i++){
    submittedAnswer = submittedAnswers[i].value;
    if(submittedAnswer != ques_obj[i]['answer']){
      number_incorrect ++;
      document.getElementById("question"+i).className = "feedback_negative";
    }
    else{
      document.getElementById("question"+i).className = "feedback_positive";
    }
    displayQuizResults(number_incorrect);
  }
}
```

Let's add our code to display our quiz results:
```javascript
function displayQuizResults(questions_wrong_count){
  if(questions_wrong_count == 0){
    quiz_feedback_div.innerHTML = "<div class='feedback_positive'>Congrats! you got a 100%!</div>";
  }
  else{
    quiz_feedback_div.innerHTML = "<div class='feedback_negative'>whoops, you got "+questions_wrong_count+" wrong...try again.</div>";
  }
}
```

Our HTML code should look like:
```html
<html>
<!-- I will be building an HTML-->  
  
  <!-- I will add head tags here -->
  <head>
    <!-- I will add a title tag here -->
    <title>Mikos's Quizzer Tool - not visible on my actual page</title>
  </head>
  <body>
    <h1>Mikos's Quizzer Tool</h1>
    <!-- I will create a div for the main quiz section here-->
    <div id="main_quiz_section">
      <!-- I will create a div for the quiz feedback section here-->
      <div id="quiz_feedback_section"></div>
      
      <!-- I will add a form tag for the quiz questions here-->
      <form id="questions_form"></form>
    </div>
    <!-- I will add a button to start the quiz here-->
    <button onclick="startQuiz()">Start Quiz</button>
  </body>
</html>
```

Our JavaScript code should now look like:
```javascript
var questions_form_div = document.getElementById("questions_form");
var quiz_feedback_section_div = document.getElementById("quiz_feedback_section");

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

function startQuiz(){
  //clear the quiz form
  questions_form_div.innerHTML = '';
  
  //create a variable for number of questions in our list
  var question_list_count = question_list.length;
  
  //loop through the questions
  for(counter=0; counter<question_list_count; counter++){
    //create variable for current question in loop
    var current_question_in_loop = question_list[counter];
    
    //create variable for current question text
    var current_question_text = current_question_in_loop['question'];
    
    //create a variable & set the display number for the current question
    var current_question_display_number = counter +1;
    
    //create a variable for the displayed question
    var displayed_question = "<label id='question"+counter+"'>"+current_question_display_number+". "+current_question_text+"</label><br>";
    
    //add the displayed question to our html
    questions_form_div.innerHTML += displayed_question;
    
    //create a variable for a displayed answer input box
    var displayed_answer_input = "<input /><br>";
    
    //add the displayed input box to our html
    questions_form_div.innerHTML += displayed_answer_input;
  }//end for loop
  //add a submit answers button
  questions_form_div.innerHTML += "<input type='button' onclick='checkAnswers()' value='Submit Answer' /><br>";
}

function checkAnswers(){
  //set number of incorrect answers to 0
  var number_incorrect = 0;
  
  //create a variable for all submitted answers
  var submittedAnswers = document.getElementsByTagName("input");

  //loop through submitted answers
  for(counter=0; counter<submittedAnswers.length;counter++){
    submittedAnswer = submittedAnswers[counter].value;
    
    //if the submitted answer does not match correct answer
    if(submittedAnswer != question_list[counter]['answer']){
      //increment the number incorrect
      number_incorrect ++;
      
      //add a negative feedback css class
      document.getElementById("question"+counter).className = "feedback_negative";
    }
    //else if submitted answer matches correct answer
    else{
      //add positive feedback css class
      document.getElementById("question"+counter).className = "feedback_positive";
    }
    //display quiz results
    displayQuizResults(number_incorrect);
  }
}

function displayQuizResults(questions_wrong_count){
  //if no questions were wrong
  if(questions_wrong_count == 0){
    //display success message
    quiz_feedback_section_div.innerHTML = "<div class='feedback_positive'>Congrats! you got a 100%!</div>";
  }
  else{ //if questions were wrong, tell the user how many
    quiz_feedback_section_div.innerHTML = "<div class='feedback_negative'>Whoops, you got "+questions_wrong_count+" wrong...try again.</div>";
  }
}
```

Feel free to Google concepts that you either you are having trouble with, or desire to learn more information about. A great website to use to learn more about the topics discussed in class:<br>
**https://www.w3schools.com/**

Simply go here, search a specific topic, and you'll find detailed explanations and examples of all the topics that were discussed today.


Instructor contact information can be found at the bottom of the lab for one-on-one questions.

Enza Instructors:
<ul>
<li>Mr. Jenkins: mjenkins@enzaacademy.org</li>
<li>Mr. Kyei: kkyei@enzaacademy.org</li>
<li>Mr. Kibret: nkibret@enzaacademy.org</li>
<li>Mr. Cudjoe: rcudjoe@enzaacademy.org</li>
</ul>
