---
title: Lab 5: STEM with Enza Academy
---
## Lab 5

**Introduction:
Today we will learn about styling our pages with CSS.**

Presentation prep for 7/21:
6:30p-7:45p & 9:30p-11p Room 328

Your HTML and JavaScript sides are now working. The only thing left to do is add pizzazz to your quizzer tool. We learned that HTML is the skeleton element of a web page, containing only the bare elements. We also learned that JavaScript acts as a muscle for the HTML skeleton, giving it functionality.

We will now go on to the aesthetics of the page, CSS(Cascading Style Sheets) are ways to make your page unique by altering the appearance. CSS is the language responsible for adding colors, changing font sizes, paragraph spacing, etc. It is the primary language for styling in web development.

We have our HTML and JavaScript, so let's start adding our CSS code. First, let's give our background a color:
```css
html{
  background-color: red;
}
```

How CSS works is we give an element we want to style, and place the style inside curly braces `{}`. The style format SHOULD look familiar to a data structure we already know -- CSS styles are comprised of a property, colon-separated with a value. Remember objects? Yeah. So we added a background color to everything within the HTML tags in the above code.

What if we want to take it a step further and add a background image? CSS has a property called a background-image. We simply set the image to the url we want to use. Simply google an image, grab the link for the image, and set that link. For example:
```css
html{
  background-image: url("https://i.kinja-img.com/gawker-media/image/upload/s--ExuCFXZ8--/c_scale,f_auto,fl_progressive,q_80,w_800/tzzllrqpzhihslnkwlq4.gif");
}
```

That adds the background image, but what if we wanted to stretch the image to a considerable size? There are different sizing values to a background size, but we will show you what `cover` does. Cover simply makes the background image stretch to the point it acts as a webpage "cover". Let's add it and see the effects:
```css
html{
  background-image: url("https://i.kinja-img.com/gawker-media/image/upload/s--ExuCFXZ8--/c_scale,f_auto,fl_progressive,q_80,w_800/tzzllrqpzhihslnkwlq4.gif");
  background-size: cover;
}
```

Now let's center our text with a text-align property:
```css
html{
  text-align: center;
  background-image: url("https://i.kinja-img.com/gawker-media/image/upload/s--ExuCFXZ8--/c_scale,f_auto,fl_progressive,q_80,w_800/tzzllrqpzhihslnkwlq4.gif");
  background-size: cover;
}
```

You now know how to add a background image to the page, so let's try changing the color of our visible quizzer heading:
```css
h1{
  color: orange;
}
```

This makes every `<h1>` on your page have the color "orange". Notice we just put the word "color" instead of "text-color" or something similar. You can research these properties to learn which ones are valid, along with the values. These are built-in to CSS, so you must learn the proper terminology of the properties/values.

Because our questions are within `<label>` tags, let's give our questions a way to stand out. Let's make them slightly larger than the rest of the text, give it bold font, and also change the color:
```css
label{
  font-size: 30px;
  font-weight:bold;
  color: yellow;
}
```

Try out your "Start Quiz" button to see the appearance changes. Let's add a little style to our input answer boxes(yes we can style those too!). Let's give it rounded edges with a `border-radius` and make the border itself a bit cleaner by giving it a `border` property:
```css
input{
  border-radius: 2px;
  border: 1px;
}
```

Remember our correct questions should turn green and incorrect ones should turn red because of the CSS classes we gave them, right? Our JavaScript code adds a class named 'feedback_positive' to correct answers and 'feedback_negative' to incorrect ones. The class adds to the label dynamically, but we still need to define those classes in CSS:
```css
.feedback_positive{
  color: green;
}
.feedback_negative{
  color: red;
}
```

Notice the dot(.) before the class names? This simply tells CSS that we will be using a custom class name instead of applying the style to a built-in HTML element. You can override HTML element styles by giving an element a specific class name. Since there are no HTML elements to accomplish the functionality we want, we simply create a class name to do so instead.

Our last step is to add style to our "Start Quiz" button itself. Let's first change its color. Not only can you add background colors to entire pages, but also to elements themselves. The same "background-color" property we used to change the page's background works the same for a button:
```css
.button_new_quiz{
  background-color: orange;
}
```

Let's also make the edges round and change the font color on the button:
```css
.button_new_quiz{
  background-color: orange;
  color: white;
  border-radius: 5px;
  border: 2px;
}
```

Notice the same properties work for the button as far as changing the text color and making the edges round.

One more thing we should do is add some padding to the buttons so that our text isn't so close to the edges of the button. This will make it look a lot better:
```css
.button_new_quiz{
  background-color: orange;
  color: white;
  border-radius: 5px;
  border: 2px;
  padding: 10px;
}
```

We now have a button that has adequate padding, a different background color, and different text color. Your code should now look like this at least:
```css
html{
  text-align: center;
  background-image: url("https://i.kinja-img.com/gawker-media/image/upload/s--ExuCFXZ8--/c_scale,f_auto,fl_progressive,q_80,w_800/tzzllrqpzhihslnkwlq4.gif");
  background-size: cover;
}

h1{
  color: orange;
}

label{
  font-size: 30px;
  font-weight:bold;
  color: yellow;
}
input{
  border-radius: 2px;
  border: 1px;
}
.feedback_positive{
  color: green;
}
.feedback_negative{
  color: red;
}
.button_new_quiz{
  background-color: orange;
  color: white;
  border-radius: 5px;
  border: 2px;
  padding: 10px;
}
```

Continue to think of ways to add more styles to your pages. A good resource is w3schools: `https://www.w3schools.com/cssref/default.asp`.

Let's see what you can come up with!


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
