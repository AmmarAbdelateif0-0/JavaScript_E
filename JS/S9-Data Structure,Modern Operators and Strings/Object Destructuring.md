### **1. What is Object Destructuring?**

Object destructuring allows you to **extract specific properties from an object** and assign them to variables with a very short syntax.
we use {} to destructuring object and we choose the properties we want if not exist return undefined

```js
const restaurant = {
  name: 'Classico Italiano',
  location: 'Via Angelo Tavanti 23, Firenze, Italy',
  categories: ['Italian', 'Pizzeria', 'Vegetarian', 'Organic'],
  starterMenu: ['Focaccia', 'Bruschetta', 'Garlic Bread', 'Caprese Salad'],
  mainMenu: ['Pizza', 'Pasta', 'Risotto'],
  order : function(starterIndex , mainIndex){
    return [this.starterMenu[starterIndex],this.mainMenu[mainIndex]];
  },
  openingHours: {

    thu: {
      open: 12,
      close: 22,
    },
    fri: {
      open: 11,
      close: 23,
    },
    sat: {
      open: 0, // Open 24 hours
      close: 24,
    },
  },
};

const { name, openingHours, categories } = restaurant;
```
This creates three variables from the `restaurant` object. Unlike arrays, the **order doesn't matter** — the variable names must **match the property names** exactly.

---

### **2. Renaming Variables While Destructuring**

You can assign property values to variables with different names:

```js
const {
  name: restaurantName,
  openingHours: hours,
  categories: tags
} = restaurant;

```

This is useful to avoid conflicts or make variable names more meaningful.

that's gonna be immensely helpful when dealing with third-party data. 

And another useful feature for when we are dealing with third-party data like that. 

So like an object that we get from somewhere else, for example, an API call, as I was just explaining.

---

### **3. Setting Default Values**

If a property might be **missing** from the object, you can provide a default value:

```js
const { 
menu = [],
starterMenu: starters = [] 
} = restaurant;
```

==If `menu` doesn't exist, it becomes an empty array instead of `undefined`.==

---

### **4. Mutating Existing Variables**

If you already declared variables and want to assign values to them from an object, you must wrap the destructuring assignment in parentheses:

```js
let a = 111;
let b = 999;
const obj = { a: 23, b: 7, c: 14 };
// we can't start a line with {} so we use () to avoid this error
({ a, b } = obj);
```

This avoids syntax errors because JavaScript would otherwise treat the curly braces as a code block.

---

### **5. Nested Object Destructuring**

When objects contain **nested objects**, you can destructure at deeper levels:

```js
const {
  fri: { open, close }
} = restaurant.openingHours;

// here we can use fri as a variable 
// fri is not defined 
```

This extracts the `open` and `close` times for Friday from the nested `openingHours` object.

You can also rename nested properties:

```js
const {
  fri: { open: o, close: c }
} = restaurant.openingHours;
```

default and renaming

```js
const {
  fri: { open: o =12, close: c=23 }
} = restaurant.openingHours;
```

---

### **6. Destructuring in Function Parameters**

A powerful use of object destructuring is within **function parameters**. Instead of passing multiple arguments in a specific order, you pass an object and destructure it directly in the function definition:

```js
restaurant.orderDelivery({
  time: '23:30',
  address: 'Via del Sole, 21',
  mainIndex: 2,
  starterIndex: 2
});
```

Inside the method:

```js
orderDelivery({ starterIndex, mainIndex, time, address }) {
  console.log(`Order received! ${this.starterMenu[starterIndex]} and ${this.mainMenu[mainIndex]} will be delivered to ${address} at ${time}`);
}

```

This way, the caller doesn’t need to remember the exact parameter order.

So if you ever need to write a function like this, so a really complex one with a lot of parameters that might be then hard to specify,

---

### **7. Default Values in Function Parameters**

You can combine destructuring with default values **inside function parameters**:

```js
orderDelivery({
  starterIndex = 1,
  mainIndex = 0,
  time = '20:00',
  address
}){
console.log(`Order received! ${this.starterMenu[starterIndex]} and ${this.mainMenu[mainIndex]} will be delivered to ${address} at ${time}`);
}
```

If any of these properties are missing from the object passed to the function, the defaults will be used automatically.


---------------------------------
### **Summary of Object Destructuring Features**

|**Feature**|**Syntax Example**|**Description**|
|---|---|---|
|Basic Destructuring|`const { name, age } = person;`|Extract properties directly from an object.|
|Renaming Variables|`const { name: fullName } = person;`|Assign to a variable with a different name.|
|Default Values|`const { menu = [] } = restaurant;`|Set fallback values when a property is missing.|
|Mutating Variables|`({ a, b } = obj);`|Assign to already declared variables (use parentheses).|
|Nested Destructuring|`const { fri: { open, close } } = openingHours;`|Extract values from nested objects.|
|Destructuring in Functions|`function order({ time, address }) { ... }`|Destructure directly in function parameters.|
|Defaults in Parameters|`function order({ time = '20:00' }) { ... }`|Use default values in parameter destructuring.|