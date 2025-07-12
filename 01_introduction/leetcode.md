## Chapter 1: Introduction to JavaScript and Node.js - LeetCode Style Problems

These problems are designed to test your foundational understanding of
JavaScript syntax, basic data types, control flow, and problem-solving logic,
which are essential for any programming role, including mobile back-end and
full-stack development. Focus on clarity, correctness, and efficiency.

---

### Problems

#### Problem 1: Sum of Two Numbers

**Description:** Given two integers, return their sum.

**Example 1:** 
``` Input: num1 = 5, num2 = 3 Output: 8 Explanation: 5 + 3 = 8.```

**Example 2:** 
``` Input: num1 = -10, num2 = 4 Output: -6 Explanation: -10 + 4 = -6. ```

> solution : 
 """ js 
        function sumOfTwoNumbers(a, b){
            return a + b;
        }
 """ 

#### Problem 2: Convert Minutes to Seconds

**Description:** Write a function that takes an integer `minutes` and converts
it to seconds.

**Example 1:** ``` Input: minutes = 5 Output: 300 
Explanation: 5 minutes * 60 seconds/minute = 300 seconds. ```

**Example 2:** ``` Input: minutes = 0 Output: 0 
Explanation: 0 minutes = 0 seconds. ```

> solution : 
 """ js 
        function minutesToSecond(minutes){
            return minutes * 60 ;
        }
 """ 

#### Problem 3: Area of a Triangle

**Description:** Write a function that takes the `base` and `height` of a
triangle and return its area. The area of a triangle is (base * height) / 2.

**Example 1:** ``` Input: base = 10, height = 5 Output: 25 Explanation: (10 *
5) / 2 = 25. ```

**Example 2:** ``` Input: base = 7, height = 3 Output: 10.5 Explanation: (7 *
3) / 2 = 10.5. ```

> solution : 
 """ js 
        function areaOfTriangle(base, height){
            return (base * height) / 2;
        }
 """ 

#### Problem 4: Return the First Element in an Array

**Description:** Create a function that takes an array and returns its first
element.

**Example 1:** ``` Input: arr = [1, 2, 3] Output: 1 ```

**Example 2:** ``` Input: arr = ["apple", "banana", "cherry"] Output: "apple"```

> solution : 
 """ js 
        function antiPop(arr){
            return arr[0];
        }
 """ 
 

#### Problem 5: Convert Age to Days

**Description:** Create a function that takes the `age` in years and returns
the age in days. Assume 365 days a year. Ignore leap years.

**Example 1:** ``` Input: age = 20 Output: 7300 Explanation: 20 * 365 = 7300```.


**Example 2:** ``` Input: age = 0 Output: 0 ```

> solution : 
 """ js 
        function ageInDays(years){
            return years * 365;
        }
 """ 
 

#### Problem 6: Is the Number Less Than or Equal to Zero?

**Description:** Create a function that takes a number as its only argument and
returns `true` if it's less than or equal to zero, otherwise return `false`.

**Example 1:** ``` Input: num = 5 Output: false ```

**Example 2:** ``` Input: num = 0 Output: true ```

**Example 3:** ``` Input: num = -2 Output: true ```

> solution : 
 """ js 
        function isnegative(number){
            return number > 0; 
        }
 """ 
 

#### Problem 7: Sum of Polygon Angles

**Description:** Given an integer `n`, return the sum of all interior angles of
an n-sided polygon (in degrees). The formula for the sum of interior angles of
an n-sided polygon is `(n - 2) * 180`.

**Example 1:** ``` Input: n = 3 Output: 180 Explanation: A triangle has 180
degrees. ```

**Example 2:** ``` Input: n = 4 Output: 360 Explanation: A quadrilateral has
360 degrees. ```

> solution : 
 """ js 
        function interiorAnglesSum(numberOfSides){
            return (numberOfSides - 2) * 180;
        }
 """ 
 

#### Problem 8: Convert Hours into Seconds

**Description:** Write a function that converts hours into seconds.

**Example 1:** ``` Input: hours = 2 Output: 7200 Explanation: 2 hours * 60
minutes/hour * 60 seconds/minute = 7200 seconds. ```

