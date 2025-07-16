
## Chapter 2: Core JavaScript - Solutions

This document provides solutions to the exercises presented in `exercises.md`
for Chapter 2. These solutions aim to demonstrate best practices, including
  clean code, basic testing principles, and considerations for performance and
  security where applicable.

---

### Section 1: Variables, Data Types, and Operators - Solutions

1.  **Variable Declaration and Reassignment:**

    *   **Solution:**
        ```javascript
        // Using let for a variable that will be reassigned
        let myNumber = 10;
        console.log(`Initial myNumber: ${myNumber}`); // Output: Initial myNumber: 10
        myNumber = 20;
        console.log(`Reassigned myNumber: ${myNumber}`); // Output: Reassigned myNumber: 20

        // Using const for a constant string
        const myConstantString = "Hello";
        console.log(`myConstantString: ${myConstantString}`); // Output: myConstantString: Hello

        try {
            // This line will cause a TypeError because const cannot be reassigned
            // myConstantString = "World";
        } catch (error) {
            console.error(`Attempted to reassign myConstantString: ${error.message}`);
            // Output: Attempted to reassign myConstantString: Assignment to constant variable.
        }

        // Using const for an object
        const myObject = { name: "Alice" };
        console.log(`Initial myObject:`, myObject); // Output: Initial myObject: { name: 'Alice' }
        myObject.name = "Bob"; // Modifying a property of the object
        console.log(`Modified myObject:`, myObject); // Output: Modified myObject: { name: 'Bob' }

        // Explanation:
        // `const` prevents the *reassignment* of the variable itself, meaning you cannot point `myConstantString` to a new string or `myObject` to a new object. However, for objects (and arrays, which are a type of object), `const` does not make the *contents* of the object immutable. You can still modify the properties of the object that `myObject` refers to. To achieve true immutability for objects, you would need techniques like `Object.freeze()` or immutable data structures.
        ```
        *Clean Code:* Use `const` by default to prevent accidental
        reassignments and make your code's intent clearer. Only use `let` when
        you explicitly know the variable will be reassigned.

