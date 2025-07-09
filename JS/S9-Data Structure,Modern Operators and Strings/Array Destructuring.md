### What is Array destructing?

**destructing** is an ES6 feature that allows you to **extract elements from arrays** (or properties from objects) and assign them to variables in a single statement.

---

### Traditional Approach (Without destructing)

```js
const arr = [2, 3, 4]; 
const a = arr[0];
const b = arr[1];
const c = arr[2];
```



This method works, but it's verbose and repetitive.

---

### Using destructing

```js
const [x, y, z] = arr; 
console.log(x, y, z); // 2 3 4

```

- The array is not modified.
    
- The values are unpacked into separate variables efficiently.
    

---

### Skipping Elements

You can skip unwanted elements using commas:

```js
const [main, , secondary] = ['Italian', 'Pizzeria', 'Vegetarian']; console.log(main, secondary); // Italian Vegetarian

```


You leave a blank space with a comma to skip the second item.

---

### Switching Variables Using Destructuring

Instead of using a temporary variable to swap two values:

**Traditional way:**

```js
let main = 'Italian';
let secondary = 'Vegetarian';
const temp = main;
main = secondary;
secondary = temp;`
```



==**With Destructuring:**==

```js
// you will get error if you declare (main and secondary as const)
[main, secondary] = [secondary, main];
```


This is shorter and avoids using a temporary variable.

---

### Function Return Value Destructuring

A function that returns an array can be destructured immediately:

order: 
```js
function(starterIndex, mainIndex) {   
return [this.starterMenu[starterIndex], this.mainMenu[mainIndex]]; 
}

```

You can destructure the result:

```js
const [starter, mainCourse] = restaurant.order(2, 0);
console.log(starter, mainCourse); // Garlic Bread Pizza

```

This allows you to return multiple values and assign them directly to variables.

---

### Nested Destructuring

When arrays are nested (arrays inside arrays), you can extract deeper values:

```js
const nested = [2, 4, [5, 6]];
const [i, , [j, k]] = nested; 
console.log(i, j, k); // 2 5 6
```



You can destructure inner arrays inside the main destructuring pattern.

---

### Setting Default Values

Destructuring allows you to set default values in case elements are missing:

```js
const [p = 1, q = 1, r = 1] = [8, 9]; 
console.log(p, q, r); // 8 9 1
```


==This is useful== when you're unsure of the array’s length, ==such as when receiving data from external sources (like an API)==.

---

### Summary of Key Features

|Feature|Syntax Example|Description|
|---|---|---|
|Basic Destructuring|`const [a, b] = [1, 2];`|Assign values directly from an array|
|Skipping Elements|`const [a, , c] = [1, 2, 3];`|Skip over unwanted elements|
|Swapping Variables|`[a, b] = [b, a];`|Switch variable values without temp variable|
|Nested Destructuring|`const [ , , [x, y]] = [ , , [5, 6]];`|Extract values from inner arrays|
|Default Values|`const [a = 1, b = 2] = [ ];`|Set fallback values for missing elements|