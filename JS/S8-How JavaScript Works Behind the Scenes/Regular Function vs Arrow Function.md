In JavaScript, regular functions and arrow functions behave differently in how they handle the `this` keyword. This difference can lead to bugs if not properly understood, especially when writing methods inside objects.

---

## Key Rule

**Arrow functions do not have their own `this`.**  
They inherit `this` from their parent (surrounding) scope.

---

## 1. Arrow Function as an Object Method

### Problem

Suppose we define an object like this:

```js
const jonas = {
  firstName: 'Jonas',
  greet: () => {
    console.log(`Hey ${this.firstName}`);
  }
};

jonas.greet(); // Output: "Hey undefined"
```

### Explanation

- The arrow function in `greet` does not have its own `this`.
    
- It inherits `this` from the global scope (`window` in browsers).
    
- `window.firstName` is undefined unless explicitly set, so the result is `"Hey undefined"`.
    

### Dangerous Side Effect with `var`

```js
var firstName = 'Matilda';
jonas.greet(); // Output: "Hey Matilda"
```

This happens because `var` declarations in the global scope create properties on the `window` object. So `window.firstName` becomes `'Matilda'`.

### Correct Approach: Use Regular Function

```js
const jonas = {
  firstName: 'Jonas',
  greet() {
    console.log(`Hey ${this.firstName}`);
  }
};

jonas.greet(); // Output: "Hey Jonas"
```

Regular functions get their own `this`, which refers to the object that calls the method.

---

## 2. Function Inside a Method

Suppose we want to check if `jonas` is a millennial:

```js
const jonas = {
  year: 1991,
  calcAge: function () {
    console.log(2037 - this.year);

    function isMillennial() {
      console.log(this.year >= 1981 && this.year <= 1996);
    }

    isMillennial();
  }
};

jonas.calcAge();
```
### Problem

- Inside `calcAge`, `this` correctly refers to `jonas`.
    
- But inside `isMillennial`, `this` is undefined, because it's a regular function call.
    
- This causes an error: `Cannot read property 'year' of undefined`.
    

### Solution 1: Use a Variable to Store `this`

```js
calcAge: function () {
  console.log(2037 - this.year);
  const self = this;

  function isMillennial() {
    console.log(self.year >= 1981 && self.year <= 1996);
  }

  isMillennial();
}
```

This was the common workaround before ES6.

### Solution 2: Use an Arrow Function

```js
calcAge: function () {
  console.log(2037 - this.year);

  const isMillennial = () => {
    console.log(this.year >= 1981 && this.year <= 1996);
  };

  isMillennial();
}
```

Arrow functions inherit `this` from their parent scope, which in this case is the `calcAge` method. Since `this` in `calcAge` refers to `jonas`, the arrow function can access `this.year` correctly.

---

## 3. The `arguments` Keyword

### Regular Functions

```js
const addExpr = function (a, b) {
  console.log(arguments);
  return a + b;
};

addExpr(2, 5, 8); // Output: Arguments(3) [2, 5, 8]
```

Regular functions have access to the special `arguments` object, which holds all arguments passed to the function, even if they are not declared in the parameter list.

### Arrow Functions

```js
const addArrow = (a, b) => {
  console.log(arguments); // ReferenceError
  return a + b;
};

addArrow(2, 5, 8);
```

Arrow functions do not have the `arguments` object.

### Modern Alternative

Use the rest parameter syntax:

```js
const add = (...args) => {
  console.log(args); // [2, 5, 8]
};
```

---

## Summary of Differences

|Feature|Regular Function|Arrow Function|
|---|---|---|
|Has its own `this`|Yes|No|
|Can be used as a method|Yes|Not recommended|
|Has `arguments` object|Yes|No|
|Suitable for callbacks|Yes|Yes|
|Inherits `this`|No|Yes (from parent scope)|

---

## Best Practices

- Always use **regular functions** for methods inside objects.
    
- Use **arrow functions** for short callbacks or when you want to inherit `this`.
    
- Avoid using `var` to prevent unexpected `this` behavior in the global scope.
    
- Prefer rest parameters over `arguments` in modern JavaScript.