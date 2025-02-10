## JavaScript Interview Questions

### \***\*\*\*\*\*\*\***\*\***\*\*\*\*\*\*\*** Basic Questions \***\*\*\*\*\*\*\***\*\***\*\*\*\*\*\*\***

#### 1. What Is JavaScript?

JavaScript is a high-level, dynamically-typed, single-threaded, synchronous programming language used for interactive web applications, supporting both client-side and server-side development.

---

#### 2. What are the features of JavaScript?

1. **JavaScript is a versatile programming language** used everywhere, from building interactive web frontends (with frameworks like React) to powering backends (using Node.js). It also extends to mobile app development (React Native) and desktop applications (Electron).
2. **JavaScript has a rich ecosystem** with many libraries, frameworks, and tools that simplify development for web, mobile, and desktop applications. It supports a wide range of use cases and helps developers build powerful solutions.
3. **JavaScript is asynchronous**, allowing tasks like data fetching or file reading to run in the background without blocking other code, making applications faster and more responsive.
4. **Event-driven** means JavaScript responds to events like user actions (clicks, typing) or system events (data loading). Code runs when these events occur, making JavaScript ideal for interactive websites and applications.
5. **JavaScript is a dynamically typed programming language**, meaning the type of a variable is determined at runtime, not at compile time.
6. **JavaScript is an object-oriented programming language** that uses prototypes rather than classes for inheritance.

---

#### 3. What are the different data types in JavaScript?

##### 1. **Primary (Primitive) Data Types**

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

#### 4. Difference between `var`, `let`, and `const`

| **Feature**        | **var**                              | **let**                   | **const**                 |
| ------------------ | ------------------------------------ | ------------------------- | ------------------------- |
| **Scope**          | Function scope                       | Block scope               | Block scope               |
| **Re-declaration** | Allowed                              | Not allowed               | Not allowed               |
| **Re-assignment**  | Allowed                              | Allowed                   | Not allowed               |
| **Hoisting**       | Hoisted (initialized as `undefined`) | Hoisted (not initialized) | Hoisted (not initialized) |

---

#### 5. What is hoisting in JavaScript?

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

#### 6. Difference between `==` and `===`

| **Operator** | **Definition**             | **Explanation**                                                             | **Example** | **Result**                                  |
| ------------ | -------------------------- | --------------------------------------------------------------------------- | ----------- | ------------------------------------------- |
| `==`         | Checks only the value      | **Loose equality**: Compares values after converting them to a common type. | `5 == '5'`  | `true` (String '5' coerced to number 5)     |
| `===`        | Checks both value and type | **Strict equality**: Compares both value and type without type conversion.  | `5 === '5'` | `false` (Different types: number vs string) |

---

#### 7. Is JavaScript a static or dynamically typed language?

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

#### 8. Is JavaScript a compiled or interpreted language?

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

#### 9. What is the difference between null and undefined?

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

#### 10. What is the `this` keyword?

The `this` keyword in JavaScript behaves differently depending on the **execution context** in which it is used. Its value is determined by how and where the function is called rather than where it is defined. Here’s how it works in different situations:

#### 1. **Global Context**

In the global scope, `this` refers to the **global object**:

- In browsers: `window`
- In Node.js: `global`

```javascript
console.log(this);
// Browser: window
// Node.js: global
```

---

#### 2. **Inside a Function (Non-Strict Mode)**

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

#### 3. **Inside a Method**

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

#### 4. **In Arrow Functions**

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

#### 5. **In a Constructor Function**

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

#### 6. **In Class Methods**

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

#### 7. **Event Handlers**

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

#### 11. What is a module in JavaScript, and what are its types?

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

### \***\*\*\*\*\*\*\***\*\***\*\*\*\*\*\*\*** Intermediate Questions \***\*\*\*\*\*\*\***\*\***\*\*\*\*\*\*\***

## 12. Type Conversion in JavaScript

Type conversion in JavaScript refers to the process of converting a value from one data type to another. JavaScript provides two types of type conversion:

- **Implicit Type Conversion (Type Coercion)**
- **Explicit Type Conversion (Type Casting)**

### 1. Implicit Type Conversion (Type Coercion)

Implicit type conversion occurs automatically when JavaScript converts a value from one type to another without explicit instructions.

#### **Examples of Implicit Conversion:**

##### **String Conversion**

When a number or boolean is concatenated with a string, JavaScript converts it into a string.

```javascript
console.log("5" + 2); // "52"
console.log("Hello" + true); // "Hellotrue"
```

##### **Number Conversion**

When a string containing a number is used in arithmetic operations, JavaScript converts it into a number.

```javascript
console.log("10" - 5); // 5
console.log("4" * 2); // 8
```

##### **Boolean Conversion**

JavaScript automatically converts values to `true` or `false` in conditional statements.

```javascript
if ("hello") {
  console.log("Truthy");
} // Truthy
if (0) {
  console.log("Falsy");
} // Does not execute
```

---

### 2. Explicit Type Conversion (Type Casting)

Explicit type conversion is when a programmer manually converts a value from one type to another using built-in functions.

#### **Methods for Explicit Conversion:**

##### **String Conversion**

```javascript
let num = 10;
console.log(String(num)); // "10"
console.log(num.toString()); // "10"
```

##### **Number Conversion**

```javascript
console.log(Number("123")); // 123
console.log(parseInt("10.5")); // 10
console.log(parseFloat("10.5")); // 10.5
```

##### **Boolean Conversion**

```javascript
console.log(Boolean(1)); // true
console.log(Boolean(0)); // false
console.log(Boolean("")); // false
```

## 13. JavaScript Scope

## Introduction

Scope in JavaScript refers to the context or environment in which variables and functions are accessible. It determines the visibility and lifetime of variables, functions, and objects in your code. Understanding scope is crucial for writing maintainable and bug-free JavaScript applications.

## Types of Scope

### 1. Global Scope

Variables declared outside of any function or block have global scope and are accessible from anywhere in the code.

```javascript
let globalVar = "I am global";

function testGlobal() {
  console.log(globalVar); // Accessible here
}

testGlobal(); // Logs "I am global"
console.log(globalVar); // Logs "I am global"
```

### 2. Local Scope (Function Scope)

Variables declared inside a function are only accessible within that function and are not visible outside of it.

```javascript
function testLocal() {
  let localVar = "I am local";
  console.log(localVar); // Accessible here
}

testLocal();
console.log(localVar); // Error: localVar is not defined
```

### 3. Block Scope

Variables declared inside a block (within `{}`) using `let` or `const` are only accessible within that block. This includes loops, conditionals, and any arbitrary block.

```javascript
if (true) {
  let blockVar = "I am block-scoped";
  console.log(blockVar); // Accessible here
}

console.log(blockVar); // Error: blockVar is not defined
```

### 4. Lexical Scope (Static Scope)

Lexical scope means that the scope of a variable is determined by its location in the source code at the time of writing. Inner functions have access to variables in their outer scope.

```javascript
function outer() {
  let outerVar = "I am outer";

  function inner() {
    console.log(outerVar); // Accessible here due to lexical scope
  }

  inner();
}

outer(); // Logs "I am outer"
```

## 14. What is a Promise?

A Promise is an object representing the eventual completion (or failure) of an asynchronous operation and its resulting value. It provides a cleaner way to handle asynchronous operations compared to traditional callback functions.

### Promise States

1. **Pending**: The promise is still in progress, neither fulfilled nor rejected
2. **Fulfilled**: The operation completed successfully, and the promise has a result
3. **Rejected**: The operation failed, and the promise has an error

### Promise Example

```javascript
let myPromise = new Promise((resolve, reject) => {
  // Simulating an API call
  fetch("https://jsonplaceholder.typicode.com/posts")
    .then((response) => {
      if (!response.ok) {
        reject("Failed to fetch data");
      } else {
        return response.json();
      }
    })
    .then((data) => {
      resolve(data); // Resolve the promise with the fetched data
    })
    .catch((error) => {
      reject(error); // Reject the promise if there's an error
    });
});

// Handling the promise
myPromise
  .then((data) => {
    console.log("Operation succeeded with data:", data); // On success
  })
  .catch((error) => {
    console.log("Operation failed with error:", error); // On failure
  });
```