2.  **Type Coercion vs. Strict Equality:**

    *   **Solution:**
        ```javascript
        console.log(5 == "5");  // Output: true
        console.log(5 === "5"); // Output: false
        ```
        *   **`==` (Loose Equality):** Performs type coercion before
            comparison. If the operands are of different types, JavaScript
            attempts to convert one or both operands to a common type before
            making the comparison. In `5 == "5"`, the string `


"5" is coerced to the number `5`, so `5 == 5` is `true`.
        *   **`===` (Strict Equality):** Performs comparison without type
            coercion. It returns `true` only if both the value and the type of
            the operands are the same. In `5 === "5"`, the types (number and
            string) are different, so it returns `false` without attempting any
            conversion.

        *Example where `==` might lead to unexpected behavior:*
        ```javascript
        console.log(null == undefined); // true (due to loose equality rules)
        console.log(null === undefined); // false

        console.log("" == 0); // true
        console.log("" === 0); // false

        // In a conditional statement:
        const value = "0";
        if (value == false) { // This evaluates to true because "0" is loosely equal to false
            console.log("Unexpectedly true!");
        }
        if (value === false) {
            console.log("Expectedly false!");
        }
        ```
        *Best Practice:* Always use `===` and `!==` unless you have a very
        specific reason to use loose equality and fully understand its
        implications. This prevents unexpected type coercion behaviors and
        makes your code more predictable.

3.  **Logical Operators:**

    *   **Solution:**
        ```javascript
        let a = true;
        let b = false;
        let c = true;

        console.log(`a && b: ${a && b}`);     // Output: a && b: false
        console.log(`a || b: ${a || b}`);     // Output: a || b: true
        console.log(`!b: ${!b}`);             // Output: !b: true
        console.log(`(a && c) || b: ${(a && c) || b}`); // Output: (a && c) || b: true
        ```
        *Explanation:*
        *   `&&` (AND): Returns `true` if both operands are `true`.
        *   `||` (OR): Returns `true` if at least one operand is `true`.
        *   `!` (NOT): Inverts the boolean value of the operand.
        *   Parentheses `()` dictate the order of operations.

4.  **Ternary Operator:**

    *   **Solution:**
        ```javascript
        const isAdult = (age) => {
            return age >= 18 ? "Adult" : "Minor";
        };

        console.log(isAdult(20)); // Output: Adult
        console.log(isAdult(16)); // Output: Minor
        console.log(isAdult(18)); // Output: Adult
        ```
        *Clean Code:* The ternary operator is useful for concise conditional
        assignments or returns, especially when the logic is simple. For more
        complex conditions, `if-else` statements are more readable.

---

### Section 2: Control Flow - Solutions

5.  **`if-else if-else` Statement:**

    *   **Solution:**
        ```javascript
        const getGrade = (score) => {
            if (score < 0 || score > 100) {
                return "Invalid Score"; // Input validation
            } else if (score >= 90) {
                return "A";
            } else if (score >= 80) {
                return "B";
            } else if (score >= 70) {
                return "C";
            } else if (score >= 60) {
                return "D";
            } else {
                return "F";
            }
        };

        console.log(getGrade(95));  // Output: A
        console.log(getGrade(82));  // Output: B
        console.log(getGrade(70));  // Output: C
        console.log(getGrade(55));  // Output: F
        console.log(getGrade(105)); // Output: Invalid Score
        ```
        *Clean Code:* Order your `if-else if` conditions from most restrictive
        to least restrictive (e.g., highest score range first) to ensure
        correct logic. Include input validation.

6.  **`switch` Statement:**

    *   **Solution:**
        ```javascript
        const getDayType = (day) => {
            switch (day.toLowerCase()) { // Convert to lowercase for case-insensitivity
                case "monday":
                case "tuesday":
                case "wednesday":
                case "thursday":
                case "friday":
                    return "Weekday";
                case "saturday":
                case "sunday":
                    return "Weekend";
                default:
                    return "Invalid Day";
            }
        };

        console.log(getDayType("Monday"));    // Output: Weekday
        console.log(getDayType("Saturday"));  // Output: Weekend
        console.log(getDayType("Funday"));    // Output: Invalid Day
        ```
        *Clean Code:* Use `break` statements to prevent 


fall-through behavior in `switch` statements. The `default` case is good for
handling unexpected inputs.

7.  **`for` Loop:**

    *   **Solution:**
        ```javascript
        const printNumbers = (n) => {
            if (n < 1) {
                console.log("Please provide a positive integer.");
                return;
            }
            for (let i = 1; i <= n; i++) {
                console.log(i);
            }
        };

        printNumbers(5);
        // Expected Output:
        // 1
        // 2
        // 3
        // 4
        // 5
        ```
        *Big-O Analysis:* Time Complexity: O(N), where N is the input number,
        as the loop runs N times. Space Complexity: O(1).

8.  **`while` Loop:**

    *   **Solution:**
        ```javascript
        const sumUntil = (limit) => {
            if (limit < 1) {
                return 0; // Or throw an error, depending on requirements
            }
            let sum = 0;
            let i = 1;
            while (i <= limit) {
                sum += i;
                i++;
            }
            return sum;
        };

        console.log(sumUntil(5)); // Output: 15 (1+2+3+4+5)
        console.log(sumUntil(1)); // Output: 1
        console.log(sumUntil(0)); // Output: 0
        ```
        *Big-O Analysis:* Time Complexity: O(N), where N is the limit. Space
        Complexity: O(1).

9.  **`for...of` Loop:**

    *   **Solution:**
        ```javascript
        const fruits = ["apple", "banana", "cherry"];

        for (const fruit of fruits) {
            console.log(fruit);
        }
        // Expected Output:
        // apple
        // banana
        // cherry
        ```
        *Clean Code:* `for...of` is generally preferred for iterating over
        array elements directly as it's more readable and less error-prone than
        `for` loops when you don't need the index.

---

### Section 3: Functions - Solutions

10. **Function Declaration vs. Expression:**

    *   **Solution:**
        ```javascript
        // Function Declaration
        function multiply(a, b) {
            return a * b;
        }

        // Function Expression
        const divide = function(a, b) {
            if (b === 0) {
                throw new Error("Division by zero is not allowed.");
            }
            return a / b;
        };

        // Demonstrating Hoisting:
        // Function declarations are hoisted, so you can call them before their definition.
        console.log(multiply(4, 2)); // Output: 8 (Works due to hoisting)

        // Function expressions are NOT hoisted. Calling 'divide' here would result in a TypeError.
        // console.log(divide(4, 2)); // TypeError: Cannot access 'divide' before initialization

        console.log(divide(10, 2)); // Output: 5 (Works after definition)
        ```
        *Clean Code:* Be aware of hoisting. While function declarations are
        hoisted, it's often considered good practice to define functions before
        they are called for better code readability and predictability.

11. **Arrow Functions:**

    *   **Solution:**
        ```javascript
        // Arrow function for multiply
        const multiplyArrow = (a, b) => a * b;

        // Arrow function for divide
        const divideArrow = (a, b) => {
            if (b === 0) {
                throw new Error("Division by zero is not allowed.");
            }
            return a / b;
        };

        // Arrow function for greetUser
        const greetUser = (name) => `Hello, ${name}!`;

        console.log(multiplyArrow(6, 3));  // Output: 18
        console.log(divideArrow(10, 5));   // Output: 2
        console.log(greetUser("Charlie")); // Output: Hello, Charlie!
        ```
        *Clean Code:* Arrow functions are concise and great for short,
        single-expression functions. For more complex logic or when `this`
        binding is critical, traditional functions might be more appropriate.

12. **Default Parameters:**

    *   **Solution:**
        ```javascript
        const greetUserWithDefault = (name = "Guest") => `Hello, ${name}!`;

        console.log(greetUserWithDefault("David")); // Output: Hello, David!
        console.log(greetUserWithDefault());       // Output: Hello, Guest!
        console.log(greetUserWithDefault(undefined)); // Output: Hello, Guest!
        ```
        *Clean Code:* Default parameters make functions more flexible and
        reduce the need for manual checks for `undefined` or `null` values
        inside the function body.

13. **Rest Parameters:**

    *   **Solution:**
        ```javascript
        const average = (...numbers) => {
            if (numbers.length === 0) {
                return 0; // Or throw an error, or return null
            }
            const sum = numbers.reduce((acc, num) => acc + num, 0);
            return sum / numbers.length;
        };

        console.log(average(1, 2, 3, 4, 5)); // Output: 3
        console.log(average(10, 20));       // Output: 15
        console.log(average());             // Output: 0
        ```
        *Big-O Analysis:* Time Complexity: O(N), where N is the number of
        arguments, due to the `reduce` operation. Space Complexity: O(N)
        because the rest parameter collects arguments into a new array.

14. **Closures:**

    *   **Solution:**
        ```javascript
        const createCounter = () => {
            let count = 0; // This 'count' variable is part of the closure

            return {
                increment: () => {
                    count++;
                    console.log(`Count incremented to: ${count}`);
                },
                getCount: () => {
                    return count;
                }
            };
        };

        const counter1 = createCounter();
        const counter2 = createCounter(); // Each call creates a new, independent closure

        counter1.increment(); // Output: Count incremented to: 1
        counter1.increment(); // Output: Count incremented to: 2
        console.log(`Counter 1 current value: ${counter1.getCount()}`); // Output: Counter 1 current value: 2

        counter2.increment(); // Output: Count incremented to: 1
        console.log(`Counter 2 current value: ${counter2.getCount()}`); // Output: Counter 2 current value: 1

        // Explanation:
        // The `increment` and `getCount` functions form a closure over the `count` variable defined in `createCounter`. Even after `createCounter` has finished executing, `increment` and `getCount` still 


