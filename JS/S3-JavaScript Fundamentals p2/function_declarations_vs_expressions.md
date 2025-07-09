* ### declarations as we learned in the last lesson [[Functions]].

==we can call a function before declaration.==

```js
function calcAge ( birthYeaar ){
	return 2025 - birthYeaar;
}
const age = calcAge(2003);
```

----------------------

* ### expression ( ==anonymous function==)

--   anonymous function is a function without a name.

==we can't call a function before write its expression.==
```js
const calcAge = function ( birthYeaar ){
	return 2025 - birthYeaar;
}
const age = calcAge(2003);
```


-----------------------------------------------
