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
> $ => it is an alias for `jquery`, you can use the word "jquery" as well
> document => is the object to be passed
> ready() => is the function to call

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

