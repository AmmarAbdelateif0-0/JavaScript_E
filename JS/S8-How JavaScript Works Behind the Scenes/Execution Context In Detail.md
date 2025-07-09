
### What's inside Execution Context ?

	1- variable Environment.
	2-Scope Chain.
	3-this Keyword.
so variable environment, scope chain and this keyword is ==generated in a so-called creation phase==.


In this environment, all our variables and function declarations are stored, and there is also a special arguments object.

This object contains, as the name says all the arguments that were passed into the function that the current execution context belongs to.

Because remember each function gets its own execution context as soon as the function is called.

So basically all the variables that are somehow declared inside a function, will end up in its variable environment.

==However, a function can also access variables outside of the function.==

what you need to know is that the scope chain basically consists of references to variables that are located outside of the current function.

Arrow Function -->  don't have the arguments object and the this keyword.