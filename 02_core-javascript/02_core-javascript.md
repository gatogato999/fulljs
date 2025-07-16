# Chapter 2: Core JavaScript - The Language Fundamentals

## 2.1 JavaScript Syntax and Basic Constructs

JavaScript, at its heart, is a dynamically typed, object-oriented, and
functional programming language. Understanding its fundamental syntax and
constructs is paramount before diving into more complex topics. This section
covers the absolute basics, forming the building blocks of any JavaScript
application.

### 2.1.1 Variables and Data Types

Variables are containers for storing data values. JavaScript has evolved in how
variables are declared, with `let` and `const` being the modern standards,
largely replacing the older `var` keyword due to their improved scoping rules.

*   **`var`**: Declares a variable. It has function scope, meaning it's
    accessible throughout the function it's declared in, regardless of block
    scope (like `if` statements or `for` loops). This can lead to unexpected
    behavior, especially in loops or conditional blocks.
*   **`let`**: Declares a block-scoped local variable. This means the variable
    is only accessible within the block (e.g., `{}`) where it is defined. `let`
    variables can be reassigned.
*   **`const`**: Declares a block-scoped local variable whose value cannot be
    reassigned once initialized. It's crucial to understand that `const`
    prevents reassignment of the variable itself, not necessarily the
    immutability of the value it holds (e.g., you can still modify properties
    of an object declared with `const`).

**Best Practice:** Always prefer `const` when a variable's value will not
change. Use `let` when reassignment is necessary. Avoid `var` in modern
JavaScript development.

JavaScript has several primitive data types and one complex data type:

| Data Type   | Description                                                              | Example                                 |
| :---------- | :----------------------------------------------------------------------- | :-------------------------------------- |
| `string`    | Represents textual data. Enclosed in single (`'`) or double (`"`) quotes. | `"Hello, World!"`, `'Node.js'`          |
| `number`    | Represents both integer and floating-point numbers.                      | `10`, `3.14`, `-5`                      |
| `boolean`   | Represents a logical entity and can have two values: `true` or `false`.  | `true`, `false`                         |
| `undefined` | A variable that has been declared but not yet assigned a value.          | `let x;`                                |
| `null`      | Represents the intentional absence of any object value.                  | `let y = null;`                         |
| `symbol`    | (ES6) A unique and immutable primitive value. Used for unique object keys. | `Symbol('description')`                 |
| `bigint`    | (ES2020) Represents whole numbers larger than 2^53 - 1.                  | `10n`, `9007199254740991n`              |
| `object`    | A collection of properties, where each property has a name and a value.  | `{ name: 'Alice' }`, `[1, 2, 3]`, `null` |

It's important to note that `typeof null` returns `'object'`, which is a
historical bug in JavaScript. Arrays and functions are also special types of
objects.

### 2.1.2 Operators

Operators perform operations on values and variables. JavaScript supports
various types of operators:

*   **Arithmetic Operators:** `+`, `-`, `*`, `/`, `%` (modulus), `**`
    (exponentiation), `++` (increment), `--` (decrement).
