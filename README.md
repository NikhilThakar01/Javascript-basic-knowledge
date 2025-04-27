# JavaScript Basics: Questions and Answers

This README contains a collection of commonly asked JavaScript basic questions along with concise answers to help and understand the core concepts.

---

## 📘 Questions and Answers

### 1. What is JavaScript?
JavaScript is a lightweight, interpreted programming language primarily used to create interactive effects within web browsers.

---

### 2. What are the different data types in JavaScript?
JavaScript has several data types, which are mainly divided into primitive and non-primitive (reference) types.

- Primitive Data Types (simple, immutable):
    1. String – Text
    2. Number – Any number (integer or decimal)
    3. Boolean – True or false
    4. Undefined – A variable declared but not assigned a value
    5. Null – Intentionally no value
    6. BigInt – For very large integers
    7. Symbol – Unique and immutable values, often used as object keys

- Non-Primitive (Reference) Data Types:
    1. Object – A collection of key-value pairs
    2. Array – A list of values
    3. Function – A block of code designed to perform a task

JavaScript is also dynamically typed, meaning you don't have to declare the type—JavaScript figures it out at runtime.

---

## 3. What is `undefined` vs `null`?

- `undefined`: A variable declared but not assigned a value.
- `null`: A value that represents "no value" or "empty".

---

### 4. What is the difference between `var`, `let`, and `const`?
In JavaScript, let, var, and const are used to declare variables, but they behave a bit differently. Here's a quick breakdown:

| Keyword | Scope        | Reassignable | Redeclarable | Hoisted |
|---------|--------------|--------------|---------------|---------|
| `var`   | Function      | Yes          | Yes           | Yes (initialized as undefined) |
| `let`   | Block         | Yes          | No            | Yes (not initialized) |
| `const` | Block         | No           | No            | Yes (not initialized) |

---

### 5. What is the difference between `==` and `===`?
- `==` compares values after type coercion.
- `===` compares both value and type (strict equality).

---

### 6. What are JavaScript functions?
Functions are reusable blocks of code that perform a specific task. 
They are defined using the `function` keyword or arrow functions (`=>`).

```js
function greet(name) {
  return "Hello " + name;
}
```

---

### 7. How do you create an object in JavaScript?
```javascript
const person = {
  name: "Alice",
  age: 25
};
```

---

### 8. How do you create an array?
```javascript
let colors = ["red", "green", "blue"];
```

---

### 9. What is a loop? Give an example.
A loop lets you repeat code multiple times.

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

---

### 10. What is the DOM?
The DOM (Document Object Model) is a programming interface that represents the structure of a web page as a tree of objects.
- When a browser loads a webpage, it turns the HTML into a DOM.
- The DOM lets JavaScript access and change content, structure, and styles on the page.

---

### 11. What is an event in JavaScript?
An event is an action that occurs in the browser, such as a click, keypress, or page load.
JavaScript can respond using event listeners.

```javascript
document.getElementById("btn").addEventListener("click", function() {
  alert("Button clicked!");
});
```

---

### 12. What is hoisting in JavaScript?
Hoisting is JavaScript’s behavior of moving variable and function declarations to the top of their scope before code execution.

```javascript
console.log(x); // undefined
var x = 5;
```

---

### 13. What is a closure?
A closure in JavaScript is when a function remembers the variables from its outer (enclosing) scope, even after that outer function has finished executing.

- Why closures are useful:
    1. Data privacy (like private variables)
    2. Remembering state
    3. Building function factories or custom callbacks

```javascript
function outer() {
  let count = 0;

  return function inner() {
    count++;
    console.log(count);
  };
}

const counter = outer();

counter(); // 1
counter(); // 2
counter(); // 3
```

---

### 14. What is a Higher-Order Function (HOF)?
A Higher-Order Function is a function that either:

- Takes another function as an argument, or
- Returns a function as a result

Basically, functions that work with other functions.

- JavaScript includes built-in HOFs like:
    - map()
    - filter()
    - reduce()
    - forEach()
    - setTimeout(), setInterval()

1. Example 1: Passing a function as an argument
```javascript
function sayHello(name) {
  return "Hello, " + name;
}

function greetUser(callback) {
  const result = callback("Alice");
  console.log(result);
}

greetUser(sayHello); // Output: Hello, Alice
```

2. Example 2: Returning a function
```javascript
function multiplyBy(factor) {
  return function(number) {
    return number * factor;
  };
}

const double = multiplyBy(2);
console.log(double(5)); // Output: 10
```

---

### 15. what is callback?
A callback in JavaScript is a function passed as an argument to another function — and it's usually called (executed) later.

- Why use callbacks?
    - To run code after something happens (like after a delay or data fetch)
    - To customize how a function behaves
    - To handle asynchronous operations

Here, `sayHello` is a callback function passed to `greetUser`.

```javascript
function sayHello(name) {
  console.log("Hello, " + name);
}

function greetUser(callback) {
  const name = "Alice";
  callback(name); // sayHello gets called here
}

greetUser(sayHello); // Output: Hello, Alice
```

A **callback doesn't run immediately** — it runs **when the outer function decides to call it**.

---