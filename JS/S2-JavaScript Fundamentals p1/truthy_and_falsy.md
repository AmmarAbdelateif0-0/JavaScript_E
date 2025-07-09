
##### - `falsy values`  : are values that are not exactly false   but will become false when we try to convert them into  Boolean.

in JavaScript there are only five falsy values.

- 5 falsy values are : ( 0 , '' ,undefined , null , NaN ).

to convert to Boolean we use the `Boolean()` function

```js
console.log(Booleab (0)); // false
console.log(Booleab ('')); // false
console.log(Booleab (undefined)); // false
console.log(Booleab (null)); // false
console.log(Booleab (NaN)); // false
```
------------------------------------
##### - `truthy values` : are any other values that are not exactly false   but will become false when we try to convert them into  Boolean.
==اي قيمة اخر مش falsy values.==



----------------------------------------------

```js
let he ; // undefined
if(he){ // type coercion
	console.log('he is a good man');
}else{
	console.log('he is a falsy value');
}
```