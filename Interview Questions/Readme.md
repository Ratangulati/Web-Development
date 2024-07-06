# Interview Questions

### What changes came in the new in the new ES6 from ES5?

1. Variable Declarations

In `ES5`, variables are declared using var, which has function scope. This can lead to issues with variable hoisting and unintended behavior.

```html
// ES5
var name = "John";
console.log(name); // Output: John

function greet() {
  var message = "Hello, " + name;
  return message;
}
console.log(greet()); // Output: Hello, John

// Issue with var and hoisting
function example() {
  if (true) {
    var test = true;
  }
  console.log(test); // Output: true
}
example();
```

In `ES6`, let and const were introduced for block-scoped variable declarations. let is used for variables that can be reassigned, while const is for constants that cannot be reassigned.

```html
// ES6
let age = 25;
const birthYear = 1999;

console.log(age); // Output: 25
console.log(birthYear); // Output: 1999
```

2. Arrow Functions

Arrow functions, introduced in `ES6`, provide a shorter syntax for writing functions. They also lexically bind the this value, which is particularly useful for maintaining the correct context inside callbacks and event handlers.

```html
// ES5
var sum = function(a, b) {
  return a + b;
};

console.log(sum(5, 3)); // Output: 8

var obj = {
  value: 10,
  increment: function() {
    setTimeout(function() {
      this.value++;
      console.log(this.value); // Output: 11
    }, 1000);
  }
};
obj.increment();

// ES6
const sum = (a, b) => a + b;

console.log(sum(5, 3)); // Output: 8

const obj = {
  value: 10,
  increment() {
    setTimeout(() => {
      this.value++;
      console.log(this.value); // Output: 11
    }, 1000);
  }
};
obj.increment();
```

3. Template Literals

Template literals, introduced in `ES6`, provide a more concise syntax for working with strings. They use backticks (`) instead of quotes, and variables are inserted using ${}.

```html
// ES5
var name = "John";
var greeting = "Hello, " + name + "!";

console.log(greeting); // Output: Hello, John!

var multiline = "This is line 1.\nThis is line 2.";

console.log(multiline); 
// Output: 
// This is line 1.
// This is line 2.

// ES6
const name = "John";
const greeting = `Hello, ${name}!`;

console.log(greeting); // Output: Hello, John!

const multiline = `This is line 1.
This is line 2.`;

console.log(multiline); 
// Output: 
// This is line 1.
// This is line 2.
```

4. Default Parameters

In `ES5` Default parameter values are set using logical OR. Default parameters in `ES6` allow function parameters to have default values if no argument is provided or if undefined is passed.

```html
// ES5
function greet(name) {
  name = name || "Guest";
  return "Hello, " + name;
}

console.log(greet()); // Output: Hello, Guest
console.log(greet("John")); // Output: Hello, John

// ES6
const greet = (name = "Guest") => `Hello, ${name}`;

console.log(greet()); // Output: Hello, Guest
console.log(greet("John")); // Output: Hello, John
```

5. Destructuring Assignment

Destructuring assignment in `ES6` allows for easier extraction of values from arrays and objects.

```html
// ES5
var person = { name: "John", age: 25 };
var name = person.name;
var age = person.age;

console.log(name); // Output: John
console.log(age); // Output: 25

var numbers = [1, 2, 3];
var first = numbers[0];
var second = numbers[1];

console.log(first); // Output: 1
console.log(second); // Output: 2

// ES6
const person = { name: "John", age: 25 };
const { name, age } = person;

console.log(name); // Output: John
console.log(age); // Output: 25

const numbers = [1, 2, 3];
const [first, second] = numbers;

console.log(first); // Output: 1
console.log(second); // Output: 2
```

6. Enhanced Object Literals

Enhanced object literals in `ES6` provide shorthand syntax for defining properties and methods in objects.

```html
// ES5
var name = "John";
var age = 25;

var person = {
  name: name,
  age: age,
  greet: function() {
    return "Hello, " + this.name;
  }
};

console.log(person.greet()); // Output: Hello, John

// ES6
const name = "John";
const age = 25;

const person = {
  name,
  age,
  greet() {
    return `Hello, ${this.name}`;
  }
};

console.log(person.greet()); // Output: Hello, John
```

7. Classes

Classes in `ES6` provide a simple and concise way to define object classes in JavaScript. `ES6` introduced the class syntax, which provides a clearer and more concise way to create objects and handle inheritance.

```html
// ES5
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.greet = function() {
  return "Hello, " + this.name;
};

var john = new Person("John", 25);
console.log(john.greet()); // Output: Hello, John


// ES6
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    return `Hello, ${this.name}`;
  }
}

const john = new Person("John", 25);
console.log(john.greet()); // Output: Hello, John
```

8. Modules

`ES6` introduced native modules, allowing for modularization using the import and export keywords. In `ES5` Modules are implemented using libraries like RequireJS or by using the module pattern.

```html
// module.js
var Module = (function() {
  var privateVar = "I am private";

  return {
    publicMethod: function() {
      return privateVar;
    }
  };
})();

// main.js
console.log(Module.publicMethod()); // Output: I am private

// module.js
export const greeting = "Hello, World!";

// main.js
import { greeting } from './module.js';
console.log(greeting); // Output: Hello, World!
```

