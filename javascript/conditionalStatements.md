# Conditional Statements

Q. What are conditional statements?

A. Conditional Statements are used to control the flow of program, what you mean by flow of program, it means, skipping a block of code in program based on some or given conditions in conditional statement.

Ex. Controlling flow of program based on two inputs of function below
```javascript
function aIsBiggerOrBIsBigger(a, b) {
	if (a < b) {
		console.log(`Second argument of function B:${b} is Bigger`);
	} else {
		console.log(`First argument of function A:${a} is Bigger`);
	}
}

aIsBiggerOrBIsBigger(10, 20);
aIsBiggerOrBIsBigger(20, 10);

```

---

Q. What are the different types of conditional statements?

A. There are 4 types of conditional statements
1. if
2. if-else
3. else-if
4. switch

---
### if (some_condition)

Before talking about conditional statement, we need to first know, which values are **true** and **false** for JavaScript Compiler.

**What are Truthy values in JS?**
Every other values other than **Falsy** in JavaScript is **Truthy**, then that mean we have to know what are **Falsy** values in JavaScript.  

| Value                                                                           | Type      | Description                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------------------- | --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [null](https://developer.mozilla.org/en-US/docs/Glossary/Null)                  | Null      | The keyword [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/null) — the absence of any value.                                                                                                                                                                                |
| [undefined](https://developer.mozilla.org/en-US/docs/Glossary/Undefined)        | Undefined | [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) — the primitive value.                                                                                                                                                                                  |
| `false`                                                                         | Boolean   | The keyword [`false`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#reserved_words).                                                                                                                                                                                          |
| [NaN](https://developer.mozilla.org/en-US/docs/Glossary/NaN)                    | Number    | [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) — not a number.                                                                                                                                                                                                     |
| `0`                                                                             | Number    | The [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) zero, also including `0.0`, `0x0`, etc.                                                                                                                                                                   |
| `-0`                                                                            | Number    | The [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) negative zero, also including `-0.0`, `-0x0`, etc.                                                                                                                                                        |
| `0n`                                                                            | BigInt    | The [`BigInt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt) zero, also including `0x0n`, etc. Note that there is no [`BigInt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt) negative zero — the negation of `0n` is `0n`. |
| `""`                                                                            | String    | Empty [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) value, also including `''` and ` `` `.                                                                                                                                                                    |
| [`document.all`](https://developer.mozilla.org/en-US/docs/Web/API/Document/all) | Object    | The only falsy object in JavaScript is the built-in [`document.all`](https://developer.mozilla.org/en-US/docs/Web/API/Document/all).                                                                                                                                                                              |

Code representation of Falsy values in JS.
```javascript
if (false) {
  // Not reachable
}

if (null) {
  // Not reachable
}

if (undefined) {
  // Not reachable
}

if (0) {
  // Not reachable
}

if (-0) {
  // Not reachable
}

if (0n) {
  // Not reachable
}

if (NaN) {
  // Not reachable
}

if ("") {
  // Not reachable
}

```

`if (some_condition) { ... // code block}`  if (`some_condition`) is truthy according to JS Compiler then only code block written inside `{}` block will be executed.