*   **Assignment Operators:** `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `**=`.
*   **Comparison Operators:** `==` (loose equality), `===` (strict equality),
    `!=` (loose inequality), `!==` (strict inequality), `>`, `<`, `>=`, `<=`.
    **Always prefer `===` and `!==`** to avoid type coercion issues.
*   **Logical Operators:** `&&` (AND), `||` (OR), `!` (NOT).
*   **Bitwise Operators:** `&`, `|`, `^`, `~`, `<<`, `>>`, `>>>`.
*   **Ternary Operator:** `condition ? expr1 : expr2` (a shorthand for `if-else`).

### 2.1.3 Control Flow

Control flow statements dictate the order in which instructions are executed.

#### Conditional Statements

*   **`if...else if...else`**: Executes a block of code if a specified
    condition is true. If the condition is false, another block can be
    executed.

    ```javascript
    if (score >= 90) {
        console.log("Grade A");
    } else if (score >= 80) {
        console.log("Grade B");
    } else {
        console.log("Grade C");
    }
    ```

*   **`switch`**: Evaluates an expression, matching the expression's value to a
    `case` clause, and executes statements associated with that case.

    ```javascript
    const day = 'Monday';
    switch (day) {
        case 'Monday':
            console.log('Start of the week');
            break;
        case 'Friday':
            console.log('End of the week');
            break;
        default:
            console.log('Mid-week');
    }
    ```

#### Loops

Loops are used to execute a block of code repeatedly.

*   **`for` loop**: Repeats a block of code a specified number of times.

    ```javascript
    for (let i = 0; i < 5; i++) {
        console.log(i);
    }
    ```

*   **`while` loop**: Repeats a block of code as long as a specified condition
    is true.

    ```javascript
    let count = 0;
    while (count < 3) {
        console.log(count);
        count++;
    }
    ```

*   **`do...while` loop**: Similar to `while`, but the block of code is
    executed at least once before the condition is tested.

    ```javascript
    let i = 0;
    do {
        console.log(i);
        i++;
    } while (i < 0); // This will still log 0 once
    ```

*   **`for...in` loop**: Iterates over the enumerable properties of an object.
    **Not recommended for arrays** due to potential issues with order and
    inherited properties.

    ```javascript
    const person = { name: 'John', age: 30 };
    for (const key in person) {
        console.log(`${key}: ${person[key]}`);
    }
    ```

*   **`for...of` loop**: (ES6) Iterates over iterable objects (like Arrays,
    Strings, Maps, Sets, NodeLists, etc.), providing direct access to the
    values.

    ```javascript
    const colors = ['red', 'green', 'blue'];
    for (const color of colors) {
        console.log(color);
    }
    ```

**Best Practice:** Use `for...of` for iterating over arrays and other iterable
collections. Use `for` loops when you need index control. Avoid `for...in` for
arrays.

## 2.2 Functions: Building Blocks of Logic

Functions are reusable blocks of code that perform a specific task. They are
fundamental to organizing code, promoting reusability, and making programs
modular.

### 2.2.1 Function Declaration and Expression

*   **Function Declaration:** Defined using the `function` keyword, followed by
    a name, a list of parameters, and the function body. They are hoisted,
    meaning they can be called before they are defined in the code.

    ```javascript
    function greet(name) {
        return `Hello, ${name}!`;
    }
    console.log(greet('Alice'));
    ```

*   **Function Expression:** Defined as part of an expression, often assigned
    to a variable. They are not hoisted, so they cannot be called before they
    are defined.

    ```javascript
    const sayHello = function(name) {
        return `Hello, ${name}!`;
    };
    console.log(sayHello('Bob'));
    ```

### 2.2.2 Arrow Functions (ES6)

Arrow functions (`=>`) provide a more concise syntax for writing function
expressions. They also have a different `this` binding behavior, which is a
significant advantage in certain contexts (especially in object methods and
callbacks).

```javascript
// Traditional function expression
const add = function(a, b) {
    return a + b;
};

// Arrow function
const subtract = (a, b) => a - b; // Concise syntax for single expression

const multiply = (a, b) => {
    // Block body for multiple statements
    const result = a * b;
    return result;
};

// Arrow function with no parameters
const sayHi = () => console.log('Hi!');

// Arrow function with one parameter (parentheses optional)
const square = num => num * num;
```

**Key differences of Arrow Functions:**

*   **Concise Syntax:** Shorter to write, especially for single-expression
    functions.
*   **No `this` binding:** They do not have their own `this` context. Instead,
    `this` is lexically bound, meaning it refers to the `this` value of the
    enclosing execution context. This solves common `this` binding issues in
    callbacks.
*   **No `arguments` object:** They do not have their own `arguments` object.
*   **Cannot be used as constructors:** They cannot be called with `new`.

### 2.2.3 Parameters and Arguments

*   **Parameters:** The named variables listed in the function definition.
*   **Arguments:** The actual values passed to the function when it is called.

**Default Parameters (ES6):** Allow parameters to be initialized with a default
value if no value or `undefined` is passed.

```javascript
function greet(name = 'Guest') {
    console.log(`Hello, ${name}!`);
}
greet(); // Hello, Guest!
greet('Charlie'); // Hello, Charlie!
```

**Rest Parameters (ES6):** Allow a function to accept an indefinite number of
arguments as an array.

```javascript
function sumAll(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}
console.log(sumAll(1, 2, 3)); // 6
console.log(sumAll(10, 20, 30, 40)); // 100
```

### 2.2.4 Scope and Closures

**Scope** determines the accessibility of variables, functions, and objects in
some particular part of your code. JavaScript has three main types of scope:

*   **Global Scope:** Variables declared outside any function or block are
    globally scoped and accessible from anywhere in the code.
*   **Function Scope:** Variables declared with `var` inside a function are
    function-scoped, meaning they are only accessible within that function.
*   **Block Scope (ES6 `let`/`const`):** Variables declared with `let` or
    `const` inside a block (`{}`) are block-scoped, meaning they are only
    accessible within that block.

**Closures** are a powerful feature in JavaScript. A closure is the combination
of a function bundled together (enclosed) with references to its surrounding
state (the lexical environment). In simpler terms, a closure gives you access
to an outer function's scope from an inner function, even after the outer
function has finished executing.

```javascript
function outerFunction(outerVariable) {
    return function innerFunction(innerVariable) {
        console.log('Outer Variable:', outerVariable);
        console.log('Inner Variable:', innerVariable);
    };
}

