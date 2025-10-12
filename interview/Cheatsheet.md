Here’s a cleaner and more professional version of your **JavaScript & Node.js Cheatsheet** — with improved grammar, structure, and clarity while keeping it concise and technical:

---

### 🟡 **JavaScript Cheatsheet**

#### 1. Language Overview

- Multi-paradigm, dynamic language (dynamic typing and operators).
- Has standard built-in objects.
- Supports OOP using prototype-based inheritance.
    

#### 2. Data Types

- **Primitive:** `number`, `bigint`, `string`, `boolean`, `symbol`, `undefined` _(absence of value)_, `null` _(intentional no value)_.
    
- **Non-primitive (Objects):** `function`, `array`, `map`, `error`, `regex`, and other objects.
    

#### 3. Variables

- `let` → Block scoped.
    
- `const` → Prevents reassignment of the value.
    
- `var` → Function scoped (legacy).
    

#### 4. Objects

- Collection of key-value pairs.
    
- Common methods: `valueOf()`, `toString()`, `toLocaleString()`.
    

#### 5. Conditional Statements

- **Falsy values:** `0`, `undefined`, `null`, `NaN`, `""` (empty string).
    
- `for...in` → Iterates over **keys** of an object.
    
- `for...of` → Iterates over **values** of iterable objects (arrays, maps, sets, etc.).
    

#### 6. Functions

- **Types:**
    
    - Function Declaration / Statement
        
    - Function Expression
        
    - Hoisted Functions
        
    - Recursion
        
    - IIFE _(Immediately Invoked Function Expression)_
        
- **Scopes:** Global, function, block (with `let`/`const`).
    
- **Closures:** A function bundled with its lexical environment.
    
- **Arrow Functions:**
    
    - No `this` binding or constructor.
        
    - Should not be used as object methods.
        
    - Cannot use `yield`.
        
- **Default Parameters:** Used when `undefined` is passed as an argument.
    
- **Rest Parameters:** Accepts indefinite arguments as an array.
    

#### 7. Classes

- Syntactic sugar over prototypes.
    
- Used as templates for creating objects.
    

#### 8. Asynchronous JavaScript

- Based on callbacks, promises, and async/await.
    
- Non-blocking execution.
    

#### 9. Execution Context

- Functions execute within their own context.
    
- When a nested function is called, the outer function’s execution is paused and stored on the call stack.
    
- Once the inner function completes, control returns to the outer function.
    

#### 10. Recursion

- A function calling itself.
    
- Useful for tree/graph traversals and iterative tasks.
    

#### 11. Memory Management

- Uses **mark-and-sweep algorithm** for garbage collection.
    

---

### 🟢 **Node.js Cheatsheet**

#### 1. Overview

- JavaScript runtime environment.
    
- Single-threaded, non-blocking, asynchronous I/O.
    
- Cross-platform.
    

#### 2. Core Components

- **V8 Engine:** Compiles and executes JavaScript.
    
- **Event Loop:** Manages asynchronous operations.
    
- **libuv:** Provides the I/O event loop and handles system calls.
    

#### 3. Key Concepts

- Single-threaded but handles concurrency via the event loop.
    
- Event-driven architecture.
    
- Excellent for I/O-heavy operations, not CPU-bound tasks.
    

---

Would you like me to also add a **short section on Promises / async-await / event loop diagram** to make this cheatsheet more interview-ready? (This is common in senior JS/Node interviews.)