have access to and can modify/read `count`. Each call to `createCounter()`
creates a new, independent `count` variable and its associated closure, which
is why `counter1` and `counter2` operate independently.

---

### Section 4: Objects and Arrays - Solutions

15. **Object Creation and Access:**

    *   **Solution:**
        ```javascript
        const book = {
            title: "The JavaScript Way",
            author: "Christian Heilmann",
            year: 2020,
            genres: ["Programming", "Web Development", "Education"]
        };

        // Access and print title using dot notation
        console.log(`Book Title: ${book.title}`); // Output: Book Title: The JavaScript Way

        // Access and print first genre using bracket notation
        console.log(`First Genre: ${book["genres"][0]}`); // Output: First Genre: Programming

        // Add a new property
        book.publisher = "Self-Published";
        console.log(`Book with Publisher:`, book);
        // Output: { title: ..., author: ..., year: ..., genres: [...], publisher: 'Self-Published' }
        ```
        *Clean Code:* Use dot notation when property names are valid JavaScript
        identifiers and known at compile time. Use bracket notation when
        property names are dynamic (e.g., from a variable) or contain special
        characters/spaces.

16. **Object Destructuring:**

    *   **Solution:**
        ```javascript
        const book = {
            title: "The JavaScript Way",
            author: "Christian Heilmann",
            year: 2020,
            genres: ["Programming", "Web Development", "Education"]
        };

        // Destructure title and author
        const { title, author } = book;
        console.log(`Title: ${title}, Author: ${author}`); // Output: Title: The JavaScript Way, Author: Christian Heilmann

        // Destructure with renaming
        const { year: publicationYear } = book;
        console.log(`Publication Year: ${publicationYear}`); // Output: Publication Year: 2020
        ```
        *Clean Code:* Destructuring makes code more readable by clearly showing
        which properties are being extracted from an object or array. It also
        reduces verbosity.