## Async/Await

`async/await` is a syntactic feature in JavaScript that simplifies working with asynchronous code, making it more readable and easier to manage than using plain promises.

### Async/Await Example

```javascript
async function fetchData() {
  try {
    const response = await fetch("url");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}
```

First, let me explain TDZ (Temporal Dead Zone) in simple terms:

The Temporal Dead Zone (TDZ) is the time between when a variable is declared (with let/const) and when it's initialized. During this time, you can't access the variable - trying to do so will result in a ReferenceError.

Think of it like this: the variable exists, but it's in a "dead zone" where you can't touch it yet.

Here's a simple example:

```javascript
console.log(name); // undefined (var doesn't have TDZ)
console.log(age); // ReferenceError (TDZ in action!)

var name = "John";
let age = 25;
```

## 15. What is TDZ?

The Temporal Dead Zone (TDZ) is the period between entering a scope where a variable is declared and its actual declaration and initialization. During this period, the variable exists but cannot be accessed.

## TDZ vs No TDZ

### Variables with TDZ (let and const)

```javascript
// TDZ starts for carName
console.log(carName); // ReferenceError: Cannot access 'carName' before initialization
let carName = "Tesla"; // TDZ ends

// Same applies for const
console.log(PI); // ReferenceError: Cannot access 'PI' before initialization
const PI = 3.14;
```

### Variables without TDZ (var)

```javascript
console.log(userName); // undefined (no error!)
var userName = "John";
```

## More TDZ Examples

### In Functions

```javascript
function demo() {
  console.log(value); // ReferenceError
  let value = 10;
}
```

### In Blocks

```javascript
{
  // TDZ starts
  const func = () => console.log(hello);

  // During TDZ
  func(); // ReferenceError

  // TDZ ends
  let hello = "Hello World";

  // Now it works
  func(); // "Hello World"
}
```

### Class Fields

```javascript
class Example {
  // TDZ for 'name' starts
  displayName() {
    console.log(this.name); // ReferenceError if called before name is initialized
  }

  name = "Example"; // TDZ ends
}
```

# 16. JavaScript Destructuring

## Introduction

**Destructuring** is a JavaScript feature that allows you to **extract** values from arrays or properties from objects and assign them to variables. It provides a more convenient and concise way to extract values from arrays and objects, rather than accessing them one by one.

## Types of Destructuring

There are two main types of destructuring in JavaScript:

1. Array Destructuring
2. Object Destructuring

## 1. Array Destructuring

Array destructuring allows you to **extract** values from an array and assign them to variables.

### Basic Array Destructuring

```javascript
const arr = [1, 2, 3];

// Extracting values from the array
const [a, b, c] = arr;

console.log(a); // 1
console.log(b); // 2
console.log(c); // 3
```

### Array Destructuring with Default Values and Skipping Elements

```javascript
const arr = [1, 2];

// Skipping the second element
const [x, , z = 5] = arr;

console.log(x); // 1
console.log(z); // 5
```

## 2. Object Destructuring

Object destructuring allows you to **extract** values from an object and assign them to variables based on the object's property names.

### Basic Object Destructuring

```javascript
const person = {
  name: "John",
  age: 30,
  city: "New York",
};

// Extracting properties from the object
const { name, age, city } = person;

console.log(name); // John
console.log(age); // 30
console.log(city); // New York
```

# 17. Spread and Rest Operators in JavaScript

Both the **spread** and **rest** operators use the same syntax (`...`), but they serve different purposes depending on how they are used.

## 1. Spread Operator (`...`)

The **spread** operator is used to **expand** or **spread** elements from an array or object into individual elements.

### Array Spread Example

```javascript
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5]; // Spread elements of arr1 and add new elements

console.log(arr2); // [1, 2, 3, 4, 5]
```

### Object Spread Example

```javascript
const person = { name: "John", age: 30 };
const newPerson = { ...person, city: "New York" }; // Spread properties of person and add new property

console.log(newPerson); // { name: "John", age: 30, city: "New York" }
```

### Spread in Function Calls

```javascript
const numbers = [1, 2, 3, 4];

// Using spread to pass array elements as individual arguments to a function
function add(a, b, c, d) {
  return a + b + c + d;
}

console.log(add(...numbers)); // 10
```

### Practical Use Cases for Spread Operator

1. **Copying Arrays**

```javascript
const originalArray = [1, 2, 3];
const copy = [...originalArray]; // Creates a shallow copy
```

2. **Merging Arrays**

```javascript
const fruits = ["apple", "banana"];
const vegetables = ["carrot", "tomato"];
const allFood = [...fruits, ...vegetables];
```

3. **Cloning Objects**

```javascript
const userSettings = { theme: "dark", notifications: true };
const defaultSettings = { language: "en" };
const finalSettings = { ...defaultSettings, ...userSettings };
```

## 2. Rest Operator (`...`)

The rest operator is used to collect multiple elements into a single array or object.

### Rest in Function Parameters

```javascript
function sum(...numbers) {
  return numbers.reduce((acc, num) => acc + num, 0);
}

console.log(sum(1, 2, 3, 4)); // 10
```

### Rest in Arrays

```javascript
const arr = [1, 2, 3, 4];
const [first, ...rest] = arr; // The rest operator collects the remaining elements

console.log(first); // 1
console.log(rest); // [2, 3, 4]
```

### Rest in Objects

```javascript
const person = { name: "John", age: 30, city: "New York" };
const { name, ...rest } = person; // The rest operator collects the remaining properties

console.log(name); // "John"
console.log(rest); // { age: 30, city: "New York" }
```

### Practical Use Cases for Rest Operator

1. **Flexible Function Arguments**

```javascript
function logAll(...args) {
  args.forEach((arg) => console.log(arg));
}
logAll("Hello", "World", "!", 123); // Works with any number of arguments
```

2. **Excluding Properties**

```javascript
const user = {
  id: 1,
  username: "john_doe",
  password: "secret",
  email: "john@example.com",
};
const { password, ...safeUser } = user; // Remove sensitive data
```

3. **Array Manipulation**

```javascript
const numbers = [1, 2, 3, 4, 5];
const [first, second, ...others] = numbers;
console.log(others); // [3, 4, 5]
```

## Key Differences Between Spread and Rest

| Aspect           | Spread                                                   | Rest                                                              |
| ---------------- | -------------------------------------------------------- | ----------------------------------------------------------------- |
| Purpose          | Expands elements (arrays, objects) into individual items | Collects multiple elements into a single array or object          |
| Used in          | Function calls, array or object literals                 | Function parameters, array destructuring, object destructuring    |
| Syntax           | `...array` or `...object`                                | `...rest` in function parameters or destructuring                 |
| Common Use Cases | Copying arrays/objects, merging arrays/objects           | Collecting function arguments, extracting parts of arrays/objects |

# 18. Difference Between Local Storage and Session Storage

Both **localStorage** and **sessionStorage** are part of the Web Storage API in JavaScript, and they allow you to store data in the user's browser. However, they differ in their **lifetime**, **scope**, and how the data is persisted. Here's a detailed comparison:

## Aspect | localStorage | sessionStorage

**Persistence**
Data persists even after the browser is closed.
Data is cleared when the browser tab or window is closed.

**Scope**
Data is accessible across all tabs and windows of the same origin.
Data is accessible only within the same tab or window where it was set.

**Storage Limit**
Typically around 5MB of data per origin.
Typically around 5MB of data per tab.

**Data Accessibility**
Accessible until explicitly deleted by the user or code.
Accessible only during the session (until the tab/window is closed).

**Use Case**
Storing data that should persist even after the session ends (e.g., user preferences, themes).
Storing data that is only needed for the duration of the page session (e.g., temporary form data, session IDs).

**Expiration**
No expiration; data remains until explicitly deleted.
Data is automatically deleted when the session ends (browser tab/window is closed).

