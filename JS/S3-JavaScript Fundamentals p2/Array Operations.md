
* to add element to the end of  array.
```js
const friends = ['anas','b3dsh','ali'];
let newsize =friends.push("kardash"); // return the length of the new array
console.log(friends)
```

* to add element to the beginning of the array.
```js
const friends = ['anas','b3dsh','ali'];
friends.unshift('kardash');
console.log(friends)

```

* remove  last element in the array .
```js
const friends = ['anas','b3dsh','ali'];
friends.pop(); // ali
// return the removed element.
```

* remove the first element in the array .

```js
const friends = ['anas','b3dsh','ali'];
friends.shift();
console.log(friends) // [ 'b3dsh','ali' ]
// return the removed element.
```

* to know the index of the element.
```js
const friends = ['anas','b3dsh','ali'];
console.log(friends.indexOf('b3dsh')); // 1 
// if exist return the index 
// if not exist return -1
```

* to check if the element exist or no (ES6).

```js
const friends = ['anas','ali','b3dsh'];
console.log(friends.includes('b3dsh')); // true
// after your decision
friends.pop();


//return ture if exist
//return false if not exist
```

==without type coercion.==

```js
const years = [2003,2004 , 2005];
console.log(years.includes('2003')) // false
console.log(years.includes(2003)) // true
```