**Example 2:** ``` Input: hours = 10 Output: 36000 ```

> solution : 
 """ js 
        function hoursToSecond(hours){
            return hours * 60 * 60;
        }
 """ 
 

#### Problem 9: Maximum Edge of a Triangle

**Description:** Create a function that finds the maximum range of a triangle's
third edge, where the side lengths are all integers. The triangle inequality
theorem states that the sum of the lengths of any two sides of a triangle must
be greater than the length of the third side. Given two sides, `side1` and
`side2`, the third side `side3` must satisfy: `side1 + side2 > side3` and
`side1 + side3 > side2` and `side2 + side3 > side1`. The maximum integer length
of the third side is `side1 + side2 - 1`.

**Example 1:** ``` Input: side1 = 8, side2 = 10 Output: 17 Explanation: 8 + 10
- 1 = 17. ```

**Example 2:** ``` Input: side1 = 5, side2 = 7 Output: 11 ```

> solution : 
 """ js 
        function maximumNumberOfEdges(side1, side 2){
            return side1 + side2 - 1;
        }
 """ 

#### Problem 10: Return the Remainder from Two Numbers

**Description:** There is a single operator in JavaScript, capable of providing
the remainder of a division operation. Two numbers are passed as parameters.
The first parameter divided by the second parameter will have a remainder.
Return that remainder.

**Example 1:** ``` Input: num1 = 1, num2 = 3 Output: 1 ```

**Example 2:** ``` Input: num1 = 3, num2 = 4 Output: 3 ```

**Example 3:** ``` Input: num1 = 5, num2 = 5 Output: 0 ```

> solution : 
 """ js 
        function mod(num1 , num2){
            return num2 % num1;
        }
 """ 

#### Problem 11: Find the Smallest Number in an Array

**Description:** Create a function that takes an array of numbers and returns
the smallest number in the array.

**Example 1:** ``` Input: arr = [34, 15, 88, 2] Output: 2 ```

**Example 2:** ``` Input: arr = [1, 0, -5, 10] Output: -5 ```

> solution : 
 """ js 
        function smallestNumber(arr) {
          // easy : Math.min(...arr)
          let smallest = Number.POSITIVE_INFINITY;
          for (let i of arr) {
            if (i < smallest) {
              smallest = i;
            }
          }
          return smallest;
        }

 """ 

#### Problem 12: Check if an Integer is Divisible By Five

**Description:** Create a function that returns `true` if an integer is
divisible by 5, and `false` otherwise.

**Example 1:** ``` Input: num = 5 Output: true ```

**Example 2:** ``` Input: num = 7 Output: false ```

> solution : 
 """ js 
        function divisibleBy5(number){
            return number % 5 === 0 ? true : false;
        }
 """ 

#### Problem 13: Power Calculator

**Description:** Create a function that takes `voltage` and `current` and
returns the calculated `power`. Formula: `power = voltage * current`.

**Example 1:** ``` Input: voltage = 110, current = 3 Output: 330 ```

**Example 2:** ``` Input: voltage = 230, current = 10 Output: 2300 ```

> solution : 
 """ js 
        function calcPower(voltage, current){
            return voltage * current;
        }
 """ 

#### Problem 14: Return the Next Number from the Integer Passed

**Description:** Create a function that takes a number as an argument,
increments the number by +1 and returns the result.

**Example 1:** ``` Input: num = 0 Output: 1 ```

**Example 2:** ``` Input: num = 9 Output: 10 ```

> solution : 
 """ js 
        function nextNumber(number){
            return number++;
        }
 """ 

#### Problem 15: Convert an Array to a String

**Description:** Create a function that takes an array of numbers or strings
and converts it to a string.

**Example 1:** ``` Input: arr = [1, 2, 3] Output: "123" ```

**Example 2:** ``` Input: arr = ["a", "b", "c"] Output: "abc" ```

> solution : 
 """ js 
        function arrayToString(arr){
            return arr.join("");
        }
 """ 

#### Problem 16: Check if a Number is Even or Odd

