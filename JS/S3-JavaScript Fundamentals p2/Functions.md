
`function` is simply a piece of code that we can reuse over and over again in our code.

in JavaScript **==function is a value==** so we can store it in a variable (anonymous function), and pass it as argument .

So it's a little bit like a variable but for whole chunks of code.

So remember a variable holds value but a function can hold one or more complete lines of code.


```js
//declaration a function
function functionName (/*parmeter*/){
	//body
	return (/*this is what the function will return*/);
}
// call function / running / invoking function
functionName(/*argument*/);
```

==we can call a function before declaration.== (because of a process called hoisting)

so for example, let's imagine a food processor, so we put foot into the processor then the processor does something to our food which is the function body basically and then in the end the food processor returns to processed food.


example
```js
function fruitProcessor (apples , oranges){
	const juice = `Juice with ${apples} apples and ${oranges} oranges`
	return juice ;
}
let result = fruitProcessor(5,2);
console.log(result) //Juice with 5 apples and 2 oranges

//you can do this also
console.log(fruitProcessor(5,2)) //Juice with 5 apples and 2 oranges
```

==this is actually a very important principle for writing clean code and this principle is called don't repeat yourself (dry)==.

What is the difference between parameters and arguments in JavaScript functions?

--> ![[Pasted image 20250610021306.png]]



[[function_declarations_vs_expressions]]
[[Arrow Function]]
