Arrow function was added to JavaScript in ES6.

Arrow function is simply a special form of function expression that is shorter and therefore faster to write .

Great for a quick one-line functions. has no `this` keyword. 

```js
const varName/*function name*/ = (/*parameters*/) => {
//body
return /*the value you want return it*/;
} 
```

* ex1

```js
const clacAge = birthYear => 2025 - birthYear;
// so (2025 - birthYear)  will automatically be returned without us having to explicitly write the return keyword.

const age = clacAge(2003);

```

-------------------------------
* ex2

```js
const yearsUntilRetirement = birthYear => {
	const age = 2025 - birthYear;
	const retirement = 65 - age ;
	return retirement ; 
}

console.log( yearsUntilRetirement(2003) );

```

------------------------------
* ex3

```js
const yearsUntilRetirement = (birthYear , firstName) => {
	const age = 2025 - birthYear;
	const retirement = 65 - age ;
	return `${firstName} retires in ${retirement} years` ; 
}

console.log( yearsUntilRetirement(2003,'Ammar') );

```