**Description:** Create a function that takes an integer as an argument and
returns "Even" for even numbers or "Odd" for odd numbers.

**Example 1:** ``` Input: num = 4 Output: "Even" ```

**Example 2:** ``` Input: num = 7 Output: "Odd" ```

> solution : 
 """ js 
        function oddOrEven(number){
            return number % 2 === 0 ? "Even" : "Odd";
        }
 """ 

#### Problem 17: Find the Largest Number in an Array

**Description:** Create a function that takes an array of numbers and returns
the largest number in the array.

**Example 1:** ``` Input: arr = [34, 15, 88, 2] Output: 88 ```

**Example 2:** ``` Input: arr = [1, 0, -5, 10] Output: 10 ```

> solution : 
 """ js 
        function largestArrayNumber(arr){
            // easy : Math.max(...arr)
            let largest = Number.NEGATIVE_INFINITY; 
            for(let i of arr){
                if (i > largest ) largest  = i;
            }
            return largest;
        }
 """ 

#### Problem 18: Return the Absolute Value of a Number

**Description:** Create a function that takes a number as an argument and
returns its absolute value.

**Example 1:** ``` Input: num = -5 Output: 5 ```

**Example 2:** ``` Input: num = 10 Output: 10 ```

> solution : 
 """ js 
        function absoluteValueOf(number){
            return Math.abs(number);
        }
 """ 

#### Problem 19: Check if a String is Empty

**Description:** Create a function that returns `true` if a string is empty and
`false` otherwise.

**Example 1:** ``` Input: str = "" Output: true ```

**Example 2:** ``` Input: str = "hello" Output: false ```

> solution : 
 """ js 
        function isEmptyString(str){
            return str === '' ? true : false;
        }
 """ 

#### Problem 20: Reverse a String

**Description:** Create a function that takes a string as input and returns the
string reversed.

**Example 1:** ``` Input: str = "hello" Output: "olleh" ```

**Example 2:** ``` Input: str = "world" Output: "dlrow" ```

> solution : 
    """ js
            function reverseString(str){
                return str.split("").reverse().join("");
            }
    """

#### Problem 21: Count Vowels in a String

**Description:** Create a function that takes a string and returns the number
of vowels (a, e, i, o, u) in the string. The string will only contain lowercase
letters and/or spaces.

**Example 1:** ``` Input: str = "hello" Output: 2 Explanation: 'e' and 'o' are
vowels. ```

**Example 2:** ``` Input: str = "rhythm" Output: 0 ```

> solution : 
    """ js
            function countStringVowels(str) {
              let numOfVow = 0;
              for (let i of str) {
                if (i.includes("a")) numOfVow++;
                if (i.includes("e")) numOfVow++;
                if (i.includes("i")) numOfVow++;
                if (i.includes("o")) numOfVow++;
                if (i.includes("u")) numOfVow++;
              }
              return numOfVow;
            }
    """

#### Problem 22: Find the Longest Word in a String

**Description:** Create a function that takes a sentence (string) and returns
the longest word in it. If there are multiple words of the same length, return
the first one encountered.

**Example 1:** ``` Input: sentence = "The quick brown fox jumps over the lazy
dog" Output: "quick" ```

**Example 2:** ``` Input: sentence = "JavaScript is awesome" Output:
"JavaScript" ```

> solution : 
    """ js
        function longestWordInString(str) {
          let longest = "";
          for (let w of str.split(" ")) {
            if (w.length > longest.length) longest = w;
          }
          return longest;
        }
    """

#### Problem 23: Check if an Array Contains a Specific Element

**Description:** Create a function that takes an array and an element. Return
`true` if the element exists in the array, otherwise return `false`.

**Example 1:** ``` Input: arr = [1, 2, 3], element = 2 Output: true ```

**Example 2:** ``` Input: arr = ["apple", "banana"], element = "orange" Output:
false ```

> solution : 
    """ js
            function include(arr, element){
                return arr.inludes(element); 
            }
    """

#### Problem 24: Sum All Numbers in an Array

**Description:** Create a function that takes an array of numbers and returns
the sum of all numbers in the array.

