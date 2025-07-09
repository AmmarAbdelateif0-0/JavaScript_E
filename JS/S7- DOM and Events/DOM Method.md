
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

the limitation of the `querySelector` Method whenever we use `querySelector` with a selector, which actually matches multiple element only the first one will get selected.

if you want to select all 
```js
	document.querySelectorAll('elementName');
	console.log(document.querySelectorAll('elementName')); // NodeList
	// if you want to know the length use 
	let Nodelistt = document.querySelectorAll('elementName');
	Nodelistt.length          // -> the length
	Nodelistt[0].textContent // -> first element
```


-------------------------------------------------------

to manipulate / access the data in the element 

* normal element
```js 
// access
console.log(Document.querySelector('elementName').textContent); // the data
let data = Document.querySelector('elementName').textContent;
// manipulate
Document.querySelector('elementName').textContent = 'aaaa' 

```


* input element

```js
//access
console.log(Document.querySelector('elementName').value); // the data
let data = Document.querySelector('elementName').value;
// manipulate
Document.querySelector('elementName').value = 'aaaa' 
```