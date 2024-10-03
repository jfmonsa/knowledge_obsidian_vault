#index
+ interpreted and compiled (just-in-time JIT)
+ ==First-class Functions==, This means:
	+ Functions are treated like any other variable
	+ we can pass it as arguments, we can return them
+ Run time environments (Javascript engines): ==Browser and Node.js==
+ Prototype-based, multi-paradigm (OOP, imperative, declarative e.g functional programming)
+ Single-threaded
+ Dynamic Language
+ Weak Typed

# 1. Core Language
## 1. Hello World
```JavaScript
console.log('Hello, World!');
```

## 2. Strict
+ we can se `'use strict';` at the start of our script or at  the top of a block o code, this means that the js engine will ignore the old javascript and use only the new
+ However if we use Classes or modules this automatically behaves if we are using `'use strict';`
## 3. Vars
+ `let`,`const`,`var`, `var`has no block scope
## 4. Data Types
### Primitives
+ String
+ Number
+ BigInt, we have to append `n` to the end of the number
	+ Was created to avoid errors
	```JavaScript
	console.log(9007199254740991 + 1); // 9007199254740992
	console.log(9007199254740991 + 2); // 9007199254740992
	```
	+ `const bigInt = 1234567890123456789012345678901234567890n;`
+ Boolean
+ null
+ undefined -> value is not assigned
+ Symbol -> Unique identifier
### Non-primitive
+ Objects
	+ use `typeof(x)` o `typeof`operator

## 5. Type Conversion
+ Using type constructors `Number()`, `String()`
+ Implicit conversion, applying number operators e.g
```JavaScript
let apples = "2";
let oranges = "3";

// both values converted to numbers before the binary plus
alert( +apples + +oranges ); // 5
```
## 6. Operators
+ **Precedence**: Unary Operators > Binary Ones. e.g: +a (unary) > (binary) a+b
+ **Assignment**: returns a value
```Javascript
let a = 1;
let b = 2;
let c = 3 - (a = b + 1);

alert( a ); // 3
alert( c ); // 0
``` 
+ Hence, we have chaining assignments
```javascript
let a, b, c;

a = b = c = 2 + 2;

alert( a ); // 4
alert( b ); // 4
alert( c ); // 4
```
+ Bitwise ops: `&,|,~,^,<<,>>,>>>`
+ **Comma** -> Evaluates several expressions dividing them wit a comma `,`. Each of them is evaluated, only the result of the last is returned
	+ **Caution** -> comma has very low precedence, parentheses matters
	+ Without them: `a = 1 + 2, 3 + 4` evaluates `+` first, summing the numbers into `a = 3, 7`, then the assignment operator `=` assigns `a = 3`, and the rest is ignored. It’s like `(a = 1 + 2), 3 + 4`.
	+ Sometimes its useful to put several actions in one line
```Javascript
// three operations in one line
for (a = 1, b = 3, c = a * b; a < 10; a++) {
 ...
}
```
## 7. Comparisons
+ Strict equality to avoid unexpected behavior
+ Don’t use comparisons >= > < <= with a variable which may be null/undefined, unless you’re really sure of what you’re doing. If a variable can have these values, check for them separately.
## 8. Conditional Branching
+ `if`,`else`,`else if`,`swith-case`,`&&`
+ **Ternary operator**: `let result = condition ? value1 : value2;`
+ **Multiple ternaries**:
```javascript
let message = (age < 3) ? 'Hi, baby!' :
  (age < 18) ? 'Hello!' :
  (age < 100) ? 'Greetings!' :
  'What an unusual age!';
```
+ **Logical Operators**: Short circuit evaluation
	+ `||` returns the first truthy value or the last value if the exp is false
	+ `&&` returns the first falsy value or the last value if the exp is true
	+ **Double not** sometimes is used to converts a value to Boolean
	+ `!`> `&&`>`||` precendence
## 9. Nullish Coalescing Operator "??"
+ `a ?? b`
+ Returns the first value if is neither `null` nor `undefined`
```javascript
let firstName = null;
let lastName = null;
let nickName = "Supercoder";

// shows the first defined value:
alert(firstName ?? lastName ?? nickName ?? "Anonymous"); // Supercoder
```
+ important difference with logical OR, OR doesn't distinguish between `false`,`0`,`""` and `null / undefined`
```javascript
let height = 0;
alert(height || 100); // 100
alert(height ?? 100); // 0
```
## 10. Loops
+ while
+ for
+ do-while
+ keywords: break, continue
+ breaking multiple-nested loops, label a loop
## 11. Functions
### a. Function Declarations
```javascript
function sayHi() {
  alert( "Hello" );
}
```
### b. Function Expressions
It allows us to create a new function in the middle of any expression.
```javascript
let sayHi = function() {
  alert( "Hello" );
};
```
### c. Call Back Functions
The idea is that we pass a function as an argument and expect it to be “called back”
### Function Declarations vs Function Expressions
+ A Function Expression is created when the execution reaches it and is usable only from that moment.
+ A Function Declaration can be called earlier than it is defined.
### d. Arrow Functions
+ `let func = (arg1, arg2, ..., argN) => expression;`


