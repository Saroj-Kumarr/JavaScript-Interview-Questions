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
