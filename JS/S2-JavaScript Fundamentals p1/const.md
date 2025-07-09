
--------------------------------------------------------
## Constant Objects and Arrays

The keyword `const` is a little misleading.
you should initialization const variable ,if didn't do that the syntax Error happen

It does not define a constant value. It defines a constant reference to a value.

**==Because of this you can NOT:==**

- Reassign a constant value
- Reassign a constant array
- Reassign a constant object

**==But you CAN:==**

- Change the elements of constant array
- Change the properties of constant object

---------------------------------------------------
## Constant Arrays

==You can change the elements of a constant array:

### Example
```js
// You can create a constant array:  
const cars = ["Saab", "Volvo", "BMW"];  
  
// You can change an element:  
cars[0] = "Toyota";  
  
// You can add an element:  
cars.push("Audi");
```


==But you can NOT reassign the array:

### Example
```js
const cars = ["Saab", "Volvo", "BMW"];  
  
cars = ["Toyota", "Volvo", "Audi"];    // ERROR
```

---------------------------------------------------------------
## Constant Objects

==You can change the properties of a constant object:

### Example
```js
// You can create a const object:  
const car = {type:"Fiat", model:"500", color:"white"};  
  
// You can change a property:  
car.color = "red";  
  
// You can add a property:  
car.owner = "Johnson";
```



==But you can NOT reassign the object:

### Example

```js
const car = {type:"Fiat", model:"500", color:"white"};  
  
car = {type:"Volvo", model:"EX60", color:"red"};    // ERROR
```