**Example 1:** ``` Input: arr = [1, 2, 3, 4] Output: 10 ```

**Example 2:** ``` Input: arr = [10, -5, 20] Output: 25 ```

> solution : 
    """ js
            function sumArrayNumbers(arr){
                return arr.reduce((acc, x) => acc + x); 
            }
    """

#### Problem 25: Filter Out Negative Numbers

**Description:** Create a function that takes an array of numbers and returns a
new array with only the non-negative numbers.

**Example 1:** ``` Input: arr = [1, -2, 3, -4, 5] Output: [1, 3, 5] ```

**Example 2:** ``` Input: arr = [-1, -5, -10] Output: [] ```

> solution : 
    """ js
            function onlyPositiveElements(arr){
                return arr.filter(x => x >= 0);
            }
    """

#### Problem 26: Repeat a String `n` Times

**Description:** Create a function that takes a string `str` and a number `n`.
Return the string `str` repeated `n` times.

**Example 1:** ``` Input: str = "abc", n = 3 Output: "abcabcabc" ```

**Example 2:** ``` Input: str = "hello", n = 0 Output: "" ```

> solution : 
    """ js
            function repeatString(str, n){
                return str.repeat(n);
            }
    """

#### Problem 27: Check if Two Strings are Anagrams

**Description:** Create a function that takes two strings and returns `true` if
they are anagrams of each other, otherwise return `false`. Anagrams are words
or phrases formed by rearranging the letters of a different word or phrase,
typically using all the original letters exactly once.

**Example 1:** ``` Input: str1 = "listen", str2 = "silent" Output: true ```

**Example 2:** ``` Input: str1 = "hello", str2 = "world" Output: false ```

> solution : 
    """ js
        function isAnagrams(str1, str2) {
          return str1.length === str2.length && 
          str1.search(str2) ? true : false;
        }
    """

#### Problem 28: Find the Missing Number in a Sequence

**Description:** Given an array `nums` containing `n` distinct numbers in the
range `[0, n]`, return the only number in the range that is missing from the
array.

**Example 1:** ``` Input: nums = [3, 0, 1] Output: 2 Explanation: n = 3 since
there are 3 numbers, so all numbers are in the range [0,3]. 2 is the missing
number. ```

**Example 2:** ``` Input: nums = [0, 1] Output: 2 Explanation: n = 2 since
there are 2 numbers, so all numbers are in the range [0,2]. 2 is the missing
number. ```

> solution : 
    """ js
            function findMissingNumber(arr) {
              arr.sort();
              let lastElement = arr[arr.length - 1];
              let arrayLength = arr.length;
              if (lastElement >= arrayLength) {arr.length = lastElement}
              let missing = [];
              for (let i = arr.length; i >= 0; i--) {
                  if (!arr.includes(i)) {missing.push(i);}
              }
              return missing;
            }
    """

#### Problem 29: Palindrome Check

**Description:** Create a function that takes a string and returns `true` if
it's a palindrome, otherwise return `false`. A palindrome is a word, phrase,
number, or other sequence of characters which reads the same backward as
forward, ignoring case and punctuation.

**Example 1:** ``` Input: str = "madam" Output: true ```

**Example 2:** ``` Input: str = "A man, a plan, a canal: Panama" Output: true
```

**Example 3:** ``` Input: str = "hello" Output: false ```

> solution : 
    """ js
            function ispalindrome(str) {
              str = str
            .toLowerCase()
            .split("")
            .filter((x) => x !== " " && x !== ":" && x !== ",")
            .join("");
              let output = true;
              for (let h = 0, r = str.length - 1; h < str.length; h++, r--) {
                output &&= str[h] === str[r];
              }
              return output;
            }
    """

#### Problem 30: FizzBuzz

**Description:** Write a program that prints the numbers from 1 to 100. But for
multiples of three print "Fizz" instead of the number and for the multiples of
five print "Buzz". For numbers which are multiples of both three and five print
"FizzBuzz".

**Example:** ``` Input: (Implicitly, numbers from 1 to 100) Output: 1, 2, Fizz,
4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, Fizz, 13, 14, FizzBuzz, ... ```