const newFunction = outerFunction('I am outer!');
newFunction('I am inner!'); // innerFunction forms a closure over outerVariable
```

Closures are essential for many advanced JavaScript patterns, including data
privacy, currying, and maintaining state in asynchronous operations.

## 2.3 Objects and Arrays: Working with Collections

Objects and arrays are fundamental data structures in JavaScript for storing
collections of data.

### 2.3.1 Objects

Objects are collections of key-value pairs. Keys (or property names) are
strings (or Symbols), and values can be any data type, including other objects
or functions.

```javascript
const person = {
    firstName: 'Jane',
    lastName: 'Doe',
    age: 25,
    isStudent: false,
    hobbies: ['reading', 'hiking'],
    address: {
        street: '123 Main St',
        city: 'Anytown'
    },
    // Method within an object
    getFullName: function() {
        return `${this.firstName} ${this.lastName}`;
    }
};

// Accessing properties
console.log(person.firstName); // Dot notation
console.log(person['age']);    // Bracket notation (useful for dynamic keys)

// Calling a method
console.log(person.getFullName());

// Adding new properties
person.email = 'jane.doe@example.com';

// Deleting properties
delete person.isStudent;
```

**Object Destructuring (ES6):** A convenient way to extract values from objects
into distinct variables.

```javascript
const { firstName, age } = person;
console.log(firstName, age); // Jane 25

// With renaming
const { lastName: surname } = person;
console.log(surname); // Doe
```

**Spread Syntax (`...`) for Objects (ES2018):** Used to copy enumerable
properties from one object to another or to merge objects.

```javascript
const defaults = { theme: 'dark', notifications: true };
const userSettings = { notifications: false, language: 'en' };

const finalSettings = { ...defaults, ...userSettings };
console.log(finalSettings); // { theme: 'dark', notifications: false, language: 'en' }
```

### 2.3.2 Arrays

Arrays are ordered collections of values. They are zero-indexed, meaning the
first element is at index 0.

```javascript
const fruits = ['apple', 'banana', 'cherry'];

// Accessing elements
console.log(fruits[0]); // apple

// Modifying elements
fruits[1] = 'grape';

// Adding elements
fruits.push('orange'); // Add to end
fruits.unshift('kiwi'); // Add to beginning

// Removing elements
fruits.pop(); // Remove from end
fruits.shift(); // Remove from beginning

// Getting array length
console.log(fruits.length);
```

**Common Array Methods:**

*   **`forEach()`**: Executes a provided function once for each array element.

    ```javascript
    fruits.forEach(fruit => console.log(fruit));
    ```

*   **`map()`**: Creates a new array populated with the results of calling a
    provided function on every element in the calling array.

    ```javascript
    const numbers = [1, 2, 3];
    const doubled = numbers.map(num => num * 2); // [2, 4, 6]
    ```

*   **`filter()`**: Creates a new array with all elements that pass the test
    implemented by the provided function.

    ```javascript
    const evenNumbers = numbers.filter(num => num % 2 === 0); // [2]
    ```

*   **`reduce()`**: Executes a reducer function (that you provide) on each
    element of the array, resulting in a single output value.

    ```javascript
    const sum = numbers.reduce((acc, num) => acc + num, 0); // 6
    ```

*   **`find()`**: Returns the value of the first element in the provided array
    that satisfies the provided testing function. Otherwise, `undefined` is
    returned.
*   **`findIndex()`**: Returns the index of the first element in the array that
    satisfies the provided testing function. Otherwise, -1 is returned.
*   **`some()`**: Tests whether at least one element in the array passes the
    test implemented by the provided function.
*   **`every()`**: Tests whether all elements in the array pass the test
    implemented by the provided function.
*   **`includes()`**: Determines whether an array includes a certain value
    among its entries, returning `true` or `false` as appropriate.

**Array Destructuring (ES6):** A convenient way to extract values from arrays
into distinct variables.

```javascript
const [first, second] = fruits;
console.log(first, second); // apple banana

