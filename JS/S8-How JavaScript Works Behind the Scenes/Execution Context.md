
### What's an Execution Context ?
	Environment in which a piece of JavaScript is executed. Stores all the necessary information for some code to be executed (Such as local variables or arguments passed into a function).
	
-> summary (which a piece of JavaScript is executed with anything he needs when executed)

JavaScript code always runs inside an execution context.

in this step the code become " Machine code " and now ready to be executed . 

example to make this a bit more intuitive.
![[Pasted image 20250620111322.png]]


![[Pasted image 20250620113135.png]]


--------------------------------------------------------------

steps for Execution Content :

* Creation of global execution context (For top-level code (Not inside a function) )
	
	in the beginning only the code that is outside of functions will be executed.
	
	Functions should only be executed when they are called.
	
	But the code inside the functions, will only be executed when the functions are called.

	in any JavaScript project, no matter how large it is, there is only ever one global execution context .
	
	==Exactly one global execution context (EC): Default context, created for code that is not inside any function (top-level).==
	
--------------------------------------------------------

* Execution of top-level code (inside global EC)
	
	it's just the computer CPU processing the machine code that it received.

--------------------------------------------------------------

* Execution of functions and waiting for callbacks.

	One execution context per function: ==For each function call, a new execution context is created.==

	For each and every function call, and you execution context will be created containing all the information that is necessary to run exactly that function.

	And the same goes for methods, of course, because they're simply functions attached to objects.

---------------------------------------------

 all these execution contexts together, make up the call stack.


when all functions are done executing, the engine will basically keep waiting for callback functions to arrive so that it can execute these.

For example: 

a callback function associated with a click event.

And remember, that it's the event loop who provides these new callback functions


