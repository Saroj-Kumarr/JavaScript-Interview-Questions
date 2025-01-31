## JavaScript Interview Questions

### 1. What Is JavaScript?

JavaScript is a high-level, dynamically-typed, single-threaded, synchronous programming language used for interactive web applications, supporting both client-side and server-side development.

---

### 2. What are the features of JavaScript?

1. **JavaScript is a versatile programming language** used everywhere, from building interactive web frontends (with frameworks like React) to powering backends (using Node.js). It also extends to mobile app development (React Native) and desktop applications (Electron).
2. **JavaScript has a rich ecosystem** with many libraries, frameworks, and tools that simplify development for web, mobile, and desktop applications. It supports a wide range of use cases and helps developers build powerful solutions.
3. **JavaScript is asynchronous**, allowing tasks like data fetching or file reading to run in the background without blocking other code, making applications faster and more responsive.
4. **Event-driven** means JavaScript responds to events like user actions (clicks, typing) or system events (data loading). Code runs when these events occur, making JavaScript ideal for interactive websites and applications.
5. **JavaScript is a dynamically typed programming language**, meaning the type of a variable is determined at runtime, not at compile time.
6. **JavaScript is an object-oriented programming language** that uses prototypes rather than classes for inheritance.

---

### 3. What are the different data types in JavaScript?

#### 1. **Primary (Primitive) Data Types**

These are the basic data types that hold a single value and are immutable (cannot be changed).

- **Number**: Represents numeric values.

  ```javascript
  let age = 30;
  ```

- **String**: Represents a sequence of characters.

  ```javascript
  let name = "Saroj";
  ```

- **Boolean**: Represents `true` or `false`.

  ```javascript
  let isActive = true;
  ```

- **Undefined**: Represents a variable that is declared but not assigned any value.

  ```javascript
  let user;
  ```

- **Null**: Represents an intentional absence of any object value.

  ```javascript
  let emptyValue = null;
  ```

- **Symbol** (introduced in ES6): A unique and immutable value used as an identifier for object properties.

  ```javascript
  let sym = Symbol("description");
  ```

- **BigInt** (introduced in ES11): Used for large integers beyond the safe integer limit of the `Number` type.

  ```javascript
  let bigNumber = 1234567890123456789012345678901234567890n;
  ```

#### 2. **Derived (Non-Primitive) Data Types**

These data types can hold multiple values and are mutable (can be changed).

- **Object**: Represents a collection of key-value pairs.

  ```javascript
  let person = { name: "John", age: 25 };
  ```

- **Array**: A special type of object that stores ordered collections of values.

  ```javascript
  let numbers = [1, 2, 3, 4, 5];
  ```

---

### 4. Difference between `var`, `let`, and `const`

| **Feature**        | **var**                              | **let**                   | **const**                 |
| ------------------ | ------------------------------------ | ------------------------- | ------------------------- |
| **Scope**          | Function scope                       | Block scope               | Block scope               |
| **Re-declaration** | Allowed                              | Not allowed               | Not allowed               |
| **Re-assignment**  | Allowed                              | Allowed                   | Not allowed               |
| **Hoisting**       | Hoisted (initialized as `undefined`) | Hoisted (not initialized) | Hoisted (not initialized) |

---

### 5. What is hoisting in JavaScript?

**Hoisting** in JavaScript is a behavior where variable and function declarations are moved (or "hoisted") to the top of their scope during the compilation phase, before the code is executed.

#### Key Points:

- **Variable hoisting**: JavaScript moves variable declarations to the top, but only the declaration, not the initialization.
- **Function hoisting**: Function declarations are hoisted along with their definition, so they can be called before they appear in the code.

#### Examples of Hoisting:

##### 1. **Variable Hoisting with `var`**

When a variable is declared using `var`, the declaration is hoisted, but the assignment is not.

```javascript
console.log(x); // undefined (due to hoisting)
var x = 5;
console.log(x); // 5
```

**Explanation**:

- The declaration `var x;` is hoisted to the top, but `x = 5;` stays where it is.
- So, initially, `x` is undefined when logged before assignment.

##### 2. **Function Hoisting**

Functions declared using the `function` keyword are hoisted with their definition, so they can be called before they are written in the code.

```javascript
sayHello(); // "Hello!"

function sayHello() {
  console.log("Hello!");
}
```

**Explanation**:

- The function `sayHello()` is hoisted with its definition, so you can call it before its declaration in the code.

---

### 6. Difference between `==` and `===`

| **Operator** | **Definition**             | **Explanation**                                                             | **Example** | **Result**                                  |
| ------------ | -------------------------- | --------------------------------------------------------------------------- | ----------- | ------------------------------------------- |
| `==`         | Checks only the value      | **Loose equality**: Compares values after converting them to a common type. | `5 == '5'`  | `true` (String '5' coerced to number 5)     |
| `===`        | Checks both value and type | **Strict equality**: Compares both value and type without type conversion.  | `5 === '5'` | `false` (Different types: number vs string) |

---

### 7. Is JavaScript a static or dynamically typed language?

JavaScript is a **dynamically typed** language. This means that variables in JavaScript do not have a fixed type, and the type of a variable can change at runtime. You can assign any type of value to a variable, and its type can be changed during execution.

### Key Points:

- **Dynamic typing**: The type of a variable is determined at runtime, and it can change as the program runs.
- **No need to specify a type**: You don't need to declare the type of a variable when you create it.

### Example of Dynamic Typing:

```javascript
let variable = 42; // variable is a number
console.log(typeof variable); // "number"

variable = "Hello!"; // Now variable is a string
console.log(typeof variable); // "string"

variable = true; // Now variable is a boolean
console.log(typeof variable); // "boolean"
```

