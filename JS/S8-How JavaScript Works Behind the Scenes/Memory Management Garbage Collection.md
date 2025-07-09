### 1. The Memory Lifecycle in JavaScript

Every value created in JavaScript goes through three main steps in memory:

1. **Allocation** – Memory is reserved for the value.
    
2. **Usage** – The program uses the value.
    
3. **Release** – The value is no longer needed, so the memory should be freed.
    

Step 1 and 2 are already understood. The focus now is on step 3 — how JavaScript frees memory.

---

### 2. Memory Release in the Stack

- The **call stack** stores function execution contexts and their local variables (primitives).
    
- When a function completes, its context is removed from the stack.
    
- Along with that, its variables are also deleted from memory.
    

**Example**:  
If a function defines variables like `y` and `z`, they exist in memory only while the function is running. Once the function ends, these are automatically deleted.

However, variables in the **global execution context** (e.g., a variable `x` declared globally) remain in memory forever because the global context never disappears.

---

### 3. Memory Release in the Heap

The **heap** stores reference types — objects, arrays, functions, and more.  
Memory management here is more complex, and it's handled by a mechanism called **garbage collection**.

---

### 4. What is Garbage Collection?

Garbage collection is an **automatic process** performed by the JavaScript engine to free up memory that is no longer in use.

All modern JavaScript engines use a method called **mark-and-sweep**.

---

### 5. How Mark-and-Sweep Works

**Step 1: Mark Phase**

- The engine starts with **roots** (such as the global context, currently active functions, event listeners, and timers).
    
- It marks all objects **reachable** from those roots as “alive.”
    
- Reachable means there is still some part of the program that can access them.
    

**Step 2: Sweep Phase**

- Any object not marked is considered unreachable.
    
- These unreachable objects are deleted from the heap, and their memory is reclaimed.
    

**Example**:  
If an object is not referenced by any variable or active process, it is deleted during this phase.

---

### 6. Memory Leaks

A **memory leak** happens when an object is no longer needed but is still reachable — so garbage collection does not remove it.

This can happen if:

- An unused event listener still references the object.
    
- A timer that is no longer needed still exists.
    
- Large global variables are declared and never cleaned up.
    

To avoid memory leaks:

- Remove event listeners when they are no longer necessary.
    
- Clear timers after they’re used.
    
- Avoid declaring large global objects.
    

---

### 7. Global Objects and Garbage Collection

Objects declared in the global context (such as top-level variables) are **never garbage collected**.  
Even if your application no longer needs them, they stay in memory because the global context is always active.

---

### 8. Related Topics Mentioned

These important JavaScript concepts are closely related to memory but are covered later in the course:

- **Closures** – Functions that keep access to outer variables even after the outer function ends.
    
- **Prototypal Inheritance** – The mechanism for sharing methods and properties among objects.
    
- **Event Loop** – How JavaScript handles asynchronous operations.
    
- **DOM Internals** – How the Document Object Model works in the browser.
    

---

### Final Notes

Garbage collection in JavaScript is automatic and cannot be controlled manually. The engine decides when and how to run it, based on memory usage and system conditions.

While memory management in reality is more advanced (with multiple heaps and collection strategies), this overview is sufficient to understand how JavaScript cleans up unused memory.

Understanding this helps you write cleaner and more efficient code, and avoid common pitfalls like memory leaks.