> solution : 
    """ js
            function fizzbuzz() {
              let arr = new Array(100).fill(0);
              for (let i in arr) {
                if (i % 3 === 0 && i % 5 === 0) console.log("fizzbuzz");
                else if (i % 3 === 0) console.log("fizz");
                else if (i % 5 === 0) console.log("buzz");
                else console.log(i);
              }
            }
    """

---

### Optimal Solutions

#### Problem 1: Sum of Two Numbers

```javascript /**
 * @param {number} num1
 * @param {number} num2
 * @return {number} */ const sumTwoNumbers = (num1, num2) => { return num1 +
   num2; };

// Big-O Analysis: // Time Complexity: O(1) - The operation takes a constant
amount of time regardless of the input values. // Space Complexity: O(1) - No
additional space is used that scales with input size. ```

#### Problem 2: Convert Minutes to Seconds

```javascript /**
 * @param {number} minutes
 * @return {number} */ const convertMinutesToSeconds = (minutes) => { return
   minutes * 60; };

// Big-O Analysis: // Time Complexity: O(1) - Constant time operation. // Space
Complexity: O(1) - Constant space. ```

#### Problem 3: Area of a Triangle

```javascript /**
 * @param {number} base
 * @param {number} height
 * @return {number} */ const triangleArea = (base, height) => { return (base *
   height) / 2; };

// Big-O Analysis: // Time Complexity: O(1) - Constant time operation. // Space
Complexity: O(1) - Constant space. ```

#### Problem 4: Return the First Element in an Array

```javascript /**
 * @param {Array<any>} arr
 * @return {any} */ const getFirstElement = (arr) => { if (arr.length === 0) {
   // Handle empty array case, though problem implies non-empty for simplicity
   return undefined; // Or throw an error, depending on requirements } 
   return arr[0]; };

// Big-O Analysis: // Time Complexity: O(1) - Accessing an element by index in
an array is a constant time operation. // Space Complexity: O(1) - Constant
space. ```

#### Problem 5: Convert Age to Days

```javascript /**
 * @param {number} age
 * @return {number} */ const convertAgeToDays = (age) => { return age * 365; };

// Big-O Analysis: // Time Complexity: O(1) - Constant time operation. // Space
Complexity: O(1) - Constant space. ```

#### Problem 6: Is the Number Less Than or Equal to Zero?

```javascript /**
 * @param {number} num
 * @return {boolean} */ const isLessThanOrEqualToZero = (num) => { return num
   <= 0; };

// Big-O Analysis: // Time Complexity: O(1) - Constant time operation. // Space
Complexity: O(1) - Constant space. ```

#### Problem 7: Sum of Polygon Angles

```javascript /**
 * @param {number} n - number of sides
 * @return {number} */ const sumOfPolygonAngles = (n) => { // A polygon must
   have at least 3 sides if (n < 3) { throw new Error("A polygon must have at
   least 3 sides."); } return (n - 2) * 180; };

// Big-O Analysis: // Time Complexity: O(1) - Constant time operation. // Space
Complexity: O(1) - Constant space. ```

#### Problem 8: Convert Hours into Seconds

```javascript /**
 * @param {number} hours
 * @return {number} */ const convertHoursToSeconds = (hours) => { return hours
   * 60 * 60; };

// Big-O Analysis: // Time Complexity: O(1) - Constant time operation. // Space
Complexity: O(1) - Constant space. ```

#### Problem 9: Maximum Edge of a Triangle

```javascript /**
 * @param {number} side1
 * @param {number} side2
 * @return {number} */ const maxTriangleEdge = (side1, side2) => { // The third
   side must be less than the sum of the other two sides. // Since side lengths
   are integers, the maximum integer length is sum - 1. return side1 + side2 -
   1; };

// Big-O Analysis: // Time Complexity: O(1) - Constant time operation. // Space
Complexity: O(1) - Constant space. ```

#### Problem 10: Return the Remainder from Two Numbers

