# Bitwise Operator

- Bitwise `&` and `|` operator can be used for logical operations.
- Bitwise `&` and `|` operator will execute both conditions on left and right of `&` and `|` operator no matter if first operand results in true or false.

```javascript
let a=5;
let b=6;

console.log(a++ > 5 & b++ > 5); // 0
console.log(a, b); // 6 7
```

- Bitwise Return value binary value, what are binary values these are 0 and 1 only.

```javascript
let a=5;
let b=6;

console.log(a++ > 5 | b++ > 5); // 1
console.log(a, b); // 6 7
```