# 2. Objects
## 12. Objects
+ keyed collections of various data and more complex entities.
+ We can implement a hashmap using object literals :D: in, delete
+ empty object
```javascript
let user = new Object(); // "object constructor" syntax
let user = {};  // "object literal" syntax
```
+ Delete property `delete user.age;`
### Multi-word properties
+ We can use multi-word property names (must be quoted) `"likes birds": true`
+ Access multi-word property names, use square bracket notation
```javascript
let user = {};
// set
user["likes birds"] = true;
// get
alert(user["likes birds"]); // true
// delete
delete user["likes birds"];
```
### Computed properties
```javascript
let fruit = prompt("Which fruit to buy?", "apple");
let bag = {
  [fruit]: 5, // the name of the property is taken from the variable fruit
};
alert( bag.apple ); // 5 if fruit="apple"
```

Works the same as:
```javascript
let fruit = prompt("Which fruit to buy?", "apple");
let bag = {};

// take property name from the fruit variable
bag[fruit] = 5;
```

We can use more complex expressions inside square brackets:
```javascript
let fruit = 'apple';
let bag = {
  [fruit + 'Computers']: 5 // bag.appleComputers = 5
};
```

### Property value shorthand
Instead of name:name we can just write name, like this:
```javascript
function makeUser(name, age) {
  return {
    name, // same as name: name
    age,  // same as age: age
    // ...
  };
}
```

### Test Existence
`"key" in object`

### For in Loop
+ To walk over all keys of an object
```javascript
for (key in object) {
  // executes the body for each key among object properties
}

for (let key in user) {
  // keys
  alert( key );  // name, age, isAdmin
  // values for the keys
  alert( user[key] ); // John, 30, true
}
```
## 13. Object References and copying
### Reference vs Primitives 
+ objects versus primitives is that objects are stored and copied “by reference”
+ primitive values: strings, numbers, booleans, etc – are always copied “as a whole value”.

> [!WARNING]
> Objects are not like that.

> A variable assigned to an object stores not the object itself, but its “address in memory” – in other words “a reference” to it.

+ When an object variable is copied, the reference is copied, but the object itself is not duplicated.
```javascript
let user = { name: "John" };
let admin = user; // copy the reference
```
+ Now we have two variables, each storing a reference to the same object
+ If we make changes to the object properties in one of its variables, we are modifying the same object
### Comparison by reference
+ Two objects are equal only if they are the same object.
```javascript
let a = {};
let b = a; // copy the reference

alert( a == b ); // true, both variables reference the same object
alert( a === b ); // true
```

```javascript
let a = {};
let b = {}; // two independent objects

alert( a == b ); // false
```

> [!IMPORTANT]
> An important side effect of storing objects as references is that an object declared as const can be modified.

### Cloning and Merging objects
+ We can clone an object by iterating
+ Or we can use `Object.assign(dest, ...sources)`
	+ dest is a target object
	+ Further arguments is a list of source objects.
	+ If the copied property name already exists, it gets overwritten
+ For nested objects use **structured cloning** to clone them 
## 14. Garbage Collection
+ The main concept of memory management in JavaScript is reachability.
## 15. Object methods, "this"
+ Since objects represents real world entities, we can use its properties to define behavior (functions)
+ Functions that are stored in object properties are called “methods”.
```javascript
let user = {
  name: "John",
  age: 30
};

user.sayHi = function() {
  alert("Hello!");
};

user.sayHi(); // Hello!
```
### Method Shorthand
```javascript
// these objects do the same

user = {
  sayHi: function() {
    alert("Hello");
  }
};

// method shorthand looks better, right?
user = {
  sayHi() { // same as "sayHi: function(){...}"
    alert("Hello");
  }
};
```
### This
+ Open recursion in OOP
+ A method access a method or property of itself
+ **Unbound this**: In JavaScript, `this` keyword this behaves unlike most other programming languages. It can be used in any function, even if it’s not a method of an object.

```javascript
let user = { name: "John" };
let admin = { name: "Admin" };

function sayHi() {
  alert( this.name );
}

// use the same function in two objects
user.f = sayHi;
admin.f = sayHi;

// these calls have different this
// "this" inside the function is the object "before the dot"
user.f(); // John  (this == user)
admin.f(); // Admin  (this == admin)

admin['f'](); // Admin (dot or square brackets access the method – doesn't matter)
```