## Example Usage

### localStorage Example:

```javascript
// Setting data in localStorage
localStorage.setItem("username", "john_doe");

// Retrieving data from localStorage
const username = localStorage.getItem("username");
console.log(username); // "john_doe"

// Removing data from localStorage
localStorage.removeItem("username");

// Clearing all data from localStorage
localStorage.clear();
```

- **localStorage** will retain the `"username"` value even if the user closes the browser or tab and reopens it, as long as they haven't explicitly cleared it or the browser hasn't cleared it.

### sessionStorage Example:

```javascript
// Setting data in sessionStorage
sessionStorage.setItem("sessionID", "abc123");

// Retrieving data from sessionStorage
const sessionID = sessionStorage.getItem("sessionID");
console.log(sessionID); // "abc123"

// Removing data from sessionStorage
sessionStorage.removeItem("sessionID");

// Clearing all data from sessionStorage
sessionStorage.clear();
```

- **sessionStorage** will store the `"sessionID"` for the duration of the tab or window's session. When the tab is closed, the data is lost.

# 19. ES6 (ECMAScript 2015) Features

## 1. let & const

Block-scoped variable declarations

```javascript
// let for block-scoped variables
let count = 0;

// const for constant values
const API_KEY = "abc123";
```

## 2. Arrow Functions

Concise function syntax with lexical this binding

```javascript
// Traditional function
function add(a, b) {
  return a + b;
}

// Arrow function
const add = (a, b) => a + b;
```

## 3. Template Literals

String interpolation and multiline strings using backticks

```javascript
const name = "John";
const greeting = `Hello ${name}!
This is a multiline
string.`;
```

## 4. Default Parameters

Functions can have default values for parameters

```javascript
function greet(name = "Guest") {
  return `Hello ${name}!`;
}
```

## 5. Destructuring

Unpack values from arrays or objects into variables

```javascript
// Array destructuring
const [first, second] = [1, 2];

// Object destructuring
const { name, age } = { name: "John", age: 30 };
```

## 6. Classes

Object-oriented programming with class syntax

```javascript
class Person {
  constructor(name) {
    this.name = name;
  }

  sayHello() {
    return `Hello, I'm ${this.name}`;
  }
}
```

## 7. Modules

Use import and export to organize code across files

```javascript
// Export
export const helper = () => {
  /* ... */
};

// Import
import { helper } from "./helper";
```

## 8. Promises

Handle asynchronous operations more easily than callbacks

```javascript
const getData = () => {
  return new Promise((resolve, reject) => {
    // Async operation
    resolve(data);
  });
};
```

## 9. Spread Operator

Expand arrays or objects into individual elements

```javascript
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5]; // [1, 2, 3, 4, 5]

const obj1 = { foo: "bar" };
const obj2 = { ...obj1, baz: "qux" };
```

## 10. Rest Operator

Collect remaining arguments into an array in functions

```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}
```

# 20. Window Object

**Definition:** The window object is the **global object** in the browser environment. It represents the browser window or tab that contains the web page and provides methods, properties, and events to interact with the browser and its environment.

**Key Responsibilities:**

1. Manages the **browser window/tab**.
2. Provides access to global variables and functions.
3. Handles **browser-level functionalities** like location, navigation, alerts, and timers.

**Common Properties:**

- window.innerWidth: Viewport width.
- window.innerHeight: Viewport height.
- window.location: URL-related information.
- window.navigator: Browser information.

**Common Methods:**

- window.alert(): Displays an alert box.
- window.open(): Opens a new browser window or tab.
- window.setTimeout(): Executes code after a delay.
- window.scrollTo(): Scrolls the window to a specific position.

**Hierarchy:**

- The window object is the top-level container in the browser.
- Example: window.document gives access to the document object.

# 21. Document Object

**Definition:** The document object is a **property of the window object** and represents the **web page itself** (the DOM). It allows you to interact with and manipulate the content, structure, and styles of the web page.

**Key Responsibilities:**

1. Represents the **HTML structure** as a tree-like DOM.
2. Provides methods to **select, create, modify, and delete elements** in the DOM.
3. Handles **content-level interactions** like event listeners and data manipulation.

**Common Properties:**

- document.title: The title of the page.
- document.body: The <body> element of the page.
- document.head: The <head> element of the page.
- document.readyState: The loading state of the document.

**Common Methods:**

- document.querySelector(): Selects an element.
- document.getElementById(): Gets an element by ID.
- document.createElement(): Creates a new element.
- document.write(): Writes directly to the page.

# 22. setTimeout and setInterval

setTimeout and setInterval are JavaScript functions used to execute code after a specified delay or at regular intervals, respectively. They are part of the Web APIs provided by browsers and are commonly used for scheduling tasks.

1. **setTimeout**

- **Purpose**: Executes a function or a piece of code **once** after a specified delay (in milliseconds).
- **Syntax**:

```javascript
setTimeout(callback, delay, arg1, arg2, ...);
```

- callback: The function to execute after the delay.
- delay: The time (in milliseconds) to wait before executing the callback.
- arg1, arg2, ...: Optional arguments to pass to the callback function.
- **Example**:

```javascript
setTimeout(() => {
  console.log("This message appears after 2 seconds.");
}, 2000);
```

- This will log the message to the console after 2 seconds (2000 milliseconds).
- **Return Value**: setTimeout returns a **timeout ID**, which is a unique identifier for the scheduled timeout. This ID can be used to cancel the timeout using clearTimeout.

```javascript
const timeoutId = setTimeout(() => {
  console.log("This will not run.");
}, 2000);
clearTimeout(timeoutId); // Cancels the timeout
```

2. **setInterval**

- **Purpose**: Repeatedly executes a function or a piece of code at specified intervals (in milliseconds) until it is stopped.
- **Syntax**:

```javascript
setInterval(callback, interval, arg1, arg2, ...);
```

- callback: The function to execute repeatedly.
- interval: The time (in milliseconds) between each execution of the callback.
- arg1, arg2, ...: Optional arguments to pass to the callback function.
- **Example**:

```javascript
setInterval(() => {
  console.log("This message appears every 1 second.");
}, 1000);
```

- This will log the message to the console every 1 second (1000 milliseconds).
- **Return Value**: setInterval returns an **interval ID**, which is a unique identifier for the scheduled interval. This ID can be used to stop the interval using clearInterval.

```javascript
const intervalId = setInterval(() => {
  console.log("This will stop after 5 seconds.");
}, 1000);
setTimeout(() => {
  clearInterval(intervalId); // Stops the interval after 5 seconds
}, 5000);
```

Key Differences:
**Feature** | **setTimeout** | **setInterval**
-----------|---------------|----------------
**Execution** | Executes once after a delay. | Executes repeatedly at intervals.
**Stopping** | Use clearTimeout(timeoutId). | Use clearInterval(intervalId).
**Use Case** | For one-time delayed tasks. | For recurring tasks (e.g., timers).

# 23. DOM (Document Object Model)

The **DOM (Document Object Model)** is a programming interface for web documents. It represents the structure of an HTML or XML document as a tree-like model, where each node in the tree corresponds to a part of the document (e.g., elements, attributes, text). The DOM provides a way for programs (typically JavaScript) to interact with and manipulate the content, structure, and style of a web page dynamically.

Key Concepts of the DOM:

1. **Tree Structure**:
   - The DOM represents a document as a hierarchical tree of **nodes**.
   - Each node is an object that represents a part of the document (e.g., elements, attributes, text).
   - The topmost node is the **document object**, which represents the entire document.

### \***\*\*\*\*\*\*\***\*\***\*\*\*\*\*\*\*** Advanced Questions \***\*\*\*\*\*\*\***\*\***\*\*\*\*\*\*\***

# 24. Synchronous vs Asynchronous Programming

1. **Synchronous Programming**

- **Definition**: In synchronous programming, tasks are executed **one at a time, in sequence**. Each task must complete before the next task can start.
- **Blocking Behavior**: If a task takes a long time to complete (e.g., reading a file or making a network request), the program will **block** (pause) until the task finishes.
- **Example**:

```javascript
console.log("Task 1");
console.log("Task 2"); // Waits for Task 1 to complete
console.log("Task 3"); // Waits for Task 2 to complete

