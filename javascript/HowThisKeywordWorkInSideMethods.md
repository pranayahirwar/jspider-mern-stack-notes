```js
// Create an employee object
let topLevelVar1 = "I am a top level variable 1";
let topLevelVar2 = "I am a top level variable 2";

const employee = {
  name: "John",
  age: 30,
  position: "Developer",
  greetGoodMorning: function () {
    // Function expression which is not using `this` keyword
    // greetGoodMorning is a method of employee object. which mean it's a special function
    // because it's a method of object, and becuase of this `this` keyword will work differnetly
    // inside this function, if we will use this keyword, like in below function.
    return `Good Morning`;
  },

  // All function defined inside oject are Function Expression and known as method.
  // CASE 01:
  methodOfObjectCase1: function () {
    // What's the value of `this` keyword here?
    // Ans: `this` keyword refers to the object which called the method. which is employee object.
    console.log(this);
  },

  // CASE 02:
  methodOfObjectCase2: () => {
    // What's the value of `this` keyword here?
    // Ans: `this` keyword refers to window object
    console.log(this);
  },

  // CASE 03:
  methodOfObjectCase3: function () {
    // What's the value of `this` keyword here?
    // Ans: `this` keyword refers to employee object
    console.log(this);

    function innerFunction() {
      // What's the value of `this` keyword here?
      console.log(this); // window object
    }
    innerFunction();
  },
  // CASE 04:
  methodOfObjectCase4: function () {
    // What's the value of `this` keyword here?
    console.log(this); // employee object

    let innerFunction = () => {
      // What's the value of `this` keyword here?
      console.log(this); // employee object
    };
    innerFunction();
  },
  // CASE 05:
  methodOfObjectCase5: () => {
    // What's the value of `this` keyword here?
    console.log(this); // window object

    function innerFunction() {
      // What's the value of `this` keyword here?
      console.log(this); // window object becaue innerFunction point to window object by default
    }
    innerFunction();
  },
  // CASE 06:
  methodOfObjectCase6: () => {
    // What's the value of `this` keyword here?
    console.log(this); // window object

    let innerFunction = () => {
      // What's the value of `this` keyword here?
      console.log(this); // window oject becaue this arrow function take value of it's parent
      // which is window object.
    };
    innerFunction();
  },
};

employee.methodOfObjectCase1();
employee.methodOfObjectCase2();
employee.methodOfObjectCase3();
employee.methodOfObjectCase4();
employee.methodOfObjectCase5();
employee.methodOfObjectCase6();
```

Note: Before understanding, how `this` keyword is working inside function which are written inside employee object. We first have to know how, `this` keyword behave in different different functions (arrow, expression and declaration) and in different scenario (when
`this` keyword is called inside object)

Note: words wrapped in `this` (backticks) mean, it's a keyword of javascript.

Take a look at below 2 tables.

`this` keyword behavior when they are used inside function
TABLE 01:

| Function Type        | NON-STRICT MODE                                         | STRICT MORE                                             |
| -------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| Function Declaration | refers to window Object in Browser                      | `undefined`                                             |
| Function Expression  | refers to window Object in Browser                      | `undefined`                                             |
| Arrow Function       | refers to current lexical environment, parent reference | refers to current lexical environment, parent reference |

`this` keyword behavior when they are used inside function and this functions is method of object.
TABLE 02:

| Function Type                           | NON-STRICT MODE                                             | STRICT MORE                                               |
| --------------------------------------- | ----------------------------------------------------------- | --------------------------------------------------------- |
| Function Declaration (Not possible)     | refers to objected which called the method                  | refers to objected which called the method                |
| Function Expression                     | refers to objected which called the method                  | refers to objected which called the method                |
| Arrow Function                          | Refers to current lexicalenvironment parent's reference     | Refers to current lexical environment parent reference    |

Steps to find `this` keyword value inside function which are written inside object and also if object contain more function inside it,

**Remember Function created inside object are known as methods and this methods special for `this` keyword.**

- Check which type of function is written inside object. (Function Expression or Arrow Function)
	 - Function Expression (REFER TABLE 02):
	    - If it's a Function Expression, then `this` keyword refers to object which called the method.
	    
		- WHAT IF ANOTHER `innerFunction()` defined inside Function Expression?
		    - Remember `innerFunction()` not special function like method, it's a normal function. Then ask which type of function it is Arrow or Expression?
			    - If function expression (REFER TABLE 01): then function expression is going to point window object. All function expression or declaration point to window object by default no matter where it's defined.
			    - if Arrow function (REFER TABLE 01): then check where this arrow function is called, who is the parent of `innerFunction()`? it is `methodOfObjectCase3()` so what is the value of `this` keyword for `methodOfObjectCase3` it's employee object, so `innerFunction()` will take it's parent value and point to employee object.

	 - Arrow Function (REFER TABLE 02)
	    - If it's a Arrow Function, then check where this function is called, and then think what is the value of `this` keyword not for arrow function, but value of parent where this arrow function is called.
		    - Eg. employee.methodOfObjectCase2() we are calling this function in top level code, this mean `this` keyword point's to window object by default.

			- WHAT IF ANOTHER `innerFunction()` defined inside Arrow Function?
		    - Remember it's not special function like method, it's a normal function. Then ask which type of function it is Arrow or Expression?
			    - **If function expression**: then function expression is going to point window object by default. All function expression or declaration point to window object by default no matter where it's defined.
         - **if Arrow function**: then check where this (eg. `methodOfObjectCase6()`) arrow function is called, who is the parent of `innerFunction()`? it is `methodOfObjectCase6()` so what is the value of `this` keyword for `methodOfObjectCase6` it's window object, so `innerFunction()` will take it's parent value and point to window object.
