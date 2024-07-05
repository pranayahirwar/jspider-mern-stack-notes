# First-class Function

A programming language is said to have **First-class functions** when functions in that language are treated like any other **variable**. For example, in such a language, a function can be passed as an *argument to other functions*, can be *returned by another function* and *can be assigned as a value to a variable*.

## [Assigning a function to a variable](https://developer.mozilla.org/en-US/docs/Glossary/First-class_Function#assigning_a_function_to_a_variable)

```js
const foo = function funName() {
  console.log("I am funName function");
};

// According to recommended way without function name 
const foo = function () {
  console.log("I am funName function");
};

// According to recommended way
const foo = () => {
  console.log("I am funName function");
};

foo(); // Invoke it using the variable
// foobar
```

We assigned an *Anonymous Function (function without function NAME if knows as Anonymous Function)* in a [Variable](https://developer.mozilla.org/en-US/docs/Glossary/Variable), then we used that variable to invoke the function by adding parentheses `()` at the end.

**Note:** Even if your function was named, you can use the variable name to invoke it. ==Naming it will be helpful when debugging your code==. _But it won't affect the way we invoke it._

## [Passing a function as an argument](https://developer.mozilla.org/en-US/docs/Glossary/First-class_Function#passing_a_function_as_an_argument)

```js
function sayHello() {
  return "Hello, ";
}

function greeting(helloMessage, name) {
  console.log(helloMessage() + name);
}

// Pass `sayHello` as an argument to `greeting` function
greeting(sayHello, "JavaScript!"); // Output: Hello, JavaScript!

greeting(sayHello(), "JavaScript!"); // Output: Error, because how our greeting function is written, helloMessage is assuemed as function or callback function and when we use () on anything other than function it's going to give
// TypeError: helloMessage is not a function

// And to avoid it error we need to change greeting function to remove () from helloMessage parameter
```

We are passing our `sayHello()` function as an argument to the `greeting()` function ==Note: while passing function sayHello we are not using () for sayHello function, if we will use () on function, then function will be called and it's returned value will be saved in argument of greeting function==, this explains how we are treating the function as a value.

**Note:** The function that we pass as an argument to another function is called a _[callback function](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)_. _`sayHello()` is a callback function._

## [Returning a function](https://developer.mozilla.org/en-US/docs/Glossary/First-class_Function#returning_a_function)

```js
function sayHello() {
  return () => {
    console.log("Hello!");
  };
}
```

In this example, we are returning a function from another function - _We can return a function because functions in JavaScript are treated as values._

**Note:** A function that returns a function or takes other functions as arguments is called a _higher-order function_.

> [!NOTE]
> Higher Order function just mean that, they can help us create different type of functions (the function which we are returning) based on argument or condition which we have used in Higher Order function  