// Output:
Task 1
Task 2
Task 3
```

- **Use Cases**:
  - Simple scripts or programs where tasks are quick and don't require waiting.
  - When the order of execution is critical.

2. **Asynchronous Programming**

- **Definition**: In asynchronous programming, tasks can be executed **concurrently** or in the background. The program doesn't wait for a task to complete before moving on to the next one.
- **Non-Blocking Behavior**: Long-running tasks (e.g., network requests, file I/O) are handled in the background, allowing the program to continue executing other tasks.
- **Example**:

```javascript
console.log("Task 1");
setTimeout(() => console.log("Task 2"), 1000); // Runs in the background
console.log("Task 3"); // Doesn't wait for Task 2 to complete

// Output:
Task 1
Task 3
Task 2 (after 1 second)
```

- **Use Cases**:
  - Applications that require responsiveness (e.g., web apps, GUIs).
  - Tasks involving I/O operations, network requests, or timers.

Key Differences:
**Feature** | **Synchronous Programming** | **Asynchronous Programming**
-----------|--------------------------|---------------------------
**Execution** | Tasks run one at a time, in sequence. | Tasks can run concurrently or in the background.
**Blocking** | Blocks execution until a task completes. | Does not block execution; continues with other tasks.
**Performance** | Can be inefficient for long-running tasks. | More efficient for long-running tasks.
**Complexity** | Easier to understand and implement. | More complex due to callbacks, promises, or async/await.
**Use Cases** | Simple scripts, sequential tasks. | Web apps, I/O operations, network requests.

# 25. JavaScript Event Handling

## 1. **Event Bubbling**

- **Definition**: When an event occurs on a DOM element, it first triggers on that element, then "bubbles up" through its ancestors in the DOM tree.
- **Order**: The event starts from the target element and propagates upward to the root of the document.
- **Example**:

```html
<div id="parent">
  <button id="child">Click Me</button>
</div>
```

```javascript
document.getElementById("parent").addEventListener("click", () => {
  console.log("Parent clicked");
});
document.getElementById("child").addEventListener("click", () => {
  console.log("Child clicked");
});
```

If you click the button, the output will be:

```
Child clicked
Parent clicked
```

- The event bubbles from the child to the parent.

## 2. **Event Capturing**

- **Definition**: The opposite of bubbling. The event starts from the root of the document and propagates downward to the target element.
- **Order**: The event starts at the top of the DOM tree and moves down to the target element.
- **Usage**: To enable capturing, set the third parameter of addEventListener to true.
- **Example**:

```javascript
document.getElementById("parent").addEventListener(
  "click",
  () => {
    console.log("Parent clicked");
  },
  true
); // Enable capturing
document.getElementById("child").addEventListener(
  "click",
  () => {
    console.log("Child clicked");
  },
  true
); // Enable capturing
```

If you click the button, the output will be:

```
Parent clicked
Child clicked
```

- The event captures from the parent to the child.

## 3. **Event Delegation**

- **Definition**: A technique where you delegate event handling to a parent element instead of attaching event listeners to individual child elements.
- **Why Use It**:
  - Improves performance by reducing the number of event listeners.
  - Simplifies handling dynamic content (e.g., elements added to the DOM after the page loads).
- **How It Works**: Use event bubbling to handle events at a higher level in the DOM tree.
- **Example**:

```html
<ul id="list">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

```javascript
document.getElementById("list").addEventListener("click", (event) => {
  if (event.target.tagName === "LI") {
    console.log("Clicked on:", event.target.textContent);
  }
});
```

- Instead of adding a click listener to each `<li>`, you add one to the parent `<ul>` and use event.target to identify the clicked element.

# 26. Callback Hell

**Callback hell** refers to a situation in programming, especially in JavaScript, where multiple nested callbacks make the code difficult to read, understand, and maintain. This problem often arises when you have several asynchronous operations that depend on each other, and each operation uses a callback to handle its result.

**Example of Callback Hell:**

```javascript
getUserData(userId, (user) => {
  getPostsByUser(user.id, (posts) => {
    getCommentsByPost(posts[0].id, (comments) => {
      sendEmailToUser(user.email, comments, (emailStatus) => {
        console.log("Email sent successfully:", emailStatus);
      });
    });
  });
});
```

- This code becomes harder to manage as the nesting grows with each dependent callback.

**How to Avoid Callback Hell:**

1. **Use Promises:**
   - Promises simplify chaining and improve readability.

```javascript
getUserData(userId)
  .then((user) => getPostsByUser(user.id))
  .then((posts) => getCommentsByPost(posts[0].id))
  .then((comments) => sendEmailToUser(user.email, comments))
  .then((emailStatus) => console.log("Email sent successfully:", emailStatus))
  .catch((error) => console.error(error));
```

2. **Async/Await:**
   - Async/await syntax allows you to write asynchronous code that looks synchronous.

```javascript
async function sendUserEmail(userId) {
  try {
    const user = await getUserData(userId);
    const posts = await getPostsByUser(user.id);
    const comments = await getCommentsByPost(posts[0].id);
    const emailStatus = await sendEmailToUser(user.email, comments);
    console.log("Email sent successfully:", emailStatus);
  } catch (error) {
    console.error(error);
  }
}
```

# 27. Debouncing and Throttling

## 1. Debouncing

Debouncing ensures that a function is executed only after a specified delay has passed since the last time it was invoked.

- **Key Idea:** Wait until the user stops triggering the event for a specific period of time before executing the function.
- **Use Case:** When you want to reduce the number of times a function is executed, especially in scenarios where the final event matters more than intermediate ones.

**Example: Debouncing a Search Input**

```javascript
function debounce(func, delay) {
  let timeout;
  return function (...args) {
    clearTimeout(timeout); // Clear the previous timer
    timeout = setTimeout(() => {
      func(...args); // Call the function with arguments
    }, delay); // Set a new timer
  };
}

// Usage
const search = (query) => {
  console.log("Searching for:", query);
};

const debouncedSearch = debounce(search, 500);

document.getElementById("searchInput").addEventListener("input", (event) => {
  debouncedSearch(event.target.value);
});
```

## 2. Throttling

Throttling ensures that a function is executed at most once every specified interval, regardless of how many times the event is triggered.

- **Key Idea:** Limit the function execution rate to once every X milliseconds.
- **Use Case:** When you want to ensure a function is executed at regular intervals, even if events are triggered more frequently.

**Example: Throttling a Scroll Event**

```javascript
function throttle(func, interval) {
  let lastExecuted = 0;
  return function (...args) {
    const now = Date.now();
    if (now - lastExecuted >= interval) {
      lastExecuted = now;
      func(...args); // Call the function with arguments
    }
  };
}

// Usage
const onScroll = () => {
  console.log("Scroll event triggered!");
};

const throttledScroll = throttle(onScroll, 1000);
window.addEventListener("scroll", throttledScroll);
```

## Key Differences Between Debouncing and Throttling

| Feature          | Debouncing                                    | Throttling                                  |
| ---------------- | --------------------------------------------- | ------------------------------------------- |
| Execution Timing | Executes after the event stops for a delay.   | Executes at regular intervals.              |
| Goal             | Reduce the number of executions.              | Spread executions over a fixed time period. |
| Use Case         | Typing in a search box, window resize.        | Scrolling, mouse dragging, API polling.     |
| Behavior         | Delays execution until the event quiets down. | Ensures periodic execution.                 |

# 28. Classes in JavaScript

Classes in JavaScript are a blueprint for creating objects. They encapsulate data (properties) and behavior (methods) into a single unit. Classes are a fundamental concept in **Object-Oriented Programming (OOP)**, and they allow you to create multiple objects with similar properties and methods in a structured way.

