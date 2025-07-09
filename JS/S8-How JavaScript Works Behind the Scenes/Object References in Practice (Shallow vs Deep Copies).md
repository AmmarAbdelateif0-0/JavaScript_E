
To **visually and practically demonstrate** how **object references** work in JavaScript, and how **modifying one object** can affect another when both point to the same data in memory. We'll also learn how to **safely copy objects**, both shallowly and deeply.

---

## 1. **Creating and Referencing an Object**

### Code:

```js
const jessica = {
  firstName: "Jessica",
  lastName: "Williams",
  age: 27,
};
```

### Explanation:

- You created an object `jessica`.
    
- It lives in the **heap** (because it's a non-primitive value).
    
- The variable `jessica` holds a **reference** to the memory location in the heap.
    

---

## 2. **Copying the Object Reference**

### Code:

```js
const marriedJessica = jessica;
marriedJessica.lastName = "Davis";
```


### Explanation:

- `marriedJessica` is **not** a new object.
    
- It’s another **reference to the same memory address** as `jessica`.
    
- When you change `marriedJessica.lastName`, you also change `jessica.lastName`.
    

### Console Output:

```js
console.log("Before:", jessica);
console.log("After:", marriedJessica);
```


**Both show `lastName: "Davis"`**, because it's **the same object**.

---

## 3. **Understanding `const` with Objects**

### Important Rule:

- Declaring an object with `const` **does not make the object immutable**.
    
- You can still **change properties** of that object.
    
- What you **cannot** do is **reassign** the object:
    
 ```js
jessica = { x: 23 }; // ❌ Error
jessica.age = 30;    // ✅ OK
```

    

---

## 4. **Passing Objects to Functions**

### Code:

```js
function marryPerson(originalPerson, newLastName) {
  originalPerson.lastName = newLastName;
  return originalPerson;
}

const marriedJessica = marryPerson(jessica, "Davis");
```


### Explanation:

- When passing an object to a function, only the **reference** is passed.
    
- Any changes made to the object **inside the function** affect the **original object**.
    
- `originalPerson` inside the function and `jessica` outside it point to the **same memory**.
    

---

## 5. **Shallow Copying an Object**

### Code:

```js
const jessica1 = {
  firstName: "Jessica",
  lastName: "Williams",
  age: 27,
  family: ["Alice", "Bob"],
};

const jessicaCopy = { ...jessica1 };
jessicaCopy.lastName = "Davis";
```


### Explanation:

- `{ ...jessica1 }` creates a **shallow copy**.
    
- A **new object** is created in memory with copied **primitive values**.
    
- However, the `family` property is an **array** (which is an object).
    
- So `family` is still **shared** between `jessica1` and `jessicaCopy`.
    

### Consequence:

```js
jessicaCopy.family.push("Mary", "John");
console.log(jessica1.family); // Also contains "Mary", "John"
```


Even though we changed `jessicaCopy.family`, `jessica1.family` also changed. Why?  
Because both point to the **same array object** in the heap.

---

## 6. **Understanding Shallow vs. Deep Copy**

|Term|Meaning|
|---|---|
|**Shallow Copy**|Only copies the **first level**. Nested objects/arrays are still referenced.|
|**Deep Copy**|Copies **everything**, including nested objects/arrays, as **brand-new** values in memory.|

---

## 7. **Deep Copy with `structuredClone()`**

### Code:

```js
const jessicaClone = structuredClone(jessica1);
jessicaClone.family.push("Mary", "John");

```


### Explanation:

- `structuredClone()` creates a **true deep copy**.
    
- All nested structures (like the `family` array) are **fully copied**, not referenced.
    
- Now `jessica1.family` and `jessicaClone.family` are **completely independent**.
    

---

##  Summary of Key Concepts

1. **Objects are stored in the heap**, and variables hold **references** to them.
    
2. Assigning or passing an object means copying the **reference**, not the actual object.
    
3. **Changing an object via one reference changes it for all references.**
    
4. `...` (spread operator) creates a **shallow copy** — only the first level is copied.
    
5. Use `structuredClone()` (or libraries like Lodash in older environments) to make a **deep copy**.