> [!DANGER]
> Calling without an object: this == undefined

+ If you come from another programming language, then you are probably used to the idea of a "bound this", where methods defined in an object always have this referencing that object.
+ In JavaScript this is “free”, its value is evaluated at call-time and does not depend on where the method was declared, but rather on what object is “before the dot”
+ The concept of run-time evaluated `this` has both pluses and minuses. On the one hand, a function can be reused for different objects. On the other hand, the greater flexibility creates more possibilities for mistakes.

> [!WARNING]
> Arrow Functions don't have this

An use case of `this` is allow method chaining
```javascript
let ladder = {
  step: 0,
  up() {
    this.step++;
    return this;
  },
  down() {
    this.step--;
    return this;
  },
  showStep() {
    alert( this.step );
    return this;
  }
};

ladder.up().up().down().showStep().down().showStep(); // shows 1 then 0
```
## 16. Constructor, operator "new"
+ Object literals allow us to create objects, but sometimes we need to create similar objects
+ That can be done using constructor functions, to implement reusable object creation code.
### Constructor functions
+ Technically are regular functions
conventions:
+ They're name with capital letter first
+ They should be executed only with `"new"` operator

```javascript
function User(name) {
  this.name = name;
  this.isAdmin = false;
}

let user = new User("Jack");

alert(user.name); // Jack
alert(user.isAdmin); // false
```

When a function is executed with `new`, it does the following steps:

1. A new empty object is created and assigned to `this`.
2. The function body executes. Usually it modifies `this`, adds new properties to it.
3. The value of `this` is returned.

> [!DANGER]
> We cannot use arrow functions, since they don´t have `this`

> [!NOTE]
> We there is a function definition with: `new function() { … }` then This constructor can’t be called again, because it is not saved anywhere, just created and called. So this trick aims to encapsulate the code that constructs the single object, without future reuse.
## 17. Optional Chaining "?."
+ safe way to access nested object properties
+ stops the evaluation if the value before ?. is undefined or null and returns undefined.
+ Other variants `?.()` for methods, `?.[]` if we’d like to use brackets [] to access properties instead of dot 

```javascript
delete user?.name; // delete user.name if user exists
```

> [!WARNING]
> We should use ?. only where it’s ok that something doesn’t exist.
## 18. Symbol
+ Only two primitive types can be object property keys: string, symbol
+ Otherwise if someone uses another type it will be converted to string
+ Symbol represents a unique identifier

> Symbols are guaranteed to be unique. Even if we create many symbols with exactly the same description

### Hidden properties
```javascript
let id = Symbol("id");

let user = {
  name: "John",
  [id]: 123 // not "id": 123
};
```
+ Also ==Symbols are skipped in `for .. in`== only direct access works
+ But `Object.assing` copies both string
### Global Symbols
+ We can have the same symbol for the same description with `Symbol.for()`, like Ruby Symbols
+ Symbol.keyFor(sym) given a symbol, it return its key (description)
## 19. Object to primitive conversion
+ no conversion to boolean. All objects are true
+ only numeric and string conversion
When it ocurrs?
+ The numeric conversion happens when we subtract objects or apply mathematical functions. for instance, Date objs can be subtracted date1 - date2
+ For string conversion usually happens wen `alert(obj)`
**We can implement this kinds of conversions by ourselves, using special object methods**
To do the conversion, JavaScript tries to find and call three object methods:
1. Call `obj[Symbol.toPrimitive](hint)` – the method with the symbolic key Symbol.toPrimitive (system symbol), if such method exists,
2.  if hint is "string" -> try calling obj.toString() or obj.valueOf(), whatever exists.
3. If hint is "number" or "default" -> try calling obj.valueOf() or obj.toString(), whatever exists.
# Asynchronous JavaScript
+ Since js is single-threaded we need Asynchronous JavaScript to manage functions or code that takes long time in order to don't block the thread
## Callback hell or callback piramid
![[Pasted image 20240815111623.png]]
## Promises
+ Foundation of asynchronous programming in modern JavaScript
+ forma en la que javascript gestiona el asincronismo
+ Is an object returned by an asynchronous function, which represents the current state of the operation
+ promise object provides methods to handle the eventual success or failure of the operation.
+ ej: `fetch` return a promise
+ Alternativa para solucionar el callback hell

## .then() y .catch()
+ Forma de gestionar las promesas
+ Después de una función que retorna una promesa
+ Una vez que la promesa se resuelva (de forma exitosa) se va a ejecutar lo que esta en el `.then()`
+ Dentro del then() pasamos un callback (generalmente arrow function) para que se ejecute cuando la promesa se resuelva
	+ Si la función que esta retornando la promesa retorna datos, el callback tendrá un parámetro
