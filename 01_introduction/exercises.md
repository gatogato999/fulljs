## Chapter 1: Introduction to JavaScript and Node.js - Exercises

These exercises are designed to reinforce your understanding of the
introductory concepts of JavaScript and Node.js, and to get you comfortable
with your development environment and basic command-line operations.

### Section 1: JavaScript and Node.js Fundamentals

1.  **Verify Node.js and npm Installation:**
    *   Open your terminal or command prompt.
    *   Run `node -v` and `npm -v`. Record the versions you have installed.
    *   If you encounter any issues, refer back to the installation section in
        Chapter 1.

2.  **Create Your First Node.js Script:**
    *   Create a new directory named `my-first-script`.
    *   Inside `my-first-script`, create a file named `hello.js`.
    *   Add a single line of JavaScript code to `hello.js` that prints "Hello
        from Node.js!" to the console.
    *   Execute the script using Node.js from your terminal.

3.  **Basic Variable Declaration and Output:**
    *   Create a new file `variables.js`.
    *   Declare a variable `userName` and assign your name to it (as a string).
    *   Declare a variable `userAge` and assign your age to it (as a number).
    *   Use `console.log()` to print a message like: "Hello, [userName]! You
        are [userAge] years old."

4.  **Simple Arithmetic Operations:**
    *   Create a file `calculator.js`.
    *   Declare two variables, `num1` and `num2`, and assign them any numeric
        values.
    *   Perform addition, subtraction, multiplication, and division using these
        variables.
    *   Print the result of each operation to the console, clearly labeling
        each output (e.g., "Sum: ", "Difference: ").

5.  **Understanding Data Types:**
    *   Create a file `datatypes.js`.
    *   Declare variables for each of the following JavaScript data types:
        `string`, `number`, `boolean`, `null`, `undefined`, `object` (e.g., an
        empty object `{}`), and `array` (e.g., an empty array `[]`).
    *   Use `console.log()` and the `typeof` operator to print the type of each
        variable to the console.

### Section 2: Command Line and Project Setup

6.  **Navigate the File System:**
    *   From your home directory, navigate into the `my-first-script` directory
        you created earlier using `cd`.
    *   From `my-first-script`, navigate back to your home directory using a
        single `cd` command (e.g., `cd ..` or `cd ~`).
    *   Create a new directory `temp_project` and then remove it.

7.  **Initialize a Node.js Project:**
    *   Create a new directory named `my-node-project`.
    *   Navigate into `my-node-project`.
    *   Run `npm init -y` to quickly initialize a new Node.js project. Examine
        the generated `package.json` file.

8.  **Install a Local Package:**
    *   In `my-node-project`, install a simple utility package like `lodash`
        (or any other small package) using `npm install lodash`.
    *   Observe the `node_modules` directory and the updated `package.json` and
        `package-lock.json` files.

9.  **Use an Installed Package:**
    *   Create an `index.js` file in `my-node-project`.
    *   Import the `lodash` package (e.g., `const _ = require('lodash');`).
    *   Use a simple `lodash` function, for example, `_.camelCase('hello
        world')`, and print the result to the console.
    *   Run `node index.js` to execute the script.

10. **Understand `devDependencies`:**
    *   Install a development dependency, for example, `nodemon`, using `npm
        install nodemon --save-dev`.
    *   Verify that `nodemon` is listed under `devDependencies` in
        `package.json`.

11. **Create and Run an npm Script:**
    *   In `package.json`, add a new script under the `scripts` section, for
        example, `"start-dev": "nodemon index.js"`.
    *   Modify `index.js` to print a message like "App is running..." every
        time it executes.
    *   Run your new script using `npm run start-dev`.
    *   Make a small change to `index.js` and observe if `nodemon`
        automatically restarts the application.

12. **Explore `node_modules` and `.gitignore`:**
    *   Explain why the `node_modules` folder should typically be excluded from
        version control.
    *   If you were to use Git, describe how you would add `node_modules` to a
        `.gitignore` file.

### Section 3: Conceptual Understanding and Research

13. **JavaScript vs. Node.js:**
    *   In your own words, explain the fundamental difference between
        JavaScript and Node.js.
    *   Provide an analogy to help someone new to programming understand this
        distinction.

14. **Event Loop Explanation:**
    *   Briefly describe the concept of the JavaScript Event Loop.
    *   Why is the Event Loop crucial for Node.js's performance and
        non-blocking I/O?

15. **Synchronous vs. Asynchronous:**
    *   Define synchronous and asynchronous operations in the context of
        programming.
    *   Give a real-world example (outside of programming) for each.
    *   How does Node.js primarily handle I/O operations (synchronously or
        asynchronously)?

16. **Benefits of Full-Stack JavaScript:**
    *   List at least three advantages of using JavaScript for both front-end
        and back-end development in a full-stack application.

17. **NPM's Role:**
    *   What is npm, and what is its primary purpose in the Node.js ecosystem?
    *   How does it contribute to rapid application development?

18. **Choosing a Code Editor:**
    *   Research at least two other popular code editors besides VS Code (e.g.,
        Sublime Text, Atom, WebStorm).
    *   List one pro and one con for each, comparing them to VS Code for
        Node.js development.

19. **`package.json` Deep Dive:**
    *   Explain the purpose of the `main` field in `package.json`.
    *   What is the difference between `dependencies` and `devDependencies`?

20. **Scalability in Node.js:**
    *   How can Node.js, being single-threaded, achieve high scalability?
    *   Mention at least one mechanism or concept that contributes to its
        scalability.

21. **JSON Importance:**
    *   Why is JSON a natural fit for data exchange in JavaScript and Node.js
        applications?
    *   How does its native support simplify development?

22. **Microservices vs. Monoliths (Brief):**
    *   Based on the introduction, briefly explain what microservices are.
    *   Why might Node.js be a good choice for building microservices?

23. **Serverless Computing (Brief):**
    *   What is the core idea behind serverless computing?
    *   How does Node.js fit into a serverless architecture?

24. **Research: Node.js Use Cases:**
    *   Search online for real-world companies or applications that use Node.js
        extensively.
    *   List at least three examples and briefly describe how Node.js is
        utilized in their systems.

25. **Reflect and Plan:**
    *   Based on what you've learned, what aspects of JavaScript or Node.js are
        you most interested in exploring further?
    *   Formulate one question you have about JavaScript or Node.js that you
        hope to answer in future chapters.

