###SWABATs

####Arrays
+ understand what an array is and when to use it
+ declare arrays and add items
+ fetch array elements by index
+ insert new values into an array
+ access array elements by their index
+ store or change elements in an array
+ call methods on an array - like length, push, pop, splice
+ understand when to use associative arrays

####Loops
+ iterate over arrays using for loops and do while loops
+ iterate over arrays using loops

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
+ <b>ARRAYS</b> - Let’s start by learning about arrays. We’ll do this by making our own arrays.
+ Think about an array as an ordered list that can be visualized as a two-column table where the left column is the index (or the order) and the right column is the thing you’re listing (Draw on board, using one of the students’ examples):
<img src= "https://s3.amazonaws.com/after-school-assets/advanced_jquery1.png">
+ Notice that the index starts at 0. This is a quirk about data structures in computer science that you just have to memorize. The first item in an array is always 0, and it increments by one.
+ So how do we translate this table into code?
  + [“Danny”, “Lyel”, “Victoria”, “Vanessa”]
  + Remember that the names are data so they must be in quotes as strings.
  + We use square brackets to denote an array.
  + We don’t explicitly write the index anywhere. (show the index above each item on the board)
+ Great, we’ve made an array. Let’s go ahead and assign it to a variable so that whenever we call the variable names we have the array returned to us.
+ <b>Model and then have students create a new file in their development directories to hold their array practice code. Have students create their own array of their choice and assign it to a variable. Have students turn to partners and check with each other.</b>
+ Great. We’ve created the array. Now what if I just want to get out one item from the array instead of the whole thing. For example, What if I want to get the third item listed in my array?
+ We access items in an array using the brackets and the index of the thing you want.
+ <b>names[3] will give me what? (the fourth). how do I get the third item?
+ So what if we want to change one of the items in the array? Any thoughts on how we can reassign/change an item?</b>
+ names[2] = “Joe” will change the third item in the array to Joe. (Model this)
+ We can also add and remove items from an array. Arrays actually have methods built in to them. Remember that methods are just a set of instructions.
  + names.push(“Alfred”) will add an item with the contents of the argument to the end of the array it is called on. 
  + names.pop() will remove the last item in an array.
+ Here are some other cool methods: .length(), .sort(), .splice(), split().
+ <b>Mini-Lab: Manipulating arrays (start with array and then have 10 instructions, what does array look like at the end?)
+ Answer: ["Peru", "Laos", "Chad", "Cuba", "Togo", "Iraq", "Iran", "Mali", "Oman", "Fiji"] </b>
+ Let’s make a new array but use numbers now. Get an example set from a student and make an integer based array. <b>Ask a few review questions (add a number? index? etc…)</b>
+ Ok, what if we want to do something to each number. Like add one to each number. We could do it manually: numbers[0] = numbers[0] +1, etc. but that would take forever
+ A better way to do this is to set up a little machine with instructions on how to iterate (go through) every number in the array and do something specific to each one.
+ We do this in javascript with something called a for loop. Here is the syntax of what a for loop looks like:
for (starting condition; ending condition; step for moving our machine forward) {
  thing that we want to do each time we cycle through this loop
+ }
+ This might make a little more sense when you see this in action - with our number array. We want to add 1 to each number in our array and alert it to our screen. Here is how we would set that up:
+ numbers = [1,2,3,4,5]
+ for (var i=0; i<numbers.length; i++) {
    + alert(numbers[i]+1)
+ }
+ Let’s walk through each part of this.
  + for is the keyword that we use to set up a loop
  + inside of the parentheses is where we set up the conditions of our loop
  + we start off by declaring the starting conditions in the for loop should start with - a counter variable i set to 0. <b>Why do we set it at 0?</b> Because the first index in our array is 0 - so we want to set up our little machine to pull out each item in the array starting with the item at index 0.
  + <b>Why do we use the variable i?</b> It’s convention to use the variable i because i is short for index - we are counting through the indices of the of the array
  + we close this condition with a ; to indicate that we are done with these starting instructions for our machine and we’re ready to move on to 
  + in the next part of our for loop we set up the ending instructions for our machine - it’s like saying this machine should keep going until this condition is true
  + The condition here is that our var i must be less than numbers.length. <b>Why is this the ending condition for our machine? What is numbers.length equal to? Does numbers[5] exist?</b> No it doesn’t. We want to make sure we stop our machine before it starts requesting indices that don’t exist. Or in other words - keep going ONLY while i is less than the length of the array (5 in this case). 
  + The last condition of the for loop are instructions for how to keep our machine moving. Here we are saying - at the end of each iteration in the loop add one to var i. <b>What would happen if we didn’t have this condition set?</b> We wouldn’t get anywhere! We wouldn’t be iterating at all, because we would just keep trying to change numbers[0] over and over again in an infinite loop.
  + <b>Everyone create a iteration.js doc and try setting up a for loop with a numbers array and alert each number doubled.</b>
+ <b>Do you guys remember what we said yesterday about ALWAYS HAVING YOUR CODE WRAPPED UP IN FUNCTIONS? Everyone go into you iteration.js doc and wrap up your for loop in a function called doubleNumbers. Did you put your numbers array in your function? Is there a better way to do this?
+ What if we set up the function to accept a numbers array instead of hardcoding one specific array into the function? Why would that be better? Set up a new numbers array and call your doubleNumbers array with your new array.</b>
+ Let’s do one more practice lab with iteration and strings instead of numbers. 
  + Everyone create an array of your top 5 favorites movies.
  + Now create a function called myFavorites();
  + This function should take in an array of favorites and for each favorite it should alert to the screen something like “The Shawshank Redemption? That is my favorite too!”
+ Now create a new array of your favorite songs. Try calling the myFavorites() function with your favorite songs array.
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

<b>jQuery</b>

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
