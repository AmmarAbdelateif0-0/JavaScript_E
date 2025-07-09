
* ==`type conversion`== ->is when we manaually convert from one type to another.
	java Script can only convert to three type     a- to string .
								     b- to number. 
								     c-to boolean (truthy and falsy).
```js
let inputYear = "1991";;
console.log(inputYear + 22); //199120
// to convert inputyear to int to add the age 
console.log(number(inputYeat) +22); // 2013
```

a- to convert str to number
```js 
// we use Number() 
//if the string only number
let Year = "2020";
console.log(Number(Year) + 5) // 2025
//if the string is not only numbers
console.log(Number('ammar')) // NaN (Not a number)
console.log(typeof NaN) // number (INVAILID Numbwe)
```
b- to convert number to str
```js
// we use String()
let number = 333;
console.log(String(number)); // "333"
```
c- truthy and falsy values [[truthy_and_falsy]]

in practice, the conversion to Boolean is always implicit (coercion) , not explicit (conversion) .

always happen in if statement expression .

----------------------------------------------------------------------


* ==`type coercion`== -> is when JavaScript automatically converts types behind the scenes for us (implicitly).
	type coercion happens whenever an operator is dealing with two values that have different types.

a-convert number to string 
```js
	console.log("I'am" + 23 + "years old"); // "I'am 23 years old"
	/* in this example js convert 23 to string 
	and concatenate this strings to one*/
```

b-convert string to number and do some arithmatic operation ( - , * ,  / , ** )

```js
console.log('23' - '10' - 3) // 10 as a number not string
```





----------------------------------------
example to consolidate your understanding
```js
let n = '1' + 1;
n = n - 1 ;
console.log( n ); // 10 as a number
```

```js
console.log(2 + 3 + 4 + '5'); // 95
// first sum the number 2 + 3 +4 = 9
// seconod concatenate the sum with the 5 
// output : '95'
```

```js
let n = '10' - '4' - '3' - 2 + '5'
// first convert  string to number 
// second do - operations so the output : 10 - 4 - 3 - 2 = 1
// third convet number to string and concatenate
// output : '15'
```

