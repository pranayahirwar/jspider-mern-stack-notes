---
Date: 11-06-2024
---

# Operator Overloading

Q. What is Operator Overloading?
A. Change in behavior or operation of **operator** based on it's **operands** is known as Operator Overloading. JS don't give access to users to overloading operators like other programming language Python, C++, instead JS has pre-overloaded some operator (like `+`,`==`,`/`) which will behave differently based on it's operands.

### Concatenation

Joining or combining (not summation or addition) of two or more operands is known as concatenation.
It is performed using `+` operator.

> To perform concatenation at least one operand should be of STRING DATATYPE.
> After concatenation result or returned value will be STRING DATATYPE

How concatenation decision made based on different datatypes of operands
- number + number : `+` operator will work as addition operator
- number + string : `+` operator will work as concatenation operator
- string + number : `+` operator will work as concatenation operator
- string + string : `+` operator will work as concatenation operator

Arithmetic operators operation (solution or evaluation) happens from LEFT -> RIGHT
Eg: `1 + 2 + "Hi" + 4 + "Hello"` -> `"3Hi4Hello"` 
Make sure to always remember return value of concatenation operation is in STRING.

---
### My Extra Notes

Some more operator which got overloaded to behave differently based on it's operands.

1. **The `==` operator** performs type coercion if the types of the two operands are different, otherwise behave like `===` if operands are same.
```javascript
console.log(1 == "1"); // true
console.log(1 == [1]); // true
```

2. **The `<` and `>` operators** can compare strings lexicographically, as well as numbers.
```javascript
console.log("10" > "2"); // false, because "1" comes before "2" lexicographically
console.log(10 > 2); // true
```

3. **The `*` operator** can perform multiplication on numbers, but if one of the operands is not a number, JavaScript will try to convert it to a number first. If it can't, the result will be `NaN`.
```javascript
console.log(2 * "3"); // 6
console.log(2 * "hello"); // NaN
```

4. **The `/` operator** behaves similarly to the `*` operator. It performs division on numbers, but if one of the operands is not a number, JavaScript will try to convert it to a number first. If it can't, the result will be `NaN`.
```javascript
console.log(6 / "3"); // 2
console.log(6 / "hello"); // NaN
```

5. **The `-` operator** also behaves similarly. It performs subtraction on numbers, but if one of the operands is not a number, JavaScript will try to convert it to a number first. If it can't, the result will be `NaN`.
```javascript
console.log(6 - "2"); // 4
console.log(6 - "hello"); // NaN
```

6. **The `%` operator** performs the modulus operation on numbers, but if one of the operands is not a number, JavaScript will try to convert it to a number first. If it can't, the result will be `NaN`.
```javascript
console.log(10 % "3"); // 1
console.log(10 % "hello"); // NaN
```
