# Table of Contents

- [JQuery](#jquery)
  * [Getting Starting with JQuery](#getting-starting-with-jquery)
    + [Download JQuery](#download-jquery)
    + [Using a *Content Delivery Network* (CND)](#using-a--content-delivery-network---cnd-)
  * [Using JQuery Wrapper Object](#using-jquery-wrapper-object)
  * [Using JQuery Raw Object](#using-jquery-raw-object)
  * [Using JQuery ready() function](#using-jquery-ready---function)
  * [Using JQuery Selectors](#using-jquery-selectors)
    + [Selector Syntax](#selector-syntax)
    + [Selecting by Tag Name](#selecting-by-tag-name)
      - [Selecting Multiple Tags](#selecting-multiple-tags)
      - [Selecting Descendants](#selecting-descendants)
    + [Selecting by ID](#selecting-by-id)
    + [Selecting by Class Name](#selecting-by-class-name)
      - [Selecting multiples Class Names](#selecting-multiples-class-names)
      - [Combine Tags with Class](#combine-tags-with-class)
    + [Selecting By Attribute Value](#selecting-by-attribute-value)
    + [Selecting Input Elements](#selecting-input-elements)
    + [Using Contains in Selectors](#using-contains-in-selectors)
    + [Selecting the First Child](#selecting-the-first-child)
    + [Using Starts With in Selectors (wildcard)](#using-starts-with-in-selectors--wildcard-)
    + [Using Ends With in Selectors (wildcard)](#using-ends-with-in-selectors--wildcard-)
    + [Find Attributes Containing a Value (wildcard)](#find-attributes-containing-a-value--wildcard-)
    + [Useful JQuery webpage](#useful-jquery-webpage)
  * [Interacting with the DOM](#interacting-with-the-dom)
    + [Iterating Through Nodes](#iterating-through-nodes)
      - [Demo](#demo)
    + [Modifying Object Properties](#modifying-object-properties)
    + [Accessing Attributes](#accessing-attributes)
    + [Modifying Attributes](#modifying-attributes)
      - [Modifying a single attribute](#modifying-a-single-attribute)
      - [Modifying Multiple Attributes](#modifying-multiple-attributes)
    + [Appending to Nodes](#appending-to-nodes)
      - [appendTo](#appendto)
      - [prependTo](#prependto)
    + [Wrapping Elements](#wrapping-elements)
    + [Removing Nodes](#removing-nodes)
    + [Modifying Styles](#modifying-styles)
      - [Modifying Multiples Styles](#modifying-multiples-styles)
    + [Modifying CSS Classes](#modifying-css-classes)
      - [`.addClass()`](#addclass)
      - [`.hasClass()`](#hasclass)
      - [`.removeClass()`](#removeclass)
      - [`.toggleClass()`](#toggleclass)
  * [Handling Events](#handling-events)
    + [Click Events](#click-events)
    + [Change events](#change-events)
    + [Mouse Events](#mouse-events)
    + [Binding to Events](#binding-to-events)
      - [Using `on()`](#using-on)
        * [Using with Child Objects](#using-with-child-objects)
        * [Using with a Map](#using-with-a-map)
      - [Using `off()`](#using-off)
      - [Binding Multiple Events with `on()`](#binding-multiple-events-with-on)
    + [Handling Hover Events](#handling-hover-events)
      - [Alternate Hover Example](#alternate-hover-example)
  * [Working with Ajax Features](#working-with-ajax-features)
    + [Loading HTML Content from the Web](#loading-html-content-from-the-web)
      - [Using `load()`](#using-load)
      - [Using `load()` With a Selector](#using-load-with-a-selector)
      - [Using `load()` With a Callback Function](#using-load-with-a-callback-function)
    + [Making GET Requests](#making-get-requests)
      - [Using `get()`](#using-get)
      - [Using `getJSON()`](#using-getjson)
    + [Making POST Requests](#making-post-requests)
      - [Using `post()`](#using-post)
    + [The `ajax()` function](#the-ajax-function)



# JQuery

## Getting Starting with JQuery

There is a few ways to get JQuery for use into the HTML

###  Download JQuery
Go to the following  [link](https://jquery.com/download). Once there you can download the production version or the development version, is highly recommend to download the production version since it weighs less .

### Using a *Content Delivery Network* (CND)
Insert the following lines of code to use with *Microsoft CDN*

```html
<head>
  <script type="text/javascript" src="http://ajax.microsoft.com/ajax/jquery/jquery-[version].js"></script>
<head>
```

Or you can insert the following lines to use along with *Google CDN*

```html
<head>
  <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/[version]/jquery.min.js"></script>
<head>
```
References:

- [Google Libraries](https://developers.google.com/speed/libraries)

  

## Using JQuery Wrapper Object

JQuery wrapper object

```javascript
$('DOMObject')
```

Using the JQuery Wrapper Object you can access to JQuery [API](https://api.jquery.com):

```javascript
$(this).attr('attributeName')
```



## Using JQuery Raw Object

JQuery Raw Object

```javascript
this
```

The main difference beetwen using the `raw object` is that here you can access to JQuery [API](https://api.jquery.com):

```
this.attr('attributeName')
```

This is wrong

## Using JQuery ready() function

Detecting when a page has loaded
1. Use `$(document).ready()` to detect when a page has loaded and is ready to use
2. Called once DOM hierarchy is loaded (but before all images have loaded)

> Where 
> `$` => it is an alias for `jquery`, you can use the word "jquery" as well
> `document` => is the object to be passed
> `ready()` => is the function to call

e.g:
```html
<head>
  <script type="text/javascript">
     $(document).ready(function(){
     //Perform some actions
     });
  </script>
</head>
```

The following code does the same with only JavaScript code:
```html
<head>
  <script type="text/javascript">
     window.onload = function(){
     //Perform some actions
     };
  </script>
</head>
```



## Using JQuery Selectors

### Selector Syntax

```javascript
$(selectorExpression)
```

or

```javascript
JQuery(selectorExpression)
```

### Selecting by Tag Name

```html
$("p") selects all <p> elements
$("a") selects all <a> elements
```

#### Selecting Multiple Tags

To reference multiple tags, use `,` character to separate the elements:

```html
$("p, a, span") selects all paragraphs, anchorsm and span elements
```

#### Selecting Descendants

- `$("ancestor descendant")` selects all descendants of the ancestor, e.g:

```javascript
$(table tr)
```

Select all `tr` elements that are descendants of the `table` element

### Selecting by ID

Use the `#` character to select elements by ID:

```javascript
$("#myID")
```

### Selecting by Class Name

Use the `.` character to select elements by class name:

```javascript
$(".myClass")
```

#### Selecting multiples Class Names

To reference multiple tags, use the `,` character to separate the class names:

```javascript
$(".myClass, .myOtherClass")
```

#### Combine Tags with Class

You can caimbine this with element names as well:

```javascript
$("a.myClass")
```

selects only `<a>` tags with `class="myClass"`

### Selecting By Attribute Value

Use brackets `[attribute]` to select based on attribute name and/or attribute value:

```javascript
$("a[title]")
```

select all `<a>` elements that have a title attribute, e.g:

```javascript
$('a[title="programmingInfo"]')
```

Select all `anchor` elements that have a "programmingInfo" title attribute value

### Selecting Input Elements

`$(:input)` selects all input elements including:

- input
- select
- textarea
- button
- image
- radio

and more, e.g: 

```javascript
$(':input[type="radio"]')
```

target all radio buttons on the page

### Using Contains in Selectors

`:contains()` will select elements that match the contents within the contains exception:

```javascript
$('div:contains("pluralsight")')
```

Select `div´s` that contain the text `pluralsight` (case sensitive)

e.g:

```html
<div>Expert pluralsight training</div>
```

### Selecting the First Child

`$('element:first-child')` selects the first child of every element group:

```javascript
$('span:first-child')
```

The above will grab all `span` tags and it only will selected the first-child, e.g:

```html
<div>
  <span>First child, first group</span> // this will be selected
  <span>Second child, first group</span> // this will be ignored
</div>
<div>
  <span>First child, second group</span> // this will be selected
  <span>Second child, second group</span> // this will be ignored
</div>
```

The tag `<div>` could be any other tag

### Using Starts With in Selectors (wildcard)

`[atribute^="value"]` will select all elements with an attribute that begins with stated value:

```javascript
$('input[value^="Events"]')
```

Selects any input element whose value attributes begins with "Events", e,g:

```html
<input type="button" value="Events - World"/>
<input type="button" value="Events - National"/>
<input type="button" value="Events - Local"/>
```

### Using Ends With in Selectors (wildcard)

`[attribute$="value"]` will select all elements with an attribute that ends with stated value:

```javascript
$('input[value$="Events"]')
```

Selects any input element whose value attribute ends with "Events", e.g:

```html
<input type="button" value="World Events"/>
<input type="button" value="National Events"/>
<input type="button" value="Local Events"/>
```

### Find Attributes Containing a Value (wildcard)

`[attribute*="value"]` will select all elements with an attribute that contain the state value:

```javascript
$('input[value*="Events"]')
```

Selects any input element whose value attribute contains "Events", e.g:

```html
<input type="button" value="World Events 2011"/>
<input type="button" value="National Events 2011"/>
<input type="button" value="Local Events 2011"/>
```

### Useful JQuery webpage

[JQuery Selectors](http://codylindley.com/jqueryselectors)

## Interacting with the DOM

`DOM` stands for "Document Object Model"

### Iterating Through Nodes

`.each(function(index, element))` is used to iterate through JQuery objects, e.g:

```javascript
$('div').each(function(index){
  alert(index + "=" `$(this).text());
});
```

> where
>
> - `function()` => it is an anonymous function
> - `$('div')` => it is a JQuery selector to grab all division and it returns an JQuery object
> - `index` => the index of the current object
> - `$(this)` => it makes reference to the current object
> - `element` => if you add it in function parameters, it makes reference to the current object, in other words "Element = $(this)"

Example using `element` as parameter function:

```javascript
$('div').each(function(index, element){
  alert(index + "=" `$(element).text());
});
```

#### Demo

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="utf-8">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>
  </head>
  <body>
    <div class="divisionA">Division A</div>
    <div class="divisionB">Division B</div>
    <div id="outputDivision"></div>
    
    <script type="application/javascript">
      let html = '';
      $('div.divisionA, div.divisionB').each(function(index){
        html += "<br> index(" + index + ") <=> " + $(this).text();
      });
      let output = $('#outputDivision');
      output.html(html);
    </script>
  </body>
</html>
```

### Modifying Object Properties

The `this.propertyName` statement can be used to modify an object's properties directly:

```javascript
$('div').each(function(index){
  this.title = "My index: " + index
});
```

> Where:
>
> - `this` => keyword represent the raw DOM object
> - `title` => propierty of raw DOM object

The above code iterates through each div and modifies the title. If the property does not exists, it will be added

### Accessing Attributes

Object attributes can be acceded using `attr()`:

```
let val = $('#CustomerDiv').attr('title');
```

retrieves the value of the title attribute

### Modifying Attributes

#### Modifying a single attribute

`.attr(attributeName, value)` is the method used to access an object's attributes and modify the value:

```javascript
$('img').attr('title', 'My image title')
```

Changes the title attribute to the value of my image title, *for all images in the html*

#### Modifying Multiple Attributes

To modify multiple attributes, pass a JSON object containing name/values pairs:

```javascript
$('img').attr({
  title: 'My image title',
  style: 'border:2px solid black'
});
```

JSON object passed and used to change title and border

### Appending to Nodes

#### appendTo

Appending adds children at the end of the matching element:

```javascript
$('<span>(Office)</span>').appendTo('.officePhone');
```

Or

```javascript
$('.officePhone').appendTo('<span>(Office)</span>');
```

Would result in `(office)` being added into each `.officePhone` class element

#### prependTo

> it has the same effect than `appendTo`

Prepending adds children at the beginning of the matching element:

```javascript
$('<span>Phone:</span>').prependTo('.phone');
```

Or

```javascript
$('.phone').prepend('<span>Phone:</span>');
```

would result in `Phone:` being added into each `.phone` class element

### Wrapping Elements

The following HTML and `.wrap()` function:

``` html
<div class="state">Arizona</div>
```

```javascript
$('.state').wrap('<div class="US_State"/>')
```

> Notice that inside the `wrap` function the div is closed, this is a short way to avoid write "</div> tag

Results in:

```html
<div class="US_State">
  <div class="state">Arizona</div>
</div>
```

### Removing Nodes

`.remove()` will remove matched elements from the DOM:

```javascript
$('.phone, .location').remove()
```

will result in objects with `.phone` or `.location` classes being removed from the DOM

Taking courses in pluralsight

### Modifying Styles

The `.css` function can be used to modify an object`s style:

```javascript
$('div').css('color', 'red')
```

#### Modifying Multiples Styles

Multiple Styles can be modified by passing a JSON object:

```javascript
$('div').css({
 'color': '#FFFFF',
 'font-weight': 'bold'
});
```

### Modifying CSS Classes

The four methods for working with CSS Class attributes are:

- `.addClass()`
- `.hasClass()`
- `.removeClass()`
- `.toggleClass()`

#### `.addClass()`

`.addClass()` add one or more class names to the class attribute of each matched element:

```javascript
$('p').addClass('classOne')
```

More than one class:

```javascript
$('p').addClass('classOne classTwo')
```

#### `.hasClass()`

`.hasClass()` return true if the selected element has a matching class that is specified:

```javascript
if($('p'.hasClass('specificStyle')){
 // perform some action  
}
```

#### `.removeClass()`

`.removeClass()` can remove one or more classes:

```javascript
$('p').removeClass('classOne classTwo');
```

remove all class attributes for the matching selector:

```javascript
$('p').removeClass();
```

#### `.toggleClass()`

`.toggleClass()` alternates adding or removing a class based on the current presence or absence of the class:

```
$('#PhoneDetails').toggleClass('highlight');
```

in the id `#PhoneDetails` has the class "highlight" this function will be remove it, otherwise it will be added

It can be used to highlight some objects on click event for example buttons when they are pressed

## Handling Events

### Click Events

`.click(handler(eventObject))` is used to listen for a click event or trigger a click event on a element:

```javascript
$('#myID').click(function(){
  alert('some alert');
});
```

raising a click event from within another function:

```javascript
$('#otherID').click(function(){
  $('#myID').click();
});
```

this would fire when the element `#otherID` was clicked and raise the click event for `#myID`

a real example could be:

```javascript
$('document').ready(function(){
  triggerEvents();
});

function triggerEvents(){
  $('#submitButton').click(function(){
    // Perform some test
  });
}
```

### Change events

`.change(hander(eventObject))` is used to listen for a change state in the element:

```javascript
$('#myID').change(function(){
  alert('some alert');
});
```

for example, grab the event of an `id` when the textbox value changes

### Mouse Events

`.mouseenter(hander(eventObject))` is used to listen when the cursor is over the element:

```javascript
$('#myDiv').mouseenter(function(){
  // Perfom some action
});
```

another example of mouse events:

```javascript
$('#myDiv').mouseenter(function(){
  // Perfom some action
}).mouseleave(function(){
  // Perform some action
});
```

You can nested several events into the same JQuery object, to know more mouse events please visit the JQuery [API](https://api.jquery.com/category/events/mouse-events)

### Binding to Events

The core of JQuery functions is call `on`, it was added in JQuery 1.7 and is the reccommend approach to use

#### Using `on()`

`on(eventType, handler(eventObject))` attaches a handler to an event for the seleted element(s):

```javascript
$('#myDiv').on('click', function(){
  // Handle click event
});
```

##### Using with Child Objects

Using `on()` function with a data in a table

```javascript
$('#myTable tbody').on('click', 'tr', function(){
  alert('row was clicked and bubbled up');
});
```

> `tr` is a descendent from `tbody`

##### Using with a Map

Multiple events and hanldlers can be defined in `on()` using a "map" (*json object*):

```javascript
$('#myTable tr').on({
  mouseenter: function(){
    $(this).addClass("over");
  },
  mouseleave: function(){
    $(this).removeClass("out");
  }
})
```



#### Using `off()`

`off(event)` is used to remove a handler previously bound to an element:

```javascript
$('#test').click(handler); // can be unbound using
$('#test').off(); // will remove all events related
```

To remove specific events:

```javascript
$('#test').off('click')
```

#### Binding Multiple Events with `on()`

- `on()` allows multiple events to be bound to one or more elements
- Event names to bind are separated with a space:

```javascript
$('#myDiv').on('mouseenter mouseleave', function(){
  $('this').tooggleClass('entered');
});
```

### Handling Hover Events

Hover events can be handled using `hover()`:

```javascript
$('selector').hover(handlerIn, handlerOut)
```

`handlerIn` is equivalent to *mouseenter* and `handlerOut` is equivalent to *mouseleave*

The following example highlights `#target` on mouseenter and set it back to white on mouseleave

```javascript
$('#target').hover(
  function(){
    $(this).css('background-color', '#00FF99');
  },
  function(){
    $(this).css('background-color', '#FFFFFF');
  }
);
```

#### Alternate Hover Example

- Another option is `$(selector).hover(handlerInOut)`
- Fires the same handler for mouseenter and mouse leave events
- Use with JQuery´s toggle methods:

```javascript
$('p').hover(function(){
  $(this).toggleClass('over');
});
```



## Working with Ajax Features

### Loading HTML Content from the Web

#### Using `load()`

`$(selector).load(url, data, callback)` allow HTML content to be loaded from a server and added into a DOM object:

```javascript
$(document).ready(function(){
  $('#helpButton').click(function(){
    $('#myDiv').load('helpDetails.html');
  });
});
```

#### Using `load()` With a Selector

A selector can be added after the URL to filter the content that is returned from a calling `load()`

```javascript
$('#myDiv').load('helpDetails.html #someDiv');
```

#### Using `load()` With a Callback Function

`load()` can be passed a callback function:

```javascript
$('#outputDiv').load('notFound.html',function(response, status, xhr){
  if(status == 'error'){
    alert(xhr.statusText);
  }
});
```

> - response: the data comming back
> - xhr: means `xml http requests` and have details about the error

### Making GET Requests

#### Using `get()`

- `get()` it is a global function

`$.get(url, data, callback, datatype)` can retrieve data from a server:

```javascript
$.get('HelpDetails.html', function(data){
  $('#outputDiv').html(data);
});
```

The above example uses only *url* and *callback* function, `get()` function uses **ajax** behind scenes

example (**using get funcion to grab a entire html webpage into a variable to be able for DOM manipulation**):

```javascript
$('#MyButton').click(function(){
  $.get('someWebPage.html', function(data){
    $('#outputDiv').html(data);
  });
});
```

#### Using `getJSON()`

`$.getJSON(url, data, callback)` can retrieve data from a server:

```javascript
$.getJSON('customerJson.aspx', {id: 1}, function(data){
  alert(data.FirstName + data.LastName);
});
```

### Making POST Requests

#### Using `post()`

- `post()` it is a global function

`$.post(url, data, callback, datatype)` can retrieve data from a server:

```javascript
$.post('HelpDetails.html', function(data){
  $('#outputDiv').html(data);
});
```

### The `ajax()` function

> `ajax()` is a global function of JQuery

The `ajax()` function provides extra control over making Ajax calls to a server

- Configure using JSON properties:
  - contentType
  - data
  - dataType
  - error
  - sucess
  - type (GET or POST)

The `ajax()` function is configured by assigning values to JSON propierties:

```javascript
$.ajax({
  url: 'someURL',
  data: someJSONObject,
  dataType: 'json', // the data type returned from the server
  sucess: function(data, status, xhr){
    alert('Insert status: ' + data.d.Status + data.d.Message); // Accesing to the JSON object by property name
  },
  error: function(xhr, status, error){
   alert('Error occurred: ' + status); 
  }
});
```