Introduced in **ES6 (ECMAScript 2015)**, classes in JavaScript are syntactic sugar over JavaScript's existing prototype-based inheritance. This means that under the hood, classes still use prototypes, but the syntax is cleaner and more intuitive.

## Simple Example: Creating a Class

Let's create a `Person` class to represent a person with a name and an age. The class will also have a method to greet the person.

```javascript
// Define the class
class Person {
  // Constructor to initialize properties
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  // Method to greet the person
  greet() {
    console.log(
      `Hello, my name is ${this.name} and I am ${this.age} years old.`
    );
  }
}

// Create an object (instance) of the Person class
const person1 = new Person("Alice", 30);

// Access properties and call methods
console.log(person1.name); // Output: Alice
person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
```

## Explanation of the Example

1. **Class Definition**:
   - The `Person` class is defined using the `class` keyword.
   - Inside the class, the `constructor` method is used to initialize the `name` and `age` properties when a new object is created.
2. **Method**:
   - The `greet` method is a function that logs a greeting message using the object's properties.
3. **Instantiation**:
   - The `new` keyword is used to create an instance of the `Person` class (`person1`).
   - The `constructor` is automatically called when the object is created.
4. **Accessing Properties and Methods**:
   - You can access the properties (`name`, `age`) and call the methods (`greet`) on the object.

## Why Use Classes?

- **Reusability**: You can create multiple objects with the same structure and behavior.
- **Encapsulation**: Data and methods are bundled together, making the code more organized.
- **Inheritance**: Classes support inheritance, allowing you to create new classes based on existing ones (more advanced topic).

# 29. Shallow vs Deep Copy in JavaScript

## Shallow Copy

A **shallow copy** creates a new object or array, but the nested objects or arrays within it are still referenced. In other words, a shallow copy copies only the top-level properties and not the nested objects.

### Characteristics:

- **Arrays**: When you create a shallow copy of an array, the array elements themselves are copied, but any nested arrays or objects are still references to the same ones as the original.
- **Objects**: Similarly, for objects, a shallow copy copies the references of the nested objects, rather than copying them completely.

### Example:

```javascript
const obj1 = {
  name: "John",
  address: { city: "New York" },
};
const shallowCopy = { ...obj1 };
console.log(shallowCopy.name); // 'John'
console.log(shallowCopy.address.city); // 'New York'
// Modifying the nested object in shallowCopy also affects obj1
shallowCopy.address.city = "San Francisco";
console.log(obj1.address.city); // 'San Francisco'
```

## Deep Copy

A **deep copy** creates a completely independent copy of an object or array, including all nested objects and arrays. This means the original object and the copied object do not share any references, even for nested structures.

### Characteristics:

- **Arrays**: For a deep copy of an array, both the array elements and all nested arrays or objects are copied.
- **Objects**: In a deep copy of an object, all nested objects are recursively copied, creating independent references for each level.

### Example:

```javascript
const obj1 = {
  name: "John",
  address: { city: "New York" },
};
const deepCopy = JSON.parse(JSON.stringify(obj1));
console.log(deepCopy.name); // 'John'
console.log(deepCopy.address.city); // 'New York'
// Modifying the nested object in deepCopy does NOT affect obj1
deepCopy.address.city = "San Francisco";
console.log(obj1.address.city); // 'New York'
```

## Key Differences

- **Shallow Copy**: Copies only the top-level structure, while nested objects or arrays are still referenced.
- **Deep Copy**: Recursively copies all nested structures, making the copy independent of the original object.

# 30. Understanding NaN in JavaScript

## What is NaN?

`NaN` stands for "Not-a-Number". It is a special value in JavaScript that represents something that is not a valid number. `NaN` is of type `number` and is usually the result of an invalid mathematical operation, such as dividing zero by zero, or attempting to perform arithmetic on non-numeric data.

### Examples:

```javascript
console.log(0 / 0); // NaN (invalid operation)
console.log(Math.sqrt(-1)); // NaN (square root of a negative number)
console.log("hello" * 2); // NaN (invalid operation with a string)
```

## How does `isNaN` work?

The `isNaN` function is used to determine whether a value is `NaN`. However, `isNaN` has some quirks. It first tries to convert the value to a number and then checks if the result is `NaN`.

- If the value is not a valid number, `isNaN` will return `true`.
- If the value is a valid number or can be converted into a number, `isNaN` will return `false`.

### Example:

```javascript
console.log(isNaN(123)); // false (123 is a number)
console.log(isNaN("123")); // false ('123' can be converted to 123)
console.log(isNaN("hello")); // true ('hello' cannot be converted to a number)
console.log(isNaN(NaN)); // true (it checks if the value is NaN)
```

# 31. Client-Side vs Server-Side JavaScript

Client-side and server-side JavaScript refer to the environments where JavaScript code is executed. Here's a breakdown of the key differences:

## 1. Client-Side JavaScript

### Environment

- Runs in the browser (e.g., Chrome, Firefox, Safari)
- Used to enhance user interaction, manipulate the DOM, and handle front-end logic

### Access

- Can only access browser APIs (e.g., `document`, `window`, `localStorage`)
- Cannot directly access server resources like databases or file systems

### Examples

- DOM manipulation (e.g., changing HTML content, styles, or responding to user events like clicks)
- Form validation
- Fetching data from APIs using `fetch` or `XMLHttpRequest`
- Animations and interactive UI elements

### Frameworks/Libraries

- React
- Angular
- Vue.js
- jQuery

### Limitations

- Cannot perform server-side operations like database queries
- Code is visible to users, making it less secure for sensitive operations
- Relies on the user's device and browser capabilities

## 2. Server-Side JavaScript

### Environment

- Runs on a server (e.g., Node.js runtime)
- Used to handle back-end logic, such as database operations, file handling, and API creation

### Access

- Can access server resources like databases, file systems, and environment variables

### Examples

- Creating RESTful APIs or GraphQL endpoints
- Handling authentication and authorization
- Processing and storing data in databases
- Server-side rendering (e.g., Next.js)

### Frameworks/Libraries

- Express.js
- NestJS
- Koa
- Fastify

### Advantages

- Can perform secure operations (e.g., database queries, file uploads)
- Code is not exposed to the client, making it more secure
- Can handle heavy computations and tasks without relying on the client's device

## Key Differences

| Aspect      | Client-Side JavaScript                         | Server-Side JavaScript                                      |
| ----------- | ---------------------------------------------- | ----------------------------------------------------------- |
| Environment | Runs in the browser                            | Runs on a server (e.g., Node.js)                            |
| Purpose     | Handles UI, interactivity, and front-end logic | Handles back-end logic, databases, and APIs                 |
| Access      | Limited to browser APIs                        | Can access server resources (e.g., databases, file systems) |
| Visibility  | Code is visible to users                       | Code is not exposed to users                                |
| Security    | Less secure for sensitive operations           | More secure for sensitive operations                        |
| Performance | Relies on the user's device                    | Can handle heavy computations on the server                 |
| Frameworks  | React, Angular, Vue.js                         | Express.js, NestJS, Fastify                                 |

## Event Loop

# 32. Understanding the JavaScript Event Loop

## Overview

The **Event Loop** is a fundamental mechanism in JavaScript that handles asynchronous operations while maintaining JavaScript's single-threaded nature. It orchestrates the execution of code by managing different types of tasks: synchronous code, promises, timers, and event listeners.

## Why is the Event Loop Important?

- **Non-Blocking Execution**: Enables handling of asynchronous tasks like network requests without blocking the main thread
- **Performance Enhancement**: Prevents UI freezing by delegating heavy tasks to Web APIs
- **Asynchronous Operation Management**: Efficiently handles Promises, `setTimeout`, `fetch()`, and other background tasks
- **UI Responsiveness**: Maintains smooth user interface by prioritizing microtasks before rendering

## Components of the Event Loop

### 1. Call Stack

The Call Stack is the primary executor of synchronous code, following the LIFO (Last In, First Out) principle:

