Both **spread** and **rest** use the same syntax: `...` (three dots), but they do **opposite things** depending on where you use them.

---

### 1. Spread Operator – Used to Unpack Values

The **spread operator** is used to **unpack** values from an array (or object) into individual elements.
#### Common Use Cases:

- To create a new array by expanding another array
- To pass array elements as separate arguments to a function
    

#### Example:
```js
const arr = [3, 4, 5];
const newArr = [1, 2, ...arr];
console.log(newArr); // [1, 2, 3, 4, 5]
```
Here, `...arr` unpacks the values inside `arr` into the new array.

we know that this is the spread syntax because we are using it on the right hand side of the assignment operator, so of the equal sign.

---

### 2. Rest Pattern – Used to Collect Values

The **rest pattern** is the opposite: it **collects** multiple elements and **packs** them into a new array (or object).

#### Use Cases:

- In **array or object destructuring**
    
- In **function parameters** (called rest parameters)
    

---

### A. Rest Pattern in Array Destructuring

```js
const numbers = [1, 2, 3, 4, 5];

const [a, b, ...others] = numbers;

console.log(a);      // 1
console.log(b);      // 2
console.log(others); // [3, 4, 5]

const [pizza , , risotto , ...otherFood] = [...restaurant.mainMenu,...restaurant.startMenu];

```
Rest , because in Left Side if = operator

Explanation:

- `a` gets the first value
- `b` gets the second
- `others` collects the **rest of the values** into an array
    

**Important rule**:  
==The rest element must always be **last** in the destructuring assignment.==

---

### B. Rest Pattern in Object Destructuring

```js
const openingHours = {
  thu: { open: 12, close: 22 },
  fri: { open: 11, close: 23 },
  sat: { open: 0, close: 24 },
};

const { sat, ...weekdays } = openingHours;

console.log(sat);      // { open: 0, close: 24 }
console.log(weekdays); // { thu: {...}, fri: {...} }
```

Explanation:

- `sat` is extracted into its own variable
- `weekdays` collects the **remaining properties** into a new object
    

---

### 3. Rest Parameters in Functions

The **rest parameters** syntax allows a function to accept **any number of arguments**, packing them into an array.

```js
function add(...numbers) {
  let sum = 0;
  for (let i = 0; i < numbers.length; i++) {
    sum += numbers[i];
  }
  console.log(sum);
}

add(2, 3);           // 5
add(5, 3, 7, 2);     // 17
add(8, 2, 5, 3, 2);  // 20
```

Explanation:

- All the arguments passed to the function are packed into the `numbers` array.
    

---

### 4. Spread and Rest Working Together

You can use **spread** when calling the function, and the **rest parameter** will collect the arguments inside the function.

```js
const x = [23, 5, 7];

add(...x); // 35
```

Explanation:

- `...x` spreads the values
- Inside the function, `...numbers` collects them again

This is useful because it allows calling a function:

- With an array (`add(...x)`)
- Or with direct values (`add(1, 2, 3)`)

---

### 5. Real-Life Example: Pizza Order Function

Sometimes you want to require one argument and allow optional extra arguments. This is a perfect use case for rest parameters.

```js
const restaurant = {
  orderPizza: function (mainIngredient, ...otherIngredients) {
    console.log(mainIngredient);
    console.log(otherIngredients);
  },
};

restaurant.orderPizza('mushrooms', 'onion', 'olives', 'spinach');
// mushrooms
// ['onion', 'olives', 'spinach']

restaurant.orderPizza('cheese');
// cheese
// []
```
Explanation:

- The first value is stored in `mainIngredient`
- The remaining values go into the `otherIngredients` array
- If there's only one value, `otherIngredients` becomes an empty array

---

### Summary: Key Differences Between Spread and Rest

|Feature|Spread|Rest|
|---|---|---|
|Syntax|`...`|`...`|
|Direction|Unpacks values|Packs values|
|Used in|Function calls, array/object literals|Destructuring, function parameters|
|Output|Individual elements|A new array or object|
|Position|Right side of `=` or in function calls|Left side of `=` or function params|
