# Unary Operator

Operator which only need one operand to complete it's operation is knows as Unary operator.

> Unary operator also return something.

There are 4 types of Unary Operator in JS
1. Pre-Increment  (++var)  updated value of var value is returned
2. Post-Increment (var++)  value before update will be returned
3. Pre-Decrement  (--var)  updated value of var value is returned
4. Post-Decrement (var--)  value before update will be returned

---

### Exercise of Unary Operator

Tell the values of B variable in below codes using all types of above Unary operator

- Pre-Increment (++var)
```javascript
let a = 10;
let b;
b = ++a;
console.log(`a=${a}, b=${b}`)
// Excepted Output: a=11, b=11
```

- Post-Increment (var++)
```javascript
let a = 10;
let b;
b = a++;
console.log(`a=${a}, b=${b}`)
// Excepted Output: a=11, b=10
```

- Pre-Decrement (--var)
```javascript
let a = 10;
let b;
b = --a;
console.log(`a=${a}, b=${b}`)
// Excepted Output: a=9, b=9
```

- Post-Decrement (var--)
```javascript
let a = 10;
let b;
b = a--;
console.log(`a=${a}, b=${b}`)
// Excepted Output: a=9, b=10
```

---
### My Extra Notes

Complete list Unary Operators in JS

1. **Unary plus (`+`)**: Tries to convert the operand into a number. Returns a number. Usually takes a string and return Number
```javascript
let str = "123";
console.log(typeof +str); // "number"
```

2. **Unary negation (`-`)**: Tries to convert the operand into a number and negates after. Returns a number.
```javascript
let str = "123";
console.log(typeof -str); // "number"
```

3. **Logical Not (`!`)**: Converts the operand to Boolean type and negates it. Returns a Boolean.
```javascript
let truthy = 1;
console.log(typeof !truthy); // "boolean"
```

4. **Bitwise Not (`~`)**: Inverts the bits of the operand. Returns a number.
```javascript
let num = 5;              // binary: 101
console.log(~num);        // -6 
console.log(typeof ~num); // "number"
```

Here's how the bitwise NOT (`~`) operator works on the number 5 step by step:

1. First, the number 5 is represented in binary. In JavaScript, numbers are stored as 64-bit floating point numbers but when you do bitwise operations, JavaScript treats them as if they were 32-bit signed integers. So, for bitwise operations, 5 is represented as `00000000000000000000000000000101`.
2. The bitwise NOT operator (`~`) inverts the bits, changing 1s to 0s and 0s to 1s. So, `~00000000000000000000000000000101` becomes `11111111111111111111111111111010`.
3. This binary number is the two's complement representation of -6. In two's complement, the leftmost bit is the sign bit. If it's 1, the number is negative. To find the absolute value of the number, we invert the bits again to get `00000000000000000000000000000101` (which is 5), and then add 1, which gives us `00000000000000000000000000000110` (which is 6). So the original number is -6.
Therefore, `~5` in JavaScript gives `-6`.

5. **Typeof (`typeof`)**: *Returns a string* indicating the type of the unevaluated operand. Returns a string.
```javascript
let num = 123;
console.log(typeof num); // "number"
console.log(typeof typeof num); // "string"
```

6. **Void (`void`)**: Discards any return value from an expression. Returns `undefined`.
```javascript
console.log(typeof void(1)); // "undefined"
```

7. **Delete (`delete`)**: Deletes an object, an object's property, or an element at a specified index in an array. *Returns a Boolean* indicating whether the operation was successful.
```javascript
let obj = {key1: 'value1', key2: 'value2'};

console.log(typeof delete obj.key1); // "boolean"
console.log(obj); // {key2: 'value2'}
```