```javascript /**
 * @param {number} num1
 * @param {number} num2
 * @return {number} */ const remainder = (num1, num2) => { // Handle division
   by zero if necessary, though problem implies num2 is non-zero if (num2 ===
   0) { throw new Error("Cannot divide by zero."); } return num1 % num2; };

// Big-O Analysis: // Time Complexity: O(1) - Constant time operation. // Space
Complexity: O(1) - Constant space. ```

#### Problem 11: Find the Smallest Number in an Array

```javascript /**
 * @param {Array<number>} arr
 * @return {number} */ const findSmallestNumber = (arr) => { if (arr.length ===
   0) { throw new Error("Array cannot be empty."); } // Using Math.min with
   spread operator for efficiency and readability return Math.min(...arr);

    // Alternative: Iterative approach // let smallest = arr[0]; // for (let i
    = 1; i < arr.length; i++) { //     if (arr[i] < smallest) { //
    smallest = arr[i]; //     } // } // return smallest; };

// Big-O Analysis: // Time Complexity: O(N) - Where N is the number of elements
in the array. Math.min(...arr) iterates through all elements. // Space
Complexity: O(N) - The spread operator creates a new array in memory for the
arguments to Math.min. Iterative approach is O(1). ```

#### Problem 12: Check if an Integer is Divisible By Five

```javascript /**
 * @param {number} num
 * @return {boolean} */ const isDivisibleByFive = (num) => { return num % 5 ===
   0; };

// Big-O Analysis: // Time Complexity: O(1) - Constant time operation. // Space
Complexity: O(1) - Constant space. ```

#### Problem 13: Power Calculator

```javascript /**
 * @param {number} voltage
 * @param {number} current
 * @return {number} */ const calculatePower = (voltage, current) => { return
   voltage * current; };

// Big-O Analysis: // Time Complexity: O(1) - Constant time operation. // Space
Complexity: O(1) - Constant space. ```

#### Problem 14: Return the Next Number from the Integer Passed

```javascript /**
 * @param {number} num
 * @return {number} */ const nextNumber = (num) => { return num + 1; };

// Big-O Analysis: // Time Complexity: O(1) - Constant time operation. // Space
Complexity: O(1) - Constant space. ```

#### Problem 15: Convert an Array to a String

```javascript /**
 * @param {Array<any>} arr
 * @return {string} */ const arrayToString = (arr) => { // The join method
   converts all elements of an array into a string. // If no separator is
   specified, array elements are separated by a comma. // Using an empty string
   as a separator concatenates them directly. return arr.join(""); };

// Big-O Analysis: // Time Complexity: O(N) - Where N is the number of elements
in the array, as it iterates through all elements to concatenate them. // Space
Complexity: O(N) - A new string is created, whose length depends on the number
of elements and their string representations. ```

#### Problem 16: Check if a Number is Even or Odd

```javascript /**
 * @param {number} num
 * @return {string} */ const isEvenOrOdd = (num) => { if (num % 2 === 0) {
   return "Even"; } else { return "Odd"; } };

// Big-O Analysis: // Time Complexity: O(1) - Constant time operation. // Space
Complexity: O(1) - Constant space. ```

#### Problem 17: Find the Largest Number in an Array

```javascript /**
 * @param {Array<number>} arr
 * @return {number} */ const findLargestNumber = (arr) => { if (arr.length ===
   0) { throw new Error("Array cannot be empty."); } // Using Math.max with
   spread operator for efficiency and readability return Math.max(...arr);

    // Alternative: Iterative approach // let largest = arr[0]; // for (let i =
    1; i < arr.length; i++) { //     if (arr[i] > largest) { //         largest
    = arr[i]; //     } // } // return largest; };

// Big-O Analysis: // Time Complexity: O(N) - Where N is the number of elements
in the array. Math.max(...arr) iterates through all elements. // Space
Complexity: O(N) - The spread operator creates a new array in memory for the
arguments to Math.max. Iterative approach is O(1). ```

#### Problem 18: Return the Absolute Value of a Number

```javascript /**
 * @param {number} num
 * @return {number} */ const absoluteValue = (num) => { return Math.abs(num);
   };

// Big-O Analysis: // Time Complexity: O(1) - Constant time operation. // Space
Complexity: O(1) - Constant space. ```