```javascript
function first() {
  console.log("First");
}
function second() {
  console.log("Second");
}
first();
second();
console.log("End");

// Output:
// First
// Second
// End
```

### 2. Web APIs

Browser or Node.js-provided APIs handle asynchronous operations including:

- `setTimeout()` and `setInterval()`
- `fetch()` requests
- DOM Events
- `MutationObserver`

### 3. Microtask Queue

Handles high-priority tasks that execute immediately after the call stack empties:

- Promise callbacks (`.then()`, `.catch()`, `.finally()`)
- `queueMicrotask()`
- `MutationObserver` callbacks

Example of microtask priority:

```javascript
console.log("Start");
setTimeout(() => console.log("setTimeout"), 0);
Promise.resolve().then(() => console.log("Promise Resolved"));
console.log("End");

// Output:
// Start
// End
// Promise Resolved
// setTimeout
```

### 4. Callback Queue

Manages lower-priority tasks from:

- `setTimeout()`
- `setInterval()`
- `setImmediate()` (Node.js)
- I/O operations

### 5. Event Loop Process

1. Executes all synchronous code in the Call Stack
2. Processes the Microtask Queue
3. Processes the Callback Queue
4. Continuously repeats this cycle

## Comprehensive Example

```javascript
console.log("Start");
setTimeout(() => console.log("setTimeout"), 0);
Promise.resolve().then(() => console.log("Promise"));
queueMicrotask(() => console.log("Microtask"));
console.log("End");

// Output:
// Start
// End
// Promise
// Microtask
// setTimeout
```

## Key Concepts Summary

| Component       | Description                                                 |
| --------------- | ----------------------------------------------------------- |
| Call Stack      | Executes synchronous code one function at a time            |
| Web APIs        | Handles asynchronous tasks outside the main thread          |
| Microtask Queue | High-priority queue that executes before the callback queue |
| Callback Queue  | Standard queue for timer and I/O callbacks                  |
| Event Loop      | Coordinates task execution between queues and call stack    |

# 33. Arrow Functions in JavaScript

## Introduction

Arrow functions are a concise syntax for writing functions in JavaScript. Introduced in ES6, they simplify function expressions and provide lexical `this` binding.

## Syntax

```javascript
// Regular function
function add(a, b) {
  return a + b;
}

// Equivalent Arrow Function
const add = (a, b) => a + b;
console.log(add(5, 3)); // Output: 8
```

## Key Features

- **Shorter Syntax**: Less boilerplate compared to normal functions.
- **Implicit Return**: Single-expression functions return values without using `return`.
- **Lexical `this`**: `this` is inherited from the surrounding scope.
- **No `arguments` Object**: Arrow functions do not have their own `arguments` object.

## Differences Between Arrow and Normal Functions

| Feature                | Normal Function                                | Arrow Function                                   |
| ---------------------- | ---------------------------------------------- | ------------------------------------------------ |
| **Syntax**             | Uses `function` keyword                        | Uses `=>` (arrow syntax)                         |
| **`this` Binding**     | Has its own `this`, determined by call context | Inherits `this` from lexical scope               |
| **Implicit Return**    | Requires explicit `return`                     | Single-expression functions return automatically |
| **`arguments` Object** | Available                                      | Not available                                    |
| **Constructor Usage**  | Can be used with `new`                         | Cannot be used with `new`                        |
| **Object Methods**     | Suitable                                       | Not recommended                                  |
| **Hoisting**           | Function declarations are hoisted              | Not hoisted when assigned to a variable          |

# 34. JavaScript Functions: Callback, Higher-Order Functions, and IIFE

## 1. Callback Function

A callback function is a function that is passed as an argument to another function and is executed later. Callbacks are commonly used in asynchronous programming, such as handling API requests, file reading, and event listeners.

### Example of a Callback Function

```javascript
function greet(name, callback) {
  console.log("Hello, " + name);
  callback();
}

function sayGoodbye() {
  console.log("Goodbye!");
}

greet("Alice", sayGoodbye);
// Output:
// Hello, Alice
// Goodbye!
```

### Key Points:

- Callbacks help in executing code after another function finishes execution.
- Commonly used in `setTimeout`, `setInterval`, event listeners, and API requests.

### Example: Asynchronous Callback with `setTimeout`

```javascript
setTimeout(() => {
  console.log("This message appears after 2 seconds");
}, 2000);
```

## 2. Higher-Order Function

A higher-order function is a function that takes another function as an argument or returns a function.

### Example: Function Taking Another Function as an Argument

```javascript
function operate(a, b, operation) {
  return operation(a, b);
}

function add(x, y) {
  return x + y;
}

console.log(operate(5, 3, add)); // Output: 8
```

### Example: Function Returning Another Function

```javascript
function multiplyBy(factor) {
  return function (number) {
    return number * factor;
  };
}

const double = multiplyBy(2);
console.log(double(5)); // Output: 10
```

### Key Points:

- Higher-order functions enable functional programming.
- Used in `map`, `filter`, `reduce` functions in JavaScript.

### Example: Using `map` with a Higher-Order Function

```javascript
const numbers = [1, 2, 3, 4];
const doubled = numbers.map((num) => num * 2);
console.log(doubled); // Output: [2, 4, 6, 8]
```

## 3. Immediately Invoked Function Expression (IIFE)

An Immediately Invoked Function Expression (IIFE) is a function that executes immediately after it is defined.

### Syntax:

```javascript
(function () {
  console.log("IIFE is executed immediately!");
})();
```

### Example: IIFE with Parameters

```javascript
(function (name) {
  console.log("Hello, " + name);
})("Alice");
```

### Why Use IIFE?

- Avoids polluting the global scope by creating variables inside a local scope.
- Useful for initialization logic that only needs to run once.

### Example: IIFE for Encapsulation

```javascript
const counter = (function () {
  let count = 0;
  return {
    increment: () => ++count,
    decrement: () => --count,
    getCount: () => count,
  };
})();

console.log(counter.increment()); // Output: 1
console.log(counter.getCount()); // Output: 1
```

# Currying in JavaScript

## What is Currying?

Currying is a functional programming technique where a function that takes multiple arguments is transformed into a series of functions, each taking a single argument.

For example, instead of writing:

```js
function add(a, b) {
  return a + b;
}
```

We use currying to transform it into:

```js
const curriedAdd = (a) => (b) => a + b;
```

Now, we can call it like this:

```js
console.log(curriedAdd(2)(3)); // Output: 5
```

---

## Why Use Currying?

### 1. **Avoid Repeating Arguments**

Currying allows partial application of functions, meaning you can pass arguments one at a time.

```js
const add5 = curriedAdd(5);
console.log(add5(10)); // Output: 15
```

This is useful when you need to reuse the same function multiple times with a fixed first argument.

### 2. **Improved Code Readability & Reusability**

Breaking functions into smaller parts makes them easier to understand and maintain.

### 3. **Function Composition**

It helps in combining multiple small functions to create more complex functions.

### 4. **Better Handling of Asynchronous Operations**

Currying simplifies logic in frameworks like Redux and middleware operations.

---

## Uses of Currying

### 1. **Event Handlers in React**

```js
const handleClick = (message) => (event) => {
  console.log(message, event.target);
};

<button onClick={handleClick("Button clicked!")}>Click Me</button>;
```

Here, `handleClick` handles the event and additional arguments separately.

### 2. **Middleware in Express.js**

```js
const logger = (prefix) => (req, res, next) => {
  console.log(`${prefix} - ${req.method} ${req.url}`);
  next();
};

app.use(logger("LOG"));
```

This allows for reusable middleware with custom prefixes.

### 3. **API Calls with Predefined Headers**

```js
const fetchWithAuth = (token) => (url) =>
  fetch(url, {
    headers: { Authorization: `Bearer ${token}` },
  });

const apiCall = fetchWithAuth("my-secret-token");
apiCall("https://api.example.com/data");
```

This avoids passing the token every time a request is made.

### 4. **Dynamic Styling in Tailwind CSS with React**

