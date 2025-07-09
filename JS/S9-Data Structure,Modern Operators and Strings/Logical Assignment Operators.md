JavaScript introduced **three new logical assignment operators** in **ES2021** to make certain expressions more concise and readable, especially when dealing with default values or conditional assignments.

These are:
1. `||=` (Logical OR assignment)
2. `&&=` (Logical AND assignment)
3. `??=` (Logical Nullish assignment)

Let’s break down each one with examples and practical use cases.

---

## 1. **Logical OR Assignment (`||=`)**

### **Purpose**:

Assigns a value to a variable **only if that variable is currently falsy** (e.g. `0`, `""`, `null`, `undefined`, `false`, `NaN`).

### **Example**:

Suppose you receive restaurant data from an API, but some restaurants may not have a `numGuests` property set.

```js
const rest1 = { name: "Capri", numGuests: 20 };
const rest2 = { name: "La Piazza" }; // no numGuests
```

Instead of writing:

```js
rest1.numGuests = rest1.numGuests || 10;
rest2.numGuests = rest2.numGuests || 10;
```

You can use the **OR assignment**:

```js
rest1.numGuests ||= 10;
rest2.numGuests ||= 10;
```


### **How it works**:

- If `rest1.numGuests` is **truthy**, it stays as is (20).
- If `rest2.numGuests` is **falsy** (in this case `undefined`), it becomes `10`.

###  Caveat:

If `numGuests` is `0` (which is a valid number), this operator **will still override it**, because `0` is falsy.


```js
rest2.numGuests = 0;
rest2.numGuests ||= 10; // Now it becomes 10 ❌ (unwanted behavior)
```

---

## 2. **Logical Nullish Assignment (`??=`)**

### **Purpose**:

Assigns a value to a variable **only if that variable is `null` or `undefined`** — not `0` or empty string.

### **Example**:

```js
rest2.numGuests = 0;
rest2.numGuests ??= 10;
console.log(rest2.numGuests); // Output: 0 ✅
```

### **Why it works**:

- The value `0` is not `null` or `undefined`, so it **doesn't get overridden**.
- Use this when you **want to allow valid falsy values** (like `0` or `""`) to stay unchanged.

---

## 3. **Logical AND Assignment (`&&=`)**

### **Purpose**:

Assigns a value **only if the variable is currently truthy**.
### **Use Case**:

You want to **anonymize** the `owner` property of a restaurant **only if it exists**.


```js
const rest1 = { name: "Capri" };
const rest2 = { name: "La Piazza", owner: "Giovanni Rossi" };

// Instead of:
if (rest2.owner) {
  rest2.owner = "ANONYMOUS";
}

// Use:
rest2.owner &&= "ANONYMOUS"; 
```

### **What happens**:

- `rest2.owner` exists and is a non-empty string (truthy), so it is updated.
- `rest1.owner` doesn't exist (undefined, falsy), so nothing happens.

---

## Summary Table

|Operator|Description|Assigns if...|Example Result|
|---|---|---|---|
|`||=`|Assigns only if variable is falsy|
|`??=`|Assigns only if variable is null or undefined|Variable is nullish|`null`, `undefined`|
|`&&=`|Assigns only if variable is truthy|Variable is truthy|`"hello"`, `123`, `true`|

---

## When to Use Each Operator

- Use `||=` when you want a **default fallback** value, but **don’t care** if `0`, `""`, or `false` are overwritten.
    
- Use `??=` when you want to **preserve valid falsy values** like `0`, `""`, or `false`.
    
- Use `&&=` when you want to **conditionally update a property** only if it already exists.