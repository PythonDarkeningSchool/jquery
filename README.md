# JQuery

## Getting Starting with JQuery

There is a few ways to get JQuery for use into the HTML

###  Download JQuery
Go to the following  [link](https://jquery.com/download). Once there you can download the production version or the development version, is highly recommend to download the production version since it weighs less .

### Using a *Content Delivery Network* (CND)
Insert the following lines of code to use with Microsoft CDN

```html
<head>
  <script type="text/javascript" src="http://ajax.microsoft.com/ajax/jquery/jquery-[version].js"></script>
<head>
```

Or you can insert the following lines to use along with Google CDN

```html
<head>
  <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/[version]/jquery.min.js"></script>
<head>
```
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

```html
$(selectorExpression)
```

or

```html
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

```html
$(table tr)
```

Select all `tr` elements that are descendants of the `table` element

### Selecting by ID

Use the `#` character to select elements by ID:

```html
$("#myID")
```

### Selecting by Class Name

Use the `.` character to select elements by class name:

```html
$(".myClass")
```

#### Selecting multiples Class Names

To reference multiple tags, use the `,` character to separate the class names:

```html
$(".myClass, .myOtherClass")
```

#### Combine Tags with Class

You can caimbine this with element names as well:

```html
$("a.myClass")
```

selects only `<a>` tags with `class="myClass"`

### Selecting By Attribute Value

Use brackets `[attribute]` to select based on attribute name and/or attribute value:

```html
$("a[title]")
```

select all `<a>` elements that have a title attribute, e.g:

```html
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

```html
$(':input[type="radio"]')
```

target all radio buttons on the page

### Using Contains in Selectors

`:contains()` will select elements that match the contents within the contains exception:

```html
$('div:contains("pluralsight")')
```

Select `div´s` that contain the text `pluralsight` (case sensitive)

e.g:

```html
<div>Expert pluralsight training</div>
```

### Selecting the First Child

`$('element:first-child')` selects the first child of every element group:

```html
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

```html
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

```html
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

```html
$('input[value*="Events"]')
```

Selects any input element whose value attribute contains "Events", e.g:

```html
<input type="button" value="World Events 2011"/>
<input type="button" value="National Events 2011"/>
<input type="button" value="Local Events 2011"/>
```



