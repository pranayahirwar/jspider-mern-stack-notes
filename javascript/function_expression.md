# Function Expression

The **`function`** keyword can be used to define a function inside an expression.

You can also define functions using the [`function` declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function) or the [arrow syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions).

## [Syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#syntax)

```js
function (param0) {
  statements
}
function (param0, param1) {
  statements
}
function (param0, param1, /* …, */ paramN) {
  statements
}

function name(param0) {
  statements
}
function name(param0, param1) {
  statements
}
function name(param0, param1, /* …, */ paramN) {
  statements
}
```

**Note:** An [expression statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/Expression_statement) cannot begin with the keyword `function` to avoid ambiguity with a [`function` declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function). The `function` keyword only begins an expression when it appears in a context that cannot accept statements.

### [Parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#parameters)

[`name`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#name) Optional

The function name. Can be omitted, in which case the function is _anonymous_. The name is only local to the function body.

[`paramN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#paramn) Optional

The name of a formal parameter for the function. For the parameters' syntax, see the [Functions reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_parameters).

[`statements`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#statements) Optional

The statements which comprise the body of the function.

## [Description](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#description)

A `function` expression is very similar to, and has almost the same syntax as, a [`function` declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function). The main difference between a `function` expression and a `function` declaration is the _function name_, which can be omitted in `function` expressions to create _anonymous_ functions. A `function` expression can be used as an [IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE) (Immediately Invoked Function Expression) which runs as soon as it is defined. See also the chapter about [functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions) for more information.

### [Function expression hoisting](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#function_expression_hoisting)

Function expressions in JavaScript are not hoisted, unlike [function declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function#hoisting). You can't use function expressions before you create them:

JSCopy to Clipboard

```js
console.log(notHoisted); // undefined
// Even though the variable name is hoisted,
// the definition isn't. so it's undefined.
notHoisted(); // TypeError: notHoisted is not a function

var notHoisted = function () {
  console.log("bar");
};
```

### [Named function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#named_function_expression)

If you want to refer to the current function inside the function body, you need to create a named function expression. This name is then local only to the function body (scope). This avoids using the deprecated [`arguments.callee`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments/callee) property to call the function recursively.

JSCopy to Clipboard

```js
const math = {
  factit: function factorial(n) {
    console.log(n);
    if (n <= 1) {
      return 1;
    }
    return n * factorial(n - 1);
  },
};

math.factit(3); //3;2;1;
```

If a function expression is named, the [`name`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/name) property of the function is set to that name, instead of the implicit name inferred from syntax (such as the variable the function is assigned to).

Unlike declarations, the name of the function expressions is read-only.

JSCopy to Clipboard

```js
function foo() {
  foo = 1;
}
foo();
console.log(foo); // 1
(function foo() {
  foo = 1; // TypeError: Assignment to constant variable.
})();
```

## [Examples](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#examples)

### [Using function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#using_function_expression)

The following example defines an unnamed function and assigns it to `x`. The function returns the square of its argument:

JSCopy to Clipboard

```js
const x = function (y) {
  return y * y;
};
```

### [Using a function as a callback](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#using_a_function_as_a_callback)

More commonly it is used as a [callback](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function):

JSCopy to Clipboard

```js
button.addEventListener("click", function (event) {
  console.log("button is clicked!");
});
```

### [Using an Immediately Invoked Function Expression (IIFE)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function#using_an_immediately_invoked_function_expression_iife)

An anonymous function is created and called:

JSCopy to Clipboard

```js
(function () {
  console.log("Code runs!");
})();

// or

!function () {
  console.log("Code runs!");
}();
```
