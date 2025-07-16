## Chapter 2: Core JavaScript - Exercises

These exercises are designed to solidify your understanding of core JavaScript
concepts, including variables, data types, operators, control flow, functions,
objects, arrays, and basic OOP/functional programming ideas. Focus on writing
clean, efficient, and readable code.

### Section 1: Variables, Data Types, and Operators

1.  **Variable Declaration and Reassignment:**
    *   Declare a variable `myNumber` using `let` and assign it the value `10`.
    *   Reassign `myNumber` to `20`.
    *   Declare a constant `myConstantString` using `const` and assign it the
    *   value `"Hello"`. Try to reassign `myConstantString` to `"World"`
    *   (observe the error).
    *   Declare a constant object `myObject` with a property `name: "Alice"`.
    *   Change the `name` property to `"Bob"`. Explain why this is possible
    *   with `const`.

2.  **Type Coercion vs. Strict Equality:**
    *   Predict the output of `console.log(5 == "5")` and `console.log(5 === "5")`.
    *   Explain the difference between `==` and `===`.
    *   Provide an example where `==` might lead to unexpected behavior.

3.  **Logical Operators:**
    *   Given `let a = true; let b = false; let c = true;`
    *   Evaluate and print the result of: `a && b`, `a || b`, `!b`, `(a && c) || b`.

4.  **Ternary Operator:**
    *   Write a function `isAdult(age)` that returns `"Adult"` if `age` is 18
    *   or more, otherwise returns `"Minor"`, using the ternary operator.

### Section 2: Control Flow

5.  **`if-else if-else` Statement:**
    *   Write a function `getGrade(score)` that takes a numerical score (0-100)
    *   and returns a letter grade based on these rules: 90-100: "A"
        *   80-89: "B"
        *   70-79: "C"
        *   60-69: "D"
        *   Below 60: "F"

6.  **`switch` Statement:**
    *   Write a function `getDayType(day)` that takes a string `day` (e.g.,
    *   "Monday", "Saturday") and returns "Weekday" for Monday-Friday and
    *   "Weekend" for Saturday-Sunday. Use a `switch` statement.

7.  **`for` Loop:**
    *   Write a function `printNumbers(n)` that uses a `for` loop to print
    *   numbers from 1 to `n` (inclusive).

8.  **`while` Loop:**
    *   Write a function `sumUntil(limit)` that uses a `while` loop to sum all
    *   integers from 1 up to `limit` (inclusive).

9.  **`for...of` Loop:**
    *   Given an array of strings `const fruits = ["apple", "banana", "cherry"];`
    *   Use a `for...of` loop to print each fruit to the console.

### Section 3: Functions

10. **Function Declaration vs. Expression:**
    *   Write a function `multiply(a, b)` using a function declaration that
    *   returns the product of `a` and `b`. Write a function `divide(a, b)`
    *   using a function expression that returns the quotient of `a` and `b`.
    *   Demonstrate hoisting by calling `multiply` before its definition and
    *   `divide` after its definition.

11. **Arrow Functions:**
    *   Convert the `multiply` and `divide` functions from the previous
    *   exercise into arrow functions. Write an arrow function
    *   `greetUser(name)` that returns `"Hello, [name]!"`.

12. **Default Parameters:**
    *   Modify the `greetUser` function to use a default parameter so that if
    *   no name is provided, it defaults to `"Guest"`.

13. **Rest Parameters:**
    *   Write a function `average(...numbers)` that takes an arbitrary number
    *   of numerical arguments and returns their average.

14. **Closures:**
    *   Create a function `createCounter()` that returns an object with two
    *   methods: `increment()` and `getCount()`. The `increment` method should
    *   increase an internal counter, and `getCount` should return its current
    *   value. Demonstrate how `createCounter` creates a closure.

### Section 4: Objects and Arrays

15. **Object Creation and Access:**
    *   Create an object `book` with properties: `title` (string), `author`
    *   (string), `year` (number), and `genres` (an array of strings). Access
    *   and print the `title` using dot notation.
    *   Access and print the first `genre` using bracket notation.
    *   Add a new property `publisher` to the `book` object.