// Skipping elements
const [, , third] = fruits;
console.log(third); // cherry
```

**Spread Syntax (`...`) for Arrays (ES6):** Used to expand an iterable (like an
array) into individual elements.

```javascript
const arr1 = [1, 2];
const arr2 = [3, 4];
const combined = [...arr1, ...arr2]; // [1, 2, 3, 4]

const copyOfFruits = [...fruits]; // Creates a shallow copy
```

## 2.4 Object-Oriented Programming (OOP) in JavaScript

While JavaScript is often described as a multi-paradigm language, it has strong
support for object-oriented programming, primarily through prototypes rather
than traditional classes (though ES6 introduced `class` syntax as syntactic
sugar over prototypes).

### 2.4.1 Prototypes and Prototypal Inheritance

In JavaScript, every object has a prototype, which is another object that it
inherits properties and methods from. When you try to access a property or
method on an object, JavaScript first checks if the object itself has that
property. If not, it looks up the prototype chain until it finds the property
or reaches the end of the chain (`null`).

```javascript
const animal = {
    eats: true,
    walk() {
        console.log("Animal walks");
    }
};

const rabbit = {
    jumps: true,
    __proto__: animal // rabbit inherits from animal
};

console.log(rabbit.eats); // true (inherited)
rabbit.walk(); // Animal walks (inherited)
```

### 2.4.2 ES6 Classes

ES6 `class` syntax provides a cleaner and more familiar way to create objects
and handle inheritance, but it's important to remember that they are still
fundamentally based on JavaScript's prototypal inheritance model.

```javascript
class Animal {
    constructor(name) {
        this.name = name;
    }

    walk() {
        console.log(`${this.name} walks.`);
    }
}

class Rabbit extends Animal {
    constructor(name, earLength) {
        super(name); // Call parent constructor
        this.earLength = earLength;
    }

    jumps() {
        console.log(`${this.name} jumps.`);
    }

    // Method overriding
    walk() {
        console.log(`${this.name} hops.`);
    }
}

const myRabbit = new Rabbit('Bugs', 'long');
myRabbit.walk(); // Bugs hops.
myRabbit.jumps(); // Bugs jumps.
console.log(myRabbit.name); // Bugs
```

**Key Concepts in Classes:**

*   **`constructor`**: A special method for creating and initializing an object
    created with a class.
*   **`extends`**: Used to create a subclass (child class) of another class.
*   **`super()`**: Used to call the constructor of the parent class.
*   **`Method Overriding`:** A subclass can provide its own implementation of a
    method that is already defined in its parent class.

## 2.5 Functional Programming Concepts

JavaScript's nature as a first-class function language makes it well-suited for
functional programming paradigms. Functional programming emphasizes writing
pure functions, avoiding side effects, and using immutable data.

### 2.5.1 First-Class Functions

In JavaScript, functions are first-class citizens, meaning they can be treated
like any other variable: assigned to variables, passed as arguments to other
functions, and returned from other functions.

```javascript
// Assign function to a variable
const greet = function(name) {
    return `Hello, ${name}!`;
};

// Pass function as an argument (Higher-Order Function)
function operateOnNumbers(num1, num2, operation) {
    return operation(num1, num2);
}

const add = (a, b) => a + b;
console.log(operateOnNumbers(5, 3, add)); // 8

// Return function from another function (Closure example)
function createMultiplier(multiplier) {
    return function(number) {
        return number * multiplier;
    };
}

const multiplyBy5 = createMultiplier(5);
console.log(multiplyBy5(10)); // 50
```

### 2.5.2 Pure Functions

A pure function is a function that:

1.  Given the same input, will always return the same output.
2.  Produces no side effects (e.g., doesn't modify global state, doesn't
    perform I/O operations).

Pure functions are easier to test, debug, and reason about, making code more
reliable and predictable.

```javascript
// Pure function
const addPure = (a, b) => a + b;

// Impure function (modifies external state)
let total = 0;
const addToTotal = (num) => {
    total += num; // Side effect: modifies external variable
    return total;
};
```

### 2.5.3 Immutability

Immutability means that once a data structure is created, it cannot be changed.
Instead of modifying existing data, you create new data structures with the
desired changes. This prevents unexpected side effects and makes state
management simpler, especially in complex applications.

```javascript
// Mutable array (bad practice in functional programming)
const mutableArray = [1, 2, 3];
mutableArray.push(4); // Modifies the original array

