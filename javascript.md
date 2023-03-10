# Javascript

## Javascript - ES7
* Created in 1995 
* Client Side (CSJS) - Front End - Browser (HTML + CSS = Web Page) / Native on the Browser / Runtime with understand the script / Network / Visual App
* Server Side (SSJS) - Back End - Server (File System, DB, API - Handle Request and Responses, work with other servers) / NodeJS / Business Logic
* DOM - Document Objects Model
* BOM - Browser Object Model - Interact with the Browser


## Ways of loading Javascript Files:
1) Add it to the header: it will stop the HTML parser, load the js file and execute it and then finishing the HTML parser.
2) Add it to the bottom to the page before closing the body: it will load most of the HTML, load the js file and execute it and then finishing the HTML parser.
3) Add the defer attribute on the script tag: it will parser all HTML then load and execute the js file.
4) Add the sync attribute on the script tag: it will parser the HTML and at the same time load and execute the js file when executing will stop the HTML parser. 

## Principles:
### 1 - Scope - There is 3 types of scopes:
* Global scope - when a variable or a function is accessible for the whole application;
* Function scope - when a variable or a function leave an is accessible only in functions;
* Block scope - when a variable leaver only in a block of code (loops, conditions, try Catches, ...).
* What is Scope Chain ? Code looks for the variable in block scope, then functional scope, and then global scope.

### 2 - Variables:

2.1 - var: 
  - if not declare "var" the variable will be turned as var and can be accessed (Global Scope);
  - is a Function Scope variable 
  - is accessed outside a block scope if declared in it.
  - can declare and later assign a mutable value
  - can be re-declared
  > Note: is the old and risk way to set a variable: In can be re-declared with the same name as a existing unknown variable (Must Investigate the scope)

2.2 - let: 
  - block scope variable 
  - can declare and later assign a mutable value
  - can't be re-declared

2.3 - const: 
  - block scope variable 
  - to declare must be assigned a immutable value
    > for Arrays and Objects creates a reference to a pointer on memory, so is possible to change the object.


###  3 - Hoisting:
  - Variables declarations and function declarations will be cached on memory before running the code.
  - Only applicable to "var" and "functions", in moment of definition of Lexical Scope (Reading JS File)

### 4 - "This" keyword
  - Refers to the object that belongs
  - if is invoked in a "function or object" like myObj.func() - this is related to 'myObj' obj
  - If is invoked without a reference it will be related to the global object, e.g: [ window (Browser) / global (NodeJS) ].func()
  - if is invoked on a event handler this will be related to the element that uses the event.
  - if is invoked on a arrow function this will be related to the outside context of the arrow function, arrow functions doesn't create execution context.
    > **** Review

### 5 - Arrow Functions
- Short Syntax
- no 'function' keyword;
- Don't have lexical scope (Code Reading Time) 'This' keyword;
- Declaring Function --> declared to a variable
- Example: Anonymous `func () => {`}, declarative `const func = () => {} `


### 6 - Prototype
- Inherit properties and methods of Javascript Objects (Array, Objects, Date...)
- A Prototype is a blueprint of a JS Object (Array, Objects, Date...)
> Documentation: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain


### 7 - How change the context of the invoking function?
- Call() - Arguments comma separated and call the function.
- Apply() - Array as argument and call the function.
- Bind() - Multiple arguments and create another function to be later call,
> *** See Study use Cases on React instead of funcName.bind(this) in render()


### 8 - Currying
- Technic that Chaining up a sequence of internal returning functions 
- Usage is for storing values that can be called multiple times without passing if again
- It's a way of verify all arguments before the final result.
- After setting all chained function and arguments will receive the final result
- E.g.: `outerFunc(arg1)(arg2)(arg3) `


### 9 - Closure
- Its a combination of two nested function (Function within a function to access the function 'inner lexical scope');
- Ideally used to create a "Private Scope" only reached from the inner function.
- Another concept is the ability of a function to remember the variables and functions that are declared in its outer scope.
- Store function scoped value to be accessible by calling returned function.
- E.g.: Eventhandler, IIFE, Any function


### 10 - Cookies
- Are data storage in a text file;
- Belong to a domain;
- Is passed as "Name=Value";
- Can pass along "expire date (UTC)"" and "Path";
- Can add as many as you want;


### 11 - Form Validation
- CheckValidity() --> Checks if the input is empty (Must bee required)
- validationMessage() --> Set a message for CheckValidity();
- Validity (A bunch of messages depending of the case);


