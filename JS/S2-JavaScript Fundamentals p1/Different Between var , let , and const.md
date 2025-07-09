
console  actually has access to all the variables that is running in the current browser tab .
<font size="6 " color ="blue">
	<table border="1">
		<th>    </th> <th>var</th> <th>let</th> <th>const </th>
		<tr><td><b>Scope</b></td><td>No</td> <td>Yes</td> <td>Yes</td></tr>
		<tr><td><b>Redeclare</b></td><td>Yes</td> <td>No</td> <td>No</td></tr>
		<tr><td><b>Reassign</b></td><td>Yes</td> <td>Yes</td> <td>No</td></tr>
		<tr><td><b>Binds this</b></td><td>Yes</td> <td>No</td> <td>No</td></tr>
		<tr><td><b>Hosting</b></td><td>Yes</td> <td>No</td> <td>No</td></tr>
		
	
	</table>
</font>
*  **Hosting** -> you can use the variable before it is declared
*  **Binds this** -> mean the variable store in windows variables so you can use this to get this variable 

```js
var x = 10;
console.log(this.x); // 10 ✅ 
```


```js
let y = 20;
console.log(this.y); // undefined ❌
```



`var` -> Global scope
`let` and `const` -> Block Scope

## What is Good?

`let` and `const` have **block scope**.
`let` and `const` can not be **redeclared**.
`let` and `const` must be **declared** before use.
`let` and `const` does **not bind** to `this`.
`let` and `const` are **not hoisted**.

## What is Not Good?

`var` does not have to be declared.
`var` is hoisted.
`var` binds to this.

# const
[[const]]


## without const , var or let

==the js work normally but instead of creating a variable in the current so-called scope ,js will create a property on global object==