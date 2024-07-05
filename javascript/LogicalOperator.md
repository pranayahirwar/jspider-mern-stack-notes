# Logical Operator

### MDN on Logical Operator

1. [Logical AND (&&)](logical_and/index.md)
2. [Logical OR (||)](logical_or/index.md)
3. [Logical NOT (!))](logical_not/index.md)

---


Q. What you mean by logical operation?

A. When two conditions (8 && 16 are not condition, (8+8) && (16+16) is condition) are compared using Logical or Bitwise operators

There are 3 types of Logical Operators
1. `&&` Logical AND Operator
2. `||` Logical OR Operator
3. `!`  Logical Negation Operator

- && operator operator will not check or evaluate it's result the 2nd operand if first operand is false

```js
let a=5;
let b=6;

console.log(a > 5 && b > 5); // Output: false
```

- and == operator will not check the 