

**Hoisting** : Makes some types of variables accessible/usable in the code before they are actually declared. “Variables lifted to the top of their scope”.

many people simply define hoisting by saying that variables are magically lifted or moved to the top of their scope `For Example`, to the top of a function.

	BEHIND THE SCENES 

**Before execution**, ==code is scanned for variable declarations==, and for each variable, a new property is created in the variable environment object.

So this happens during the so-called creation phase of the execution context that we talked about before.

Then for each variable that is found in the code, a new property is created in a variable environment object And that's how hoisting really works.


![[Pasted image 20250622100709.png]]

TDZ -> Temporal Dead Zone which makes it so that we can't access the variables between the beginning of the scope and to place where the variables are declared.

TDZ start from the beginning of the scope until the line where the variable is defined. 


==we can use function declarations== before they are actually declared in the code, again, ==because they are stored in the variable environment object==, even before the code starts executing.

![[Pasted image 20250622102940.png]]

in fact in the Temporal Dead Zone where it is still initialized, but the engine knows that it will eventually be initialized because it already read the code before and set the job variable in the variable environment to uninitialized.

Then when the execution reaches the line where the variable is declared, it is removed from the Temporal Dead Zone and it's then safe to use.

[[Hosting In Practice]]

[[Different Between var , let , and const]]