### 8. Is JavaScript a compiled or interpreted language?

**JavaScript is mainly interpreted**, but modern engines like **V8** use **JIT (Just-In-Time) compilation** to improve performance. The engine converts the JavaScript code into optimized **machine code** just before it runs. This combination of interpretation and JIT compilation allows JavaScript to be both **fast** and **flexible**, making it ideal for dynamic web applications.

**1. Interpreter:**

The interpreter comes into action **first** to quickly execute the code. It:

- Parses the JavaScript code and converts it into an intermediate representation called **bytecode**.
- Starts executing the bytecode **line by line**, allowing the program to run immediately.

This ensures fast start-up, especially for smaller scripts or code that doesn't run repeatedly.

**2. Compiler:**

The compiler comes into action **after** the interpreter identifies "hot code" (frequently executed code):

- **Hot Code Detection**: The engine tracks which functions, loops, or code blocks are executed often.
- **Just-In-Time (JIT) Compilation**: The compiler optimizes these "hot" parts by converting them into highly efficient **machine code** for faster execution.

---

### 9. What is the difference between null and undefined?

The difference between `null` and `undefined` in JavaScript is as follows:

1. **`undefined`**:

   - **Type**: `undefined` is a primitive data type in JavaScript.
   - **Value**: It is the default value assigned to variables that have been declared but not assigned a value.
   - **Example**:
     ```javascript
     let a;
     console.log(a); // undefined
     ```
   - **Use case**: It indicates that a variable has been declared but has not yet been assigned any value.

2. **`null`**:
   - **Type**: `null` is also a primitive value, but it represents the intentional absence of any object value.
   - **Value**: It is explicitly assigned to a variable to indicate that the variable is empty or has no value.
   - **Example**:
     ```javascript
     let b = null;
     console.log(b); // null
     ```
   - **Use case**: It is used when you want to indicate that a variable should be empty or intentionally hold no value.

---

# JavaScript Concepts: `this` Keyword and Modules

## 10. What is the `this` keyword?

The `this` keyword in JavaScript behaves differently depending on the **execution context** in which it is used. Its value is determined by how and where the function is called rather than where it is defined. Here’s how it works in different situations:

### 1. **Global Context**

In the global scope, `this` refers to the **global object**:

- In browsers: `window`
- In Node.js: `global`

```javascript
console.log(this);
// Browser: window
// Node.js: global
```

---

### 2. **Inside a Function (Non-Strict Mode)**

In a regular function, `this` refers to the **global object** when in non-strict mode.

```javascript
function show() {
  console.log(this);
}

show();
// Browser: window
// Node.js: global
```

In **strict mode**, `this` is `undefined`:

```javascript
"use strict";

function show() {
  console.log(this);
}

show();
// undefined
```

---

### 3. **Inside a Method**

When `this` is used in an object’s method, it refers to the **object that owns the method**:

```javascript
const obj = {
  name: "Saroj",
  greet() {
    console.log(this.name);
  },
};

obj.greet();
// Output: Saroj
```

---

### 4. **In Arrow Functions**

Arrow functions don’t have their own `this`. Instead, they inherit `this` from their **lexical scope** (the surrounding function or block).

```javascript
const obj = {
  name: "Saroj",
  greet: () => {
    console.log(this.name);
  },
};

obj.greet();
// Output: undefined (or empty, because `this` refers to the global object)
```

In contrast, regular functions create their own `this`:

```javascript
const obj = {
  name: "Saroj",
  greet() {
    console.log(this.name);
  },
};

obj.greet();
// Output: Saroj
```

---

### 5. **In a Constructor Function**

When a constructor function is used with the `new` keyword, `this` refers to the newly created object.

```javascript
function Person(name) {
  this.name = name;
}

const person = new Person("Saroj");
console.log(person.name);
// Output: Saroj
```

---

### 6. **In Class Methods**

In a class, `this` refers to the instance of the class:

```javascript
class Person {
  constructor(name) {
    this.name = name;
  }
  greet() {
    console.log(this.name);
  }
}

const saroj = new Person("Saroj");
saroj.greet();
// Output: Saroj
```

---

### 7. **Event Handlers**

In an event handler, `this` usually refers to the element that received the event:

```javascript
const button = document.querySelector("button");

button.addEventListener("click", function () {
  console.log(this);
  // Output: <button> element
});
```

Using an arrow function in event handlers, `this` will refer to the **outer lexical context**:

```javascript
button.addEventListener("click", () => {
  console.log(this);
  // Output: the global object or undefined in strict mode
});
```

---

## 11. What is a module in JavaScript, and what are its types?

A **module** is a reusable block of code that can include variables, functions, or classes, which are exported from one file and imported into another. Modules allow better **encapsulation**, **reusability**, and **maintainability**.

---

### 1. **Types of Modules in JavaScript**

#### a. **ECMAScript Modules (ES Modules)**

This is the modern way to work with modules.

**Example: Exporting:**

```javascript
// math.js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;

// Default export
export default function multiply(a, b) {
  return a * b;
}
```

**Importing:**

```javascript
// main.js
import multiply, { add, subtract } from "./math.js";

console.log(add(2, 3)); // Output: 5
console.log(subtract(5, 2)); // Output: 3
console.log(multiply(3, 4)); // Output: 12
```

---

#### b. **CommonJS Modules**

These are used in Node.js.

**Example: Exporting:**

```javascript
// math.js
const add = (a, b) => a + b;
const subtract = (a, b) => a - b;

module.exports = { add, subtract };
```

**Importing:**

```javascript
// main.js
const { add, subtract } = require("./math");

console.log(add(2, 3)); // Output: 5
console.log(subtract(5, 2)); // Output: 3
```
