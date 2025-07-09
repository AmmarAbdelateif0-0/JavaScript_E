
to select the element from the page

```js
// we use the Doucment class
document.querySelector(/*the element in html*/);
// if the element is a normal
document.querySelector('elementName');
// if the element is a id
document.querySelector('#elementName');
// if the element is a class
document.querySelector('.elementName');


console.log(document.querySelector('elementName')); 
// <elementName>....</elementName>
```

-------------------------------------------------------------

to manipulate the style in the element 

```js
document.querySelector('elementName').style.CSS_proparty
```

* background-color
```js
document.querySelector('elementName').style.backgroundColor = 'the color'
```

* width
```js
document.querySelector('elementName').style.width = 'width size'
```