17. **Array Manipulation:**

    *   **Solution:**
        ```javascript
        const colors = ["red", "green", "blue", "yellow"];
        console.log(`Initial array:`, colors); // Output: Initial array: [ 'red', 'green', 'blue', 'yellow' ]

        // Add "purple" to the end
        colors.push("purple");
        console.log(`After push:`, colors); // Output: After push: [ 'red', 'green', 'blue', 'yellow', 'purple' ]

        // Remove the first element
        colors.shift();
        console.log(`After shift:`, colors); // Output: After shift: [ 'green', 'blue', 'yellow', 'purple' ]

        // Add "orange" to the beginning
        colors.unshift("orange");
        console.log(`After unshift:`, colors); // Output: After unshift: [ 'orange', 'green', 'blue', 'yellow', 'purple' ]

        console.log(`Final array:`, colors);
        ```
        *Clean Code:* Understand the difference between methods that modify the
        original array (`push`, `pop`, `shift`, `unshift`, `splice`) and
        methods that return a new array (`map`, `filter`, `slice`). For
        functional programming, prefer methods that return new arrays to
        maintain immutability.

18. **`map()` Method:**

    *   **Solution:**
        ```javascript
        const numbers = [1, 2, 3, 4, 5];
        const squaredNumbers = numbers.map(num => num * num);

        console.log(`Original numbers:`, numbers);         // Output: Original numbers: [ 1, 2, 3, 4, 5 ]
        console.log(`Squared numbers:`, squaredNumbers); // Output: Squared numbers: [ 1, 4, 9, 16, 25 ]
        ```
        *Big-O Analysis:* Time Complexity: O(N), where N is the number of
        elements in the array, as it iterates through each element once. Space
        Complexity: O(N), as a new array of the same size is created.

19. **`filter()` Method:**

    *   **Solution:**
        ```javascript
        const products = [
            { name: "Laptop", price: 1200 },
            { name: "Mouse", price: 25 },
            { name: "Keyboard", price: 75 },
            { name: "Monitor", price: 300 }
        ];

        const affordableProducts = products.filter(product => product.price < 100);

        console.log(`All products:`, products);
        console.log(`Affordable products:`, affordableProducts);
        // Output: Affordable products: [ { name: 'Mouse', price: 25 }, { name: 'Keyboard', price: 75 } ]
        ```
        *Big-O Analysis:* Time Complexity: O(N), where N is the number of
        elements in the array. Space Complexity: O(K), where K is the number of
        elements that pass the filter (K <= N).

