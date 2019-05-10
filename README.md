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

