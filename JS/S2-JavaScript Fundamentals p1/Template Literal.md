- normal concatenation
```js
let name = "ammar";
let age =22;
let job = "learner"
let fullInfo = "I'm" + name + ",a " + age + "years old"+job+"!" 
```


- concatenation using Template Literal
in template literal  write the string between -`backtick`
if you're using the variables you use the ${ } and write the variable name inside.

```js
let name = "ammar";
let age =22;
let job = "learner"
let fullInfo =`I'm ${name} ,a ${age} years old ${job}`
```



- some developers actually started using `backtick` for all string instead of thinking about which quotation marks you should use.