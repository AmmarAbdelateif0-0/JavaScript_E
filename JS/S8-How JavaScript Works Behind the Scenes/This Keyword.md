The `this` keyword is a special variable in JavaScript that is created for every execution context. It is one of the three key components of an execution context, along with the variable environment and the scope chain.

---

### Key Characteristics of `this`

- The value of `this` is not fixed.
    
- It is determined at the time the function is called.
    
- It depends on how the function is called, not where it is defined.
    

---

## Ways `this` is Determined

### 1. Method Call (Function attached to an object)

When a function is called as a method of an object, `this` refers to the object the method belongs to.

**Example:**
```js
const person = {
  name: 'Jonas',
  year: 1989,
  calcAge: function () {
    console.log(this.year);
  }
};

person.calcAge(); // Output: 1989
```

In this example, `this` refers to the `person` object.

---

### 2. Regular Function Call

When a function is called normally (not as a method), `this` behaves differently depending on strict mode:

- In strict mode: `this` is `undefined`
    
- In non-strict mode: `this` is the global object (`window` in browsers)
    

**Example:**

```js
"use strict";
function showThis() {
  console.log(this); // Output: undefined
}

showThis();
```

---

### 3. Arrow Functions

Arrow functions do not have their own `this`. They inherit `this` from the surrounding lexical scope.

**Example:**

```js
const person = {
  year: 1989,
  greet: function () {
    const inner = () => {
      console.log(this.year);
    };
    inner();
  }
};
person.greet(); // Output: 1989
```

Here, `this` in the arrow function refers to the `person` object because it is inherited from the `greet` method.

---

### 4. Event Listeners

When a function is used as an event handler, `this` refers to the DOM element that the event handler is attached to.

**Example:**

```js
const button = document.querySelector('button');

button.addEventListener('click', function () {
  console.log(this); // Output: the button element
});
```

---

### What `this` Does Not Refer To

- `this` does not refer to the function itself.
    
- `this` does not refer to the variable environment.
    

---

### Other Invocation Types

Other ways to invoke functions, such as using the `new` keyword or the `call`, `apply`, and `bind` methods, also affect the value of `this`. These will be discussed separately.

---

## Summary Table

|Invocation Type|`this` Refers To|
|---|---|
|Method|The object that owns the method|
|Regular Function|`undefined` in strict mode, or `window`|
|Arrow Function|The `this` value from the surrounding scope|
|Event Listener|The DOM element that receives the event|