###SWBATs

####jQuery
+ understand the JS behind jQuery and how the same thing can be done with either
+ use jQuery grep to filter items in an array
+ know where to look for jQuery resources
+ use jQuery .each function to iterate
+ make custom HTML5 data attributes and use the jQuery data method to retrieve (one argument) and set values (two arguments)
+ retrieve and set values from forms using the jQuery .val method
+ validate form input with common validation functions and regex
+ build their own regular expressions

###Lesson Plan

####jQuery
+ Understanding how to iterate through a JS array with a for loop is important and useful, but there is an even easier way to iterate through an array using the jQuery .each method.
+ We’re going to do a lot more jQuery review today but for now we’ll just walk through how to use .each like this:
  + $(numbers).each(function(i, value){
    +  alert(value+1);      
  + });
+ You can see that we start with a $ sign - which is the jQuery object and kind of how we say “Hey, jQuery! Got something for you.” And the thing that we have - numbers - goes in parentheses - kind of like an argument - and we are going to call .each on this numbers array. 
+ .each does exactly what you think it would do - it takes out each item in the array and it does whatever we tell it to do with each one.
+ The way that we tell it what to do is by feeding the .each method a function as an argument. You might remember this from Intro to Web Design class - arguments can be functions. We do this a lot with jQuery.
+ You can see that the function that goes into .each has two arguments - the i stands for index and the value is the actual thing in the array. Go ahead and try using .each to iterate through your numbers array.
+ Now try recreating your myFavorites function with jQuery .each.

####More jQuery

+ Now that you’ve gotten back into the swing of things with JavaScript it’s time to get reacquainted with Query.
+ BUT before we do that let’s do a quick review of working the DOM. <b>Does anyone remember what DOM stands for?</b> This stands for document object model and it is a structural representation of our HTML in tree form. Like this:
<img src="https://s3.amazonaws.com/after-school-assets/advanced_jquery2.png">
+ This model enables us to modify the content and visual presentation on our HTML document with JavaScript and jQuery.
+ What kind of things can we do with JS + DOM.
  + Add/remove/hide/show HTML elements in the page.
  + Add/remove/change HTML attributes.
  + Add/remove/change  CSS styles.
  + Listen for key presses or mouse events upon Elements
  + Create events in the page.
+ We can select elements on the page like this:
  + $("p");
+ And manipulate content like this:
  + $("#foo").text("hello world"); //this sets the text in #foo div to “hello world”
+ You probably already remember how jQuery helps to simplify your life. Let’s dive right in to practicing some more.
+ jQuery is a JavaScript library. <b>What is a library again?</b>
  + A library is a  collection of code that extends the abilities and features of a core programming language, offering additional methods and often simplifying the process to build in that native language.
+ <b>Why use jQuery?</b>
  + It just works everywhere! jQuery has been written to solve many cross browser issues that exist in core JavaScript.
  + Terse code. You can often write fewer lines of code than you would in using core JavaScript to accomplish the same thing. Hence jQuery’s slogan “Write Less Do More”.
  + Popularity. jQuery is currently at the time of writing this by far the most popular JavaScript framework. That means more forums, more code sharing, and more plugins.
  + Easy extending methods. Coders can create and share their own custom plugins easily.
  + Familiar DOM selectors. If you already know CSS you’re a step ahead as jQuery uses all our familiar CSS selector statements.
+ To set up a document to run jQuery we must link to the jQuery core library first! Imagine that JavaScript is like a pet dog. On it’s own it knows how to eat, sleep, and play. Loading jQuery is like teaching the dog new tricks such as roll over, fetch, etc… Imagine what would happen if we gave the command for our dog to fetch before we had taught it this trick (linked to jQuery). Therefore, we always link to the jQuery core library first.
+ Remote link:
`<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js"></script>`
+ Local link (downloaded from jquery.com):
`<script src=”js/jquery-1.8.2.min.js"></script>`
+ Both using local as fallback solution:
`<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js"></script>
<script>window.jQuery || document.write('<script src="js/jquery-1.8.2.min.js"> <\/script>')</script>`
+ <b>jQuery syntax</b>  
+ Here is an example of the syntax for using a jQuery method
  + $(selector).method(parameters);
  + '$' refers to the jQuery object.
+ 'selector' asks jQuery to go out into the DOM (Document Object Model) web page and select an element(s). In jQuery we can use all of the familiar selectors we use in CSS yay!
+ 'method' these are various actions and commands attached to the jQuery object that allow us to do things like fade elements in an out or change the content of the DOM and much much more.
+ 'parameters' are options we can set for each method.
+ An example of real code:
  + $('h1').css({'background':'yellow'});
  + '$' refers to the jQuery object.
  + ’h1' asks jQuery to go out into the DOM (Document Object Model) web page and select all `<h1>`.
  + ’css' method applies some CSS upon the selected element(s).
  + '{'background':'yellow'}’ changes the background color to yellow.
+ If you want to do something to your DOM jQuery probably has a method for it. 
+ YOU DO NOT HAVE TO MEMORIZE ALL OF THE METHODS
+ Having an idea of what possibilities are available is useful, and familiarizing yourself with some that you will use from day to day is useful, unless you’re a jQuery guru you probably will not memorize every method. Fortunately we can look them up and see their usage at sites like:
  + API: [http://api.jquery.com/](http://api.jquery.com/)
  + Documentation: [http://docs.jquery.com/](http://docs.jquery.com/)
  + Or nifty cheatsheets like: [http://oscarotero.com/jquery/](http://oscarotero.com/jquery/)
  + and http://overapi.com/jquery
+ How will I know when to use jQuery versus core JavaScript?
  + Firstly, jQuery is written in JavaScript so you can think of them as variations of the same thing instead of two separate things. To help answer this, jQuery methods are useful for many things; however there are certain fundamental parts of JavaScript that we still need in order to make flexible web applications. For example jQuery on its own does not have method for declaring variables, functions, if statements, or doing math…
  + This means that we can get a lot more mileage by integrating jQuery with core JavaScript.
+ An example of JS and jQuery working together (demo in JSfiddle):
  + var x = 12, 
  + y = 5,
  + total = x + y;

  + If (total === 17) {
  +  $(’p').text('Correct!');
  + } else {
  + $(’p').text('Incorrect.');
  + }
+ Set up steps for using jQuery in your websites:
   + Include link to jQuery core library:
  `<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.10.1/jquery.min.js"></script>`
  + Link to your custom js file
  `<script src=”./js/app.js"></script>`
  + Start your app.js with document ready command:
    + $(document).ready(function() {
      + // your app code goes here.
    + });
+ We’re going to get A LOT more practice with this in the coming days. Today we’re going to wrap up with a fun little lab to help you build and publish your own chrome extension lab.
