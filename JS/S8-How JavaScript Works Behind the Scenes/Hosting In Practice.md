### Variables

```js
console.log(me); // undefined
console.log(job); // you can't access 'job' before declaration 
console.log(year);  // you can't access 'year' before declaration 


var me = 'Jonas';
let job = 'teacher';
const year = 1991;
```

-----------------------------------------------
### Functions
```js
console.log(addDecl(2, 3)); // 6
console.log(addExpr(2, 3)); // you can't access 'addExpr' before declaration 
console.log(addArrow); // undefined
console.log(addArrow(2, 3)); // undefined(2,3) so u get error  addArrow is not a function

  

function addDecl(a, b) {

  return a + b;

}

  

const addExpr = function (a, b) {

  return a + b;

};

  

var addArrow = (a, b) => a + b;
```

-------------------------------------------
problem in var
### Example 

```js
console.log(undefined); // falsy value

if (!numProducts) deleteShoppingCart(); // !undefined = 1
//All products deleted!

  

var numProducts = 10;

  

function deleteShoppingCart() {

  console.log('All products deleted!');

}
```

var is a window property

```js
var x = 1;
// if you open console and write window and enter you will ind the x in it.
let y = 2;

const z = 3;

  

console.log(x === window.x);

console.log(y === window.y);

console.log(z === window.z);
```