// Immutable approach (good practice)
const originalArray = [1, 2, 3];
const newArray = [...originalArray, 4]; // Creates a new array

// For objects
const originalObject = { a: 1, b: 2 };
const newObject = { ...originalObject, b: 3, c: 4 }; // Creates a new object
```

### 2.5.4 Higher-Order Functions

Higher-order functions are functions that either take one or more functions as
arguments or return a function as their result. Examples include `map`,
`filter`, `reduce`, `forEach`, which are commonly used with arrays.

## 2.6 Error Handling

Robust applications require effective error handling to gracefully manage
unexpected situations and provide meaningful feedback. JavaScript uses a
`try...catch...finally` block for synchronous error handling and
promises/async-await for asynchronous error handling.

### 2.6.1 `try...catch...finally`

*   **`try`**: Defines a block of code to be tested for errors while it is
    being executed.
*   **`catch`**: Defines a block of code to be executed if an error occurs in
    the `try` block.
*   **`finally`**: Defines a block of code to be executed regardless of whether
    an error occurred or not.

```javascript
function divide(a, b) {
    try {
        if (b === 0) {
            throw new Error("Division by zero is not allowed.");
        }
        return a / b;
    } catch (error) {
        console.error("An error occurred:", error.message);
        return null; // Or re-throw, or handle appropriately
    } finally {
        console.log("Division attempt finished.");
    }
}

console.log(divide(10, 2));
console.log(divide(10, 0));
```

### 2.6.2 Custom Errors

You can create custom error types by extending the built-in `Error` class. This
allows for more specific error handling and better organization of error types
in your application.

```javascript
class ValidationError extends Error {
    constructor(message) {
        super(message);
        this.name = "ValidationError";
    }
}

function validateEmail(email) {
    if (!email.includes("@")) {
        throw new ValidationError("Invalid email format.");
    }
    return true;
}

try {
    validateEmail("testexample.com");
} catch (error) {
    if (error instanceof ValidationError) {
        console.error("Validation Error:", error.message);
    } else {
        console.error("Unknown Error:", error.message);
    }
}
```

## 2.7 Modules: Organizing Code

As applications grow, organizing code into manageable, reusable units becomes
crucial. JavaScript modules (introduced in ES6) provide a standardized way to
encapsulate code and manage dependencies.

### 2.7.1 ES Modules (`import`/`export`)

ES Modules are the modern standard for modular JavaScript. They use `import`
and `export` statements.

**`math.js` (exporting module):**

```javascript
// math.js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;

export default function multiply(a, b) {
    return a * b;
}
```

**`app.js` (importing module):**

```javascript
// app.js
import { add, subtract } from ".//math.js"; // Named imports
import multiply from ".//math.js";         // Default import

console.log(add(5, 3));       // 8
console.log(subtract(5, 3));  // 2
console.log(multiply(5, 3));  // 15
```

**Key characteristics of ES Modules:**

*   **Static Structure:** Imports and exports are resolved at compile time,
    allowing for static analysis and tree-shaking (removing unused code).
*   **Strict Mode by Default:** Modules automatically run in strict mode.
*   **Module Scope:** Variables and functions declared in a module are scoped
    to that module and not globally available unless explicitly exported.
*   **Single Instance:** Each module is evaluated only once, and subsequent
    imports return the same instance.

### 2.7.2 CommonJS Modules (`require`/`module.exports`)

CommonJS is the module system primarily used in Node.js environments before ES
Modules gained widespread support. It uses `require()` for importing and
`module.exports` or `exports` for exporting.

**`utils.js` (exporting module):**

```javascript
// utils.js
const greet = (name) => `Hello, ${name}!`;
const PI = 3.14159;

module.exports = {
    greet: greet,
    PI: PI
};

// Or directly export properties
// exports.greet = greet;
// exports.PI = PI;
```

**`main.js` (importing module):**

```javascript
// main.js
const { greet, PI } = require(".//utils.js");

console.log(greet("World")); // Hello, World!
console.log(PI);            // 3.14159
```

**Differences and Usage:**

*   Node.js natively supports CommonJS modules. To use ES Modules in Node.js,
    you typically need to set `type": "module"` in your `package.json` or use
    the `.mjs` file extension.
*   ES Modules are generally preferred for modern JavaScript development,
    including front-end and increasingly in Node.js.

## 2.8 JSON: JavaScript Object Notation

