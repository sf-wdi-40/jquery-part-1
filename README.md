# Introduction to jQuery

## jQuery's Piece

- jQuery is a library for working with JavaScript.
- It abstracts away some of the more tedious actions that you do in a website powered by JavaScript.
- It also gives us a syntax that is clearer to make it easy to understand what is going on in the code.
- jQuery syntax looks like this:

```javascript
$("selector").action();
```

- The selector is actually the same as CSS. It allows us to target elements to apply functionality.
- Actions are collections of JavaScript functions that allow us to manipulate the element(s) selected.
- Here are a few things you can do with jQuery actions:
	- "Listen" for events such as clicks and perform some operation.
	- Change HTML attributes and inner-html on the fly.
	- Add and remove CSS classes from HTML elements.
	- Perform light animations.
	- Get data from APIs.

## Setting Up jQuery

- The main documentation for jQuery can be found [here](http://jquery.com/).
- The jQuery CDN can be found [here](http://code.jquery.com/).
- Just like we saw with Bootstrap, we will create a custom app.js file that will use the jQuery library.

## `$(document).ready()`

- One of the first things to note about jQuery is that it runs immediately when the browser reaches the `script` tag.
- In order to ensure that our JavaScript code runs after all of the HTML is loaded in, we must listen for a completion event from the browser:

```javascript
$(document).ready(function() {

	//Your code here

});
```

## Listening for Events

- Event listening is one of the most powerful features of jQuery.
- By setting up events, we can trigger certain actions in response to receiving those events by the user.
- Here is an example of how we can do this:

HTML:

```html
<button id="click-me">Click Me!</button>
```

JS:

```javascript
$(document).on("click", "#click-me", function() {
	alert("Click received!");
});
```

- There are a variety of events we can listen for. Here are some common ones:
	- click - click of the mouse
	- mouseenter - mouse enters an element
	- mouseleave - mouse leaves an element
	- blur - user clicks out of form element
	- focus - user clicks in to a form element
	- dblclick - double click of mouse
	- change - select / checkbox / radio button value changes

## Changing Style Properties

- One of the many things that jQuery does well is gives you the ability to alter the HTML style attribute on the fly.
- It makes it easy to do things like change the background color or the font size in response to events.
- We will be using the [.css method](http://api.jquery.com/css/) to accomplish this.
- Here is an example of how to do this with a click event:

HTML:

```html
<div id="animated-div"></div>

<button id="change-color">Change Color</button>
```

JS:

```javascript
$(document).on("click", "#change-color", function() {
	$("#animated-div").css("background-color", "blue");
});
```

## Altering HTML Classes

- Sometimes you may want to change more than just a single CSS property.
- For this you need to be able to add and remove classes, which will apply and remove many properties at the same time.
- Let's take an example of doing this with a click event:

HTML:

```html
<div id="animated-div"></div>

<button id="add-red-class">Add Big Red Class</button>
```

CSS:

```css
.big-red {
	background-color:red;
	width:400px;
	height:400px;
}
```

JS:

```javascript
$(document).on("click", "#add-red-class", function() {
	$("#animated-div").addClass("big-red");
});
```

- jQuery can add, remove, and also toggle classes. Read more about it here:
	- [.addClass()](https://api.jquery.com/addclass/)
	- [.removeClass()](https://api.jquery.com/removeclass/)
	- [.toggleClass()](http://api.jquery.com/toggleclass/)

## Changing Inner HTML

- Apart from stylistic changes, jQuery can also edit the entire HTML contents of a container.
- This can be useful for replacing text and even layouts without having to refresh the page.
- For this we will be using the [.html()](http://api.jquery.com/html/) method.
- Let's take an example:

HTML:

```html
<div id="animated-div"></div>

<button id="change-text">Change Text</button>
```

JS:

```javascript
$(document).on("click", "#change-text", function() {
	$("#animated-div").html("<h1>Hey everyone!</h1>");
});
```

## Getting Data from Users

- In our last class we saw that we could use data that was either hard-coded or retrieved from a user via the `prompt` function.
- In a real website however, you will almost always want to get data from the user via UI components such as form elements.

## jQuery .val() Method

- jQuery offers us an easy way to grab form data and use it in our application.
- Imagine we have a simple HTML input:

```html
<input name="email" type="email" />
```

- Can you name a couple of ways we can "select" this element via jQuery?
- Now that we have that, we can extract the value by using the `.val()` method:

```javascript
$("input").val();
```

- We could even assign the value of this input to a variable, which will allow us to use its value at a later time throughout our application:

```javascript
var emailAddress = $("input").val();
```

## In-Class Lab

- For this lab you will be working with jQuery to activate the functionality for a small [style-switcher application](https://github.com/sf-wdi-44/jQuery-Style-Switcher)