20. **`reduce()` Method:**

    *   **Solution:**
        ```javascript
        const prices = [10, 20, 30, 40];
        const totalSum = prices.reduce((accumulator, currentValue) => accumulator + currentValue, 0);

        console.log(`Prices:`, prices);
        console.log(`Total sum: ${totalSum}`); // Output: Total sum: 100
        ```
        *Big-O Analysis:* Time Complexity: O(N), where N is the number of
        elements in the array. Space Complexity: O(1), as only a single
        accumulator variable is used.

---

### Section 5: OOP, Functional Programming, Error Handling, and Modules - Solutions

21. **ES6 Classes and Inheritance:**

    *   **Solution:**
        ```javascript
        class Person {
            constructor(name, age) {
                this.name = name;
                this.age = age;
            }

            greet() {
                console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
            }
        }

        class Student extends Person {
            constructor(name, age, studentId) {
                super(name, age); // Call the parent class constructor
                this.studentId = studentId;
            }

            // Override the greet method
            greet() {
                console.log(`Hello, my name is ${this.name}, I am ${this.age} years old, and my student ID is ${this.studentId}.`);
            }

            study() {
                console.log(`${this.name} is studying.`);
            }
        }

        const person1 = new Person("John Doe", 30);
        person1.greet(); // Output: Hello, my name is John Doe and I am 30 years old.

        const student1 = new Student("Jane Smith", 20, "S12345");
        student1.greet(); // Output: Hello, my name is Jane Smith, I am 20 years old, and my student ID is S12345.
        student1.study(); // Output: Jane Smith is studying.
        ```
        *Clean Code:* Classes provide a clear, structured way to define objects
        and their relationships. Use `super()` in subclass constructors to
        properly initialize parent class properties.

22. **Pure Functions and Immutability:**

    *   **Solution:**
        ```javascript
        // Pure function: no side effects, same output for same input
        const addTax = (price, taxRate) => {
            // Input validation for robustness
            if (typeof price !== 'number' || typeof taxRate !== 'number' || price < 0 || taxRate < 0) {
                throw new Error("Invalid input: price and taxRate must be non-negative numbers.");
            }
            return price * (1 + taxRate);
        };

        console.log(`Price with tax: ${addTax(100, 0.05)}`); // Output: Price with tax: 105
        console.log(`Original price remains: 100`); // Demonstrates immutability of input

        // Immutable array update
        const originalUsers = [
            { id: 1, name: "Alice" },
            { id: 2, name: "Bob" },
            { id: 3, name: "Charlie" }
        ];

        const updateUserName = (users, id, newName) => {
            // Input validation
            if (!Array.isArray(users) || typeof id !== 'number' || typeof newName !== 'string') {
                throw new Error("Invalid input: users must be an array, id a number, newName a string.");
            }

            return users.map(user => {
                if (user.id === id) {
                    // Return a new object with the updated name
                    return { ...user, name: newName };
                } else {
                    // Return the original object for other users
                    return user;
                }
            });
        };

        const updatedUsers = updateUserName(originalUsers, 2, "Robert");

        console.log(`Original Users:`, originalUsers);
        // Output: Original Users: [ { id: 1, name: 'Alice' }, { id: 2, name: 'Bob' }, { id: 3, name: 'Charlie' } ]
        console.log(`Updated Users:`, updatedUsers);
        // Output: Updated Users: [ { id: 1, name: 'Alice' }, { id: 2, name: 'Robert' }, { id: 3, name: 'Charlie' } ]
        ```
        *Clean Code:* Prioritize pure functions and immutable data structures.
        This makes your code easier to test, debug, and reason about,
        especially in concurrent or complex state management scenarios. The
        `map` method is excellent for transforming arrays immutably.

