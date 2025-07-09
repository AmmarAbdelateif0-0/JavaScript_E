#### **1. What Is Memory Management?**

Memory management is how JavaScript handles:

- **Allocating memory** when you create a variable
    
- **Using memory** when the value is accessed or updated
    
- **Freeing memory** when the value is no longer needed
    

In JavaScript, this is done **automatically** behind the scenes, unlike in lower-level languages like C or C++.

---

#### **2. Types of Values in JavaScript**

JavaScript has two main types of values:

- **Primitive values:**  
    These include `number`, `string`, `boolean`, `undefined`, `null`, `symbol`, and `bigint`.  
    These are simple values stored directly.
    
- **Objects:**  
    Everything else is an object. This includes arrays, functions, and objects created using `{}`.
    

---

#### **3. Memory Areas: Stack and Heap**

- **Call Stack:**  
    Stores primitive values and keeps track of function calls.
    
- **Heap:**  
    Stores objects and functions.
    

---

#### **4. Primitive Values Are Stored in the Stack**

When you create a primitive value:

```js
let age = 25;

```

JavaScript stores the value `25` directly in the stack.

If you copy it:

```js
let newAge = age;
newAge++;
```

Each variable holds its own **copy** of the value. Changing `newAge` does not affect `age`.

---

#### **5. Objects Are Stored in the Heap**

Objects are more complex and stored in a different area — the heap. But the variable itself doesn’t store the object directly; it stores a **reference** to it.

```js
let location = { city: "Cairo" };
let newLocation = location;
newLocation.city = "Alex";
```

Both `location` and `newLocation` point to the **same** object in the heap. Updating one will affect the other.

---

#### **6. Variables Store References to Objects**

When you assign an object to another variable:

```js
let user = { name: "Ammar" };
let admin = user;
```

Both `user` and `admin` reference the **same** object in memory. If you change `admin.name`, the change appears in `user` too.

---

#### **7. Functions Are Also Objects**

Functions are stored in the heap as well:

```js
function greet() {
  console.log("Hello");
}
```

Here, `greet` holds a **reference** to a function object in the heap.

---

#### **8. Summary**

- **Primitive values** (like numbers and strings) are stored in the **stack**.
    
- **Objects and functions** are stored in the **heap**.
    
- Variables that hold objects store only a **reference**, not the object itself.
    
- **Copying a reference** does not create a new object; it just creates another pointer to the same object.