#### Problem 19: Check if a String is Empty

```javascript /**
 * @param {string} str
 * @return {boolean} */ const isEmptyString = (str) => { return str.length ===
   0; };

// Big-O Analysis: // Time Complexity: O(1) - Accessing string length is a
constant time operation. // Space Complexity: O(1) - Constant space. ```

#### Problem 20: Reverse a String

```javascript /**
 * @param {string} str
 * @return {string} */ const reverseString = (str) => { // Convert string to
   array, reverse array, then join back to string return
   str.split("").reverse().join(""); };

// Big-O Analysis: // Time Complexity: O(N) - Where N is the length of the
string. split(), reverse(), and join() all take linear time. // Space
Complexity: O(N) - An array of characters is created, which scales with the
string length. ```

#### Problem 21: Count Vowels in a String

```javascript /**
 * @param {string} str
 * @return {number} */ const countVowels = (str) => { const vowels = "aeiou";
   let count = 0; for (let i = 0; i < str.length; i++) { if
   (vowels.includes(str[i])) { count++; } } return count; };

// Big-O Analysis: // Time Complexity: O(N) - Where N is the length of the
string. We iterate through the string once. // Space Complexity: O(1) - The
'vowels' string and 'count' variable take constant space. ```

#### Problem 22: Find the Longest Word in a String

```javascript /**
 * @param {string} sentence
 * @return {string} */ const findLongestWord = (sentence) => { const words =
   sentence.split(" "); let longestWord = "";

    for (let i = 0; i < words.length; i++) { // Remove punctuation for accurate
        length comparison if necessary // For this problem, assuming words are
        separated by single spaces and no punctuation. const currentWord =
        words[i]; if (currentWord.length > longestWord.length) { longestWord =
        currentWord; } } return longestWord; };

// Big-O Analysis: // Time Complexity: O(L) - Where L is the total number of
characters in the sentence. split() takes O(L), and the loop iterates through
words, which in total processes all characters. // Space Complexity: O(W) -
Where W is the number of words in the sentence, as an array of words is
created. ```

#### Problem 23: Check if an Array Contains a Specific Element

```javascript /**
 * @param {Array<any>} arr
 * @param {any} element
 * @return {boolean} */ const containsElement = (arr, element) => { return
   arr.includes(element);

    // Alternative: Iterative approach // for (let i = 0; i < arr.length; i++)
    { //     if (arr[i] === element) { //         return true; //     } // } //
    return false; };

// Big-O Analysis: // Time Complexity: O(N) - Where N is the number of elements
in the array. In the worst case, we might have to check every element. // Space
Complexity: O(1) - Constant space. ```

#### Problem 24: Sum All Numbers in an Array

```javascript /**
 * @param {Array<number>} arr
 * @return {number} */ const sumArray = (arr) => { let sum = 0; for (let i = 0;
   i < arr.length; i++) { sum += arr[i]; } return sum;

    // Alternative: Using reduce // return arr.reduce((accumulator,
    currentValue) => accumulator + currentValue, 0); };

// Big-O Analysis: // Time Complexity: O(N) - Where N is the number of elements
in the array, as we iterate through all elements once. // Space Complexity:
O(1) - Constant space (for the sum variable). ```

#### Problem 25: Filter Out Negative Numbers

```javascript /**
 * @param {Array<number>} arr
 * @return {Array<number>} */ const filterNegativeNumbers = (arr) => { const
   result = []; for (let i = 0; i < arr.length; i++) { if (arr[i] >= 0) {
       result.push(arr[i]); } } return result;

    // Alternative: Using filter method // return arr.filter(num => num >= 0);
    };

// Big-O Analysis: // Time Complexity: O(N) - Where N is the number of elements
in the array, as we iterate through all elements once. // Space Complexity:
O(N) - In the worst case (all numbers are non-negative), a new array of size N
is created. ```

#### Problem 26: Repeat a String `n` Times