23. **Error Handling with `try-catch`:**

    *   **Solution:**
        ```javascript
        const parseJSON = (jsonString) => {
            try {
                const parsedObject = JSON.parse(jsonString);
                console.log("Successfully parsed JSON:", parsedObject);
                return parsedObject;
            } catch (error) {
                if (error instanceof SyntaxError) {
                    console.error("JSON Parsing Error: Invalid JSON format.", error.message);
                } else {
                    console.error("An unexpected error occurred during JSON parsing:", error.message);
                }
                return null;
            }
        };

        // Test cases
        parseJSON(`{"name": "Alice", "age": 30}`); // Valid JSON
        parseJSON(`{"name": "Bob", "age": 25,}`); // Invalid JSON (trailing comma)
        parseJSON(`not a json string`);          // Invalid JSON
        ```
        *Best Practice:* Always wrap potentially error-prone operations (like
        `JSON.parse()`, network requests, file I/O) in `try...catch` blocks.
        Provide specific error messages and handle different error types if
        possible.

24. **Custom Error:**

    *   **Solution:**
        ```javascript
        class InvalidInputError extends Error {
            constructor(message) {
                super(message);
                this.name = "InvalidInputError";
            }
        }

        const processInput = (value) => {
            if (typeof value !== 'number') {
                throw new InvalidInputError("Input must be a number.");
            }
            return value * 2;
        };

        try {
            console.log(processInput(5));     // Output: 10
            console.log(processInput("hello")); // This will throw an error
        } catch (error) {
            if (error instanceof InvalidInputError) {
                console.error(`Caught InvalidInputError: ${error.message}`);
            } else {
                console.error(`Caught unexpected error: ${error.message}`);
            }
        }
        ```
        *Clean Code:* Custom error classes improve the clarity and
        maintainability of your error handling logic. They allow you to catch
        and respond to specific types of errors more effectively.

25. **ES Modules (Conceptual):**

    *   **Solution:**
        *   `utils.js` (conceptual):
            ```javascript
            // utils.js
            export const capitalize = (str) => str.charAt(0).toUpperCase() + str.slice(1);

            class Logger {
                log(message) {
                    console.log(`[Logger]: ${message}`);
                }
            }
            export default Logger;
            ```
        *   `app.js` (importing):
            ```javascript
            // app.js
            import { capitalize } from ".//utils.js"; // Named import
            import MyLogger from ".//utils.js";      // Default import (can be named anything)

            console.log(capitalize("hello")); // Output: Hello

            const logger = new MyLogger();
            logger.log("This is a log message."); // Output: [Logger]: This is a log message.
            ```
        *Best Practice:* Use named exports for multiple items and a default
        export for the primary export of a module. This provides flexibility
        and clarity.

26. **CommonJS Modules (Conceptual):**

    *   **Solution:**
        *   `config.js` (conceptual):
            ```javascript
            // config.js
            module.exports = {
                API_KEY: "your_api_key_here",
                DB_URL: "mongodb://localhost:27017/mydb"
            };
            ```
        *   `server.js` (importing):
            ```javascript
            // server.js
            const config = require(".//config.js");

            console.log(`API Key: ${config.API_KEY}`);
            console.log(`Database URL: ${config.DB_URL}`);

            // Or using destructuring directly:
            const { API_KEY, DB_URL } = require(".//config.js");
            console.log(`API Key (destructured): ${API_KEY}`);
            ```
        *Best Practice:* CommonJS is the default module system in Node.js. Use
        `require()` and `module.exports` for Node.js-specific scripts or older
        projects. For new projects, consider using ES Modules with Node.js
        configuration.