## Chaining promises
To avoid "called back hell" We should rewrite it as:
```javascript
fetchPromise
  .then((response) => response.json())
  .then((data) => {
    console.log(data[0].name);
  });
```

> Instead of calling the second then() inside the handler for the first then(), we can return the promise returned by json(), and call the second then() on that return value. This is called promise chaining and means we can avoid ever-increasing levels of indentation when we need to make consecutive asynchronous function calls.

## Handling Errors `.catch()`
+ To support error handling, `Promise` objects provide a [`catch()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/catch) method
+ add catch() to the end of a promise chain
## Combining multiple promises
+ Different from promise chain which is what you need when your operation consists of several asynchronous functions, and you need each one to complete before starting the next one

> there are other ways you might need to combine asynchronous function calls, and the Promise API provides some helpers for them.

#### `Promise.all()`
+ The promise returned by Promise.all() is:
	+ **Fulfilled** when and if _all_ the promises in the array are fulfilled. In this case, the `then()` handler is called with an array of all the responses, in the same order that the promises were passed into `all()`
	+ **rejected** when and if _any_ of the promises in the array are rejected. In this case, the `catch()` handler is called with the error thrown by the promise that rejected.
	
```javascript
const fetchPromise1 = fetch(
  "https://mdn.github.io/learning-area/javascript/apis/fetching-data/can-store/products.json",
);
const fetchPromise2 = fetch(
  "https://mdn.github.io/learning-area/javascript/apis/fetching-data/can-store/not-found",
);
const fetchPromise3 = fetch(
  "https://mdn.github.io/learning-area/javascript/oojs/json/superheroes.json",
);

Promise.all([fetchPromise1, fetchPromise2, fetchPromise3])
  .then((responses) => {
    for (const response of responses) {
      console.log(`${response.url}: ${response.status}`);
    }
  })
  .catch((error) => {
    console.error(`Failed to fetch: ${error}`);
  });

```

#### `Promise.any()`
+ is like Promise.all(), except that it is fulfilled as soon as any of the array of promises is fulfilled, or rejected if all of them are rejected:

##  `async` and `await`
+ Adding async at the start of a function makes it an async function
+ Inside an async function, you can use the await keyword before a call to a function that returns a promise.
+ We can even use a try...catch block for error handling, exactly as we would if the code were synchronous.
+ note that you can only use await inside an async function, unless your code is in a JavaScript module.
+ just like a promise chain, await forces asynchronous operations to be completed in series. This is necessary if the result of the next operation depends on the result of the last one
	+ but if that's not the case then something like Promise.all() will be more performant.
### Resources
+ https://www.youtube.com/watch?v=RvYYCGs45L4 - JavaScript Promise in 100 Seconds (Fireship)
# Event Loop
+ El event loop es el que se encarga de implementar las operaciones asíncronas o el non-blocking. El event loop corre en el único hilo que existe en Node y como mencionamos anteriormente, al bloquear el único hilo de node, estamos bloqueando el event loop.
+ **Call Stack**: Cada vez que una función va a ser ejecutada pasa por el call stack.
+ **Callback Queue**: Aquí se agregan los callback o funciones que se ejecutan una vez las operaciones asíncronas hayan terminado

> El event loop es el que se encarga de revisar que el call stack este vacío para añadir lo que está dentro del callback queue y ejecutarlo.
# Browser
## Console
+ If we use `Shift + Enter`we can write multi-line code in the console
## alert, prompt, confirm

# Automated Testing
+ When testing a code by manual re-runs, it’s easy to miss something.
+ For instance, we’re creating a function f. Wrote some code, testing: f(1) works, but f(2) doesn’t work. We fix the code and now f(2) works. Looks complete? But we forgot to re-test f(1). That may lead to an error.
+ When we develop something, we keep a lot of possible use cases in mind
## Behavior Driven Development
+ BDD is three things in one: tests AND documentation AND examples.

## Development Flow
Using Mocha Library (Javascript)

```javascript
describe("pow", function() {
  it("raises to n-th power", function() {
    assert.equal(pow(2, 3), 8);
  });
});
```

1. An initial spec is written, with tests for the most basic functionality. (the example right above)
2. An initial implementation is created.
3. To check whether it works, we run the testing framework Mocha (more details soon) that runs the spec. While the functionality is not complete, errors are displayed. We make corrections until everything works.
4. We add more use cases to the spec, probably not yet supported by the implementations. Tests start to fail.
5. Go to 3, update the implementation till tests give no errors.
---
-> more info: https://javascript.info/testing-mocha