```js
const applyStyle = (baseClass) => (extraClass) => `${baseClass} ${extraClass}`;

const buttonClass = applyStyle("bg-blue-500 text-white px-4 py-2");
console.log(buttonClass("rounded-lg")); // bg-blue-500 text-white px-4 py-2 rounded-lg
```

---

# 36. map(), filter(), and reduce() in JavaScript

## **1. map()**

The `map()` method creates a new array by applying a function to each element of the original array. It does not modify the original array.

### **Example:**

```js
const numbers = [1, 2, 3, 4];
const doubled = numbers.map((num) => num * 2);
console.log(doubled); // Output: [2, 4, 6, 8]
```

### 🔹 **Key Points:**

- Returns a new array.
- Does not modify the original array.
- Used when you need to transform each element.

---

## **2. filter()**

The `filter()` method creates a new array containing only the elements that satisfy a given condition.

### **Example:**

```js
const numbers = [1, 2, 3, 4, 5];
const evenNumbers = numbers.filter((num) => num % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]
```

### 🔹 **Key Points:**

- Returns a new array.
- Only includes elements that pass the condition.
- Used when you need to filter out certain elements.

---

## **3. reduce()**

The `reduce()` method reduces an array to a single value by executing a function on each element.

### **Example:**

```js
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // Output: 10
```

### 🔹 **Key Points:**

- Returns a single accumulated value.
- Often used for calculations like sums, averages, etc.
- Needs an initial value (second parameter).

# 37. forEach vs map in JavaScript

Both `forEach` and `map` are used to iterate over arrays in JavaScript, but they have key differences in behavior and use cases.

## Key Differences

| Feature          | `forEach`                                                                      | `map`                                                                  |
| ---------------- | ------------------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| **Purpose**      | Executes a function for each array element.                                    | Creates a new array by transforming each element.                      |
| **Return Value** | `undefined` (does not return a new array).                                     | Returns a new array with modified values.                              |
| **Chaining**     | Cannot be chained (since it returns `undefined`).                              | Can be chained with other array methods like `.filter()`, `.reduce()`. |
| **Mutation**     | Often used for side effects (e.g., updating UI, modifying external variables). | Used for data transformation without modifying the original array.     |

# 37. call(), apply(), and bind() in JavaScript

## 1. `call` Method

### Definition

The `call` method invokes a function with a specified `this` value and individual arguments.

### Syntax

```javascript
functionName.call(thisArg, arg1, arg2, ...);
```

- `thisArg`: The value to be passed as the this context to the function.
- `arg1, arg2, ...`: Arguments to be passed to the function.

### Real-Life Use Case

```javascript
function calculateTotal(discount) {
  return (
    this.items.reduce((total, item) => total + item.price, 0) * (1 - discount)
  );
}

const customer1 = {
  items: [{ price: 100 }, { price: 200 }],
};

const customer2 = {
  items: [{ price: 50 }, { price: 300 }],
};

const total1 = calculateTotal.call(customer1, 0.1);
console.log(total1); // Output: 270

const total2 = calculateTotal.call(customer2, 0.2);
console.log(total2); // Output: 280
```

## 2. `apply` Method

### Definition

The `apply` method is similar to `call`, but it takes arguments as an array (or array-like object) instead of individual arguments.

### Syntax

```javascript
functionName.apply(thisArg, [argsArray]);
```

- `thisArg`: The value to be passed as the this context to the function.
- `argsArray`: An array of arguments to be passed to the function.

### Real-Life Use Case

```javascript
function findMax() {
  return Math.max.apply(null, this.numbers);
}

const dataset1 = {
  numbers: [10, 20, 30, 40],
};

const dataset2 = {
  numbers: [5, 15, 25],
};

const max1 = findMax.apply(dataset1);
console.log(max1); // Output: 40

const max2 = findMax.apply(dataset2);
console.log(max2); // Output: 25
```

## 3. `bind` Method

### Definition

The `bind` method creates a new function with a fixed `this` value and optionally pre-filled arguments. Unlike `call` and `apply`, `bind` does not immediately invoke the function; it returns a new function that can be called later.

### Syntax

```javascript
const newFunction = functionName.bind(thisArg, arg1, arg2, ...);
```

- `thisArg`: The value to be passed as the this context to the function.
- `arg1, arg2, ...`: Optional arguments to be pre-filled in the new function.

### Real-Life Use Case

```javascript
function sendGreeting(message) {
  return `${this.name}, ${message}`;
}

const user = {
  name: "John",
};

const greetJohn = sendGreeting.bind(user);

console.log(greetJohn("welcome to our website!"));
// Output: "John, welcome to our website!"
console.log(greetJohn("thank you for subscribing!"));
// Output: "John, thank you for subscribing!"
```

## Key Differences

| Method  | Invocation | Arguments Format     | Use Case                                    |
| ------- | ---------- | -------------------- | ------------------------------------------- |
| `call`  | Immediate  | Individual arguments | When you know the arguments upfront         |
| `apply` | Immediate  | Array of arguments   | When arguments are in an array or list      |
| `bind`  | Deferred   | Individual arguments | When you want to create a reusable function |

## Additional Real-Life Scenarios

### Borrowing Methods

```javascript
const car = {
  name: "Tesla",
  drive() {
    console.log(`${this.name} is driving!`);
  },
};

const bike = {
  name: "Harley",
};

car.drive.call(bike); // Output: "Harley is driving!"
```

### Currying with `bind`

```javascript
function multiply(a, b) {
  return a * b;
}

const double = multiply.bind(null, 2);
console.log(double(5)); // Output: 10 (2 * 5)
```

### Event Handlers

```javascript
const button = document.querySelector("button");

const handler = {
  message: "Button clicked!",
  handleClick() {
    console.log(this.message);
  },
};

button.addEventListener("click", handler.handleClick.bind(handler));
```

### What is Memoization ?

Memoization is an optimization technique in JavaScript used to speed up computer programs by storing the results of expensive function calls and returning the cached result when the same inputs occur again.

Here's a simple implementation:

```javascript
function memoize(fn) {
  const cache = new Map();

  return function (...args) {
    const key = JSON.stringify(args);

    if (cache.has(key)) {
      return cache.get(key);
    }

    const result = fn.apply(this, args);
    cache.set(key, result);
    return result;
  };
}

// Example: Fibonacci calculation
const fibonacci = memoize((n) => {
  if (n <= 1) return n;
  return fibonacci(n - 1) + fibonacci(n - 2);
});

console.log(fibonacci(40)); // Significantly faster than non-memoized version
```

Key benefits:

- Reduces computational complexity
- Avoids redundant calculations
- Improves performance for recursive or computationally expensive functions

Practical use cases:

- Complex mathematical calculations
- API call caching
- Expensive recursive algorithms
- Computationally intensive function results

Considerations:

- Increases memory usage
- Best for pure functions with predictable inputs
- Not suitable for functions with side effects

# 38. Object Prototype in JavaScript

## **Definition**

In JavaScript, an **object prototype** is the mechanism that allows objects to inherit properties and methods from other objects. This forms the foundation of **prototype-based inheritance**, where objects can share behavior without requiring traditional class-based inheritance.

Every JavaScript object has an internal property called `[[Prototype]]`, which refers to another object. This referenced object (the **prototype**) serves as a blueprint, providing properties and methods that the current object can use. If a property or method is not found on the object itself, JavaScript looks for it in the prototype chain.

## **Key Concepts**

1. **Prototype Chain**: If a property is not found on an object, JavaScript will look up the prototype chain until it finds the property or reaches `null`.
2. **`prototype` Property**: Functions (including constructor functions) have a special `prototype` property that defines properties and methods for objects created using that function.
3. **Shared Methods**: Methods defined on an object's prototype are shared among all instances of that object.

## **Examples**

### **1. Constructor Function Example**

```javascript
// Constructor function
function Animal(name) {
  this.name = name;
}

// Adding a method to the prototype
Animal.prototype.speak = function () {
  console.log(`${this.name} makes a sound`);
};

const dog = new Animal("Dog");
dog.speak(); // Output: Dog makes a sound

console.log(dog.__proto__ === Animal.prototype); // true
console.log(Animal.prototype.__proto__ === Object.prototype); // true
```