### 12 - Undeclared and Undefined;
- Undeclared variables are the uncreated variables on the Program. The JS gives a runtime error;
- Undefined variables are created variables but has bo value attribution to this variable. The JS gives a error as undefined; 


### 13 - ViewState vs SessionState
- ViewState is a section related to a Page;
- SessionState is a section related to all web application pages;


### 14 - Change a style 
- document.getElement...().style.fontSize = 10;
- document.getElement...().className = "blah";


### 15 - Loops in JS:
- For --> for(let i; i > ...; i++) or for(let key in obj);
- ForEach
- While --> while(true){}
- Do-While --> 
```
do {
...
} while (true);
```


### 16 - Delete Object Property:
`var student = { name: "Matheus", age: 15}
Delete student.age;`


### 17 - Manipulate Arrays:
- [].pop() --> remove and return the last;
- [].unshift() --> add at the beginning;
- [].shift() --> return initial element;
- [].splice(init, final, values) --> add to a specific place;
- [].push() --> add at the end;
- [].slice(init, final) --> breakdown into a new array
...


### 18 - Object Creation:
- const user = `new Object()` // Constructor Function ;
- const user2 = {...};
- const user3 = `Object.create(BaseObject)`
- const user4 = `Object.assign({}, obj1, obj2);` ==> Combination of Object ==> '{}' object to be created (can have other param), 'obj1, obj2, ...' objects to be joint 
 

### 19 - `Blur()` remove the Focus from a Object;


### 20 - Reference Vs Value
- Primitives will receive copy of the values in the memory (If it's changes it will not reflect in the initial referenced value)
- Non-primitives will point to the same space in the memory (If it's change will modify the initial referenced value)


### 21 - CallBack Functions - cb / callbackfunc
- Functions passed as parameters to be called by the main function  
- Can have arguments to be filled by the main function


### 22 - Constructor Function
- Pascal Notation - Capital Letter
- Create Objects
e.g.: const person1 = new Person(args)


### 23 - Rest Parameter (...) vs spread operator (...)
* Rest Parameter - ...args in a function --> E.g.: `func(a, ...args){}` --> Then look for args inside the function
* Spread Operator - Spreads arrays and objects / spreads arguments on a function ==> `[...array] & {...obj}`


### 24 - Date API
  * new Date() date Object
  * getTime() in Milliseconds

  > *** milliseconds to days `Math.floor(a.getTime() / 1000 / 60 'seconds' / 60 'hours' / 24 'days')`

  > *** Two Dates same day --> Breakdown Year / Month / Day match both dates 
  > *** Add Days or Remove Days:

      ` const today = new Date()
          const otherDate = new Date()
          otherDate.setDate(today.getDate() + or - days) will return a Integer
          console.log(new Date(otherDate))
      `
  >  Difference Between two Dates: (days, Hours, Minutes, Seconds)

      `
          const date1 = new Date(date);
          const date2 = new Date(refDate);
          let diffInMilliseconds = date1.getTime() - date2.getTime();
          const diffDays = Math.floor(diffInMilliseconds / 1000 / 60 / 60 / 24);
          diffInMilliseconds = diffInMilliseconds - diffDays * 1000 * 60 * 60 * 24;
          const diffHours = Math.floor(diffInMilliseconds / 1000 / 60 / 60);
          diffInMilliseconds = diffInMilliseconds - diffHours * 1000 * 60 * 60;
          const diffMin = Math.floor(diffInMilliseconds / 1000 / 60);
          diffInMilliseconds = diffInMilliseconds - diffMin * 1000 * 60;
          const diffSeconds = Math.floor(diffInMilliseconds / 1000);
          return `${diffDays} days, ${diffHours} hours, ${diffMin} minutes, ${diffSeconds} seconds`;
      `
  > Near Quarter of Day or hour:

      `
          function NearQuarterHour(date) {
              const currentHour = new Date(date).getHours();
              if (currentHour >= 0 && currentHour <= 6) {
                  return `1/4 hour`;
              } else if (currentHour > 6 && currentHour <= 12) {
                  return `2/4 hour`;
              } else if (currentHour > 12 && currentHour <= 18) {
                  return `3/4 hour`;
              } else {
                  return `4/4 hour`;
              }
          }
      `

### 25 - Math:
  * Math.floor() - Return Integer
  * Math.abs() - absolute value


### References:
https://www.w3.org/wiki/JavaScript_best_practices