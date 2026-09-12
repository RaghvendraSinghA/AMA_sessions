- What are template literals in JavaScript?
  - Template literals are strings enclosed in backticks (`).
  - They allow us to embed variables and expressions using `${}`.
  - Example: `Hello, ${name}`

- What is the `this` keyword in JavaScript?
  - `this` refers to the object associated with the current execution context.
  - Its value depends on how the function is called.
  - In an object method, `this` usually refers to the object that called the method.

- What is execution context?
  - Execution context is the environment in which JavaScript code is evaluated and executed.
  - It contains information such as variables, functions, and the value of `this`.
  - The main types are global execution context, function execution context, and eval execution context.

- Which CLI command is used to check the group name?
  - The `groups` command is used to check the groups associated with the current user.
  - Example: `groups`

- What is the difference between `find()` and `filter()` in JavaScript?
  - `find()` returns the first element that satisfies the condition.
  - `filter()` returns an array containing all elements that satisfy the condition.
  - If no element is found, `find()` returns `undefined`, while `filter()` returns an empty array.

- Explain the call stack.
  - The call stack keeps track of function calls during program execution.
  - When a function is called, it is added to the top of the stack.
  - When the function finishes, it is removed from the stack.
  - JavaScript uses the call stack to execute synchronous code.

- What happens when we concatenate a string with number?
  - JavaScript converts the number into a string and then concatenates them.
  - Example: `"Age: " + 25` results in `"Age: 25"`.

- What is the difference between `forEach()` and `map()`?
  - `forEach()` executes a function for each element but does not create a new array.
  - `map()` executes a function for each element and returns a new array containing the results.
  - `map()` should be used when you want to transform the elements.

- What is an object in JavaScript?
  - An object is a collection of key-value pairs.
  - Keys are used to identify properties, and values can contain any valid JavaScript data type.
  - Example: `{ name: "John", age: 25 }`

- What is scope chaining?
  - Scope chaining is the process JavaScript uses to find a variable in the current scope and then search outer scopes if it is not found.
  - It continues searching through the outer lexical environments until the variable is found or the global scope is reached.

- What is an array in JavaScript?
  - An array is an ordered collection of values of same data-type but, in javascript we have list
    which is dynamic array, It can contain multiple-datatype inside it and its size can grow automatically.
  - It can contain multiple values of different data types.
  - Array elements are accessed using indexes starting from `0`.
  - Example: `["Apple", "Banana", "Mango"]`

- What is the difference between `undefined` and `null`?
  - `undefined` usually means a variable has been declared but has not been assigned a value.
  - `null` is an explicitly assigned value that represents the absence of a value.
  - Example: `let a;` gives `undefined`, while `let b = null;` gives `null`.

- What is the difference between `shift()` and `unshift()`?
  - `shift()` removes the first element from an array and returns it.
  - `unshift()` adds one or more elements to the beginning of an array and returns the new array length.
