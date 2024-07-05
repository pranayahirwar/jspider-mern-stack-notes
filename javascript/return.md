The **`return`** statement ends function execution and specifies a value to be returned to the function caller.

# Syntax

```js-nolint
return;
return expression;
```

- `expression` {{optional_inline}}
  - The expression whose value is to be returned. If omitted, `undefined` is returned.

# Description

The `return` statement can only be used within **function bodies**. When a `return` statement is used in a function body, the execution of the function is stopped. The `return` statement has different effects when placed in different functions:

- In a plain function (function declared using `function` keyword), call to that function evaluates (will return) the value used in return keyword.
- In an async function, the produced promise is resolved with the returned value.
- In a generator function, the produced generator object's `next()` method returns `{ done: true, value: returnedValue }`.
- In an async generator function, the produced async generator object's `next()` method returns a promise fulfilled with `{ done: true, value: returnedValue }`.

> [!IMPORTANT]
> If a `return` statement is executed within a `try...catch`, `try` block, its `finally` block, if present, is first executed, before the value is actually returned.

## Automatic Semicolon Insertion

The syntax forbids (restrict) line terminators (what is line terminators?) between the `return` keyword and the expression to be returned.

```js-nolint example-bad
// return expression_to_be_returned
return
a + b;
```

The code above is transformed by [automatic semicolon insertion (ASI)](/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#automatic_semicolon_insertion) into:

```js-nolint
return;
a + b;
```

This makes the function return `undefined` and the `a + b` expression is never evaluated. This may generate [a warning in the console](/en-US/docs/Web/JavaScript/Reference/Errors/Stmt_after_return).

To avoid this problem (to prevent ASI), you could use parentheses:

```js-nolint
return (
  a + b
);
```

# Examples

## Interrupt a Function

A function immediately stops at the point where `return` is called.

```js
function counter() {
  // Infinite loop
  for (let count = 1; ; count++) {
    console.log(`${count}A`); // Until 5
    if (count === 5) {
      return;
    }
    console.log(`${count}B`); // Until 4
  }
  console.log(`${count}C`); // Never appears
}

counter();

// Logs:
// 1A
// 1B
// 2A
// 2B
// 3A
// 3B
// 4A
// 4B
// 5A
```

## Returning a Function

See also the article about [Closures](/en-US/docs/Web/JavaScript/Closures).

```js
function magic() {
  return function calc(x) {
    return x * 42;
  };
}

const answer = magic();
answer(1337); // 56154
```
