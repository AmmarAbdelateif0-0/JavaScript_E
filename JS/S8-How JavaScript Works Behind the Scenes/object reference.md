### 🔹 What Is an Object Reference?

When you assign an object to a variable in JavaScript, **the variable doesn't store the object itself**.  
Instead, it stores a **reference (a pointer)** to the location of the object in memory (the heap).

---

###  Example 1: Assigning an Object to a Variable

```js
const user = {
  name: "Ammar",
  age: 25
};

```
Here:

- The object `{ name: "Ammar", age: 25 }` is stored in the **heap**.
    
- The variable `user` holds a **reference** to that object.
    

---

###  Example 2: Copying an Object Reference

```js
const user = {
  name: "Ammar",
  age: 25
};

const admin = user;

admin.age = 30;

console.log(user.age);  // 30

```

**Explanation:**

- `admin = user` does **not** create a new object.
    
- It copies the **reference**, so both `admin` and `user` point to the **same** object in memory.
    
- Changing `admin.age` also changes `user.age`, because it's **one object with two names**.
    

---

### ❗ Why Is This Important?

This can lead to **unexpected behavior** if you think you're copying an object, but you're actually copying a reference.

---

###  Example 3: Comparing Object References

```js
const obj1 = { value: 10 };
const obj2 = { value: 10 };
const obj3 = obj1;

console.log(obj1 === obj2); // false
console.log(obj1 === obj3); // true
```

**Why?**

- `obj1` and `obj2` are two different objects (even though they look the same).
    
- `obj3` is a reference to `obj1`, so they point to the **same** object.
    

---

###  Example 4: Cloning an Object to Avoid Reference Sharing

If you want to **copy the contents** instead of the reference, use:

#### Option 1: `Object.assign()`

```js
const original = { name: "Ammar" };
const copy = Object.assign({}, original);

copy.name = "Ali";

console.log(original.name); // "Ammar"
console.log(copy.name);     // "Ali"
```
#### Option 2: Spread Syntax

```js
const original = { name: "Ammar" };
const copy = { ...original };

copy.name = "Ali";

console.log(original.name); // "Ammar"
console.log(copy.name);     // "Ali"

```

These methods create a **shallow copy**, meaning they only copy **top-level properties**.