```javascript /**
 * @param {string} str
 * @param {number} n
 * @return {string} */ const repeatString = (str, n) => { if (n < 0) { throw
   new Error("Number of repetitions cannot be negative."); } return
   str.repeat(n);

    // Alternative: Iterative approach // let result = ""; // for (let i = 0; i
    < n; i++) { //     result += str; // } // return result; };

// Big-O Analysis: // Time Complexity: O(N * M) - Where N is the number of
repetitions and M is the length of the string. The `repeat` method or iterative
concatenation will build a string of length N*M. // Space Complexity: O(N * M)
- The resulting string will have a length of N*M. ```

#### Problem 27: Check if Two Strings are Anagrams

```javascript /**
 * @param {string} str1
 * @param {string} str2
 * @return {boolean} */ const areAnagrams = (str1, str2) => { // Anagrams must
   have the same length if (str1.length !== str2.length) { return false; }

    // Convert to lowercase and sort characters, then compare const sortedStr1
    = str1.toLowerCase().split("").sort().join(""); const sortedStr2 =
    str2.toLowerCase().split("").sort().join("");

    return sortedStr1 === sortedStr2; };

// Big-O Analysis: // Time Complexity: O(N log N) - Where N is the length of
the strings. The dominant operation is sorting, which is O(N log N). // Space
Complexity: O(N) - New arrays and strings are created during the split, sort,
and join operations. ```

#### Problem 28: Find the Missing Number in a Sequence

```javascript /**
 * @param {Array<number>} nums
 * @return {number} */ const findMissingNumber = (nums) => { const n =
   nums.length; // Sum of numbers from 0 to n is n * (n + 1) / 2 const
   expectedSum = n * (n + 1) / 2;

    // Calculate the actual sum of numbers in the array let actualSum = 0; for
    (let i = 0; i < n; i++) { actualSum += nums[i]; }

    // The missing number is the difference between the expected sum and the
    actual sum return expectedSum - actualSum;

    // Alternative using XOR (more advanced, handles overflow better for very
    large numbers) // let missing = n; // for (let i = 0; i < n; i++) { //
    missing ^= i ^ nums[i]; // } // return missing; };

// Big-O Analysis: // Time Complexity: O(N) - Where N is the number of elements
in the array. We iterate through the array once to calculate the sum. // Space
Complexity: O(1) - Constant space is used for variables. ```

#### Problem 29: Palindrome Check

```javascript /**
 * @param {string} str
 * @return {boolean} */ const isPalindrome = (str) => { // Normalize the
   string: convert to lowercase and remove non-alphanumeric characters const
   cleanedStr = str.toLowerCase().replace(/[^a-z0-9]/g, "");

    // Compare the cleaned string with its reverse const reversedStr =
    cleanedStr.split("").reverse().join("");

    return cleanedStr === reversedStr;

    // Alternative: Two-pointer approach (more efficient for very long strings
    as it avoids creating new strings) // let left = 0; // let right =
    cleanedStr.length - 1; // while (left < right) { //     if
    (cleanedStr[left] !== cleanedStr[right]) { //         return false; //
    } //     left++; //     right--; // } // return true; };

// Big-O Analysis: // Time Complexity: O(N) - Where N is the length of the
string. Cleaning, splitting, reversing, and joining all take linear time. //
Space Complexity: O(N) - New strings and arrays are created during the cleaning
and reversing process. ```

#### Problem 30: FizzBuzz

```javascript /**
 * @param {number} n - The upper limit (inclusive) for FizzBuzz.
 * @return {Array<string | number>} - An array containing the FizzBuzz
   sequence. */ const fizzBuzz = (n) => { const result = []; for (let i = 1; i
   <= n; i++) { let output = ""; if (i % 3 === 0) { output += "Fizz"; } if (i %
   5 === 0) { output += "Buzz"; } if (output === "") { result.push(i); } else {
       result.push(output); } } return result; };

// Example usage for the problem statement (1 to 100): // const
fizzBuzzSequence = fizzBuzz(100); // fizzBuzzSequence.forEach(item =>
console.log(item));

// Big-O Analysis: // Time Complexity: O(N) - Where N is the upper limit. We
iterate from 1 to N once. // Space Complexity: O(N) - An array of size N is
created to store the results. ```