16. **Object Destructuring:**
    *   Given the `book` object from the previous exercise, use object
    *   destructuring to extract `title` and `author` into separate variables.
    *   Use destructuring with renaming to extract `year` as `publicationYear`.

17. **Array Manipulation:**
    *   Given `const colors = ["red", "green", "blue", "yellow"];`
    *   Add "purple" to the end of the array.
    *   Remove the first element from the array.
    *   Add "orange" to the beginning of the array.
    *   Print the final array.

18. **`map()` Method:**
    *   Given `const numbers = [1, 2, 3, 4, 5];`
    *   Use `map()` to create a new array where each number is squared.

19. **`filter()` Method:**
    *   Given `const products = [{ name: "Laptop", price: 1200 }, { name:
    *   "Mouse", price: 25 }, { name: "Keyboard", price: 75 }];` Use `filter()`
    *   to create a new array containing only products with a price less than
    *   100.

20. **`reduce()` Method:**
    *   Given `const prices = [10, 20, 30, 40];`
    *   Use `reduce()` to calculate the total sum of all prices.

### Section 5: OOP, Functional Programming, Error Handling, and Modules

21. **ES6 Classes and Inheritance:**
    *   Define a `Person` class with a `constructor` that takes `name` and
    *   `age` and a method `greet()` that prints a greeting. Define a `Student`
    *   class that `extends` `Person`. The `Student` constructor should also
    *   take a `studentId`. Override the `greet()` method to include the
    *   `studentId`.
    *   Create instances of both `Person` and `Student` and call their `greet()` methods.

22. **Pure Functions and Immutability:**
    *   Write a pure function `addTax(price, taxRate)` that returns the price
    *   with tax added. It should not modify `price` or any external state.
    *   Given an array `const originalUsers = [{ id: 1, name: "A" }, { id: 2,
    *   name: "B" }];`
    *   Write a function `updateUserName(users, id, newName)` that returns a
    *   *new* array with the user's name updated, without modifying
    *   `originalUsers`.

23. **Error Handling with `try-catch`:**
    *   Write a function `parseJSON(jsonString)` that attempts to parse a JSON
    *   string using `JSON.parse()`. Use a `try...catch` block to handle
    *   potential `SyntaxError` if the string is not valid JSON. If an error
    *   occurs, print an error message and return `null`.

24. **Custom Error:**
    *   Define a custom error class `InvalidInputError` that extends `Error`.
    *   Write a function `processInput(value)` that throws an
    *   `InvalidInputError` if `value` is not a number. Otherwise, return
    *   `value * 2`. Use `try...catch` to handle `InvalidInputError`
    *   specifically.

25. **ES Modules (Conceptual):**
    *   Imagine you have a file `utils.js` with an `export` for a function
    *   `capitalize(str)` and a `default export` for a `Logger` class. Write
    *   the `import` statements you would use in another file (`app.js`) to use
    *   both `capitalize` and `Logger`.

26. **CommonJS Modules (Conceptual):**
    *   Imagine you have a file `config.js` that exports an object
    *   `module.exports = { API_KEY: "abc", DB_URL: "xyz" };` Write the
    *   `require` statement you would use in another file (`server.js`) to
    *   import and use these configuration values.

27. **JSON `stringify` and `parse`:**
    *   Given a JavaScript object `const user = { id: 1, name: "Charlie",
    *   isActive: true };` Convert this object into a JSON string.
    *   Convert the JSON string back into a JavaScript object.
    *   Print both the JSON string and the re-parsed object.

28. **Nested JSON Access:**
    *   Given the following JSON string:
        ```json
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
        ```
    *   Parse this JSON string into a JavaScript object.
    *   Access and print the customer's email.
    *   Access and print the `productId` of the second item.

29. **`this` Keyword in Objects:**
    *   Create an object `person` with `firstName`, `lastName`, and a method
    *   `fullName()` that returns the full name using `this`. Demonstrate
    *   calling `fullName()`.

30. **Higher-Order Function Example:**
    *   Write a higher-order function `applyOperation(arr, operation)` that
    *   takes an array of numbers and a function `operation`. It should return
    *   a new array where `operation` has been applied to each element.
    *   Demonstrate its use by passing an array and a function that doubles
    *   each number.

