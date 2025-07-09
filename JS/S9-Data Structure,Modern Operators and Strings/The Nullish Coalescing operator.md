
The **nullish coalescing operator** is a new operator introduced in **ES2020**, and although its name might sound strange, it serves a very practical purpose:

> **It allows us to set default values only when a variable is `null` or `undefined` — not when it is `0` or `""` (empty string).**

---

###  Background: The Problem with the OR (`||`) Operator

Previously, we used the **OR operator (`||`)** to set default values:

```js
const numGuests = 0;
const guests = numGuests || 10;
console.log(guests); // Output: 10 ❌ (unexpected)
```

#### Why is this wrong?

Because `0` is treated as a **falsy value**, JavaScript **ignores it** and moves to the second operand (`10`). But we **do want to allow `0`** as a valid number of guests.

This is a problem when you want to keep values like:
- `0` (zero)
- `""` (empty string)

Those are **falsy**, but **not invalid** in many cases.

---

### Solution: `??` Nullish Coalescing Operator

The **nullish coalescing operator (`??`)** solves this issue by only treating **`null` or `undefined`** as "missing" values.

```js
const numGuests = 0;
const guests = numGuests ?? 10;
console.log(guests); // Output: 0 ✅ (correct)
```

#### Now:
- If `numGuests` is `0`, it will be **kept**.
- If `numGuests` is `undefined` or `null`, only then `10` is used.

---

###  How It Works (Conceptually)

- `??` is similar to `||`, but:
    - `||` uses **falsy values**: `false`, `0`, `""`, `null`, `undefined`, `NaN`
    - `??` uses **nullish values only**: `null`, `undefined`

---
### More Examples:

```js
console.log(null ?? 'Default');        // 'Default'
console.log(undefined ?? 'Default');   // 'Default'
console.log(0 ?? 'Default');           // 0
console.log('' ?? 'Default');          // ''
console.log(false ?? 'Default');       // false
```
###  Compared to OR (`||`):

```js
console.log(0 || 'Default');           // 'Default' ❌
console.log('' || 'Default');          // 'Default' ❌
```
---

###  Use Case: Safer Defaults

Let’s say you have this object:

```js
const restaurant = {
  name: 'Italian Bistro',
  numGuests: 0,
};
```
Using `||`:

```js
const guests = restaurant.numGuests || 10;
console.log(guests); // 10 ❌
```

Using `??`:

```js
const guests = restaurant.numGuests ?? 10;
console.log(guests); // 0 ✅
```

Now it behaves as expected.

---

###  Common Mistake

Don't confuse `??` with `||` — they are similar in structure but **very different in behavior**.  
Use `??` only when you want to handle `null` or `undefined` — not other falsy values like `0` or `""`.

---

###  Summary

| Operator | Checks For              | Example   | Result               |
| -------- | ----------------------- | --------- | -------------------- |
| `        |                         | `         | **All falsy values** |
| `??`     | **Only null/undefined** | `0 ?? 10` | `0` ✅                |

> Use `??` when `0` or `""` should be treated as **valid**, not missing.