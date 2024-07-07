# Logical Operator

## MDN on Logical Operator

1. [Logical AND (&&)](logical_and/index.md)
2. [Logical OR (||)](logical_or/index.md)
3. [Logical NOT (!))](logical_not/index.md)

---

Q. What you mean by logical operation?

A. A logical operation refers to a mathematical function that operates on binary values (true or false) and returns a binary value as the result. In programming, logical operations are used to perform operations on boolean values (`true` or `false`) and can be used to control the flow of the program based on conditions. The most common logical operations are:

- **AND** (`&&`): Returns `true` if both operands are true; otherwise, returns `false`.
- **OR** (`||`): Returns `true` if at least one of the operands is true; otherwise, returns `false`.
- **NOT** (`!`): Returns `true` if the operand is false, and `false` if the operand is true

There are 3 types of Logical Operators
1. `&&` Logical AND Operator
2. `||` Logical OR Operator
3. `!` Logical Negation Operator

- && operator operator will not check or evaluate it's 2nd operand, if first operand is false

```js
let a=5;
let b=6;

console.log(a > 5 && b > 5); // Output: false
```