JSON (JavaScript Object Notation) is a lightweight data-interchange format. It
is easy for humans to read and write and easy for machines to parse and
generate. It is based on a subset of JavaScript Programming Language, Standard
ECMA-262 3rd Edition - December 1999. JSON is a text format that is completely
language independent but uses conventions that are familiar to programmers of
the C-family of languages, including C, C++, C#, Java, JavaScript, Perl,
Python, and many others.

### 2.8.1 JSON Syntax Rules

*   Data is in name/value pairs (e.g., `"name": "John"`).
*   Data is separated by commas.
*   Curly braces `{}` hold objects.
*   Square brackets `[]` hold arrays.
*   Keys must be strings, written with double quotes.
*   Values must be one of the following data types:
    *   a string (in double quotes)
    *   a number
    *   an object (JSON object)
    *   an array
    *   a boolean (`true` or `false`)
    *   `null`

**Example JSON:**

```json
{
  "firstName": "John",
  "lastName": "Doe",
  "age": 30,
  "isStudent": false,
  "address": {
    "streetAddress": "21 2nd Street",
    "city": "New York",
    "state": "NY",
    "postalCode": "10021-3100"
  },
  "phoneNumbers": [
    {
      "type": "home",
      "number": "212 555-1234"
    },
    {
      "type": "office",
      "number": "646 555-4567"
    }
  ],
  "children": [],
  "spouse": null
}
```

### 2.8.2 Working with JSON in JavaScript

JavaScript provides built-in methods for working with JSON:

*   **`JSON.parse()`**: Converts a JSON string into a JavaScript object.

    ```javascript
    const jsonString = 
        `{
            "name": "Alice", 
            "age": 28, 
            "city": "Wonderland"
        }`;
    const jsObject = JSON.parse(jsonString);
    console.log(jsObject.name); // Alice
    ```

*   **`JSON.stringify()`**: Converts a JavaScript object into a JSON string.

    ```javascript
    const person = {
        name: "Bob",
        age: 35,
        city: "Builderville"
    };
    const jsonOutput = JSON.stringify(person);
    console.log(jsonOutput); // "{"name":"Bob","age":35,"city":"Builderville"}"

    // With pretty-printing
    const prettyJsonOutput = JSON.stringify(person, null, 2);
    console.log(prettyJsonOutput);
    /*
    {
      "name": "Bob",
      "age": 35,
      "city": "Builderville"
    }
    */
    ```

JSON is the de facto standard for data exchange in web APIs and is crucial for
communication between front-end (mobile) applications and back-end services.

## 2.9 Summary

This chapter provided a comprehensive overview of core JavaScript fundamentals.
We started with basic syntax, variable declarations (`let`, `const`), and the
various data types. We explored operators, control flow statements (`if/else`,
`switch`, loops), and the different ways to define and use functions, including
function declarations, expressions, and ES6 arrow functions. Key concepts like
parameters, arguments, default parameters, rest parameters, scope, and closures
were explained in detail.

We then moved on to JavaScript's primary data structures: objects and arrays.
We covered object creation, property access, methods, destructuring, and the
spread syntax. For arrays, we discussed common methods for manipulation and
iteration (`forEach`, `map`, `filter`, `reduce`), along with destructuring and
the spread syntax. The chapter also introduced object-oriented programming in
JavaScript, explaining prototypes, prototypal inheritance, and the ES6 `class`
syntax.

Functional programming concepts such as first-class functions, pure functions,
immutability, and higher-order functions were highlighted, showcasing
JavaScript's versatility. We discussed error handling mechanisms using
`try...catch...finally` and custom errors. The importance of code organization
through modules was addressed, covering both ES Modules (`import`/`export`) and
CommonJS (`require`/`module.exports`). Finally, we delved into JSON, its syntax
rules, and how to parse and stringify JSON data in JavaScript.

Mastering these core JavaScript concepts is essential for building any
application, whether it's a simple script, a complex front-end interface, or a
robust mobile back-end with Node.js. The principles discussed here will serve
as the foundation for all subsequent chapters.

## 2.10 References

[1] MDN Web Docs. *JavaScript Guide*. Available at: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)

[2] MDN Web Docs. *JavaScript Reference*. Available at: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)

[3] Ecma International. *ECMAScript® Language Specification*. (Various editions). Available at: [https://www.ecma-international.org/publications-and-standards/standards/ecma-262/](https://www.ecma-international.org/publications-and-standards/standards/ecma-262/)

[4] JSON.org. *Introducing JSON*. Available at: [https://www.json.org/json-en.html](https://www.json.org/json-en.html)


