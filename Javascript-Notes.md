
# **Phase 1 - Basics Of JavaScript (Part 1)**

## **1. Introduction to JavaScript and Why Learn It**<!-- {"collapsed":true} -->

JavaScript is the most widely used language for web development. It powers both frontend and backend (via Node.js), making it a full-stack language. It’s also essential for learning DSA due to its readability, flexibility, and large community.

- **Use Cases:**

    - Web development

    - Game development

    - Server-side scripting (Node.js)

    - Data structures and algorithm practice (LeetCode, HackerRank)

**Video Reference:**
Akshay Saini – [Namaste JavaScript Playlist](https://www.youtube.com/playlist?list=PLlasXeu85E9cQ32gLCvAvr9vNaUccPVNP)
Start with:  [How Javascript works](https://youtu.be/ZvbzSrg0afE?si=ujEB--eTxw086qNu) 


## **2. What is an Execution Context?**<!-- {"collapsed":true} -->

It is the environment in which JavaScript code is executed. There are two types:

- **Global Execution Context (GEC)**

- **Function Execution Context (FEC)**

Each context has:

- Memory Component (Variable Environment)

- Code Component (Thread of Execution)

```
//Javascript
Example: Simple Hello Function Call.

var x = 1;

function sayHello() {
  var y = 2;
  console.log("Hello", x + y);
}
sayHello();
```


**What happens under the hood:**

- JS creates a GEC first.

- Memory phase: allocates memory for `x` and `sayHello`.

- Execution phase: assigns `x = 1`, and calls `sayHello()`.

- Inside `sayHello`, a new FEC is created.

**Akshay Saini Explanation Video:**
[Episode 2 - Execution Context](https://www.youtube.com/watch?v=ylakWCz3B5g) 


## 3**. JavaScript is Synchronous and Single-Threaded.**<!-- {"collapsed":true} -->


- Synchronous: Executes one line at a time.

- Single-threaded: Only one call stack; one operation at a time.


```c
code :
console.log("Start");
console.log("Middle");
console.log("End");

Output:

Start
Middle
End
```

- No multitasking happens.


## **4. Call Stack in JavaScript**<!-- {"collapsed":true} -->

```
function one() {
  two();
}
function two() {
  console.log("Inside two");
}
one();
```


Call Stack Flow:

- one() is pushed

- Inside one(), two() is called → pushed

- two() finishes → popped

- one() finishes → popped

Akshay Saini Video :[Execution and Call Stack ](https://youtu.be/iLWTnMzWtj4?si=iqR2qcxdoBJMe7KL) 

## **5. Objects in JavaScript**<!-- {"collapsed":true} -->

**Theory:** Objects are collections of key-value pairs. Each key (also called a property) is a string, and its value can be anything — a number, string, array, another object, or a function (called a method).

For Example:-

```
let person = {
  name: "John",
  age: 30,
  greet: function () {
    console.log("Hello " + this.name);
  }
};
```


Accessing properties:

```
console.log(person.name);  // Dot notation
console.log(person['age']);  // Bracket notation
```

Modifying properties:

```
person.age = 31;  //Modify
```

Adding properties:

```
person.city = "New York";  //Add
```

Deleting properties:

```
delete person.city; //Delete
```

Looping through an object:

```
for (let key in person) {
  console.log(key + ": " + person[key]);
}
```

Object Methods and `this` Keyword:

```
const car = {
  brand: "Toyota",
  model: "Camry",
  displayInfo() {
    console.log(`${this.brand} ${this.model}`);
  }
};

car.displayInfo(); // Toyota Camry
```


| | | |
|-|-|-|
|**Video Reference:-** |[Objects](https://youtu.be/vVYOHmqQDCU?si=H7OIgYylq2xBmYpJ)  ||

## **6. Arrays In Javascript    Video Reference  :-**[ Arrays in JavaScript](https://youtu.be/cejBux2gtEE?si=14b3zLbL-yxa_0J9)<!-- {"collapsed":true} -->

**Theory:** Arrays are ordered collections of values. They can hold elements of any type and can be accessed using indices.

```
Syntax: let fruits = ["Apple", "Banana", "Mango"];

------------------------------------------------------
  
If you want Accessing elements:
console.log(fruits[1]);  // Banana
```

Adding elements:

```
fruits.push("Orange");
```

Removing elements:  

```
fruits.pop();        // Removes last
fruits.shift();      // Removes first
fruits.unshift("Kiwi");  // Adds to beginning
```

Looping over an array:

```
for (let fruit of fruits) {
  console.log(fruit);
}
```

## **7.Functions in JavaScript  Video Reference : -** [Funtions](https://youtu.be/FOD408a0EzU?si=bFI9KNbyceDB80Ww)<!-- {"collapsed":true} -->

**Theory:** Functions are blocks of reusable code. JavaScript supports both function declarations and expressions.

**Function Declaration:**

```
function greet(name) {
  return "Hello " + name;
}
```

Function Expression:

```
const greet = function(name) {
  return "Hello " + name;
};
```

Arrow Functions (ES6):

```
const greet = (name) => "Hello " + name;
```


```
let fruits = ["apple", "banana", "mango"];
```

**Array Methods:**

| | <!-- {"fullWidth":true} -->|
|-|-|
|Method<!-- {"cell":{"colwidth":109}} -->|Description|
|`push()`<!-- {"cell":{"colwidth":109}} -->|Adds to end   ---------------------------------------------------------------------------------------------fruits.push()|
|`pop()`<!-- {"cell":{"colwidth":109}} -->|Removes from end  -----------------------------------------------------------------------------------fruits.pop()|
|`shift()`<!-- {"cell":{"colwidth":109}} -->|Removes from start-----------------------------------------------------------------------------------fruits.shift()|
|`unshift()`<!-- {"cell":{"colwidth":109}} -->|Adds to start  ---------------------------------------------------------------------------------------------fruits.unshift()|
|`splice()`<!-- {"cell":{"colwidth":109}} -->|Add/remove items -------------------------------------------------------------------------------------fruits.splice()|
|`slice()`<!-- {"cell":{"colwidth":109}} -->|Extracts section  ----------------------------------------------------------------------------------------fruits.slice()|
|`indexOf()`<!-- {"cell":{"colwidth":109}} -->|Finds index of value -----------------------------------------------------------------------------------fruits.indexOf()|
|`includes()`<!-- {"cell":{"colwidth":109}} -->|Checks if value exists  -------------------------------------------------------------------------------fruits.includes()|
|`join()`<!-- {"cell":{"colwidth":109}} -->|Converts array to string  -----------------------------------------------------------------------------fruits.join()|


Arrays vs Objects

| | | |
|-|-|-|
|Feature<!-- {"cell":{"colwidth":174}} -->|Arrays<!-- {"cell":{"colwidth":254}} -->|Objects<!-- {"cell":{"colwidth":223}} -->|
|**Use-case**<!-- {"cell":{"colwidth":174}} -->|Ordered collections<!-- {"cell":{"colwidth":254}} -->|Key-value mappings<!-- {"cell":{"colwidth":223}} -->|
|**Indexing**<!-- {"cell":{"colwidth":174}} -->|Numerical<!-- {"cell":{"colwidth":254}} -->|Key-based<!-- {"cell":{"colwidth":223}} -->|
|**Built-in Ops**<!-- {"cell":{"colwidth":174}} -->|Rich with many methods<!-- {"cell":{"colwidth":254}} -->|Limited built-in methods<!-- {"cell":{"colwidth":223}} -->|
**Example:** Use array for list of items; use object for user profile.


1. Nested Objects and Arrays

- You can have objects inside arrays and arrays inside objects.

```
const users = [
  { name: "Alice", age: 25 },
  { name: "Bob", age: 30 }
];

const company = {
  name: "TechCorp",
  employees: ["Alice", "Bob", "Charlie"]
};
```

Accessing:

```
console.log(users[1].name);         // Bob
console.log(company.employees[0]); // Alice
```


## **8.Scope and Closures Video Reference :-** [Closure and Scope](https://youtu.be/VaH09NXQZ58?si=KWcELPBxgcAOdo3N)<!-- {"collapsed":true} -->

**Theory:**

- **Scope**: Defines the accessibility of variables.

- **Closure**: A function that remembers the scope in which it was created.

Example:

```
function outer() {
  let count = 0;
  return function inner() {
    count++;
    return count;
  };
}

let counter = outer();
console.log(counter()); // 1
console.log(counter()); // 2
```

## **9.Hoisting In Javascript     Video Reference:-** [Hoisting ](https://youtu.be/Fnlnw8uY6jo?si=DZNpeclVgr4ia82o)<!-- {"collapsed":true} -->

**Theory:** Variables and function declarations are moved (hoisted) to the top of their scope before code execution.

```
Example:

-----------------------------------------------------------------------

console.log(x); // undefined
var x = 10;

foo(); // "Hello"
function foo() {
  console.log("Hello");
}
```


**Let and Const are not hoisted the same way** (they are hoisted but not initialized).


## **10.Higher Order Functions   Video Reference : -** [Higher Order Function](https://youtu.be/HkWxvB1RJq0?si=TMg6nVs-H2kuUZrU)<!-- {"collapsed":true} -->

- A **higher-order function** is a function that either takes another function as an argument or returns a function as its result.

Example 1: Passing a function

```
function greet(name) {
  return `Hello, ${name}`;
}

function processGreeting(greetingFunction, name) {
  console.log(greetingFunction(name));
}

processGreeting(greet, "John");  // Output: Hello, John
```


Example 2: Returning a function

```
function multiplier(factor) {
  return function(num) {
    return num * factor;
  };
}

const double = multiplier(2);
console.log(double(5)); // Output: 10
```


## **11.Callback Functions   Video Reference : -** [Callback Funtions](https://youtu.be/btj35dh3_U8?si=7nfYLqgxajjUkyvA)<!-- {"collapsed":true} -->

A **callback** is a function passed into another function as an argument and is executed later.

```
Example : 
----------------------------------------------------------------------

function fetchData(callback) {
  setTimeout(() => {
    callback("Data loaded");
  }, 1000);
}

fetchData(function(data) {
  console.log(data); // Output after 1 sec: Data loaded
});
```


## **12.Array Methods - forEach, map, filter, reduce  Video Reference : -** [Methods](https://youtu.be/OMoxLUxW7Wc?si=pXzctlPaegjLqyfK)<!-- {"collapsed":true} -->


```
For Each 

let nums = [1, 2, 3];
nums.forEach(n => console.log(n));

-------------------------------------------------------------------

map
let doubled = nums.map(n => n * 2);  // [2, 4, 6]

-------------------------------------------------------------------

Filter
let evens = nums.filter(n => n % 2 === 0);  // [2]

-------------------------------------------------------------------

reduce
let sum = nums.reduce((acc, curr) => acc + curr, 0);  // 6
```


## **13. Recursion – Foundation of Problem Solving  Video Refernce :-** [Recursion](https://youtu.be/DICBCBZn_L4?si=M6LeBTSdfNgO6XTe)  [Recursion - 2](https://youtu.be/51aNw5ShvmQ?si=vE8APQ-fgkioviRp)<!-- {"collapsed":true} -->

**What is Recursion?**
Recursion is a process in which a function calls itself directly or indirectly to solve a problem.

**Why use it?**

- Solves problems by breaking them down into smaller subproblems.

- Works well with divide-and-conquer strategies.

**Structure of Recursive Function:**

1. **Base Case** – When to stop recursion.

1. **Recursive Case** – The actual recursion step.


```
function countDown(n) {
  if (n === 0) {
    console.log("Done!");
    return;
  }
  console.log(n);
  countDown(n - 1); // Recursive case
}
countDown(5);
```


Common Problems:

- Factorial

- Fibonacci

- Sum of digits

- Reverse string
Recursion vs Iteration

| | | |
|-|-|-|
|Feature<!-- {"cell":{"colwidth":160}} -->|Recursion<!-- {"cell":{"colwidth":228}} -->|Iteration<!-- {"cell":{"colwidth":220}} -->|
|**Uses stack**<!-- {"cell":{"colwidth":160}} -->|Yes (Call Stack)<!-- {"cell":{"colwidth":228}} -->|No<!-- {"cell":{"colwidth":220}} -->|
|**Readability**<!-- {"cell":{"colwidth":160}} -->|Cleaner for some tasks<!-- {"cell":{"colwidth":228}} -->|Often more efficient<!-- {"cell":{"colwidth":220}} -->|
|**Performance**<!-- {"cell":{"colwidth":160}} -->|Slower if not optimized<!-- {"cell":{"colwidth":228}} -->|Faster<!-- {"cell":{"colwidth":220}} -->|

1. Reverse a String using Recursion

```
function reverse(str) {
  if (str === "") return "";
  return reverse(str.slice(1)) + str[0];
}

console.log(reverse("hello")); // "olleh"
```


1. Palindrome Check with Recursion<!-- {"offset":1} -->

```
function isPalindrome(str) {
  if (str.length <= 1) return true;
  if (str[0] !== str[str.length - 1]) return false;
  return isPalindrome(str.slice(1, -1));
}

console.log(isPalindrome("racecar")); // true
```

When to Use Recursion?

Use recursion when:

- Problem has **sub-problems** of the same structure.

- You can define a **clear base case**.

- You want clean, elegant code over performance.


Tail Recursion (Conceptual)

- Some languages support **tail call optimization**. JavaScript does **not** optimize tail-recursive calls in most engines.


## **14.Memoization Video Reference : -**  [Memoization -Complete master class](https://youtu.be/rPEMYhpmcXY?si=4GQhW3k8tZascIku)<!-- {"collapsed":true} -->

- Memoization is a technique to cache function results to avoid redundant calculations.


```
function memoize(fn) {
  let cache = {};
  return function(n) {
    if (n in cache) {
      return cache[n];
    } else {
      let result = fn(n);
      cache[n] = result;
      return result;
    }
  };
}

function square(n) {
  return n * n;
}

const memoizedSquare = memoize(square);
console.log(memoizedSquare(5));  // 25
console.log(memoizedSquare(5));  // Cached: 25
```


## **15. Time and Space Complexity Basics   Video Reference :-** [Video 1](https://youtu.be/LaexPVi1VRE?si=I4YXEeG5h95bEwwF)  [Video 2](https://youtu.be/FPu9Uld7W-E?si=-1xccXuYV7fKvZSR)  [Video 3](https://youtu.be/PwKv8fOcriM?si=6Q1v5VKSzTeuIaGx)<!-- {"collapsed":true} -->

**What is Time Complexity?**

- How the runtime of an algorithm grows as input size increases.

**Big-O Notation Examples:**

- `O(1)` – Constant time

- `O(n)` – Linear time

- `O(n^2)` – Quadratic time

```
function printFirstItem(arr) {
  console.log(arr[0]); // O(1)
}

function printAllItems(arr) {
  arr.forEach(item => console.log(item)); // O(n)
}
```

**What is Space Complexity?**

-  How much memory (RAM) an algorithm needs as input size grows.


## **16.Advanced Array Operations, Spread/Rest, and Destructuring**<!-- {"collapsed":true} -->

1. Spread Operator (`...`)

```
With Arrays     
---------------------------------------------------------------

const arr1 = [1, 2];
const arr2 = [...arr1, 3, 4];
console.log(arr2); // [1, 2, 3, 4]


With Objects
---------------------------------------------------------------

const obj1 = { name: "Alice" };
const obj2 = { ...obj1, age: 25 };
console.log(obj2); // { name: "Alice", age: 25 }
```

1. Rest Operator (`...`).<!-- {"offset":1} -->

```
function sum(...args) {
  return args.reduce((acc, val) => acc + val, 0);
}

console.log(sum(1, 2, 3)); // 6
```

1. Destructuring : Extract values from arrays or properties from objects.<!-- {"offset":2} -->

```
Array 
------------------------------------------
const [first, second] = [10, 20];
console.log(first); // 10


Object
----------------------------------------
const user = { name: "Alice", age: 25 };
const { name, age } = user;
console.log(name); // Alice


Nested Destructuring

----------------------------------------

const person = {
  name: "John",
  address: {
    city: "NY",
    zip: 12345
  }
};

const {
  address: { city }
} = person;
console.log(city); // NY

```

1. Chaining Array Methods<!-- {"offset":3} -->

```
const result = [1, 2, 3, 4, 5]
  .filter(n => n % 2 === 0)
  .map(n => n * 10);
console.log(result); // [20, 40]
```


## 1**7.Understanding Call Stack and Execution Context  Video Reference : -** [Call Stack ](https://youtu.be/fFd8OhrHfIM?si=ssuskO0IB8LbxtGK)<!-- {"collapsed":true} -->

### What is the Call Stack?

The **call stack** is a data structure that keeps track of function calls in JavaScript. It's a stack of frames, where each frame represents a function call. When a function is called, a new frame is added to the stack, and when the function finishes, the frame is popped off the stack.

###  Execution Context

Each time a function is called, a new **execution context** is created. The execution context is an abstract concept in JavaScript that contains:

- **Variable Environment**: Holds the variables and functions defined in the context.

- **Scope Chain**: Links to parent scopes.

- **`this` Keyword**: Refers to the object to which the function belongs.


### Call Stack Example

```
function a() {
  console.log('In function A');
  b();  // Function b is called
}

function b() {
  console.log('In function B');
  c();  // Function c is called
}

function c() {
  console.log('In function C');
}

a();
```

**Call Stack Trace:**

1. `a()` is called, added to the call stack.

1. Inside `a()`, `b()` is called, so `b()` is added to the call stack.

1. Inside `b()`, `c()` is called, so `c()` is added to the call stack.

1. `c()` completes, removed from the stack.

1. `b()` completes, removed from the stack.

1. `a()` completes, removed from the stack.

### Execution Context Stack

When `a()` is called:

- **Execution context for `a()`** is created.

- When `b()` is called inside `a()`, a new **execution context for `b()`** is created.

- Inside `b()`, when `c()` is called, a new **execution context for `c()`** is created.

After each function finishes, its execution context is popped from the stack.


### Understanding Execution Context

- **Global Execution Context**: Created when the script starts. Contains global objects and functions.

- **Function Execution Context**: Created when a function is called, and each function has its own context.


### Stack Overflow

A **stack overflow** happens when the call stack exceeds its limit due to excessive recursion or too many function calls. This causes the JavaScript engine to crash.

Example of stack overflow:

```
function recursive() {
  recursive();  // Calls itself indefinitely
}

recursive();  // Will cause stack overflow
```


### The Role of `this` in Execution Context

- In a **global execution context**, `this` refers to the global object (`window` in browsers).

- In a **function execution context**, `this` refers to the object that is calling the function, or `undefined` in strict mode.

### Closure and Call Stack

Closures can be affected by the call stack. A closure is created when a function retains access to its lexical environment, even after the outer function has finished execution.

Example:


```
function outer() {
  let x = 10;
  function inner() {
    console.log(x);
  }
  return inner;
}

let closure = outer();
closure();  // 10
```

Even though the `outer` function has finished executing, the closure still retains access to the variable `x`.


### Call Stack and Performance

The call stack size and function execution can impact performance. Deep recursion or a large number of function calls may cause stack overflow errors or slow down the program.


### Visualizing Call Stack with Debugging

Using browser developer tools, you can observe the call stack in real-time by setting breakpoints or stepping through the code. This is helpful for debugging recursive functions or tracking the execution flow of your program.


## **18.Understanding the Event Loop  Video Reference :-** [Event Loop](https://youtu.be/8zKuNo4ay8E?si=iRnUx56R1Kn2v3C7) <!-- {"collapsed":true} -->


### **What is the Event Loop?**

The **Event Loop** is a fundamental concept in JavaScript that allows asynchronous operations, such as setTimeout, HTTP requests, and promises, to execute without blocking the main thread. JavaScript operates on a single thread, and the event loop ensures that long-running tasks do not block the execution of other code.

### **Event Loop Mechanism**

JavaScript has a **single-threaded execution model**, which means only one task is executed at a time. However, the event loop allows multiple tasks to be processed concurrently, without blocking the main execution.

The event loop works with the following components:

- **Call Stack**: Where the execution of code happens.

- **Message Queue**: Holds the tasks that are waiting to be executed (i.e., events or callback functions).

- **Web APIs**: Browser-provided APIs that handle asynchronous tasks (e.g., `setTimeout`, HTTP requests).

- **Event Loop**: A loop that checks the call stack and message queue, ensuring that tasks in the message queue are executed when the call stack is empty.

### Phases of the Event Loop

1. **Execute Synchronous Code**: Code in the call stack is executed synchronously.

1. **Check Message Queue**: After synchronous code execution, the event loop checks the message queue for tasks to execute.

1. **Execute Asynchronous Code**: Asynchronous tasks (like timers, I/O operations) are moved from the message queue to the call stack to execute once the call stack is empty.

```
Event Loop Example:

console.log('Start');  // Synchronous task

setTimeout(() => {
  console.log('Inside setTimeout');  // Asynchronous task
}, 1000);

console.log('End');  // Synchronous task
```

**
Execution Flow:**

1. The synchronous code `console.log('Start')` is executed first.

1. The `setTimeout()` function is placed in the Web APIs environment, and the callback is moved to the message queue after 1 second.

1. The synchronous code `console.log('End')` is executed next.

1. After the call stack is empty, the event loop picks the callback from the message queue and moves it to the call stack.

1. Finally, the asynchronous callback `console.log('Inside setTimeout')` is executed.

**Output:**


```
Start
End
Inside setTimeout
```


### **Microtasks vs Macrotasks**

The event loop processes tasks in two categories: **microtasks** and **macrotasks**.

- **Macrotasks**: These include tasks like I/O, timers, setTimeout, etc.

- **Microtasks**: These include promises, process.nextTick, etc.

The event loop gives priority to **microtasks** before executing **macrotasks**. After each macrotask is completed, the event loop checks the microtask queue for pending tasks.


```
Microtask Example:
-------------------------------------------------------
console.log('Start');

Promise.resolve().then(() => {
  console.log('Inside Promise');
});

console.log('End');
```


**Execution Flow:**

1. `console.log('Start')` is executed first.

1. The promise is placed in the microtask queue.

1. `console.log('End')` is executed next.

1. The event loop checks the microtask queue and executes the `console.log('Inside Promise')`.

**Output:**

```
Start
End
Inside Promise
```

### Event Loop and Async Operations

The event loop enables JavaScript to handle asynchronous operations efficiently. It allows I/O-bound tasks, such as network requests, to be executed without blocking the execution of other tasks.



### Understanding Asynchronous JavaScript



In JavaScript, most operations, such as DOM manipulation, HTTP requests, and timers, are asynchronous. The event loop and its associated components (like the message queue and Web APIs) enable the handling of these asynchronous operations in a non-blocking manner.



### Event Loop and Performance

Although the event loop is powerful, excessive use of asynchronous tasks (especially large I/O operations) can degrade performance. Understanding the event loop helps in writing efficient code that minimizes blocking of the main thread and improves application responsiveness.

### Troubleshooting Event Loop Issues


Common event loop issues include:

- **Callback Hell**: When asynchronous functions are nested inside each other, it can make the code difficult to read and maintain. This is also known as "callback hell." Promises and async/await can help mitigate this.

- **Blocking the Event Loop**: Heavy synchronous tasks or long-running loops can block the event loop, leading to poor application performance.


## **19. OOPS (Object Oriented Programming)**<!-- {"collapsed":true} -->


### 🧠 OOPS in JavaScript — Simple Notes + Internal Explanation

### 🔹 What is OOPS?

OOPS stands for **Object-Oriented Programming System**.
It’s a way to organize code using objects.
**Objects** = Data + Functions bundled together.

Example:

```javascript
"hello".toLowerCase(); // "hello" is a string object
```

### ✅ Why use OOPS?

- Code reuse (write once, use many times)

- Clean structure

- Easy to debug and maintain

- Works like real-life objects

### 🔑 Key Terms & Internal Working

### 1. **Constructor Function**

✅ Used to create objects with the same properties and methods.

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
  this.sayHello = function() {
    console.log("Hi, I'm " + this.name);
  };
}

const p1 = new Person("Alice", 25);
p1.sayHello(); // Hi, I'm Alice
```

🧠 **How it works internally:**

- `new` creates a blank object `{}`.

- Sets `this` to that object.

- Adds properties/methods to it.

- Returns the object.

### 2. **Prototypes**

✅ A way to share functions across all objects created by a constructor.

```javascript
Person.prototype.greet = function() {
  console.log("Hello from " + this.name);
};

p1.greet(); // Hello from Alice
```

🧠 **Internal working:**

- JavaScript links objects using `[[Prototype]]`.

- When `p1.greet()` is called, JS looks:

- In `p1` object.

- If not found, it goes to `Person.prototype`.

This is called **Prototype Chain**.

### 3. **Classes (ES6)**

✅ A cleaner way to write constructor functions and prototypes.

```javascript
class Car {
  constructor(brand) {
    this.brand = brand;
  }

  drive() {
    console.log(`${this.brand} is driving`);
  }
}

const c1 = new Car("BMW");
c1.drive(); // BMW is driving
```

🧠 **Internally:**

- Behind the scenes, `class` still uses `prototype`.

- Methods in class go to `Car.prototype`.

### 4. **Instances**

✅ Objects created from a constructor or class.

```javascript
const c2 = new Car("Toyota"); // Instance of Car
```

### 🔒 4 Pillars of OOPS + Internal Explanation

### 1. **Abstraction**

✅ Hides internal details, shows only what’s needed.

```javascript
class Phone {
  constructor(model) {
    this.model = model;
  }

  call() {
    console.log("Calling...");
  }
}

const myPhone = new Phone("iPhone");
myPhone.call(); // Only uses public method
```

🧠 Internally:

- You don’t see how `call()` works — just use it.

### 2. **Encapsulation**

✅ Keep data safe inside objects (like a capsule).

```javascript
class BankAccount {
  #balance = 0; // private

  deposit(amount) {
    this.#balance += amount;
  }

  getBalance() {
    return this.#balance;
  }
}
```

🧠 Internally:

- `#balance` can’t be accessed outside.

- Only class methods can modify it.

### 3. **Inheritance**

✅ One class inherits (gets) features from another.

```javascript
class Animal {
  speak() {
    console.log("Animal speaks");
  }
}

class Dog extends Animal {
  bark() {
    console.log("Dog barks");
  }
}

const d1 = new Dog();
d1.speak(); // Animal speaks
d1.bark();  // Dog barks
```

🧠 Internally:

- `Dog.prototype.__proto__` points to `Animal.prototype`.

- JS checks the whole prototype chain when method is called.

### 4. **Polymorphism**

✅ Same method name, different behavior.

```javascript
class Animal {
  sound() {
    console.log("Some sound");
  }
}

class Cat extends Animal {
  sound() {
    console.log("Meow");
  }
}

const kitty = new Cat();
kitty.sound(); // Meow
```

🧠 Internally:

- Method in `Cat` **overrides** method in `Animal`.

- JS uses the nearest match in prototype chain.

### 🧠 Final Internal Summary:

When you write:

```javascript
const p = new Person("Bob", 30);
```

- JS does:

- `let obj = {};`

- `obj.__proto__ = Person.prototype;`

- `Person.call(obj, "Bob", 30);`

- Returns `obj`



---

## **20.PROTOTYPE**<!-- {"collapsed":true} -->

Here’s a **simple and complete explanation of Prototypes in JavaScript**, including **how it works internally** — in the same beginner-friendly style as before:

### 🧠 JavaScript Prototypes — Simple Notes + Internal Working

### 🔹 What is a Prototype?

- In JavaScript, **every object has a hidden internal property** called `[[Prototype]]`.

- It acts like a **blueprint** from which the object can **inherit properties and methods**.

- You can access it using `.prototype` (for functions) or `__proto__` (for objects).

### 📦 Real Life Analogy:

> Imagine objects as students and the prototype as a shared “classroom” whiteboard.
> All students can read from the whiteboard — but none of them own it individually.

### ✅ Example: Without Prototype

```javascript
function Person(name) {
  this.name = name;
  this.sayHello = function() {
    console.log("Hi, I'm " + this.name);
  };
}

const p1 = new Person("Alice");
const p2 = new Person("Bob");

p1.sayHello(); // Hi, I'm Alice
p2.sayHello(); // Hi, I'm Bob
```

👎 Problem: Every object has its own copy of `sayHello()` — uses more memory.

### ✅ Example: With Prototype (Better)

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.sayHello = function() {
  console.log("Hi, I'm " + this.name);
};

const p1 = new Person("Alice");
const p2 = new Person("Bob");

p1.sayHello(); // Hi, I'm Alice
p2.sayHello(); // Hi, I'm Bob
```

👍 Now, `sayHello` is stored **once** in the prototype, and all objects share it.

### 🧠 How it Works Internally

When you call `p1.sayHello()`:

1. JS looks in `p1` object itself.

1. If not found, it looks in `p1.__proto__`.

1. `p1.__proto__` === `Person.prototype`

1. It finds `sayHello` in prototype and runs it.

This search chain is called the **Prototype Chain**

### 🔍 Visual of Prototype Chain

```javascript
p1 --> { name: "Alice" }
     ⬇️
p1.__proto__ --> Person.prototype
               ⬇️
Person.prototype.__proto__ --> Object.prototype
                             ⬇️
null (end of chain)
```

### 🧪 How to Check It

```javascript
console.log(p1.__proto__ === Person.prototype); // true
console.log(Person.prototype.constructor === Person); // true
```

### 🛠 Built-in Prototypes

Even built-in types (Array, String, etc.) use prototypes!

```javascript
const arr = [1, 2, 3];
arr.push(4); // push() is from Array.prototype

console.log(arr.__proto__ === Array.prototype); // true
```

### 🧠 Object vs. Function Prototypes

- **Functions** have a `.prototype` property (used to create new objects).

- **Objects** have `__proto__` (used to inherit behavior).

Example:

```javascript
function Animal() {}
const dog = new Animal();

console.log(dog.__proto__ === Animal.prototype); // true
console.log(Animal.prototype.__proto__ === Object.prototype); // true
```

### 🔁 Inheritance via Prototypes

```javascript
function Animal() {}
Animal.prototype.eat = function() {
  console.log("eating...");
};

function Dog() {}
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.bark = function() {
  console.log("barking...");
};

const d1 = new Dog();
d1.eat();  // eating... (from Animal)
d1.bark(); // barking... (from Dog)
```

### ⚠️ Important Tips

- Don’t overuse `__proto__` — use `Object.getPrototypeOf()` instead (safer).

- Only use `.prototype` with functions meant to create objects (constructors).

- Avoid modifying `Object.prototype` — it affects all objects!

### ✅ Summary

| | |
|-|-|
|Term|Meaning|
|`.prototype`|Property on constructor functions|
|`__proto__`|Property on objects (link to prototype)|
|`Prototype Chain`|Lookup path when accessing properties|
|Inheritance|Objects get methods from their prototype|
