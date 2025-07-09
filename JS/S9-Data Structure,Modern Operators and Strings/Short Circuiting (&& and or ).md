In JavaScript, logical operators like `||` (OR) and `&&` (AND) are often used with **Boolean values**, but they can also work with **any data type**, and return **non-Boolean values**.

This leads to a powerful concept called **short-circuiting**.

---

### 1. The OR (`||`) Operator

The `||` operator **returns the first truthy value** it finds or ==the **last value** if none are truthy==.

#### Rules:
- It **stops** as soon as it finds a **truthy** value (short-circuiting).
- If **all values are falsy**, it returns the **last one**.

#### Examples:

```js
console.log(3 || 'Jonas');         // 3
console.log('' || 'Jonas');        // 'Jonas'
console.log(true || 0);            // true
console.log(undefined || null);    // null
```
#### Explanation:

- `3 || 'Jonas'`: 3 is truthy → returned.
- `'' || 'Jonas'`: empty string is falsy → continues to 'Jonas', which is truthy.
- `true || 0`: true is truthy → returned.
- `undefined || null`: both are falsy → returns the last one, null.

---

### Chained Example:

```js
console.log(undefined || 0 || '' || 'hello' || 23 || null);  // 'hello'
```

**Why?**
- All values before `'hello'` are falsy.
- `'hello'` is the first truthy value → short-circuit → returned.

---

### Practical Example: Setting Default Values

Suppose we want to set a default number of guests for a restaurant:

```js
const restaurant = {};
const guests1 = restaurant.numGuests || 10;
== const guests2 = restaurant.numGuests ? restaurant.numGuests : 10; 
console.log(guests1); // 10
```

If `restaurant.numGuests` is `undefined`, the default `10` will be used.

---

### Problem: What if `numGuests = 0`?

```js
restaurant.numGuests = 0;
const guests2 = restaurant.numGuests || 10;
console.log(guests2); // 10 ❌
```

This gives `10`, which is incorrect — we **do have** 0 guests, but 0 is a **falsy** value.

We'll solve this issue using the **nullish coalescing operator (`??`)**, but that's for the next lesson.

---

## 2. The AND (`&&`) Operator

The `&&` operator **returns the first falsy value** or the **last value** if all are truthy.

#### Rules:

- It **stops** when it finds a **falsy** value.
- If **all values are truthy**, it returns the **last** one.

#### Examples:

```js
console.log(0 && 'Jonas');         // 0
console.log(7 && 'Jonas');         // 'Jonas'
```
#### Explanation:

- `0 && 'Jonas'`: 0 is falsy → returned.
- `7 && 'Jonas'`: 7 is truthy → continues and returns 'Jonas'.


---

### Chained Example:

```js
console.log('Hello' && 23 && null && 'Jonas');  // null
```

**Why?**

- 'Hello' is truthy → continue
- 23 is truthy → continue
- `null` is falsy → stop and return `null`
- `'Jonas'` is never evaluated

---

### Practical Use: Optional Function Call

Instead of writing:

```js
if (restaurant.orderPizza) {
  restaurant.orderPizza('mushrooms', 'spinach');
}
```

You can write:

```js
restaurant.orderPizza && restaurant.orderPizza('mushrooms', 'spinach');
```

**Explanation**:  
If `orderPizza` exists (truthy), it is called.  
If it's `undefined` or falsy, nothing happens.  
This avoids using a full `if` statement.

---

## Summary

### OR (`||`) Operator

- Returns the **first truthy** value.
- If all are falsy → returns the **last**.
- Useful for setting **default values**.
- Short-circuits when it finds a **truthy** value.

### AND (`&&`) Operator

- Returns the **first falsy** value.
- If all are truthy → returns the **last**.
- Useful for executing **code only if a condition is true**.
- Short-circuits when it finds a **falsy** value.

---

### Final Notes

- Logical operators don’t return `true` or `false` by default — they return the actual value that caused the short-circuit.
- Don't overuse short-circuiting to replace all `if` statements — use it when it improves clarity.
- To fix the issue with `0` being treated as falsy in defaults, the **nullish coalescing operator (`??`)** is recommended (covered in the next lesson).