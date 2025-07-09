
### 1-parsing

Parsing : which essentially means to read the code, and checks if there are any syntax errors.

During the parsing process, the code is parsed into a data structure called the abstract syntax tree or AST.

![[Pasted image 20250620103104.png]]

 AST : This works by first splitting up each line of code into pieces that are meaningful to the language like the const or function keywords, and then saving all these pieces into the tree in a structured way.
 
the resulting tree will later be used to generate the machine code.

is this tree has anything to do with the DOM tree ? 
	this tree has absolutely nothing to do with the DOM.

----------------
### 2-compilation

compilation : which takes the generated AST and compiles it into machine code.

This machine code then gets executed right away because remember modern JavaScript engine use just-in-time compilation.

--------------------------------
### 3-Execution

running the machine code 

remember execution happens in the JavaScript engines call stack.

------------------------------------------
### 4-Optimization

==modern JavaScript== engines actually have some ==pretty clever optimization strategies.==

==What they do is to create a very unoptimized version of machine code in the beginning just so that it can start executing as fast as possible.==

Then in ==the background==, ==this code is being optimized and recompiled during the already running program execution.==

And this can be done most of the times and ==after each optimization the unoptimized code is simply swept for the new more optimized code without ever stopping execution of course.==

![[Pasted image 20250620103845.png]]