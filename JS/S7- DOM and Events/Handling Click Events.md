to select the element from the page

```js
// we use the Doucment class
Document.querySelector(/*the element in html*/);
// if the element is a normal
Document.querySelector('elementName');
// if the element is a id
Document.querySelector('#elementName');
// if the element is a class
Document.querySelector('.elementName');


console.log(Document.querySelector('elementName')); 
// <elementName>....</elementName>
```

-----------------------------------------
# Event 

JavaScript can be executed when an event occurs, like when a user clicks on an HTML element.

To execute code when a user clicks on an element, add JavaScript code to an HTML event attribute.



```js
document.querySelector('elementName').addEventListener('action' , function () {/*
the executed code after action
*/ })
```


Examples of HTML events:

- When a user clicks the mouse
- When a web page has loaded
- When an image has been loaded
- When the mouse moves over an element
- When an input field is changed
- When an HTML form is submitted
- When a user strokes a key


example after click on button the background-Color become red 
```js
document.querySelector('elementName').addEventListener('click' , function () {
	document.querySelector('body').style.backgroundColor = 'red';
})
```