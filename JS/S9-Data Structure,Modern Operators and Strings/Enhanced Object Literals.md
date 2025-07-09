### **What Are Enhanced Object Literals?**

Enhanced Object Literals are a feature introduced in **ES6** that make it easier and shorter to define objects. They provide a more concise and flexible syntax when defining object properties and methods.

Let’s explore the **three key enhancements** this feature offers:

---

### **1. Shorthand for Property Assignment**

**Before ES6:**

When you define an object and want to include a variable as a property, you had to do this:

```js
const openingHours = { /*...*/ };

const restaurant = {
  name: 'Classico Italiano',
  openingHours: openingHours  // full assignment
};
```

**With Enhanced Object Literals:**

If the property name and variable name are the same, you can just write:

```js
const restaurant = {
  name: 'Classico Italiano',
  openingHours  // shorthand
};
```

> This works because JavaScript understands to use the variable name as both the key and the value.

---

### **2. Shorthand for Defining Methods**

**Before ES6:**

```js
const restaurant = {
  order: function(starterIndex, mainIndex) {
    return [this.starterMenu[starterIndex], this.mainMenu[mainIndex]];
  }
};
```
**With Enhanced Object Literals:**

```js
const restaurant = {
  order(starterIndex, mainIndex) {
    return [this.starterMenu[starterIndex], this.mainMenu[mainIndex]];
  }
};
```

> You no longer need the `function` keyword or a colon. It’s cleaner and easier to read.

---

### **3. Computed Property Names**

This allows you to use **expressions** as property keys.

**Example:**
```js
const weekdays = ['mon', 'tue', 'wed', 'thu', 'fri', 'sat', 'sun'];

const openingHours = {
  [weekdays[3]]: { open: 12, close: 22 },   // thu
  [weekdays[4]]: { open: 11, close: 23 },   // fri
  ['day-' + (2 + 4)]: { open: 0, close: 24 } // day-6
};
```

> You can use any valid expression inside the `[]`. This is useful when property names are dynamically generated.

---

### **Why It Matters**

These features:

- Reduce repetition and improve clarity
- Make objects more flexible and dynamic
- Improve developer productivity

They are widely used in modern JavaScript development, especially when working with APIs, configurations, or complex objects.