27. **JSON `stringify` and `parse`:**

    *   **Solution:**
        ```javascript
        const user = { id: 1, name: "Charlie", isActive: true };

        // Convert JavaScript object to JSON string
        const jsonString = JSON.stringify(user);
        console.log(`JSON String: ${jsonString}`); // Output: JSON String: {"id":1,"name":"Charlie","isActive":true}

        // Convert JSON string back to JavaScript object
        const parsedObject = JSON.parse(jsonString);
        console.log(`Parsed Object:`, parsedObject); // Output: Parsed Object: { id: 1, name: 'Charlie', isActive: true }

        // Verify type
        console.log(`Type of parsedObject: ${typeof parsedObject}`); // Output: Type of parsedObject: object
        ```
        *Clean Code:* `JSON.stringify()` and `JSON.parse()` are essential for
        data serialization and deserialization, especially when communicating
        with APIs or storing data. Remember to handle potential parsing errors
        with `try...catch`.

28. **Nested JSON Access:**

    *   **Solution:**
        ```javascript
        const jsonString = `
        {
          "orderId": "12345",
          "customer": {
            "name": "Diana Prince",
            "email": "diana@example.com"
          },
          "items": [
            { "productId": "A1", "quantity": 2, "price": 10.50 },
            { "productId": "B2", "quantity": 1, "price": 50.00 }
          ]
        }
        `;

        const order = JSON.parse(jsonString);

        // Access customer's email
        console.log(`Customer Email: ${order.customer.email}`); // Output: Customer Email: diana@example.com

        // Access productId of the second item (index 1)
        console.log(`Second Item Product ID: ${order.items[1].productId}`); // Output: Second Item Product ID: B2
        ```
        *Clean Code:* When accessing nested properties, ensure each level
        exists to avoid `TypeError` (e.g., `order.customer?.email` using
        optional chaining for safer access in production code).

29. **`this` Keyword in Objects:**

    *   **Solution:**
        ```javascript
        const person = {
            firstName: "Alice",
            lastName: "Wonderland",
            fullName: function() {
                // `this` refers to the `person` object itself when called as a method
                return `${this.firstName} ${this.lastName}`;
            },
            // Arrow function for fullName (demonstrates lexical 'this')
            // arrowFullName: () => {
            //     // In an arrow function, 'this' refers to the 'this' of the enclosing lexical context.
            //     // In this case, it would likely be the global object (window in browser, undefined in strict mode Node.js).
            //     // So, this.firstName would be undefined.
            //     return `${this.firstName} ${this.lastName}`;
            // }
        };

        console.log(person.fullName()); // Output: Alice Wonderland

        // Example of 'this' context change if not careful
        // const getFullName = person.fullName;
        // console.log(getFullName()); // This would likely output 'undefined undefined' in non-strict mode,
                                   // or throw an error in strict mode, because 'this' would be global/undefined.
        ```
        *Best Practice:* Be mindful of the `this` keyword. For object methods,
        regular function expressions are usually preferred. For callbacks where
        you want `this` to retain the context of the surrounding code, arrow
        functions are ideal.

30. **Higher-Order Function Example:**

    *   **Solution:**
        ```javascript
        /**
         * Applies an operation function to each element of an array.
         * @param {Array<number>} arr - The input array of numbers.
         * @param {function(number): number} operation - A function to apply to each number.
         * @returns {Array<number>} A new array with the operation applied to each element.
         */
        const applyOperation = (arr, operation) => {
            if (!Array.isArray(arr) || typeof operation !== 'function') {
                throw new Error("Invalid input: first argument must be an array, second must be a function.");
            }
            return arr.map(operation);
        };

        // Example operation: doubling a number
        const double = (num) => num * 2;

        const numbers = [1, 2, 3, 4, 5];
        const doubledNumbers = applyOperation(numbers, double);

        console.log(`Original numbers:`, numbers);
        console.log(`Doubled numbers:`, doubledNumbers); // Output: Doubled numbers: [ 2, 4, 6, 8, 10 ]

        // Another example: squaring a number
        const square = (num) => num * num;
        const squaredNumbers = applyOperation(numbers, square);
        console.log(`Squared numbers:`, squaredNumbers); // Output: Squared numbers: [ 1, 4, 9, 16, 25 ]
        ```
        *Clean Code:* Higher-order functions promote code reusability and
        abstraction. They are a cornerstone of functional programming and make
        your code more modular and testable. The `map` method is a perfect
        example of a built-in higher-order function.


