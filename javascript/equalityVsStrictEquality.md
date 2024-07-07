# Equality (`==`) & Strict Equality (`===`)

## Equality (`==`)

- In `==` type coercion implicit conversion of datatype happens, if datatype of two operand are not of same datatype.

Q. Write step by step process how `==` work if datatype of x and y are equal and not equal

A.

if datatype of ()

## Strict (`===`)

- In `===` type coercion implicit conversion of datatype happens will not happen if datatype of two operand are different and JS will return `false`.
---

```javascript
// What will be output
console.log(1 > 2 > 3) // Output: false

// 1. first 1 > 2 operation will evaluate it will return false, and this false will be inputted to next operator with operand 3
// 2. now false > 3 operation will happen, one is Boolean datatype and other is number, so Type Coercion will happen false will be converted to Number Datatype which is 0, so 0 > 3 is false. Hence false is returned in output

let a=5;
let b=6;

console.log(a > 5); // Output: fasle
console.log(a++ > 5); // Output: false
console.log(a > 5 && b > 5); // Output: true
console.log(a > 5 || b > 5); // Output: true

console.log(!a > 5); // Output: false
// 1. Here Operator precedance will take in effect
// 2. Unary operator (!) is having more precedence than comparasion operator (>)
// 3. So try to solve !5 first, ! operator expects boolean operand, but we have given number datatype here, so ! operator will try to convert number (5) to Boolean datatype which will result in true because it's not falsy value it's truthy value. Now ! operator will be used on true value, which result in false
// 4. Now false left operand for > operator will be compared with right operand (5), now false will be converted to number datatype again becuase of > operator which will be 0, so now 0 > 5 which  results to false  


// #################################################
// # LOGICAL && OPERATOR QUESTIONS
// #################################################
let a=5;
let b=6;
console.log(a++ > 5 && b++ > 5);
console.log(a, b)

// #################################################
// # LOGICAL || OPERATOR QUESTIONS
// #################################################
let a=5;
let b=6;
console.log(a++ > 5 || b++ > 5); // true
console.log(a, b) // 6 7
```
