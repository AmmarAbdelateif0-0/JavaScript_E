
### **What is a Callback Function in JavaScript?**

A **callback function** is a function that is **passed as an argument to another function**, and it is **executed later**, usually after some kind of event or operation.

---

### **Basic Example:**

```js
function greet(name) {
  console.log(`Hello, ${name}`);
}

function processUserInput(callback) {
  const name = "Ammar";
  callback(name); // Calling the callback
}

processUserInput(greet);

```
#### What happens here?

- `greet` is passed to `processUserInput` as a **callback**.
    
- Inside `processUserInput`, the callback is **called with the name**.
    

---

### **Common Use Case: setTimeout**

```js
setTimeout(() => {
  console.log("This runs after 2 seconds");
}, 2000);

```

Here, the arrow function is a **callback**. It's executed **after 2000 milliseconds**.

---

### **Why Use Callbacks?**

- To **wait** for something to finish (e.g., a timer, a request).
    
- To make code **asynchronous** (not blocking).
    
- To allow **custom behavior** to be injected into functions.

-----------------------------------------------------------------------
## 1. **Basic Math Example**

You can pass any function as a callback—even math operations:

```js
function calculate(a, b, operation) {
  return operation(a, b); // callback
}

function add(x, y) {
  return x + y;
}

function multiply(x, y) {
  return x * y;
}

console.log(calculate(5, 3, add));      // 8
console.log(calculate(5, 3, multiply)); // 15

```

### Explanation:

- `calculate` takes two numbers and a **callback**.
    
- You choose what operation (add, multiply) by passing the function.
    

---

## 2. **Sorting with a Callback**

```js
const numbers = [10, 5, 2, 20];

numbers.sort(function(a, b) {
  return a - b; // sort in ascending order
});

console.log(numbers); // [2, 5, 10, 20]

```
- Here, the callback `(a, b) => a - b` tells `.sort()` **how to compare** numbers.
    

---

## 3. **Using setTimeout (Asynchronous)**

```js
console.log("Start");

setTimeout(() => {
  console.log("Callback after 2 seconds");
}, 2000);

console.log("End");

```

### Output:

```js
Start
End
Callback after 2 seconds

```

- The callback is **delayed**, but the rest of the code keeps running.
    

---

## 4. **Click Event Callback (Browser)**

```html
<button id="myBtn">Click me</button>

<script>
  document.getElementById("myBtn").addEventListener("click", function () {
    alert("Button clicked!");
  });
</script>

```

- The function passed to `addEventListener` is a **callback** that runs **only when** the user clicks the button.
    

---

## 5. **Custom Callback Example**

```js
function fetchData(callback) {
  console.log("Fetching data...");

  setTimeout(() => {
    const data = { name: "Ammar", age: 22 };
    callback(data);
  }, 1000);
}

function showData(info) {
  console.log("Received:", info);
}

fetchData(showData);

```
### Output:

```js
Fetching data...
Received: { name: 'Ammar', age: 22 }
```

- `fetchData` simulates a data fetch and **passes the result** to the `showData` callback.
    

---

## Summary

|Concept|Description|
|---|---|
|Callback|A function passed into another function|
|Purpose|Delay execution or customize behavior|
|Common uses|Event handling, async code, array methods|