### **2. Array Prototype Example**

```javascript
// Adding a custom method to Array prototype
Array.prototype.sum = function () {
  return this.reduce((acc, val) => acc + val, 0);
};

const numbers = [1, 2, 3, 4, 5];
console.log(numbers.sum()); // Output: 15
```

### **3. Object Prototype Example**

```javascript
// Creating an object and setting its prototype manually
const person = {
  greet: function () {
    console.log("Hello!");
  },
};

const employee = Object.create(person);
employee.greet(); // Output: Hello!

console.log(employee.__proto__ === person); // true
```

### **4. String Prototype Example**

```javascript
// Adding a custom method to String prototype
String.prototype.reverse = function () {
  return this.split("").reverse().join("");
};

const message = "Hello World";
console.log(message.reverse()); // Output: "dlroW olleH"
```

# 39. Generator Functions in JavaScript

A **generator function** is a special type of function that allows execution to be **paused and resumed later**, making it useful for handling iteration, asynchronous tasks, and memory-efficient operations. Unlike regular functions that execute fully when called, generator functions return values one at a time using the `yield` keyword while maintaining their state.

## **Key Features**

1. **Lazy Execution** – Code runs only when `next()` is called.
2. **Pausing and Resuming** – Uses `yield` to pause execution and resume later.
3. **Iterator Implementation** – Works seamlessly with iterators.
4. **State Retention** – Remembers the last execution position.

## **Basic Example**

```javascript
function* countUp() {
  yield 1;
  yield 2;
  yield 3;
}

const counter = countUp();
console.log(counter.next().value); // 1
console.log(counter.next().value); // 2
console.log(counter.next().value); // 3
console.log(counter.next().done); // true
```

## **Real-Life Example: Pagination Data Fetching**

Imagine you need to fetch paginated data from an API, but instead of loading everything at once, you fetch only what is needed.

```javascript
function* fetchPages(totalPages) {
  for (let page = 1; page <= totalPages; page++) {
    yield `Fetching data for page ${page}...`;
  }
}

const paginator = fetchPages(3);
console.log(paginator.next().value); // "Fetching data for page 1..."
console.log(paginator.next().value); // "Fetching data for page 2..."
console.log(paginator.next().value); // "Fetching data for page 3..."
console.log(paginator.next().done); // true
```

## **Use Cases of Generator Functions**

- **Iterating large datasets efficiently**
- **Lazy-loading content (e.g., pagination, infinite scrolling)**
- **Handling asynchronous tasks (e.g., async/await, Promises)**
- **Simulating streams of data (e.g., logs, real-time events)**

# JavaScript Array and String Methods

## Array Methods

1. **push()**
   - Adds one or more elements to the end of the array.
   ```javascript
   const arr = [1, 2];
   arr.push(3); // [1, 2, 3]
   ```
2. **pop()**
   - Removes the last element from the array.
   ```javascript
   const arr = [1, 2, 3];
   arr.pop(); // [1, 2]
   ```
3. **shift()**
   - Removes the first element from the array.
   ```javascript
   const arr = [1, 2, 3];
   arr.shift(); // [2, 3]
   ```
4. **unshift()**
   - Adds one or more elements to the beginning of the array.
   ```javascript
   const arr = [2, 3];
   arr.unshift(1); // [1, 2, 3]
   ```
5. **splice()**
   - Adds or removes elements from the array.
   ```javascript
   const arr = [1, 2, 3, 4];
   arr.splice(2, 1); // Removes 1 element at index 2 → [1, 2, 4]
   const arr = [1, 2, 4];
   arr.splice(2, 0, 3); // Adds 3 at index 2 → [1, 2, 3, 4]
   ```
6. **slice()**
   - Returns a shallow copy of a portion of the array.
   ```javascript
   const arr = [1, 2, 3, 4];
   arr.slice(1, 3); // [2, 3]
   ```
7. **map()**
   - Returns a new array by applying a function to each element.
   ```javascript
   const arr = [1, 2, 3];
   const doubled = arr.map((num) => num * 2); // [2, 4, 6]
   ```
8. **filter()**
   - Returns a new array with elements that pass a test.
   ```javascript
   const arr = [1, 2, 3, 4];
   const even = arr.filter((num) => num % 2 === 0); // [2, 4]
   ```
9. **reduce()**
   - Reduces the array to a single value by applying a function.
   ```javascript
   const arr = [1, 2, 3, 4];
   const sum = arr.reduce((acc, num) => acc + num, 0); // 10
   ```
10. **find()**
    - Returns the first element that satisfies a condition.
    ```javascript
    const arr = [1, 2, 3, 4];
    const firstEven = arr.find((num) => num % 2 === 0); // 2
    ```
11. **includes()**
    - Checks if an array includes a certain value.
    ```javascript
    const arr = [1, 2, 3];
    arr.includes(2); // true
    ```
12. **indexOf()**
    - Returns the first index of a value; -1 if not found.
    ```javascript
    const arr = [1, 2, 3];
    arr.indexOf(2); // 1
    ```
13. **sort()**
    - Sorts the elements of the array (default is lexicographical).
    ```javascript
    const arr = [3, 1, 2];
    arr.sort(); // [1, 2, 3]
    ```
14. **reverse()**
    - Reverses the array in place.
    ```javascript
    const arr = [1, 2, 3];
    arr.reverse(); // [3, 2, 1]
    ```
15. **concat()**
    - Merges two or more arrays.
    ```javascript
    const arr1 = [1, 2];
    const arr2 = [3, 4];
    arr1.concat(arr2); // [1, 2, 3, 4]
    ```

## String Methods

1. **charAt()**
   - Returns the character at the specified index.
   ```javascript
   const str = "hello";
   str.charAt(1); // "e"
   ```
2. **substring()**
   - Extracts a portion of the string between two indices.
   ```javascript
   const str = "hello";
   str.substring(1, 4); // "ell"
   ```
3. **slice()**
   - Extracts a section of the string (similar to substring but supports negative indices).
   ```javascript
   const str = "hello";
   str.slice(1, 4); // "ell"
   ```
4. **toUpperCase()**
   - Converts the string to uppercase.
   ```javascript
   const str = "hello";
   str.toUpperCase(); // "HELLO"
   ```
5. **toLowerCase()**
   - Converts the string to lowercase.
   ```javascript
   const str = "HELLO";
   str.toLowerCase(); // "hello"
   ```
6. **trim()**
   - Removes whitespace from both ends of the string.
   ```javascript
   const str = " hello ";
   str.trim(); // "hello"
   ```
7. **split()**
   - Splits the string into an array of substrings.
   ```javascript
   const str = "hello world";
   str.split(" "); // ["hello", "world"]
   ```
8. **replace()**
   - Replaces a substring with another string.
   ```javascript
   const str = "hello world";
   str.replace("world", "everyone"); // "hello everyone"
   ```
9. **replaceAll()**
   - Replaces all occurrences of a substring with another string.
   ```javascript
   const str = "hello world world";
   str.replaceAll("world", "everyone"); // "hello everyone everyone"
   ```
10. **includes()**
    - Checks if the string contains a certain substring.
    ```javascript
    const str = "hello world";
    str.includes("world"); // true
    ```
11. **indexOf()**
    - Returns the first index of a substring; -1 if not found.
    ```javascript
    const str = "hello world";
    str.indexOf("world"); // 6
    ```
12. **startsWith()**
    - Checks if the string starts with a given substring.
    ```javascript
    const str = "hello world";
    str.startsWith("hello"); // true
    ```
13. **endsWith()**
    - Checks if the string ends with a given substring.
    ```javascript
    const str = "hello world";
    str.endsWith("world"); // true
    ```
14. **join()** (For Arrays of Strings)
    - Joins all elements of an array into a string.
    ```javascript
    const arr = ["hello", "world"];
    arr.join(" "); // "hello world"
    ```

---
